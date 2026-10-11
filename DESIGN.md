# Shade Theory: Design Language

**Brand:** Shade Theory Window Film, automotive window tint in Phoenix, AZ (fictional)
**Concept:** *Glass and glare.* The page is harsh desert sunlight: bright cool white everywhere. The only dark objects are pieces of film. The design shows the product working instead of describing it.
**Audience:** Phoenix-area drivers who want a cooler car and need to stay within Arizona tint law.
**Mood:** Precise, calm, technical, a little dry. A trustworthy specialist, not a "custom car" shop.

---

## 1. Core principles

1. **Light vs. shade is the visual system.** The background is bright and every dark element (film swatches, the tinted window, the heat bar, the swatch-book section) stands for film. Never add dark elements that don't mean "tint."
2. **Show the numbers tint is sold on.** VLT %, TSER %, IR rejection %, °F, and the legal VLT threshold. These are the actual units of the trade and they should be the biggest type on the page.
3. **One warm accent: the sun.** Amber appears only where heat or sun is meant (the temperature figure, the slider thumb, heat-rejection bars).
4. **Flat, ruled tables over cards.** Comparisons are tables with a 1.5px ink top rule and hairline rows. No rounded corners, no shadows.
5. **Light, single theme.** Don't make a dark variant. The glare is the point.

## 2. Colour tokens

| Token | Hex | Use |
|---|---|---|
| `--glare` | `#F5F6F6` | Page background (cool white, slightly green-grey, never cream) |
| `--ink` | `#121417` | Text, buttons, heat bar, swatch-book section |
| `--film` | `#0D1013` | Tint overlay, darkest swatch |
| `--smoke` | `#5B626A` | Labels, secondary text |
| `--body-2` | `#33383E` | Paragraphs |
| `--line` | `#D9DCDE` | Hairlines |
| `--sun` | `#F0950C` | Amber accent: temperature, slider thumb, heat bars, focus ring |
| `--legal` | `#1E7A43` | "Legal" status |
| `--illegal` | `#C2361F` | "Too dark" status |

**Film swatch ramp:** greys from `rgb(24,27,30)` at 5% VLT to roughly `rgb(172,175,178)` at 70% VLT, with a slight blue lift. Text goes light on dark swatches and ink on 50%+ swatches.

## 3. Typography

| Role | Family | Settings |
|---|---|---|
| Display | **Darker Grotesque** (Google Fonts) | Weight 900, line-height 0.8–0.85, letter-spacing −0.02em. Hero 58–138px. Big numeric readouts (VLT, TSER, °F, prices) also use this face at 34–58px |
| Body | **Figtree** | 400/500/600, 16.5px, 1.55 line-height |
| Data / labels | **DM Mono** | 11.5px UPPERCASE with 0.08em tracking for labels. Statute numbers, shade lists and the heat bar |

Darker Grotesque's tall, tight shapes at weight 900 are the brand's voice. Use it for headings and big numbers only, never for body text.

## 4. Layout

- Max width 1380px. Gutter `clamp(16px, 4vw, 60px)`.
- **Heat bar:** a 34px ink strip above the nav showing live conditions in mono: "PHOENIX TODAY **112°F** · UV INDEX **11 · EXTREME** · DASHBOARD TEMP, UNTINTED, 1 HR ~165°F", with values in amber.
- **Nav:** 76px tall with a bottom hairline. The logo is a three-step tint swatch (dark / mid / light block) plus the wordmark in Darker Grotesque 900.
- **Hero:** asymmetric two columns (0.9fr / 1.25fr). Left: the headline with the temperature in amber ("It's **112°** out. Your car doesn't need to know."). Right: the interactive window demo.
- **Section head:** two columns, a giant H2 on the left and an explanatory paragraph aligned to its bottom on the right.
- Mobile: single column, readouts stack, and wide tables scroll inside their container.

## 5. Signature components

- **Tint window demo (hero):** a 16:9 desert scene (sky gradient, sun bloom, layered mesas, saguaro silhouettes) clipped to a car side-window shape (`clip-path: polygon(10% 0,100% 0,100% 100%,0 100%,0 34%)`). A `--film` overlay sets opacity from VLT and has a faint diagonal glass reflection. Controls below it:
  - A VLT range slider from 5 to 70%. The track is a dark-to-light gradient and the thumb is a square amber block. Tick labels in mono read "5 · limo" through "70 · near clear".
  - A segmented control for film type (Carbon / Ceramic / IR Ceramic) with a 1.5px ink border. The selected option is filled ink.
  - Three readouts under an ink rule: TSER %, cabin °F after one hour, and the Arizona front-door legal status in green or red.
  - Fine print explaining that the figures are typical.
- **Swatch book:** a full-bleed ink section with six overlapping tall swatch strips (5, 15, 20, 35, 50, 70). Each strip shows a huge number, mono meta (name, VLT, legality) and a punched rivet hole. Strips lift on hover. Clicking one loads that shade into the demo.
- **Film comparison table:** columns for Carbon, Ceramic and IR Ceramic, with headers in display type and a sub-caption. Rows have mono uppercase labels. The heat-rejection row includes thin amber bar graphs. Prices are in display type.
- **Law diagram:** a flat sedan side-view SVG. The front door glass is light, the rear glass is film-dark, the AS-1 strip is called out, and the VLT rules are labelled on the body. Beside it is a ruled list: zone, rule and statute/threshold in mono.
- **Cure timeline:** four columns divided by hairlines (Day 0–3, 3–7, 7+, 30), each with a big display label and short instructions.

## 6. Motion

- Only the film overlay fades (0.25s) as the slider moves, and swatches lift on hover. Both are disabled under reduced-motion.
- The interactive demo is the moment. Don't add any other entrance animation.

## 7. Voice

- Plain and knowledgeable, like a tint installer explaining it at the counter: "Darkness and heat rejection are separate things."
- Cite the actual law (ARS 28-959.01, >33% VLT front doors) and real cure behaviour.
- Use concrete Phoenix details: 112°F, UV 11, steering wheel heat.

## 8. Don'ts

- No "luxury black" site with gold accents.
- No glassmorphism or blur cards. Real tint isn't frosted.
- No sunset-gradient hero backgrounds. The sun is a small amber accent, not a wash.
- Don't claim darker = cooler. Lead with TSER and IR rejection.
