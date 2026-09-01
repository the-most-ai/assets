# AvangardAI — Design System

> **AvangardAI** — ИИ-платформа для отделов продаж и контакт-центров. Увеличивает конверсию в сделку с помощью ИИ-продуктов для отделов продаж.
>
> Positioning: *«№1 ИИ-вендор в России, 2025»*.

This design system captures the visual language of AvangardAI's 2025
investor/marketing materials — a bilingual (primarily Russian) pitch deck
and an analytical A4 report ("ИИ во втором квартале 2025 года").

---

## Sources

- **Figma file** — `Avangard AI _ Presentation.fig` (attached VFS)
  - `/page/Pitch-Deck` — 20-slide 1920×1080 sales/pitch deck (the canonical source of truth)
  - `/page2` — shorter cover + product deck variant (Cover is bold red/orange "Avangard AI Presentation")
  - `/Export` — 20 A4 (595×842) portrait pages from the Q2-2025 report
- **Uploads**
  - `uploads/AvangardAI logo.svg` — official wordmark

No production codebase was provided.

---

## What this folder contains

```
README.md                    ← you are here
SKILL.md                     ← for Claude Code / skill invocation
colors_and_type.css          ← all design tokens (import this first)
assets/
    logo-wordmark.svg          AvangardAI full wordmark (black)
    logo-mark-blue.svg         Small triangular "house" mark in accent blue
    bg-chaos-blue-60.png       Blue abstract-cube texture (primary hero)
    bg-chaos-blue-30.png       Softer variant, often with multiply blend
    bg-chaos-large.png         Alternate blue-chaos texture
    avatar-vitaly.png          CEO headshot (Виталий Александров)
    product-screenshot.png     Product screenshot used in cases
    texture-1.png, texture-2.png  Additional editorial textures
fonts/                       ← (see note below)
preview/                     ← Design System cards (registered assets)
ui_kits/
    pitch_deck/                ← 1920×1080 slide recreations
    report/                    ← 595×842 A4 report pages
```

### Note on fonts

**Both primary typefaces are now self-hosted and embedded** as base64
data-URIs inside `colors_and_type.css`, so slides/reports render fully
offline (no Google Fonts / CDN needed for print):
- **Golos Text** — `fonts/GolosText-VariableFont_wght.ttf`, embedded.
- **Geist Mono** — `fonts/GeistMono-VariableFont_wght.ttf` (Vercel Geist,
  OFL), embedded. Variable weight 300–700 covers eyebrows / counters /
  footer tags.

The `@import` from Google Fonts is kept as a harmless online fallback; the
embedded `@font-face` rules are declared after it and take precedence.

---

## CONTENT FUNDAMENTALS

**Language.** Primary Russian, with light English tech terms left
untranslated — *GenAI*, *LLM*, *RAG*, *Structured Output*, *ROI*, *API*,
*CVAT*, *RTX 3090*. Product and company names in Latin, everything else
in Cyrillic. English is never translated to Russian when the term is
industry standard.

**Tone.** Confident, slightly editorial, business-analytical. Not
playful. Writes to C-level and commercial-dept leaders. No exclamation
marks except in rallying calls-to-action ("Читайте, делитесь, внедряйте!",
"Следующей такой историей может стать ваша.").

**Person & address.** Mostly 3rd-person analytical ("Мы подготовили…",
"Наш анализ показывает…"). Direct "вы" is used in closing CTAs
("Начните с простого пилотного проекта…").

**Casing.** Sentence case in body and titles. All-caps only for the mono
eyebrow tag ("ВВЕДЕНИЕ", "ПРОБЛЕМА", "РЕШЕНИЕ", "РЕЗУЛЬТАТ"). No
ALL-CAPS prose. Headlines use regular (400) weight Golos Text — never
bold display — letter-spacing tightened to `-0.02em` → `-0.03em`.

**Emphasis.** Bold is used liberally **inside paragraphs** to highlight
key claims ("**GenAI технологии достигли уровня зрелости**"). Blue
(`#3737FF`) is used to tint leading phrases in larger intros.

**Numbers.** Russian metric formatting — "на 40-70%", "до 20 минут",
"3х быстрее", "~5000 токенов в секунду". Ranges with hyphens; approx
with tilde. Monetary isn't used in the sampled corpus.

