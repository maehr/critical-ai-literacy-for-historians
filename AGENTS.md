# AGENTS Guidelines for Critical AI Literacy for Historians

This repository provides multilingual educational exercises for developing critical AI literacy in historical research. These guidelines apply when interacting with the repository using AI agents (e.g., Copilot, Cursor, or other AI tools).

## 1) Use Preview Mode During Interactive Sessions

- **Always run `quarto preview`** while iterating on documentation. Live reload works for `.qmd`, `.md`, and asset files.
- **Do not run production commands inside agent sessions** unless explicitly requested by the human maintainer:
  - Avoid: `quarto render`, `quarto publish gh-pages`
- Keep the preview server running while editing to verify changes in real-time.

## 2) Available Skills

The following agent skills are available in `.agent/skills` to automate common tasks. **Always check these skills before performing manual work.**

- **Bibliography Management**: Managing citations and format conversion (`.agent/skills/bibliography/SKILL.md`)
- **Glossary Creation**: Guidelines for creating and maintaining glossaries (`.agent/skills/glossary/SKILL.md`)
- **Setup New Exercise**: Creating new exercises with correct structure and metadata (`.agent/skills/new_exercise/SKILL.md`)
- **Sync Exercises**: Audit and sync missing files across languages (`.agent/skills/sync_exercises/SKILL.md`)
- **Translation**: Translating content between EN/DE/FR (`.agent/skills/translation/SKILL.md`)
- **Validate Scientific Backing**: Ensure exercises are supported by quality literature (`.agent/skills/validate_backing/SKILL.md`)

## 3) Multilingual Content Management

This repository maintains content in three languages: English (en/), German (de/), and French (fr/).

### Translation Workflow

- **Manual Translations**: All translations should be done manually by qualified translators or native speakers to ensure accuracy and cultural appropriateness.
- **Keeping Translations in Sync**: When updating content:
  1. Make changes to the English version first (en/)
  2. Mark the corresponding German and French files as needing translation
  3. Create an issue using the label `translation-needed` to track translation work
  4. Ensure all three language versions have parallel content structure

### Content Parity

- Each language directory should have identical file structure
- Exercise numbering and naming should be consistent across languages
- When adding new exercises, create placeholder files in all three languages

## 4) Exercise Metadata Standards

### Categories

Exercises must use **exactly one** of these categories (based on the German structure, adapted for other languages):

- **KI & Digitale Methoden** (AI & Digital Methods / IA & Méthodes numériques)
- **Quellen** (Sources)
- **Methoden** (Methods / Méthodes)
- **Public History**

### Tags

Use descriptive tags that characterize the exercise. **Choose 2-4 tags**.
Examples (not exhaustive): `Prompting`, `Toolkritik`, `Reproduzierbarkeit`, `Ethics`, `Source Criticism`, `Data Literacy`.

### Required YAML Front Matter

Every exercise must include:

```yaml
lang: en # or de, fr
title: 'Exercise Title'
description: 'Brief description'
author:
  - name: 'Author Name'
    affiliation: 'Institution'
date: 'YYYY-MM-DD'
date-modified: 'YYYY-MM-DD'
categories: [Category] # ONE category only
tags: [Tag1, Tag2, Tag3] # 2-4 tags
difficulty: 'Beginner' # or Intermediate, Advanced
time_estimate: '45 minutes'
draft: false
```

## 5) Citations and Bibliography

### bibliography.bib Standards

- Use consistent BibTeX formatting
- Include DOI when available
- Use descriptive citation keys: `authorYEARkeyword` format (e.g., `russell2020artificial`)
- Required fields for articles: `author`, `title`, `journal`, `year`, `volume`, `pages`, `doi`
- Required fields for books: `author`, `title`, `publisher`, `year`, `isbn`

### Citing in Exercises

- Use `[@citationkey]` for inline citations
- Reference the `bibliography.bib` file in `_metadata.yml` for each language
- Ensure all cited works are relevant to AI literacy and historical research

## 6) Repository Structure

This is an educational content repository with the following structure:

```
critical-ai-literacy-for-historians/
├── en/               # English content
│   ├── index.qmd
│   ├── about.qmd
│   └── exercises/
├── de/               # German content
│   ├── index.qmd
│   ├── about.qmd
│   └── exercises/
├── fr/               # French content
│   ├── index.qmd
│   ├── about.qmd
│   └── exercises/
├── assets/           # Shared images and fonts
└── bibliography.bib  # Shared citations
```

## 7) Formatting and Linting

- Run **`npm run format`** before commits to enforce Prettier formatting
- Use **`npm run check`** to verify formatting without writing changes
- All `.qmd`, `.md`, `.yml`, and `.json` files should be formatted with Prettier

