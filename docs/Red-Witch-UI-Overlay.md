# Red Witch — Daughters of the Moon

*A cultural/lunar overlay for the Red Witch calendar system.*

---

## 1. Concept summary (one-liner)

An opt-in overlay where each user has a **Moon Sign** — the lunar phase on the night of their first period — and annual celebrations/observances (First Moon Night). Each moon phase maps to an archetype (e.g., Waxing Gibbous → “The Builder”), and the overlay surfaces gentle ritual suggestions, archetypal insights, and optional reminders while never altering raw cycle logs.

---

## 2. UX / Product behavior (how it behaves in the app)

**Onboarding (first enable)**

* When user enables “Daughters of the Moon” overlay: show short explainer card: purpose, privacy, opt-in only, not a medical tool.
* Request (optional) entry: *Date of First Period* (can be entered, imported from historical logs, or left blank). Clear CTA: “Add my First Moon Night” or “I prefer not to enter.”
* If user is uncomfortable: allow “Create Moon Sign from approximate age / year” (approximate) — make uncertainty explicit.

**Display**

* Overlay toggled on → shows a transparent layer above calendar days.
* On days tied to overlay (First Moon Night anniversary, moon-phase archetype month, ritual suggestions) show small crescent glyph in corner of day tile. Tap opens card.
* Layer legend available in overlay settings.
* Option: show a *Moon Sign* badge in user profile / cycle header: “Moon Sign: Waxing Gibbous (Red Witch)”.

**Interactions**

* Tap First Moon Night anniversary → shows a modal with: archetype text, ritual ideas (1–3), permission to add calendar event, share (image or text), and privacy controls.
* Allow user to hide any ritual or archetype text if they prefer purely informational experience.

**Notifications**

* Opt-in only reminders for First Moon Night anniversaries (e.g., “Your First Moon Night is in 3 days — want a private ritual prompt?”). Include quick toggles for push, in-app, or none.

**Accessibility & Literacy**

* Short, plain-language explanations; optional expanded cultural background.
* Icon-only mode off by default. Readable fonts, high contrast option, large tap targets.

---

## 3. Archetypes — mapping to lunar phases

Use 8 canonical lunar phase buckets (matches typical astrology/computation libs):

1. **New Moon** — *The Seed*

   > Quiet, inward, new beginnings. Rituals: journaling intentions, private silence.
   > *Red Witch style*: “Roots night — plant a seed (literal or symbolic).”

2. **Waxing Crescent** — *The Seeker*

   > Curiosity, small steps. Rituals: list three things to try this year.

3. **First Quarter** — *The Challenger*

   > Action, decisions, momentum. Rituals: small boundary-setting exercise.

4. **Waxing Gibbous** — *The Builder* (example archetype for your prompt)

   > Refinement, focused growth, persistence.
   > *UI card text example*: “Waxing Gibbous: You are a Builder. This year, tend what grew from your first Moon. Small acts repeated make structures lasting.”
   > *Ritual suggestions*: light a candle and name one project to protect; a 5-minute gratitude for growth.

5. **Full Moon** — *The Radiant*

   > Culmination, visibility, celebration. Rituals: small public or private celebration.

6. **Waning Gibbous** — *The Healer*

   > Reflection, recovery, sharing. Rituals: release exercise; comfort food recipe card.

7. **Last Quarter** — *The Sage*

   > Re-evaluation, letting go. Rituals: write what no longer serves you.

8. **Waning Crescent** — *The Restorer*

   > Rest, restoration, dreamwork. Rituals: gentle breathwork, sleep intention.

**Naming / Tone:** give option for “mythic” vs “plain” UI copy (mythic = poetic “Builder”, plain = “Growth / Consistency”).

---

## 4. Feature: Moon Sign & Annual First Moon Night

**Moon Sign (one-time derived attribute)**

* Definition: `moon_sign = lunar_phase_at(datetime(first_period_date), location)` (phase bucket as above). Stored as overlay metadata (not altering raw logs).
* Display: Badge + archetype text + 1–3 ritual suggestions.

**First Moon Night (annual recurrence)**

* Create an overlay-only recurring event: `FirstMoonNight` with recurrence rule: annually on calendar date of first_period_date by default.
* Optional mode: align recurrence to **lunar calendar** (same lunar phase each year) — because the lunar cycle ~29.53d moves the phase vs Gregorian date. If chosen, compute the next occurrence that matches the original lunar phase (astronomical computation). Provide both options to user and explain difference in plain language.

