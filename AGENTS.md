# AGENTS Guidelines for Critical AI Literacy for Historians

This repository holds multilingual educational exercises for critical AI literacy in historical research. These guidelines apply to every AI agent that works on this repository. They also apply to every person who directs such an agent. This file is the contract. If another file contradicts this file, follow this file and report the contradiction.

## 1) Use Preview Mode During Interactive Sessions

- Run `quarto preview` while you edit content. Live reload works for `.qmd`, `.md`, and asset files.
- Do not run production commands in an agent session. The human maintainer must ask for them first.
  - Do not run `quarto render`.
  - Do not run `quarto publish gh-pages`.
- Keep the preview server active while you edit, because the preview is the only check of the content.

## 2) Available Skills

The skills in `.agent/skills` automate common tasks. Read the skill before you do the work by hand.

- Bibliography Management: manage citations and convert formats (`.agent/skills/bibliography/SKILL.md`)
- Setup New Exercise: create an exercise with the correct structure and metadata (`.agent/skills/new_exercise/SKILL.md`)
- Sync Exercises: audit and sync missing files across the languages (`.agent/skills/sync_exercises/SKILL.md`)
- Translation: translate content from German into English and French (`.agent/skills/translation/SKILL.md`)
- Validate Scientific Backing: check that literature supports an exercise (`.agent/skills/validate_backing/SKILL.md`)

There is no glossary skill. The course glossary is a content page. See section 5.

## 3) Multilingual Content Management

This repository holds content in German (`de/`), English (`en/`), and French (`fr/`).

### Translation Workflow

German leads. The audience is German-speaking historians, and the German files are the most complete. `de/` is the reference version. `en/` and `fr/` follow `de/`.

Caution: do not edit `en/` or `fr/` to add new substance. The two versions then drift from the reference version.

1. Write the change in the German file first.
2. Translate the change into English and French, or mark the two files as outdated.
3. Open an issue with the label `translation-needed` for each translation that you do not write.
4. Keep the same structure in all three language versions.

A translated file must carry the automated-translation callout that `.agent/skills/translation/SKILL.md` defines.

### Content Parity

- Give each language directory the same file structure.
- Use the same exercise order and the same slug in all three languages.
- When you add an exercise, create a stub file in the other two languages.

### Resource Localization

- Flag a resource that exists in one language only. Use the form `(GERMAN only)`, `(ENGLISH only)`, or `(FRENCH only)`.
- Propose a localized alternative when one exists, for example a translated edition of a book.
- Check `bibliography.bib` for a language-specific edition before you add a new entry.

## 4) Exercise Metadata Standards

### Categories

An exercise must carry exactly one category. The four categories below are the complete list. Use the label of the language of the file.

| German                 | English              | French                   |
| ---------------------- | -------------------- | ------------------------ |
| KI & Digitale Methoden | AI & Digital Methods | IA & Méthodes numériques |
| Quellen                | Sources              | Sources                  |
| Methoden               | Methods              | Méthodes                 |
| Public History         | Public History       | Public History           |

Ethics is not a category. Ethical awareness applies to every exercise, so it does not divide the set. Use the tag `Ethik`, `Ethics`, or `Éthique` instead.

Do not invent a category. To add a category, change this table first. Then change the three other files that hold the same list, in the same pull request:

- `.agent/skills/new_exercise/SKILL.md`
- `.agent/skills/translation/SKILL.md`
- `.github/ISSUE_TEMPLATE/exercise_proposal.yml`

### Tags

Use descriptive tags that characterize the exercise. Three to five tags are recommended. There is no upper limit. Translate a tag into the language of the file. Examples are `Prompting`, `Toolkritik`, `Reproduzierbarkeit`, `Ethik`, `Quellenkritik`, and `Datenkompetenz`.

### Difficulty and Time

Every exercise must carry a `difficulty` field and a `time_estimate` field. `README.md` promises both to the learner.

- `difficulty` takes one of three values: `Beginner`, `Intermediate`, or `Advanced`. These values stay in English in all three languages, because they are machine values and not learner text.
- `time_estimate` takes a quoted string with a number and a unit. Use `min` for minutes and `d` for days. Examples are `'60 min'`, `'45-60 min'`, and `'2 d'`.
- State the honest time for the complete exercise. If an exercise needs archive visits over several days, write days.

### Required YAML Front Matter

Every exercise must carry the fields below. The order of the fields is free. The example uses single quotes, because Prettier formats this file. See section 8.

