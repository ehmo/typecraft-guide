# Typecraft Guide (Condensed)

Evidence-prioritized playbook for writing and reviewing typography across web, iOS, Android, print, and presentations.

Use this as a fast decision tree, not an aesthetic opinion quiz:
start with body text defaults, enforce accessibility first, then refine hierarchy and style.

## 0) Core principles

- Body text is the anchor. If body is wrong, everything else fails.
- Measure, not fonts, carries most of perceived quality.
- Avoid defaults by category: each medium has practical floors and conventions.
- Prefer small, testable increments over dramatic redesigns.
- If a rule hurts meaning, defer and document the tradeoff.

## 1) Confidence markers

- `[STRONG]` strong evidence or broad consensus
- `[MODERATE]` majority-supported but with some variation
- `[CONTESTED]` debated or context dependent
- `[PLATFORM]` convention of Apple/Google ecosystem, not universal truth

## 2) Fast evaluation flow

1. Define medium: print, web, mobile, UI platform, slide deck.
2. Confirm mandatory constraints:
   - minimum size,
   - minimum contrast,
   - minimum scalability (200% zoom/resizing),
   - spacing/tolerance.
3. Validate body text parameters.
4. Validate hierarchy, punctuation, emphasis, layout.
5. Validate platform conventions.
6. Return findings by severity.

## 3) Body text fundamentals

### 3.1 Size defaults

| Context | Default range |
| --- | --- |
| Print body | 10-12 pt |
| Web body (desktop) | 16-20 px (1.0-1.25 rem) |
| Web body (mobile) | 16-18 px |
| iOS | 17 pt body |
| Android | 16 sp body large (14 sp minimum baseline in legacy UIs) |
| Presentations | keep 12-15 lines on screen |

Rule: optical size differs by font design. Verify by eye at target viewport size.

### 3.2 Line height

- General body: `1.4`–`1.6`.
- Compact UI: `1.2`–`1.4`.
- Large headings: `1.1`–`1.2`.
- Use unitless CSS (`line-height: 1.5`), avoid px/em in global body rules.
- Web accessibility minimum: default should tolerate `1.5x` override.

### 3.3 Measure (line length)

- Ideal: around `45-75` characters per line.
- Desktop web: keep to ~66 CPL where possible.
- Mobile: `30-50` CPL.
- Use `max-width` constraints (`max-width: 65ch` is a strong default).
- Never let text run edge-to-edge on wide viewports.

### 3.4 Font selection and pairing

- Print body: serif is often preferable; web allows serif or sans depending on system.
- Prioritize medium-specific quality (x-height, contrast, spacing) over brand trend.
- Keep families tight: one family usually enough; two is safe.
- Use high-quality fonts; avoid decorative faces for long-form body text.

### 3.5 Paragraph rhythm

- For digital: spacing between paragraphs is standard.
- For print: first-line indentation is a valid alternative.
- Do not combine indentation and paragraph spacing at once.

## 4) Punctuation and special characters

### 4.1 Quotes

- Use typographic quotes in body text:
  - double: `“ ”`
  - single: `‘ ’`
- Use straight quotes only for code, foot/inch notation, and technical constraints.

### 4.2 Dashes and hyphens

- `-` = hyphen.
- `–` = en dash (ranges).
- `—` = em dash (sentence breaks/parenthetical asides).
- Do not use `--` as a final em dash substitute.
- “from 1990-2000” style ranges are inconsistent.

### 4.3 Spacing and ellipsis

- One space after a sentence period.
- No intentional multiple word spaces for alignment.
- Use nonbreaking space where punctuation must stay with preceding token (`5 kg`, initials).
- Prefer `…` over `...`; avoid orphaning with NBSP when needed.

## 5) Emphasis and marks

- Bold/italic: choose one, use sparingly.
- Avoid underlining except for hyperlinks.
- ALL CAPS: acceptable for short labels only; add ~5–12% tracking for readability.
- Small caps: only real OpenType small caps; keep letter spacing applied.
- Kerning on by default (`font-kerning: normal`).
- Ligatures: safe defaults (`common-ligatures`) are fine unless readability is harmed.