**Vocabulary.** "ИИ-фикация", "ИИ-вендор", "GenAI", "RAG", "AI First",
"пилотный проект", "бизнес-процессы", "ROI". No emoji anywhere. No
marketing superlatives ("best-in-class", etc). No jargon-y startup slang.

**Examples in the wild.**
- Eyebrow: `ВВЕДЕНИЕ`
- H1: *"ИИ-фикация бизнеса: от простых решений к стратегическим преимуществам"*
- Lead: *"В 2025 году искусственный интеллект перестал быть привилегией технологических гигантов."*
- Footer tag: `№1 ИИ-вендор в России · 2025`
- Deck footer: `AvangardAI — ИИ-платформа увеличения продаж`

---

## VISUAL FOUNDATIONS

### Palette

The **Style** slide documents `#6675FF` as "Blue", but every live slide
in the canonical `Pitch-Deck/Presentation` page actually uses
`rgb(55,55,255) = #3737FF`. Use **#3737FF** for pill fills and accents;
treat `#6675FF` as the documented/brand color (still available as
`--blue-doc`).

| Role | Hex | Where |
|---|---|---|
| **Black** | `#000000` | Dominant dark slide surface |
| **Near-black** | `#1F1F1F` | Card on black |
| **Fog** | `#EFEFEF` | Dominant light slide surface |
| **White** | `#FFFFFF` | Cards, pill fills |
| **Blue (live)** | `#3737FF` | Accent pill fill, CTA — what the deck uses |
| **Blue (doc)** | `#6675FF` | Documented "Blue" on style slide |
| **Blue deep** | `#0008B5` | Pressed/darker variant |
| **Blue dim** | `#BCBCFF` | In-paragraph highlight |
| **Light Blue** | `#E2E7FF` | Lavender-ice surface |
| **Lavender card** | `#EBEFFF` | Soft light-blue card |
| **Lilac** | `#E386FA` | Editorial accent pill |
| **Orange crush** | `#FF3D00` | Red-orange, reserved for the `/cover/Cover` variant |