```yaml
lang: de # or en, fr
title: 'Exercise Title'
subtitle: 'Short second line'
description: 'Brief description'
author:
  - name: 'Author Name'
    orcid: 0000-0000-0000-0000
    email: author@example.org
    affiliations:
      - 'Institution'
date: '2026-01-31'
date-modified: '2026-01-31'
categories: [Quellen] # exactly one category from the table above
image: ../../assets/images/example.png
tags:
  - Tag1
  - Tag2
  - Tag3
difficulty: Beginner # Beginner, Intermediate, or Advanced
time_estimate: '60 min'
draft: false
```

Notes on the fields:

- `author` takes a list. Each author takes an `affiliations` list. Do not write a scalar `affiliation`.
- `subtitle` and `image` are required, because every exercise carries them.
- `date-modified` takes a real date. Replace `today` with a real date in every file that you change.
- Use double quotes in the front matter of a `.qmd` file, because all exercises use double quotes. Prettier does not read `.qmd` files, so no tool changes this style.

## 5) Terminology and Content Rules

### Never Name an AI Product

Describe what a tool must be able to do. Do not name an AI product, an AI vendor, or a model. Write "a KI-System that can read a PDF file" and not a product name. This rule applies to exercise text, to prerequisites, and to links. A link to vendor documentation names a vendor, so use a neutral source instead.

### One Term for the Audit Trail

The log of AI use has one name: **KI-Protokoll**. Use this term in every German file. Do not write Prompt-Protokoll, Audit Trail, Analyseprotokoll, Rechercheprotokoll, Suchprotokoll, Entscheidungslog, or Prüfpfad. Use "AI log" in every English file. Use "journal IA" in every French file. Name the German term once in each translated file.

### Glossary

The course glossary is `de/glossary.qmd`. It holds a short working definition of every term that an exercise uses without explanation. When you introduce a term, add the definition to the glossary. Link to the anchor of the entry, for example `[Prompt](../glossary.qmd#gl-prompt)`.

### Callouts

Quarto has five callout types: `note`, `tip`, `important`, `caution`, and `warning`. Write them as `.callout-note`, `.callout-tip`, `.callout-important`, `.callout-caution`, and `.callout-warning`.

Caution: `callout-info` is not a Quarto callout type. Quarto renders such a block as a plain division without a title bar or a color.

### Language Level

- Write short sentences for a reader who is not tech savvy.
- Define a term before you use it.
- State the workload of an exercise before the first step, and not in the hand-in section.

## 6) Citations and Bibliography

### bibliography.bib Standards

- Use consistent BibTeX formatting.
- Include the DOI when one exists.
- Use the citation key format `authorYEARkeyword`, for example `russell2020artificial`.
- Give an article these fields: `author`, `title`, `journal`, `year`, `volume`, `pages`, and `doi`.
- Give a book these fields: `author`, `title`, `publisher`, `year`, and `isbn`.

### Citing in Exercises

- Use `[@citationkey]` for an inline citation.
- Reference `bibliography.bib` in the `_metadata.yml` file of each language.
- Cite every work that the bibliography section lists.

## 7) Repository Structure

```
critical-ai-literacy-for-historians/
├── de/               # German content (reference version)
│   ├── index.qmd
│   ├── glossary.qmd
│   └── exercises/
├── en/               # English content
│   ├── index.qmd
│   └── exercises/
├── fr/               # French content
│   ├── index.qmd
│   └── exercises/
├── assets/           # Shared images and fonts
└── bibliography.bib  # Shared citations
```

## 8) Formatting and Linting

Run `npm run format` before you commit. Run `npm run check` to verify the formatting without a change.

Caution: `npm run check` verifies none of the course content. Prettier has no parser for `.qmd`. The command `npx prettier --file-info de/exercises/zitieren.qmd` reports `"inferredParser": null`. Therefore Prettier skips all 30 content files. The `.husky/pre-commit` hook and the CI `lint` job run the same command, so they skip the same files. A green check does not mean that the content is correct. Verify content with `quarto preview`. Issue #26 tracks a fix.

Prettier formats `.md`, `.yml`, and `.json` files. `.prettierrc` sets `singleQuote: true`. Prettier also formats a YAML code block inside a Markdown file, so it rewrites the quotes in every YAML example in this file to single quotes. This behaviour is intended. Do not change the examples in this file to double quotes, because `npm run format` reverts the change. The rule for the front matter of a `.qmd` file is different, because Prettier never reads those files. See section 4.

## 9) Commits and Changelog

- Use `npm run commit` for the Conventional Commits wizard.
- Run `npm run changelog` after a commit, then update `CHANGELOG.md`.
- Use these commit types: `feat`, `fix`, `docs`, `chore`, and `refactor`.

## 10) Documentation Practices