**Example UI choice during setup:**

* “Celebrate on the same calendar date every year (e.g., July 11),” or “Celebrate on the same lunar phase each year (e.g., the Full Moon closest to my first night).”
* Default: calendar date (simpler & predictable) with an “advanced” toggle for lunar-phase-aligned recurrence.

---

## 5. Data model / JSON plugin manifest (modular overlay)

This is an example overlay configuration that plugs into your overlays system. It references core data but stores only interpretation metadata.

```json
{
  "overlay_id": "daughters_of_the_moon_v1",
  "display_name": "Daughters of the Moon",
  "type": "cultural",
  "opt_in": true,
  "version": "1.0",
  "default_enabled": false,
  "config_schema": {
    "first_period_date": { "type": "date", "optional": true, "description": "Date of user's first period" },
    "moon_sign_mode": { "type": "enum", "values": ["mythic","plain"], "default": "mythic" },
    "recurrence_mode": { "type": "enum", "values": ["calendar_date", "lunar_phase"], "default": "calendar_date" },
    "reminders_enabled": { "type": "boolean", "default": false }
  },
  "derived_attributes": {
    "moon_sign": { "type": "string", "computed_by": "computeMoonSign(first_period_date, user_location)" },
    "first_moon_anniversary": { "type": "date", "computed_by": "computeAnniversary(first_period_date, recurrence_mode)"}
  },
  "ui": {
    "legend": "Shows your Moon Sign and First Moon Night. Opt-in only. Not a medical tool.",
    "icon": "crescent-glyph",
    "color_token": "overlay-moon-teal"
  },
  "disclaimer": "This overlay provides cultural and reflective content only. It does not replace medical advice."
}
```

**Notes:** overlay stores *only* the date(s) and computed tags; raw cycle logs remain the single source of truth elsewhere.

---

## 6. Pseudocode — how overlay reads core data, computes Moon Sign, and shows events

(Use your app’s astronomical library in production — example uses a hypothetical `astro` lib.)

```
function enableOverlay(user):
  config = loadOverlayConfig(user, "daughters_of_the_moon_v1")
  if not config.first_period_date:
    promptUserForFirstPeriodDate()
  else:
    sign = computeMoonSign(config.first_period_date, user.location)
    saveDerivedAttribute(user.id, "moon_sign", sign)

function computeMoonSign(date, location):
  # use astronomy lib to get moon phase angle: 0-360
  phaseAngle = astro.getMoonPhaseAngle(date, location)
  # convert angle to bucket:
  # 0: New, 0-45: WaxingCrescent, 45-90: FirstQuarter, etc. (use standard mapping)
  return phaseBucketFromAngle(phaseAngle)

function computeAnniversary(first_date, mode):
  if mode == "calendar_date":
    return recurrence(rule="RRULE:FREQ=YEARLY;BYMONTH=month;BYMONTHDAY=day", start=first_date)
  else:
    # find next date each year where moon phase == original phase within +/- N days
    desiredPhase = astro.getMoonPhaseAngle(first_date)
    for yearOffset in 0..100:
      baseline = first_date + yearOffset years
      candidate = astro.findNearestDateWithPhase(baseline, desiredPhase)
      schedule candidate as recurrence for that year
```

**Important**: mark lunar-phase computations as approximate and provide disclosures. Use server-side deterministic astro lib (or an established package) and compute using `user.location` for accuracy.

---

## 7. UI elements & microcopy (legend, disclaimers, cards)

**Overlay Legend (short):**
“Daughters of the Moon: an opt-in cultural layer. Your *Moon Sign* is the lunar phase on the night of your first period. The overlay suggests reflective prompts and an optional annual recurrence. Not medical.”

**Modal header for Moon Sign card:**
“Your Moon Sign — Waxing Gibbous (The Builder)”

**Card body short example:**
“Waxing Gibbous: You are a Builder. This sign honors steady refinement and resilience. Ritual idea: for 5 minutes today, name one thing you will protect this year.”

**Risk/Compliance disclaimer (required per CO-004 & R-CO-001):**
“This overlay is a cultural and reflective tool, not a medical or contraceptive method. If you’re seeking medical guidance about fertility, menstruation, or contraception, consult a qualified healthcare provider.”

---

## 8. Privacy & consent (required behavior)

