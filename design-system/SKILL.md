---
name: avangardai-design
description: Use this skill to generate well-branded interfaces and assets for AvangardAI (ИИ-платформа для отделов продаж и контакт-центров), either for production or throwaway prototypes/mocks/decks/reports. Contains essential design guidelines, colors, type, fonts, assets, and UI kit components for prototyping.
user-invocable: true
---

Read the README.md file within this skill, and explore the other available files.

Key files:
- `README.md` — brand context, content fundamentals, visual foundations, iconography
- `colors_and_type.css` — all design tokens (import first in any HTML artifact)
- `preview/` — small cards illustrating each token/component
- `ui_kits/pitch_deck/` — 1920×1080 slide recreations (Title, SectionDivider, TwoColumnCase, FrostedTiles, Contact)
- `ui_kits/report/` — 595×842 A4 pages (Cover, Intro, Case)
- `assets/` — wordmark, mark, chaos-cube textures, avatar, product screenshot

If creating visual artifacts (slides, mocks, throwaway prototypes), copy assets out and create static HTML files for the user to view, importing `colors_and_type.css`. Use Golos Text for narrative and Geist Mono for eyebrows / counters / footer tags. Primary accent is `#3C50FF` on `#0F002C` ink or `#E2E7FF` lavender-ice surfaces. Avoid gradients and emoji.

If working on production code, copy assets and read the rules here to become an expert designer for this brand.

If the user invokes this skill without other guidance, ask what they want to build or design, ask a few questions (surface, tone, audience), and act as an expert designer who outputs HTML artifacts *or* production code.
