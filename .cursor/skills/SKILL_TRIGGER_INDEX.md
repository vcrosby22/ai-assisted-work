# Skill trigger index

Purpose: quick reference for project-local Cursor skills and the keywords that should cause an agent to consider loading them.

## Project skills

| Skill | Path | Use when the user mentions... |
|-------|------|-------------------------------|
| `product-management` | `.cursor/skills/product-management/SKILL.md` | pm, product management, product planning, product strategy, product design, product discovery, prioritization, roadmap, PRD, backlog, requirements, release planning, stakeholder product docs, Design Thinking, UCD, HCD, Service Design, Service Blueprinting, Double Diamond, journey mapping, prototyping, usability testing |
| `regulated-medtech-design` | `.cursor/skills/regulated-medtech-design/SKILL.md` | medtech, med tech, medical device, regulated product, regulated products, healthcare, health tech, digital health, SaMD, software as a medical device, AI medical device, AI/ML medical device, clinical, patient safety, FDA, 510(k), De Novo, PMA, MDR, IVDR, CE mark, notified body, ISO 13485, ISO 14971, IEC 62366, human factors, usability engineering, design controls, risk management, QMS, post-market surveillance, compliance-aware design |
| `design-knowledge` | `.cursor/skills/design-knowledge/SKILL.md` | build a new product, new product, website, landing page, web app, storefront, e-commerce, shop, checkout, donation page, donate, nonprofit site, mission site, UI, UX, user interface, frontend, design system, redesign, wireframe, sitemap, information architecture, WCAG, accessibility, static site, full-stack, REST API for UI, implement the site, ship the site |

## Routing notes

- If both skills match, load `product-management` for PM framing and `regulated-medtech-design` for compliance-aware regulated product constraints.
- **New product / build a website:** load `design-knowledge` for UI/IA/implementation; add `product-management` when the user needs PRD, roadmap, or discovery—not for visual implementation alone.
- **Regulated + customer UI:** load `regulated-medtech-design` and `design-knowledge` (accessibility + patterns); PM skill optional.
- Regulated healthcare/medtech outputs are PM/design framing only, not legal or regulatory advice.
- Keep trigger lists updated when adding or renaming skills.
