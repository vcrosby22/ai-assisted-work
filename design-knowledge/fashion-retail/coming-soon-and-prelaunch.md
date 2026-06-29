# Coming-soon & pre-launch pages

**Purpose:** Build a high-converting pre-launch / coming-soon page that captures a waitlist. This is the **most common Program Edge inbound** ("clean modern coming-soon page to build hype and collect email signups"), so it's worth a tight, repeatable spec.

**Harvest / review:** 2026-06 — Benchmarks: good pre-launch waitlists convert cold traffic at **8–20%**.

---

## The one-screen spec

A coming-soon page has exactly **one job**: capture the contact. Everything serves that.

| Element | Rule |
|---------|------|
| **Headline** | One specific, outcome-driven line. Names the thing and the moment ("The first drop is almost here"), not a vague slogan. |
| **One action above the fold** | A single email (or email+SMS) field and one button. **No nav, no "learn more"**, no competing links. |
| **Launch window** | Always show one. A countdown to a concrete date is strongest; even "Summer 2026" beats an open-ended "coming soon." |
| **Social proof** | A live signup counter ("Join 200+ on the list") or referral position. Social proof can lift conversion meaningfully (cited up to ~270%). Add once numbers aren't embarrassing. |
| **Imagery** | Real product shot, a painterly/branded illustration, **or nothing** (type-led). Never a generic stock photo — it's the biggest single conversion-killer here. |
| **Brand feel** | Bold-minimal, expressive type, tight palette. The page is the brand's first impression — make it feel "expensive." See [`visual-design-and-editorial.md`](visual-design-and-editorial.md). |

---

## Patterns that convert

- **One field, one button.** Every extra field drops completion. Ask for email only; add SMS only if the drop strategy needs it.
- **Countdown timer** to the drop — converts the urgency lever (see [`drop-marketing-and-launch.md`](drop-marketing-and-launch.md)) into a visible element.
- **Reward the signup** — promise early access + launch-day discount right at the field; it raises perceived value of joining.
- **Success state that keeps going** — after signup, offer a share/referral action (move them up the list) instead of a dead "thanks."
- **Pair the page with a launch moment** — the page + a launch video + coordinated creator reposts in hour one is the amplification pattern.
- **Mobile-first** — most traffic is phone; the field + button must be thumb-reachable and the type must hold at 375px.

---

## Anti-patterns

| Avoid | Why |
|-------|-----|
| Generic stock hero image | Single biggest conversion-killer on pre-launch pages |
| "Coming soon" with no date | Removes the urgency lever |
| Multi-field forms / asking for name+phone+email | Each field cuts completion |
| Nav bar / multiple CTAs | Splits the one action; this page should have no exits but the form |
| Empty social-proof ("Join 3 people") | Showing a tiny number hurts; hide the counter until it helps |

---

## Program Edge build recipe (static, deployable)

Static one-pager (Cloudflare Pages, Victoria's stack) with: expressive display + mono type, near-black or warm-off-white field, oversized headline, countdown JS, single email capture wired to a list provider (Formspree fastest for spec builds; Mailchimp/Beehiiv/Klaviyo for real), success state, optional signup counter. Reusable as a **template** — parameterize brand name, city, accent color, drop date. See live reference build: `program-edge-proposals/streetwear-coming-soon/`.

---

## Sources

- [Flowjam — high-converting waitlist landing pages](https://www.flowjam.com/blog/waitlist-landing-page-examples-10-high-converting-pre-launch-designs-how-to-build-yours) — 8–20% benchmark, one-field rule — 2026-06
- [Waitlister — coming-soon page examples](https://waitlister.me/growth-hub/blog/coming-soon-page-examples) — 2026-06
- [StartUp Fashion — pre-launch landing pages](https://startupfashion.com/5-great-pre-launch-landing-pages-to-inspire-you/) — fashion-specific — 2026-06
- [Shopify — coming soon page examples & templates](https://www.shopify.com/blog/coming-soon-page) — 2026-06
- [Moosend — waitlist landing page best practices](https://moosend.com/blog/waitlist-landing-page/) · [GetResponse](https://www.getresponse.com/blog/waitlist-landing-page) — 2026-06

**Agent hint:** Demand mechanics behind the page → [`drop-marketing-and-launch.md`](drop-marketing-and-launch.md). No photos for the hero → [`garments-without-photos.md`](garments-without-photos.md).