* Overlay is **opt-in only**. Never enabled by default (CO-002, R-CO-002).
* If user supplies `first_period_date`, store it only in overlay metadata scope (encrypted like other sensitive health data). Do not copy to general notes without explicit consent (CO-006).
* Allow user to: export overlay data, delete overlay (removes derived attributes but not raw logs), configure sharing (if they want to post a First Moon Night graphic).
* Age-sensitivity: if detected user is under an age threshold (app policy), show simplified language and require guardian/age-appropriate flows as per regulatory rules.

Suggested privacy microcopy on save: “Your First Moon Night date is stored with the overlay and can be deleted any time. This date isn’t shared unless you explicitly share a card.”

---

## 9. Accessibility & localization

* Provide two reading tiers: **Short** (1–2 sentences) and **Expanded** (full cultural context).
* Localize archetype names and ritual suggestions with cultural sensitivity.
* Provide alt text for all icons.
* High contrast color tokens and dyslexia-friendly font option.

---

## 10. Visual design tokens (suggested)

* Primary overlay color: `--overlay-moon-teal: #2E9EA8` (use for glyph fills)
* Accent: `--overlay-moon-gold: #F0C05A` (for badges)
* Iconography: 8 lunar glyphs (new, crescent, quarter, gibbous, full, etc.) — simple shapes that scale to 16px.
* Ensure WCAG AA contrast for text on badges; provide alternate outline-only badge for dark mode.

---

## 11. Safety / Compliance checklist (map to your doc requirements)

* CO-001: Overlay reads core logs (no duplication). ✔️
* CO-002: Toggle on/off independently. ✔️
* CO-003: Transparent visual layer + legend. ✔️
* CO-004: Include legend, explanation, and risk disclaimer. ✔️ (copy above)
* CO-005: Modular JSON plugin model included. ✔️
* CO-006: Overlay-only derived attributes; raw data untouched. ✔️
* CO-007: Clear labeling: “cultural/wellness overlay — not a medical method.” ✔️

Also mitigate R-CO-001 and R-CO-003 by surfacing the disclaimer prominently at onboarding and inside the overlay settings.

---

## 12. Developer / engineering notes

* **Compute lunar phase:** use a reliable astronomy library on backend (e.g., `astral`, `pysolar` alternatives or a deterministic in-house lib). Compute with timezone & geolocation for accuracy.
* **Storage:** overlay metadata lives in `overlay_meta` table keyed by `user_id` + `overlay_id`. Encrypt at rest.
* **UI integration:** reuse existing overlay-layer UI (toggles, legends). Add overlay-specific settings page with first_period_date input, recurrence_mode toggle, and reminders toggle.
* **Testing:** unit tests for mapping of phase angle → bucket, for recurrence options (calendar vs lunar), and for privacy flows (delete overlay removes derived attrs).
* **Export/Share:** allow user to share a stylized card (SVG) that includes their Moon Sign and ritual text; do not include `first_period_date` unless user checks a box.

---

## 13. Example archetype copy pack (short — for translation/localization)

Provide mythic and plain versions for each phase. Example (Waxing Gibbous):

* Mythic: “Waxing Gibbous — The Builder. Tends small acts that make great forms.”
* Plain: “Growth & refinement. Focus on improving something you already started.”
* Ritual (short): “Light a candle and name one thing to protect this year.”
* Accessibility alt: “Waxing Gibbous — crescent with bulging lit side.”

---

## 14. Quick implementation checklist (actionable)

1. Add overlay manifest to overlays registry.
2. Implement overlay settings UI (input, toggles).
3. Hook compute function to run whenever first_period_date saved.
4. Show Moon Sign badge on profile header when overlay enabled.
5. Implement First Moon Night recurrence generator (calendar-date default; lunar-phase advanced).
6. Add legend + risk disclaimer text to overlay UI.
7. QA: privacy deletion test + accessibility audit.

---

## 🌕 DAUGHTERS OF THE MOON — LORE & CALENDAR OBSERVANCES

### ✦ Core Ethos

> *“Every daughter carries her own moon — waxing, waning, radiant, hidden — and through her phases, she remembers she is cyclic, not linear.”*

The Daughters’ culture views each menstrual cycle and lunar cycle as reflections of one another. Their shared calendar honors personal beginnings (*First Moon Night*), collective moments of balance and rest, and archetypal festivals tied to the Moon’s major positions each year.
No worship, no doctrine — just rhythm, reflection, and story.

---

## ✦ Annual Cycle (Observances)

