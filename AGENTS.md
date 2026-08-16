# AGENTS Guidelines for Critical AI Literacy for Historians

This repository holds multilingual educational exercises for critical AI literacy in historical research. This file is the contract for every agent that works here, and for every person who directs one. If another file contradicts this file, follow this file and report the contradiction.

## 1) Use Preview Mode During Interactive Sessions

- Run `quarto preview` while you edit content. Live reload works for `.qmd`, `.md`, and asset files.
- Keep the preview server active, because the preview is the only check of the content.
- Do not run `quarto render` or `quarto publish gh-pages` in an agent session. The maintainer must ask first.

## 2) Available Skills

The skills in `.agent/skills` automate common tasks. Read the skill before you do the work by hand.

- Bibliography Management: manage citations and convert formats (`.agent/skills/bibliography/SKILL.md`)
- Setup New Exercise: create an exercise with the correct structure and metadata (`.agent/skills/new_exercise/SKILL.md`)
- Sync Exercises: audit and sync missing files across the languages (`.agent/skills/sync_exercises/SKILL.md`)
- Translation: translate content from German into English and French (`.agent/skills/translation/SKILL.md`)
- Validate Scientific Backing: check that literature supports an exercise (`.agent/skills/validate_backing/SKILL.md`)

## 3) Multilingual Content Management

This repository holds content in German (`de/`), English (`en/`), and French (`fr/`).

### Translation Workflow

German leads. The audience is German-speaking historians. `de/` is the reference version, and `en/` and `fr/` follow it.

Caution: do not add new substance to `en/` or `fr/`. The two versions then drift from the reference version.

1. Write the change in the German file first.
2. Translate the change into English and French, or mark the two files as outdated.
3. Open an issue with the label `translation-needed` for each translation that you do not write.
4. Give a translated file the automated-translation callout from `.agent/skills/translation/SKILL.md`.

### Content Parity and Resource Localization

- Give each language directory the same file structure.
- Use the same exercise order and the same slug in all three languages.
- When you add an exercise, create a stub file in the other two languages.
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

Do not invent a category. This table is the only full copy. The dropdown in `.github/ISSUE_TEMPLATE/exercise_proposal.yml` repeats it, so change both files in the same pull request.

### Tags

Use descriptive tags that characterize the exercise. Three to five tags are recommended, and there is no upper limit. Translate a tag into the language of the file. Examples are `Prompting`, `Toolkritik`, `Reproduzierbarkeit`, `Ethik`, `Quellenkritik`, and `Datenkompetenz`.

### Difficulty and Time

Every exercise must carry a `difficulty` field and a `time_estimate` field, because `README.md` promises both to the learner.

- `difficulty` takes `Beginner`, `Intermediate`, or `Advanced`. These values stay in English in all three languages, because they are machine values and not learner text.
- `time_estimate` takes a quoted number and a unit: `min` for minutes, `d` for days. Examples are `'60 min'`, `'45-60 min'`, and `'2 d'`. State the honest time for the complete exercise, and write days for an exercise that needs archive visits.

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

- `author` takes a list. Each author takes an `affiliations` list. Do not write a scalar `affiliation`.
- `subtitle` and `image` are required, because every exercise carries them.
- `date-modified` takes a real date. Replace `today` with a real date in every file that you change.
- Use double quotes in the front matter of a `.qmd` file, as all 24 exercises do. Prettier never reads `.qmd` files, so no tool changes this style.

## 5) Terminology and Content Rules

**Never name an AI product.** Do not name an AI product, an AI vendor, or a model. Describe what the tool must be able to do, for example "a KI-System that can read a PDF file". This rule covers exercise text, prerequisites, and links, so cite a neutral source instead of vendor documentation.

**Three protocols, one name each.** The course documents three different things. Name each one exactly:

- **KI-Protokoll**: AI use, that is material, prompt, answer, checks and decision.
- **Rechercheprotokoll**: searching, that is date, system, query, filters, hits and selection rules. The sections _Schneeballverfahren_, _Entscheidungen_ and _Reject-Log_ belong inside it.
- **Analyseprotokoll**: one source, that is citation, access date, display form, and external and internal criticism.

Do not write Prompt-Protokoll, Audit Trail, Suchprotokoll, Snowball-Protokoll, Entscheidungslog, Prompt- und Entscheidungsprotokoll, Prompt- und Entscheidungsnachweis, KI-Reflexion or Prüfpfad. Each of the three has an entry in `de/glossary.qmd`. Link it on first use per file. In English and French, keep the German term once in each translated file.

**Glossary.** The course glossary is the content page `de/glossary.qmd`, and not a skill. It holds a short working definition of every term that an exercise uses without explanation. When you introduce a term, add the definition, then link to the anchor of the entry, for example `[Prompt](../glossary.qmd#gl-prompt)`.

**Callouts.** Quarto has five callout types: `note`, `tip`, `important`, `caution`, and `warning`. Caution: `callout-info` is not one of them. Quarto renders such a block as a plain division without a title bar and without a color.

**Language level.** Write short sentences for a reader who is not tech savvy. Define a term before you use it. State the workload of an exercise before the first step, and not in the hand-in section.

