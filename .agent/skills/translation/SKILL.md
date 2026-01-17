---
name: Translation
description: Guidelines for translating content between English, German, and French, ensuring parallel structure and metadata synchronization.
---

# Translation Skill

This skill provides instructions for translating content in the `critical-ai-literacy-for-historians` repository.

## 1. Translation Workflow

1. **Source of Truth**: The English version (`en/`) is the primary source. Changes should usually be made there first.
2. **Manual Translation**: Use manual translation or expert review. AI suggestions should be carefully vetted for cultural nuance and historical accuracy.
3. **Sync-Check**: Ensure content exists in all three language directories:
   - `en/path/to/file.qmd`
   - `de/path/to/file.qmd`
   - `fr/path/to/file.qmd`

## 2. File Parity

- **Structure**: Keep the directory structure identical across `en/`, `de/`, and `fr/`.
- **Filenames**: specific exercise files should have `en/exercises/exercise-SLUG.qmd` matching `de/exercises/exercise-SLUG.qmd`.

## 3. Metadata Translation

Translate user-facing metadata in the YAML frontmatter, but keep technical keys in English.

- **Translate**: `title`, `description`
- **Do NOT Translate**: `lang` (use standard codes: `en`, `de`, `fr`), `date`, `date-modified`
- **Categories**: map strict categories:
  - `AI Literacy` -> `KI-Kompetenz` -> `Littératie IA`
  - `Source Criticism` -> `Quellenkritik` -> `Critique des sources`
  - `Ethics` -> `Ethik` -> `Éthique`
  - `Methods` -> `Methoden` -> `Méthodes`
- **Tags**: Translate tags to the target language as defined in `AGENTS.md`.

## 4. Content Guidelines

- **Tone**: Academic but accessible.
- **Terminology**: careful consistency with historical research terms in the target language.
- **Citations**: Use the same citation keys `[@key]` from `bibliography.bib`.