Below are **eight key observances** (one for each lunar phase archetype), plus two **cross-phase festivals** that mark transitions and community gatherings. These can appear as optional overlay events with ritual cards or “reflection prompts.”

---

### 🌑 **Roots Night (New Moon Festival)**

**Timing:** Nearest New Moon after the March Equinox
**Themes:** renewal, intentions, ancestral grounding
**Lore:** The Daughters begin their year in darkness — a time of sowing dreams, whispering wishes to the soil, and honoring those who came before.
**Ritual ideas:**

* Plant a seed or symbol of what you wish to grow this year.
* Spend one evening in silence — write what you want to become real.

---

### 🌒 **Night of Seeking (Waxing Crescent)**

**Timing:** first Waxing Crescent after Roots Night
**Themes:** curiosity, exploration, new learning
**Lore:** The Seekers look for what glimmers in the unknown. This observance celebrates curiosity and beginner’s courage.
**Ritual ideas:**

* Learn one small new skill.
* Light a candle and speak aloud something you’ve never dared to try.

---

### 🌓 **Day of Courage (First Quarter)**

**Timing:** first First Quarter Moon after the June Solstice
**Themes:** boundaries, courage, decisive action
**Lore:** The Challengers remind the sisterhood that growth requires edge.
**Ritual ideas:**

* Write a boundary you’ll hold.
* Burn or bury a note of what you will no longer carry.

---

### 🌔 **Builder’s Vigil (Waxing Gibbous)**

**Timing:** mid-summer Waxing Gibbous Moon
**Themes:** persistence, craftsmanship, commitment
**Lore:** The Builders guard the works of the hands and heart.
**Ritual ideas:**

* Name one thing worth finishing.
* Offer gratitude for the tools that sustain you (hands, mind, allies).

---

### 🌕 **Radiance Night (Full Moon Celebration)**

**Timing:** the Full Moon nearest harvest time (late August–September)
**Themes:** joy, visibility, self-honoring
**Lore:** The Radiants hold festivals of light, music, and laughter.
**Ritual ideas:**

* Celebrate something you completed.
* Gather friends and share stories of what bloomed this year.

---

### 🌖 **Night of Sharing (Waning Gibbous)**

**Timing:** first Waning Gibbous after Radiance Night
**Themes:** healing, generosity, community care
**Lore:** The Healers gather to rest and share what they have learned.
**Ritual ideas:**

* Cook or craft something and gift it.
* Journal gratitude for comfort and connection.

---

### 🌗 **Sage’s Turning (Last Quarter)**

**Timing:** the Last Quarter before the Winter Solstice
**Themes:** wisdom, discernment, release
**Lore:** The Sages remind that endings feed the next beginning.
**Ritual ideas:**

* Write down what you’ve learned and what you’ll leave behind.
* Meditate on what truly matters.

---

### 🌘 **Dreamfast (Waning Crescent)**

**Timing:** final Waning Crescent before the New Moon nearest the year’s end
**Themes:** rest, sleep, liminality, quiet repair
**Lore:** The Restorers guard the threshold between years.
**Ritual ideas:**

* Sleep early, set a dream intention.
* Create a cozy night — tea, warmth, slow breathing.

---

## ✦ Cross-Phase Gatherings

### 🌗↔🌑 **The Veil Night (Between Waning Crescent and New Moon)**

**Timing:** roughly once a year, when one lunar cycle ends and the next begins
**Themes:** endings and beginnings intertwined
**Lore:** Sisters gather to “close the book” on the year — writing one page to release, one page to invite.
**Ritual idea:** burn the old wish list, bury its ashes, and write a new one.

---

### 🌕↔🌑 **Twin Moon Festival**

**Timing:** when two Full Moons fall in a single solar month (a “Blue Moon”)
**Themes:** rare radiance, community celebration, storytelling
**Lore:** A festival of collective brightness; Daughters share stories of their First Moon Nights, celebrating cycles of becoming.
**Ritual ideas:**

* Host a meal by moonlight.
* Share a story about your first or most recent personal transformation.

---

## ✦ Optional Micro-Observances (for app reminders)

Short reflective “Moon Prompts” that can appear throughout the year:

