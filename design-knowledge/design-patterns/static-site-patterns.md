# Static site patterns

**Purpose:** Section-based marketing sites (HTML, Astro, Next static) without app complexity.

**Harvest / review:** 2026-05

---

## Common sections (order)

| Section | Role |
|---------|------|
| **Hero** | Value prop + primary CTA + supporting image |
| **Problem / mission** | Why the org exists |
| **Programs / features** | 3–6 cards with links |
| **Social proof** | Quotes, logos, stats |
| **CTA band** | Repeat donate/signup |
| **Footer** | Nav repeat, legal, contact |

---

## Patterns

- **Semantic HTML:** `header`, `main`, `section`, `footer`, proper headings.
- **Performance:** optimize hero images (WebP/AVIF, `srcset`, lazy below fold).
- **SEO:** unique `title`/`description` per page; one `h1`.
- **Contact forms:** label every field; spam protection without CAPTCHA hell when possible.

---

## Anti-patterns

| Avoid | Why |
|-------|-----|
| 5MB hero image | CWV failure |
| Carousels for critical content | Low engagement; a11y pain |
| Wall of text | Scanning fails |

---

## Agent hint

Also load [`../website-design/information-architecture.md`](../website-design/information-architecture.md) and [`../ui-design/accessibility.md`](../ui-design/accessibility.md).
