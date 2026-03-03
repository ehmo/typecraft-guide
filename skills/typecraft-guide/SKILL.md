---
name: typecraft-guide
description: Use for typography evaluation, cleanup, and composition guidance across web, iOS, Android, print, and presentations.
---

# Typecraft Guide

## 0) When to use this skill

Use this skill whenever you need to:
- review typography quality in prose, UI copy, docs, slides, or style guides,
- convert rough copy into typography-correct copy quickly,
- generate platform-specific recommendations for text rendering.

## 1) Scope

The source playbook is in `typography-reference.md`. Source references live in the root README under [Sources](../../README.md#sources-with-publicationupdate-dates).
This skill applies the following workflow to avoid over-correcting:

1. Identify platform + medium (`web`, `iOS`, `android`, `print`, `presentation`).
2. Pick goal: **evaluation**, **improvement**, or **creation**.
3. Apply the strongest rules first: body size, line-height, measure, contrast, and accessibility.
4. Report issues by severity (`critical`, `important`, `recommended`).

### Reference loading policy

- Read `typography-reference.md` for nearly every typography task unless the request is only for a tiny stylistic rewrite.
- Read `../../README.md` sources section when you need to justify a contested/platform-specific recommendation or include source-backed rationale.
- Read neither if the task is purely mechanical (e.g., “fix only one typo in body text already marked for correction”).

## 2) Operating rules

### Core defaults
- Start with body typography first; all other styles derive from it.
- Keep confidence tags: `[STRONG]`, `[MODERATE]`, `[CONTESTED]`, `[PLATFORM]`.
- Prefer short, testable edits. Avoid style churn unless it changes readability or accessibility.

### Severity definitions
- `critical`: violates legal/accessibility requirements or makes content hard to read.
- `important`: materially reduces readability, hierarchy, or consistency.
- `recommended`: improves polish, consistency, or maintainability.

### Default evaluation sequence
1. Body size / line-height / measure.
2. Punctuation marks and special characters.
3. Emphasis (bold/italic/all-caps/small-caps/links).
4. Color contrast and hierarchy.
5. Spacing, tables, lists, platform constraints.
6. Accessibility and platform-specific checks.

## 3) Required output

For each pass, emit:
- **Verdict**: pass/fail/needs work.
- **Top 3 findings** with severity and exact rule.
- **Before/after snippets** where a concrete edit is beneficial.
- **Short rationale** tied to the platform context.
- **Final check**: contrast, scaling, and spacing tolerance.

When ambiguity exists, ask one targeted follow-up before making irreversible editorial changes (for example: copy tone constraints, brand style, legal typography requirements).

## 4) Platform and policy triggers

- Always read: [./typography-reference.md](./typography-reference.md)
- Always reference: [../../README.md#sources-with-publicationupdate-dates](../../README.md#sources-with-publicationupdate-dates)
- For strict code tasks, keep changes minimal and preserve existing copy intent.
- If a request is purely factual and asks for a rule table, provide the concise checklist and no narrative.

## 5) End condition

Stop when:
- all critical findings are addressed or explicitly deferred with rationale,
- the resulting result preserves original meaning,
- and accessibility thresholds are met (`WCAG 2.2` requirements in the reference).