| Lunar Phase     | Prompt Title    | Short Text                           |
| --------------- | --------------- | ------------------------------------ |
| New Moon        | “Begin Again”   | *What seed wants planting tonight?*  |
| Waxing Crescent | “Small Steps”   | *Try something tiny but new.*        |
| First Quarter   | “Stand Firm”    | *Where do you need to say no?*       |
| Waxing Gibbous  | “Keep Building” | *Patience is also creation.*         |
| Full Moon       | “Shine”         | *Celebrate one visible part of you.* |
| Waning Gibbous  | “Give Back”     | *Who needs your comfort?*            |
| Last Quarter    | “Simplify”      | *Let go of what’s complete.*         |
| Waning Crescent | “Rest”          | *Your stillness is sacred too.*      |

---

## ✦ Lore Tone & Style Guidelines

* **Inclusive:** “Daughters” = symbolic; use “those who flow with the Moon” in plain-language mode.
* **Cultural Variance:** localize imagery (candles, water, plants) according to region.
* **Optional Mythic Layer:** internal lore names (Seed, Seeker, Challenger, Builder, Radiant, Healer, Sage, Restorer) map cleanly to the archetypes in your phase model.

---

## ✦ Integration Notes

* Each observance can appear as an optional event on the overlay calendar, toggled in settings (“Show Cultural Observances”).
* Event cards can display: name, 2–3 lines of lore text, 1–2 ritual suggestions, and a quick “Add to my calendar” button.
* Provide plain-language equivalents for accessibility (e.g., *“Roots Night — a reflection day for new beginnings”*).

---

## 🌙 The Four Inner Moons

*(menstrual cycle phases through the Daughter’s lens)*

Each cycle is a miniature lunar month — four moons moving through her inner sky.
They say: *“The Moon moves above; we move within.”*

| Physiological Phase            | Lunar Phase                                            | Archetype                                  | Mythic Tone                                                                                    | Plain Tone                                                                           |
| ------------------------------ | ------------------------------------------------------ | ------------------------------------------ | ---------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ |
| **Menstrual / Bleeding**       | 🌑 **New Moon**                                        | *The Crone / The Seed*                     | Darkness and renewal. She sheds what was; silence becomes soil. Dreams whisper from the roots. | Low energy, introspection, emotional reset; time for rest and reflection.            |
| **Follicular / Pre-Ovulation** | 🌒 **Waxing Crescent → First Quarter**                 | *The Maiden / The Seeker / The Challenger* | Curiosity stirs. Light returns. She explores, plans, begins.                                   | Rising energy, clarity, motivation to try new things and set goals.                  |
| **Ovulatory / Fertile**        | 🌕 **Full Moon**                                       | *The Mother / The Radiant*                 | Full bloom. Creative, expressive, outward. She offers her gifts openly.                        | Peak energy and sociability; good time for communication, connection, presentation.  |
| **Luteal / Pre-Menstrual**     | 🌖 **Waning Gibbous → Last Quarter → Waning Crescent** | *The Healer / The Sage / The Restorer*     | Turning inward again. She discerns, heals, releases what’s complete.                           | Energy gradually declines; useful time for completion, reflection, boundaries, rest. |

---

### ✦ Symbolic Alignment

In Daughter lore, the “outer” moon and the “inner” moon are always in conversation, but **not required to match**.

* When someone bleeds on the **New Moon**, they’re called **Red Moon aligned** — associated with introspection, healing, and solitary wisdom.
* When bleeding occurs on the **Full Moon**, they’re **White Moon aligned** — associated with nurturing, fertility, and outward energy.
* **Half-Moon bleedings** (First or Last Quarter) are **Gray or Purple Moons** — liminal types who balance both inner and outer cycles.

They teach that none are better — they simply express different creative and emotional tides.

---

### ✦ Seasonal & Psychological Parallels

| Inner Moon           | Corresponding Season | Energetic Quality      | Journal Prompt                               |
| -------------------- | -------------------- | ---------------------- | -------------------------------------------- |
| New Moon / Menstrual | Winter               | Rest, clarity, reset   | “What do I release so new growth can begin?” |
| Waxing / Follicular  | Spring               | Growth, curiosity      | “What is calling me to explore?”             |
| Full / Ovulatory     | Summer               | Vitality, expression   | “Where can I shine or share more freely?”    |
| Waning / Luteal      | Autumn               | Reflection, refinement | “What needs completion before I rest?”       |

---

### ✦ In App Context

If you include this lore in *Daughters of the Moon*:

* It can appear as an **optional “Cycle Archetype” overlay**, toggled inside the same cultural layer.
* Users could see both **outer moon** and **inner moon** progress rings, with short micro-texts (“Your inner moon is waning; take things slow.”).
* Never medicalize: frame it as *cultural reflection* and *emotional journaling aid*.

---