Dark slides are **black**, light slides are **fog (#EFEFEF) or white**.
Lavender-ice and lilac are editorial accents, used on no more than a
handful of slides each.

### Typography
- **Golos Text** — everything narrative. Regular (400) dominates at all sizes, including 64px+ headlines (NOT bold). SemiBold / Bold reserved for in-paragraph emphasis and small pills.
- **Geist Mono** — all eyebrows, footer tags, numerical index labels, section counters ("01", "02", "03"), and occasional big numerical displays at ~70px Light (the `numeric-display` role).
- Letter-spacing tightens proportionally: headlines −0.02/−0.03em, body −0.01em, small labels +0.01em.
- Line-height: 1.15 titles, 1.30–1.35 body.

### Backgrounds, imagery & motif
- The **signature motif** is a 3D *blue-chaos cube cluster* render (`bg-chaos-blue-60.png`, `129378f4a267.png`). It appears at the bottom of the title slide, rotated 90°, bleeding off the edge. Also used with `mix-blend-mode: multiply` as an atmospheric overlay.
- Editorial covers may replace the texture with a flat **orange-red (#FF3D00) bleed** plus a huge Golos wordmark (see `page2/Cover`).
- No gradients, no duotones, no photography other than the CEO headshot on the title slide.
- No hand-drawn illustrations, no doodles, no playful vectors.
- Card corners vary intentionally: **0 radius** for editorial full-bleed blocks, **12px** for report cards, **24–48px** for "soft product" cards, **1000px** (pill) for small labels and CTA chips.

### Animation & interaction (for web/HTML output)
- Not present in source (static deck + PDF). **House rules** introduced for this system:
  - Ease: `cubic-bezier(.22,.61,.36,1)` (Apple-like) or `cubic-bezier(.65,0,.35,1)` for transitions.
  - Durations: 150–220ms for hover; 400–600ms for page/slide transitions.
  - Hover: accent buttons darken to `--accent-deep` (`#4A3AFF`); white cards lift `translateY(-2px)` + `shadow-md`.
  - Press: `scale(0.98)` + `shadow-sm`.
  - No bounces, no parallax, no entrance carousels. The brand is editorial, not dynamic.

### Borders, dividers, strokes
- Hairline dividers in reports: `1px solid rgba(6, 0, 18, 0.11)` — almost a ghost line.
- Pill labels on dark use a 1px white border at full opacity.
- Accent pills are full-fill `#3C50FF` (white text) or inverse (white fill + ink text).

### Shadows & elevation
- Almost none by default — the deck is flat.
- `--shadow-md` (`0 8px 24px rgba(15,0,44,.10)`) used for product mockups and elevated white cards.
- `--shadow-glow` (accent-tinted) reserved for the rare primary CTA in web contexts.

### Transparency, blur
- Frosted overlay tiles: `rgba(255,255,255,0.12)` + `backdrop-filter: blur(20px)` on dark hero sections (e.g., "Обработка жалоб и запросов клиентов" tiles).
- Overlay text color on dark is either full white or `rgba(255,255,255,0.65)`.

### Layout rules
- Slide grid: 1920×1080 with **40px gutter** (outer padding), headers 114–188px tall.
- Report grid: 595×842 with **28px gutter**.
- Fixed elements per slide: (a) Header row with title, (b) Footer row with wordmark + `№1 ИИ-вендор в России · 2025` + page counter.
- Content sections are usually 2-column on wide slides, 1-column on A4, with generous whitespace.

### Corner radii — quick reference
| Surface | Radius |
|---|---|
| Full-bleed slide block | 0 |
| A4 report stat card | 12 |
| Dark pill-ish case card | 24–48 |
| Button / label | 1000 (pill) |

### Cards — what they look like
- **Report card (dark)**: `background: #19191D`, `border-radius: 48px`, 40px padding, centered white text at 21px.
- **Report card (white)**: `background: #FFFFFF`, `border-radius: 12px`, shadow optional, 40px padding, 24px ink text, centered or top-left.
- **Frosted tile**: `background: rgba(255,255,255,0.12)`, `backdrop-filter: blur(20px)`, no border, 40px padding.
- **Pill label**: `background: #FFFFFF`, `border-radius: 1000px`, 10×12 padding, 12px bold Golos Text in ink.

---

## ICONOGRAPHY

The sampled Figma uses very few icons — this is an **editorial system, not
an icon-heavy one**. What exists:

- **In-house triangular "house" mark** — the AvangardAI logo glyph itself
  (two shapes: a roof chevron + trapezoid). Stored as
  `assets/logo-mark-blue.svg` and `assets/logo-mark-blue-2.svg`. Used
  standalone at 28×28 in footers or framed inside an 80px white circle
  next to contact info.
- **Thin-stroke utility icons** — 28×28 Feather-like line icons with
  1.5px stroke, round joins. Used on case cards ("cloud-check",
  "arrow-up-right"). Only a handful of distinct glyphs.
- **No icon font** is referenced.
- **No emoji.** Anywhere.
- **No unicode pictographs** like ✓, ✗, →, etc. used decoratively.

**Substitution policy.** When a UI surface needs an icon that isn't
in the Figma file, use **Lucide** (`lucide.dev` via CDN) — stroke width
1.5, round cap, round join — it matches the existing Feather-style
glyphs exactly. Color defaults to `currentColor`; on accent backgrounds
icons are white, on light backgrounds they are ink or accent blue.

Loaded on demand via:
```html
<script src="https://unpkg.com/lucide@latest/dist/umd/lucide.min.js"></script>
```

---

## Index / manifest

- `colors_and_type.css` — tokens, import first in any HTML artifact
- `preview/` — one HTML card per design-system concept (palette, type, logo, component states, etc.). Each is registered in the asset review panel.
- `ui_kits/pitch_deck/` — recreations of key 1920×1080 pitch slides (Title, Section Divider, Two-Column Case, Frosted Tiles, Closing).
- `ui_kits/report/` — recreations of the A4 report (Cover, Intro, Case Study, Quote).
- `assets/` — raw brand assets (logo, textures, hero image, avatar, product screenshot).

---

## Known caveats

1. **Fonts**: `uploads/Golos_Text.zip` was missing; using Google Fonts-delivered Golos Text instead. Flagged above.
2. **Codebase**: none attached — UI kits focus on the *presentation* product (pitch deck + report) which is the only surface visible in Figma. The product UI itself (the sales platform) isn't in the Figma and isn't mocked.
3. **Icons**: Lucide is used as the substitution library; the sampled corpus has too few icons to extract a custom set.