## 8) Commits and Changelog

- Use **`npm run commit`** to follow Conventional Commits standard
- After committing, generate entries with **`npm run changelog`** and update `CHANGELOG.md`
- Use conventional commit types: `feat`, `fix`, `docs`, `chore`, `refactor`

## 9) Documentation Practices

- Use `.qmd` (Quarto Markdown) for all educational content
- Include valid YAML front matter in all `.qmd` files
- Write in clear, accessible academic language
- Include learning objectives, activities, and reflection prompts in exercises
- Link to relevant resources and further reading

## 10) Content Quality Standards

### Exercise Structure & Development

Each exercise follows a strict pedagogical structure. See `de/exercises/prompt-engineering.qmd` or `de/exercises/quellenkritik-bundesrat-europarat-1949.qmd` for reference.

**Standard Sections:**

1. **Overview and Didactic Goal** (`## Überblick und didaktisches Ziel`)
   - Context of the exercise.
   - Specific competencies being trained.
2. **Prerequisites** (`## Voraussetzungen`)
   - Required methodological knowledge.
   - Technical requirements (Internet access, specific tools).
3. **Learning Objectives** (`## Lernziele`)
   - Bullet points describing what students will be able to do.
4. **Step-by-Step Sections** (Numbered, e.g., `## 1. Orientierung...`)
   - **Goal** (`### Ziel`): What is achieved in this step?
   - **Task** (`### Aufgabe`): Concrete manual task for the student.
   - **AI Task** (`### Aufgabe ... mittels KI`): The specific prompt or workflow to test with an agent.
   - **Reflection/Work Assignment** (`### Arbeitsauftrag (Reflexion)`): Critical comparison of AI output vs. manual work, or reflection on the process.
5. **Deliverables/Learning Outcome** (`## Lernergebnis`)
   - What the student takes away (artifacts, protocols, insights).
6. **Bibliography** (`## Bibliographie`)

### Pedagogical Principles

Exercises should promote:

- Critical thinking about AI as tool and method
- Digital source criticism skills
- Ethical awareness (bias, privacy, representation)
- Transparency and reproducibility in research
- FAIR and CARE principles

## 11) GitHub Features and Security

- Use **issue templates** for new exercise proposals
- Enable **GitHub Security Alerts** and Dependabot updates
- Keep `SECURITY.md` current with reporting procedures
- Use branch protection on `main` branch

## 12) Website Publishing

- In repo **Settings → Pages**:
  - Source: **Deploy from a branch**
  - Branch: **`gh-pages`**, folder: **`/ (root)`**
- **Production commands** (run _outside_ agent sessions unless explicitly authorized):
  - `quarto render`
  - `quarto publish gh-pages`

## 13) Commands Recap

| Command                   | Purpose                                          |
| ------------------------- | ------------------------------------------------ |
| `quarto preview`          | Live preview with reload                         |
| `npm run check`           | Verify formatting                                |
| `npm run format`          | Apply Prettier formatting                        |
| `npm run commit`          | Conventional Commits wizard                      |
| `npm run changelog`       | Generate changelog from commits                  |
| `npm run prepare`         | Setup Husky git hooks                            |
| `quarto render`           | **Production render** (avoid in agent sessions)  |
| `quarto publish gh-pages` | **Production publish** (avoid in agent sessions) |

## 14) Verification Checklist

Before finalizing changes:

- [ ] All files formatted with `npm run check`
- [ ] `quarto preview` renders without errors
- [ ] All three languages have parallel content structure
- [ ] Exercise metadata follows standards (correct categories/tags)
- [ ] Bibliography entries are properly formatted
- [ ] All citations are valid and referenced
- [ ] Links work correctly
- [ ] Images have alt text
- [ ] YAML front matter is valid

## 15) Common Tasks

### Adding a New Exercise

**Use the `Setup New Exercise` skill.**

1. Determining topic and creating a unique slug.
2. Creating the **primary draft** file (full content).
3. Creating **stubs** in the other two languages (parity).
4. Adding citations to `bibliography.bib` if needed.
5. Previewing with `quarto preview`.

### Updating Existing Content

1. Make changes to content.
2. Update `date-modified` in YAML front matter.
3. If adding entirely new sections, use the `Translation` skill to update the other languages.
4. Preview changes with `quarto preview`.
5. Format and commit.

### Maintaining Bibliography

1. Check for duplicate entries.
2. Ensure consistent formatting.
3. Verify DOIs are valid and accessible.
4. Use descriptive citation keys.
5. Keep entries relevant to AI literacy in historical research.

**Principle**: Maintain high-quality, accessible, multilingual educational content following FAIR principles. Ensure consistency across languages while respecting cultural and linguistic differences.