- Use `.qmd` for all educational content.
- Give every `.qmd` file valid YAML front matter.
- Write clear academic language that a novice understands.
- Give each exercise learning objectives, activities, and reflection prompts.
- Link to relevant resources and to further reading.

## 11) Content Quality Standards

### Exercise Structure

Each exercise follows a fixed pedagogical structure. Use `de/exercises/prompt-engineering.qmd` or `de/exercises/quellenkritik-bundesrat-europarat-1949.qmd` as the reference.

1. Overview and didactic goal (`## Überblick und didaktisches Ziel`)
   - Give the context of the exercise.
   - Name the competencies that the exercise trains.
2. Prerequisites (`## Voraussetzungen`)
   - Name the methodological knowledge that the learner needs.
   - Name the capabilities that the tool needs. Do not name a product.
3. Learning objectives (`## Lernziele`)
   - List what the learner can do after the exercise.
4. Numbered steps, for example `## 1. Orientierung`
   - Goal (`### Ziel`): state the result of the step.
   - Task (`### Aufgabe`): give the manual task.
   - AI task (`### Aufgabe ... mittels KI`): give the prompt or the workflow to test.
   - Reflection (`### Arbeitsauftrag (Reflexion)`): compare the AI output with the manual work.
5. Learning outcome (`## Lernergebnis`)
   - List the artifacts, the protocols, and the insights that the learner takes away.
6. Bibliography (`## Bibliographie`)

### Pedagogical Principles

An exercise must promote:

- Critical thinking about AI as a tool and as a method
- Digital source criticism
- Ethical awareness of bias, privacy, and representation
- Transparency and reproducibility in research
- The FAIR principles and the CARE principles

## 12) GitHub Features and Security

- Use the issue templates for a new exercise proposal.
- Keep GitHub Security Alerts and Dependabot updates active.
- Keep `SECURITY.md` current.
- Keep branch protection active on `main`.

## 13) Website Publishing

- In repository Settings, open Pages.
  - Set Source to "Deploy from a branch".
  - Set Branch to `gh-pages` and the folder to `/ (root)`.
- Run the production commands outside an agent session, unless the maintainer authorizes them.
  - `quarto render`
  - `quarto publish gh-pages`

## 14) Commands Recap

| Command                   | Purpose                                                          |
| ------------------------- | ---------------------------------------------------------------- |
| `quarto preview`          | Live preview with reload. This is the only check of the content. |
| `npm run check`           | Verify formatting. This skips all `.qmd` files.                  |
| `npm run format`          | Apply Prettier formatting and tidy the bibliography              |
| `npm run commit`          | Conventional Commits wizard                                      |
| `npm run changelog`       | Generate the changelog from the commits                          |
| `npm run prepare`         | Set up the Husky git hooks                                       |
| `quarto render`           | Production render. Avoid in an agent session.                    |
| `quarto publish gh-pages` | Production publish. Avoid in an agent session.                   |

## 15) Verification Checklist

Check this list before you finish a change.

- [ ] `npm run format` ran without an error.
- [ ] `quarto preview` renders the changed pages without an error.
- [ ] The three languages have the same structure.
- [ ] Each exercise carries exactly one category from the table in section 4.
- [ ] Each exercise carries `difficulty` and `time_estimate`.
- [ ] `date-modified` holds a real date in every changed file.
- [ ] No AI product, vendor, or model is named.
- [ ] The audit trail is named KI-Protokoll.
- [ ] Every callout uses one of the five valid types.
- [ ] Every new term has a glossary entry.
- [ ] The bibliography entries are complete, and every citation resolves.
- [ ] Every link works, and every image has alt text.

## 16) Common Tasks

### Add a New Exercise

Use the Setup New Exercise skill.

1. Choose the topic and a unique slug.
2. Write the full German file in `de/exercises/`.
3. Create a stub in `en/exercises/` and in `fr/exercises/`.
4. Add the citations to `bibliography.bib`.
5. Add every new term to `de/glossary.qmd`.
6. Check the result with `quarto preview`.

### Update Existing Content

1. Change the German file.
2. Set `date-modified` to the current date.
3. Use the Translation skill for the English file and the French file, or open an issue with the label `translation-needed`.
4. Check the result with `quarto preview`.
5. Run `npm run format`, then commit.

### Maintain the Bibliography

1. Search for duplicate entries.
2. Apply the formatting rules in section 6.
3. Verify that each DOI resolves.
4. Use descriptive citation keys.
5. Keep every entry relevant to AI literacy in historical research.

**Principle**: keep the content accessible, multilingual, and high in quality. Follow the FAIR principles. Keep the three languages consistent, and respect the differences between them.
