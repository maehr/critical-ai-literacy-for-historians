# Contributing

Thank you for your interest in this course. This file tells you what you need in order to change the
content, and which rules a pull request must follow.

Read [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) first. It applies to every interaction in this project.

`AGENTS.md` is the full contract for this repository. This file summarizes the parts that a human
contributor needs. If the two files disagree, follow `AGENTS.md` and report the contradiction in an issue.

## What this project is

The repository holds a Quarto website with exercises on critical AI literacy for historians. The content
lives in `.qmd` files. There is no Python code, no R code, and no container to build.

## Tools you need

- [Quarto](https://quarto.org/docs/get-started/), version 1.6 or later
- [Node.js](https://nodejs.org/en/download/), version 20 or later

GitHub Codespaces installs both for you. See the section "For Contributors" in
[README.md](https://github.com/maehr/critical-ai-literacy-for-historians#for-contributors-setup-with-github-codespaces).

For a local setup, run these commands once:

```bash
npm install
npm run prepare
```

`npm run prepare` installs the Husky git hooks. The pre-commit hook runs `npm run check`.

## The three languages, and why German leads

The content exists in German (`de/`), English (`en/`), and French (`fr/`).

German is the reference version, because the course addresses German-speaking historians. Follow this
order:

1. Write the change in the German file.
2. Translate the change into the English file and the French file.
3. If you cannot translate, open an issue with the label `translation-needed` for each missing
   translation.

Caution: do not add new substance to `en/` or `fr/`. The two versions then drift from the reference
version.

Keep the file structure, the exercise order, and the slug identical in all three languages. When you add an
exercise, create a stub file in the other two languages.

## How an exercise is built

Each exercise follows a fixed structure. Use `de/exercises/prompt-engineering.qmd` as the model.

1. `## Überblick und didaktisches Ziel`: give the context, and name the competencies.
2. `## Was Sie brauchen`: give the duration, the core path, the optional steps, the hand-in minimum, the
   prior knowledge, and the capabilities that the tool needs.
3. `## Lernziele`: list what the learner can do after the exercise.
4. Numbered steps, for example `## 1. Orientierung`. Each step holds four parts: `### Ziel`,
   `### Aufgabe`, `### Aufgabe ... mittels KI`, and `### Arbeitsauftrag (Reflexion)`.
5. `## Lernergebnis`: list the artifacts, the protocols, and the insights.
6. `## Bibliographie`

## The metadata standard

Every exercise carries YAML front matter. The order of the fields is free.

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
categories: [Quellen] # exactly one category, see the table below
image: ../../assets/images/example.png
tags:
  - Tag1
  - Tag2
  - Tag3
difficulty: Beginner # Beginner, Intermediate, or Advanced
time_estimate: '60 min'
draft: false
```

The example above shows single quotes, because Prettier formats a YAML block inside a Markdown file. In a
real `.qmd` file, use double quotes, as every exercise does. Prettier does not change the front matter of a
`.qmd` file.

`difficulty` and `time_estimate` are required, because `README.md` promises both to the learner.

- `difficulty` takes `Beginner`, `Intermediate`, or `Advanced`. The value stays in English in all three
  languages, because it is a machine value.
- `time_estimate` takes a quoted number and a unit. Use `min` for minutes and `d` for days. Examples are
  `60 min`, `45-60 min`, and `2 d`. State the honest time for the complete exercise.

An exercise carries exactly one category. The table below is the complete list. Use the label of the
language of the file.

| German                 | English              | French                   |
| ---------------------- | -------------------- | ------------------------ |
| KI & Digitale Methoden | AI & Digital Methods | IA & Méthodes numériques |
| Quellen                | Sources              | Sources                  |
| Methoden               | Methods              | Méthodes                 |
| Public History         | Public History       | Public History           |

Ethics is not a category, because ethical awareness applies to every exercise. Use the tag `Ethik`,
`Ethics`, or `Éthique` instead.

## The three protocols

The course documents three different things. Each one has one name, and each one has an entry in
`de/glossary.qmd`. Link the entry on first use in a file.

| Name                   | What the learner records                                                             |
| ---------------------- | ------------------------------------------------------------------------------------ |
| **KI-Protokoll**       | AI use: material, prompt, answer, checks, and decision                               |
| **Rechercheprotokoll** | Searching: date, system, query, filters, hits, and selection rules                   |
| **Analyseprotokoll**   | One source: citation, access date, display form, and external and internal criticism |

Do not invent a fourth name, and do not use an old one. `AGENTS.md` section 5 lists the names that this
project rejected.

## Name a capability, never a product

Never name an AI product, an AI vendor, or a model. Describe what the tool must be able to do instead, for
example "a KI-System that can read a PDF file". The rule covers the exercise text, the prerequisites, and
the links, so cite a neutral source instead of vendor documentation.

One exception applies. A citation keeps the published title of a work, because you must not rename a
published work. The rule still applies to your own prose about that work.

## How to propose an exercise

1. Open an issue with the
   [exercise proposal template](https://github.com/maehr/critical-ai-literacy-for-historians/issues/new?template=exercise_proposal.yml).
2. Wait for the maintainer to accept the proposal. The maintainer checks the fit with the four categories
   and with the exercises that exist.
3. Write the German file, then the two stubs, then the translations.
4. Add every new citation to `bibliography.bib`. Use the key format `authorYEARkeyword`, and add the DOI
   when one exists.
5. Open a pull request that refers to the issue.

Discuss a large change in an issue before you write it.

## Before you open a pull request

Run these commands:

```bash
npm run format   # applies Prettier and tidies the bibliography
npm run check    # verifies the formatting, .qmd files include
quarto preview   # renders the changed pages
```

Prettier reads `.qmd` files. The pre-commit hook and the CI lint job both run `npm run check`, and a
failure blocks the deploy. Run `npm run format` after you edit content, or the commit fails.

Caution: put a blank line before a closing `:::` fence. Without the blank line, Prettier indents the fence
into the list above it.

Check this list as well:

- [ ] The three languages hold the same structure.
- [ ] `date-modified` holds a real date in every file that you changed.
- [ ] The front matter carries one category, `difficulty`, and `time_estimate`.
- [ ] No AI product, vendor, or model is named outside a citation title.
- [ ] Every callout uses one of the five Quarto types: `note`, `tip`, `important`, `caution`, `warning`.
- [ ] Every new term has a glossary entry, and the first use links to it.
- [ ] Every link works, and every image has alt text.

Use `npm run commit` for the commit message. The wizard writes
[Conventional Commits](https://www.conventionalcommits.org/). Use the types `feat`, `fix`, `docs`, `chore`,
and `refactor`.

## Review

The maintainer reviews every pull request. A pull request needs one approval before it merges. GitHub
Actions runs the lint job, the render, and the dead link check on every pull request. All three must pass.