## 6) Headings and hierarchy

- Prefer 2–3 heading levels.
- Headings should be differentiated by size + spacing, then weight.
- Keep heading style consistent; avoid centered headings and all caps for long headings by default.
- Increase weight slightly in dark themes; avoid pure white text on pure black.

### 6.1 Platform scale reference (quick)

#### iOS body and title styles
- Body: `17 pt`
- Headline: around `17 pt`, semibold
- Callout: `16 pt`
- Caption: `11-12 pt`

#### Android (Material) practical body scale
- Display/Headline/Title: follow Material 3 token set.
- Body large/medium: `16 sp` / `14 sp`.
- Body small/caption: around `12 sp` / `11 sp`.

## 7) Color and contrast

- Text contrast:
  - normal text AA `4.5:1`,
  - large text AA `3:1`.
- Prefer near-black on light mode; avoid pure black in body.
- Prefer off-white/dim white in dark mode; avoid pure white.
- Use color tokens and alpha for hierarchy, not dozens of bespoke text colors.
- In dark mode: slightly increase weight + small tracking + modest line-height increase.

## 8) Layout and spacing behavior

- Left alignment is default for body.
- Centered text for short titles, labels, invitations; not body paragraphs.
- Justified only with adequate widths and hyphenation control.
- Line breaks should remain stable with user text-size overrides.
- For tables:
  - keep borders minimal,
  - use `tabular-nums` for numbers,
  - align numbers right.
- Lists: use consistent hanging indentation, keep grammatical structure parallel.

## 9) Responsive typography

- Use `clamp()` only with bounded ratios.
- Max font size should not exceed ~2.5× min size to preserve zoom/reflow behavior.
- Scale container width and font size together to preserve effective measure.
- Use max-width text containers rather than letting line length explode.

## 10) Font performance

- For 1–2 styles, static fonts are fine.
- For 3+ styles or responsive optical needs, prefer variable fonts.
- Web performance defaults:
  - WOFF2,
  - metric overrides (`size-adjust`, `ascent-override`, `descent-override`) for CLS safety,
  - `font-display: swap` or `optional` depending on priorities,
  - preload critical font assets only.

## 11) Accessibility and platform-specific checks

### 11.1 WCAG 2.2 baseline

- Contrast ratios as above.
- Support 200% resize (or equivalent platform scaling).
- No horizontal scroll at 320px text flow.
- Permit custom spacing overrides (line-height, letter-spacing, word-spacing).
- Never disable zoom (`user-scalable=no`, `maximum-scale=1`) for web.

### 11.2 iOS

- Use Dynamic Type (`Text` styles or `.relativeTo`) over fixed points.
- Test scale categories (`xSmall` to `AX5`) where relevant.
- Honor bold text / high contrast preferences.

### 11.3 Android

- Use `sp` for text.
- Verify at system font scale 200%.
- Use Material typography tokens where practical.

## 12) Common errors (high impact)

- Too-short/too-long body sizes.
- Ignoring WCAG contrast or resize requirements.
- Wrong dash/quote characters.
- Overusing bold/italics/all-caps.
- Centered dense body paragraphs.
- Justified text with no hyphenation.
- Fixed pixel sizes in scaled interfaces.
- Excessive font families.
- Multiple fonts in one paragraph.

## 13) Checklist

Use this if the input is a full typography pass:

### Critical
- body size in medium-appropriate range
- body line-height within `1.4`–`1.6`
- measure in sensible bounds
- contrast ratio and resizing support
- no all-caps paragraphs
- smart quotes for prose
- no fixed-space hacks (double spaces, `--` em dash substitution)

### Important
- 2-3 heading levels only
- underline only links
- consistent paragraph spacing rules
- hyphenation policy for justified content
- heading-space hierarchy clear
- color hierarchy via tokens

### Recommended
- `text-wrap: balance` on headings
- `text-wrap: pretty` on long paragraphs
- `font-optical-sizing: auto`
- font loading strategy with preload + `font-display`
- explicit source spacing and non-breaking spaces where needed
