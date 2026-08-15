---
name: Setup New Exercise
description: Create a new exercise in German and generate stubs for English and French.
---

# Setup New Exercise Skill

Use this skill when the user asks to create a new exercise or to add a module.

`AGENTS.md` is the contract. If this skill contradicts `AGENTS.md`, follow `AGENTS.md`.

## 1. Preparation

- Choose the topic and a unique slug, for example `bias-in-ocr`.
- Write the full exercise in German. German leads. English and French follow.
- Choose exactly one category from the table in `AGENTS.md` section 4. Do not invent a category, and do not copy the table into another file. Ethics is a tag, and not a category.
- Choose three to five tags in the language of the file.
- Choose a `difficulty` value: `Beginner`, `Intermediate`, or `Advanced`.
- Choose an honest `time_estimate`, for example `'60 min'` or `'2 d'`.
- Prefer resources that exist in all three languages. Flag a resource that exists in one language only.

## 2. File Creation

Create three files: one full German file and two stubs.

### A. German Exercise (Full Template)

File: `de/exercises/[slug].qmd`

The block below uses single quotes, because Prettier formats this skill file. Write double quotes in the `.qmd` file, as the existing exercises do. See `AGENTS.md` section 8.

```yaml
---
lang: de
title: 'Titel'
subtitle: 'Kurze zweite Zeile'
description: 'Kurzbeschreibung'
author:
  - name: 'Name'
    orcid: 0000-0000-0000-0000
    email: name@example.org
    affiliations:
      - 'Institution'
date: '2026-01-31'
date-modified: '2026-01-31'
categories: [Quellen]
image: ../../assets/images/example.png
tags:
  - Tag1
  - Tag2
  - Tag3
difficulty: Beginner
time_estimate: '60 min'
draft: true
---
```

Use the section structure from `AGENTS.md` section 11. Close the file with the bibliography division:

```markdown
## Bibliographie

::: {#refs}
:::
```

### B. Language Stubs

For English and French, create a file with minimal content to establish file parity.

File: `[en|fr]/exercises/[slug].qmd`

```yaml
---
lang: en
title: 'TRANSLATION NEEDED: [Original Title]'
description: 'Translation needed'
draft: true
---
::: callout-warning
## Translation Needed

This exercise exists in German only.
:::
```

## 3. Content Rules

- Do not name an AI product, an AI vendor, or a model. Describe the capability that the tool needs.
- Name the audit trail KI-Protokoll. Do not use another name.
- Add every new term to `de/glossary.qmd`, then link to the anchor of the entry.
- Caution: `callout-info` is not valid. Use only `note`, `tip`, `important`, `caution`, and `warning`.
- State the workload of the exercise before the first step.

## 4. Next Steps

1. Check the result with `quarto preview`. `npm run check` does not read `.qmd` files.
2. Tell the user that the German file and the two stubs exist.
3. Suggest the Translation skill for the English version and the French version.