## 6) Citations and Bibliography

- Use consistent BibTeX formatting, and include the DOI when one exists.
- Use the citation key format `authorYEARkeyword`, for example `russell2020artificial`.
- Give an article these fields: `author`, `title`, `journal`, `year`, `volume`, `pages`, and `doi`.
- Give a book these fields: `author`, `title`, `publisher`, `year`, and `isbn`.
- Use `[@citationkey]` for an inline citation, and cite every work that the bibliography section lists.
- Reference `bibliography.bib` in the `_metadata.yml` file of each language.

## 7) Repository Structure

Each language directory holds `index.qmd` and `exercises/`. `de/` also holds `glossary.qmd`.

```
critical-ai-literacy-for-historians/
├── de/               # German content (reference version)
├── en/               # English content
├── fr/               # French content
├── assets/           # Shared images and fonts
└── bibliography.bib  # Shared citations
```

## 8) Formatting and Linting

Run `npm run format` before you commit. Run `npm run check` to verify the formatting without a change.

Caution: `npm run check` verifies none of the course content. Prettier has no parser for `.qmd`, so it skips all 30 content files. The `.husky/pre-commit` hook and the CI `lint` job run the same command and skip the same files. Verify content with `quarto preview`. Issue #26 tracks a fix.

Prettier formats `.md`, `.yml`, and `.json` files, and also a YAML code block inside a Markdown file. `.prettierrc` sets `singleQuote: true`, so every YAML example in this file and in the skills is single-quoted. Do not "correct" these examples to double quotes, because `npm run format` reverts the change. The rule for `.qmd` front matter is different. See section 4.

## 9) Commits and Changelog

- Use `npm run commit` for the Conventional Commits wizard.
- Run `npm run changelog` after a commit, then update `CHANGELOG.md`.
- Use these commit types: `feat`, `fix`, `docs`, `chore`, and `refactor`.

## 10) Documentation Practices

- Use `.qmd` for all educational content, with valid YAML front matter.
- Write clear academic language that a novice understands, and link to further reading.

## 11) Content Quality Standards

### Exercise Structure

Each exercise follows a fixed pedagogical structure. Use `de/exercises/prompt-engineering.qmd` or `de/exercises/quellenkritik-bundesrat-europarat-1949.qmd` as the reference.

1. `## Überblick und didaktisches Ziel`: give the context, and name the competencies that the exercise trains.
2. `## Was Sie brauchen`: name the duration, the core path, the optional steps, the hand-in minimum, the knowledge that the learner needs, and the capabilities that the tool needs. State the hand-in minimum here, not only in the hand-in section.
3. `## Lernziele`: list what the learner can do after the exercise.
4. Numbered steps, for example `## 1. Orientierung`, each with four parts:
   - `### Ziel`: state the result of the step.
   - `### Aufgabe`: give the manual task.
   - `### Aufgabe ... mittels KI`: give the prompt or the workflow to test.
   - `### Arbeitsauftrag (Reflexion)`: compare the AI output with the manual work.
5. `## Lernergebnis`: list the artifacts, the protocols, and the insights that the learner takes away.
6. `## Bibliographie`

### Pedagogical Principles

An exercise must promote:

- Critical thinking about AI as a tool and as a method
- Digital source criticism
- Ethical awareness of bias, privacy, and representation
- Transparency and reproducibility in research
- The FAIR principles and the CARE principles

## 12) GitHub Features and Security

- Use the issue templates for a new exercise proposal.
- Keep GitHub Security Alerts, Dependabot updates, and branch protection on `main` active.
- Keep `SECURITY.md` current.

## 13) Website Publishing

- In repository Settings, open Pages. Set Source to "Deploy from a branch", Branch to `gh-pages`, and the folder to `/ (root)`.
- Run `quarto render` and `quarto publish gh-pages` outside an agent session, unless the maintainer authorizes them.

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
- [ ] Each exercise carries one category from section 4, plus `difficulty` and `time_estimate`.
- [ ] `date-modified` holds a real date in every changed file.
- [ ] No AI product, vendor, or model is named, and each protocol uses its own name from section 5.
- [ ] Every callout uses one of the five valid types, and every new term has a glossary entry.
- [ ] The bibliography entries are complete, and every citation resolves.
- [ ] Every link works, and every image has alt text.

## 16) Common Tasks

### Add a New Exercise

Use the Setup New Exercise skill.

1. Choose the topic and a unique slug.
2. Write the full German file in `de/exercises/`, then create a stub in `en/exercises/` and in `fr/exercises/`.
3. Add the citations to `bibliography.bib`, and add every new term to `de/glossary.qmd`.
4. Check the result with `quarto preview`.

### Update Existing Content

1. Change the German file, and set `date-modified` to the current date.
2. Use the Translation skill for the English file and the French file, or open an issue with the label `translation-needed`.
3. Check the result with `quarto preview`.
4. Run `npm run format`, then commit.

### Maintain the Bibliography

Apply the rules in section 6. Search for duplicate entries, verify that each DOI resolves, and keep every entry relevant to AI literacy in historical research.
