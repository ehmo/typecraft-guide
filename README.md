# Typecraft Guide Skill

This repository publishes a typography skill for fast review and correction across web, iOS, Android, print, and presentation contexts.

The skill turns a long-form typography reference into an actionable AI workflow:

- evaluate existing typography against evidence-based defaults,
- call out critical vs important fixes with severity,
- propose concise, platform-aware edits for content, code, or UI copy.

## Install

```bash
npx skills add ehmo/typecraft-guide
# Some environments use `npx skill`; if yours does, use:
npx skill add ehmo/typecraft-guide
```

(Claude marketplace install is configured through `.claude-plugin/marketplace.json`.)

## Contributing (Pull Requests)

- Fork the repository and create a feature branch from the default branch.
- Keep PRs focused: one meaningful change per PR (for example, one skill rule tweak, one wording improvement, or one source update).
- When changing review logic, update both `SKILL.md` and `typography-reference.md` if the behavior changes.
- If any recommendation changes, add or update the relevant entry in the [Sources section](#sources-with-publicationupdate-dates).
- Verify relative links, markdown rendering, and `package.json` file references for the changed paths.
- PR title format should be clear and scoped (`feat: ...`, `fix: ...`, `docs: ...`).
- In the PR description include:
  - what changed,
  - why it improves output quality,
  - and a short example of expected impact.

Example PR checklist:

- [ ] Scope matches the PR title
- [ ] File path references are still correct
- [ ] Sources and rationale are still accurate where used
- [ ] README structure still matches the repo model (runtime + reference + metadata)
- [ ] No absolute links added

## What this skill does

- [skills/typecraft-guide/SKILL.md](skills/typecraft-guide/SKILL.md) is the runtime file.
- [skills/typecraft-guide/typography-reference.md](skills/typecraft-guide/typography-reference.md) is the concise ruleset for typography decisions.

## Repo structure

```text
typecraft-guide/
├── README.md
├── agents/
│   └── openai.yaml
├── assets/
│   ├── typecraft-guide-small.svg
│   └── typecraft-guide-large.svg
├── LICENSE
├── CHANGELOG.md
├── package.json
├── .claude-plugin/
│   └── marketplace.json
├── skills/
│   └── typecraft-guide/
│       ├── SKILL.md
│       └── typography-reference.md
```

## Why this exists

The original raw guide was broad and detailed. This version keeps the strongest, high-impact rules and strips repetition so the model can act on typography constraints quickly without losing rigor.

## Reference materials and why they matter

- [skills/typecraft-guide/typography-reference.md](skills/typecraft-guide/typography-reference.md): the core, concise typography playbook used by the skill for review and composition decisions.
- [README Sources section](#sources-with-publicationupdate-dates): the evidence trail supporting the playbook; used to justify severity and platform defaults when needed.
- [skills/typecraft-guide/SKILL.md](skills/typecraft-guide/SKILL.md): operational instructions for how the model invokes and applies the above references.

## Source references (with role and rationale)

- [Sources section below](#sources-with-publicationupdate-dates) is the master source index. It is used for claimability and traceability.
- Butterick, *Practical Typography* — practical style and typographic hierarchy principles.
- Apple Human Interface Guidelines — iOS/macOS typography standards and Dynamic Type behavior.
- Material Design 3 — Android/Material scale, spacing, and accessibility defaults.
- WCAG 2.2 — legal-grade accessibility requirements for readability and contrast.
- Richardson 2022 (Springer) — evidence basis for serif vs. sans-serif readability claims.
- Dyson & Kipping line-length research — supports line-length boundaries for sustained reading comfort.
- Johnson, Bui, Schmitt 2018 — supports spacing, punctuation, and readability assertions.
- Cloud Four justified text research — informs when justified text is and is not recommended.
- Smashing Magazine fluid typography analysis — modern practical clamp-based type scaling guidance.
- HTTP Archive Web Almanac 2025 — empirical web performance and typography usage trends.
- MDN Web CSS docs — canonical web font, text-rendering, and CSS behavior references.

## Sources (with publication/update dates)

- [Butterick, *Practical Typography* (2nd ed.)](https://practicaltypography.com/) — 2016-2024 updates; accessed 2026-03-03
- [Apple Human Interface Guidelines](https://developer.apple.com/design/human-interface-guidelines/) — continuously updated; accessed 2026-03-03
- [Material Design 3](https://m3.material.io/) — continuously updated; accessed 2026-03-03
- [WCAG 2.2](https://www.w3.org/TR/WCAG22/) — 2023-06-05
- [Richardson, J.T.E. (2022): *The Legibility of Serif and Sans Serif Typefaces*](https://link.springer.com/book/10.1007/978-3-030-90984-0) — 2022
- [Dyson & Kipping line-length research](https://journals.uc.edu/index.php/vl/article/view/5671) — publication year listed in article metadata
- [Johnson, Bui, Schmitt (2018): spacing study](https://pubmed.ncbi.nlm.nih.gov/29691763/) — 2018
- [Cloud Four justified text research](https://cloudfour.com/thinks/justified-text-better-than-expected/) — 2024-2025
- [Smashing Magazine fluid typography analysis](https://www.smashingmagazine.com/2022/01/modern-fluid-typography-css-clamp/) — 2022-01-16
- [HTTP Archive Web Almanac (2025)](https://almanac.httparchive.org/en/2025/) — 2025
- [Web platform documentation on font/text rendering and CSS properties](https://developer.mozilla.org/en-US/docs/Web/CSS) — continuously updated; accessed 2026-03-03
