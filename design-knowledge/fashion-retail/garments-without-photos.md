# Representing garments without product photos

**Purpose:** The recurring "I don't have final product photos yet" problem. Fashion sells on imagery, but new brands rarely have shots at launch. How to fill the image slots without looking cheap or unfinished.

**Harvest / review:** 2026-06

---

## First, split the problem: mood vs. product

The "no photos" problem is really **two** problems, and they have **opposite** answers. Don't apply one rule to both.

| | Mood / atmosphere imagery (hero, lookbook, "the vibe") | Product imagery (the specific items being sold) |
|---|---|---|
| **Question** | Does the page *feel* like this brand? | What exactly does the customer get? |
| **No photos yet?** | **Use curated, on-brand stock** — this is the #1 conversion lever in fashion; not having it is the mistake | Use **flats or labeled frames** — never someone else's product passed off as theirs |
| **Why** | Atmosphere can be borrowed honestly; a moody streetwear shot sets tone without claiming to be their product | Faking the actual product misrepresents the drop and erodes trust |

The nuance behind "never use stock": the killer is **generic, off-brand** stock (the obvious template studio shot). **Curated, on-vibe** photography — the right subculture, lighting, and mood — is not only allowed, it's essential. When a client asks for "placeholder images that fit the [X] vibe," they're asking for the mood layer, and they're right to.

**Make borrowed imagery read as the brand:** pull license-clean shots (Unsplash/Pexels) that match the subculture, then **duotone/grade them to the brand palette** (grayscale base + an accent tint + a dark floor) so a row of disparate photos looks like one coherent campaign. Label them honestly ("placeholder — your campaign shot here") in client demos. Self-host + optimize for production (don't hotlink a CDN on a live site).

---

## The product-slot decision

For the **product** slots specifically, three legitimate options, in rough order of premium feel. **Never** drop generic stock apparel photos here — that's where faking it actually hurts.

| Option | When | Feel |
|--------|------|------|
| **Type-led / "nothing"** | Strongest brand voice, fastest | Editorial, confident. Whitespace + bold type carries it; no garment imagery at all. |
| **Labeled image frames** | You want to *show where photos go* (client demos) | Honest placeholder — styled empty frames that read "product shot here," not broken. Doubles as a spec for the photographer. |
| **Technical flats (line art)** | You want garments visible now, on-brand | Authentic fashion language — the industry's own blueprint drawing. Reads intentional, not "icon clip-art." |

The crude-icon trap: a generic outline t-shirt icon (the kind in any icon font) reads as placeholder clip-art and *weakens* the page. If you draw a garment, draw it as a **proper flat**, not an icon.

---

## Technical flats — the right visual language

A **flat sketch** is a 2D technical drawing of a garment as if laid flat on a table, front (and/or back) view, drawn with clean solid lines. It's the blueprint that goes in a tech pack for the manufacturer — so it's the *native* way fashion represents a garment without a photo. Getting flats right is what separates "intentional fashion illustration" from "icon."

What makes a flat read as real (not an icon):

- **Correct proportion / fit** — boxy streetwear = wide body, short length, **dropped shoulders**; not a symmetrical narrow tee outline.
- **Construction detail** — ribbed collar/cuffs/hem shown as **double parallel lines**; topstitching as **dashed lines**; visible seams.
- **Garment-specific anatomy** — hoodie: hood seam, kangaroo pocket, drawstrings, ribbed waistband + cuffs. Tee: ribbed crew, sleeve hems, side seams. Jacket: center placket/zip, collar, pockets.
- **Consistent line weight** and clean symmetry; flats are precise, not sketchy.
- **Front view by default**; add back view in a tech-pack context.

Use them as **labeled image slots**: each flat sits where a real product photo will go, captioned with the piece name. When the brand delivers photography, the flat is swapped out — zero layout change.

---

## Patterns

- Draw flats as inline SVG (crisp at any size, themeable via `currentColor`, tiny payload) sized ~96–140px in a card grid.
- One accent on hover (border/lift) to make the grid feel interactive.
- Keep flats monochrome to match a bold-minimal palette; the garment shape carries it.
- If type-led, replace the garment row entirely with an oversized collection statement + the drop list — often the most premium move for a no-photo brand.

---

## Anti-patterns

| Avoid | Why |
|-------|-----|
| Generic stock garment photos | Biggest single conversion-killer; reads as not-a-real-brand |
| Icon-font t-shirt glyphs | Clip-art feel; undermines a premium page |
| Symmetric "narrow tee" outline for a streetwear brand | Wrong fit signal; streetwear is boxy/dropped-shoulder |
| Mixing flats and real photos in one grid | Inconsistent; looks half-finished |

---

## Sources

- [Points of Measure — drawing technical flats & croquis](https://www.pointsofmeasure.com/tutorials-education/diy-technical-design-section-2-drawing-technical-flats-and-croquis) — 2026-06
- [Techpacker — fashion flat sketches basics](https://techpacker.com/blog/design/what-you-need-to-know-about-fashion-flat-sketches/) — flat = garment blueprint — 2026-06
- [Techpack Wizard — what flats are & how to sketch them](https://techpackwizard.com/what-are-flats-in-fashion-design-and-why-they-re-important/) · [fashion croquis explained](https://techpackwizard.com/fashion-croquis/) — 2026-06
- [Fashion Illustration Tribe — flat sketches: technical & creative](https://fashionillustrationtribe.com/fashion-flat-sketches/) — 2026-06
- Waitlist research (generic-stock = top conversion-killer): see [`coming-soon-and-prelaunch.md`](coming-soon-and-prelaunch.md) sources.

**Agent hint:** Reference implementation of SVG flats as image slots: `program-edge-proposals/streetwear-coming-soon/`.
