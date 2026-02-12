---
name: Translation
description: Guidelines for translating content between English, German, and French, ensuring parallel structure and metadata synchronization.
---

# Translation Skill

This skill provides instructions for translating content in the `critical-ai-literacy-for-historians` repository.

## 1. Scenarios

### A. New Exercise Translation (1 to 2)

- **Input**: One complete exercise file (e.g., `de/exercises/ex1.qmd`) and two stubs/missing files.
- **Goal**: Create full translations in the other two languages.
- **Process**:
  1. Read the distinct source file.
  2. Translate Title, Description, and Tags (map categories strict).
  3. Translate body content (Sections, text).
  4. **Resource Localization**: Check if referenced resources (books, websites, datasets) are available in the target language.
     - If not available, flag them (e.g., `(GERMAN only)`).
     - Propose/Search for localized alternatives if possible.
  5. **Preserve**: YAML keys (`lang`, `date`), Code blocks, Citation keys `[@ref]`.
  6. **Internal Link Structure**: When encountering internal links like `[Label](file.qmd)`, ensure they point to the correct translated filename (e.g., `[Label](translated-file.qmd)`).
  7. **Translation Disclaimer**: Add a standard disclaimer at the beginning of the content (after YAML) with the correct relative path to the original source.
     - Template (EN target):

       ```markdown
       ::: callout-warning

       ## Automated Translation

       This exercise was automatically translated from the [German original](../../de/exercises/source-file.qmd) and may contain errors. Please consult the original version when in doubt.
       :::
       ```

### B. Sync Update

- **Input**: Source file has changed, target files are outdated.
- **Goal**: Update targets to match source changes, including ensuring resource localization consistency.

## 2. Metadata Translation Guide

- **Categories**: Map strictly.
  - `AI Literacy` <-> `KI-Kompetenz` <-> `Littératie IA`
  - `Source Criticism` <-> `Quellenkritik` <-> `Critique des sources`
  - `Ethics` <-> `Ethik` <-> `Éthique`
  - `Methods` <-> `Methoden` <-> `Méthodes`
  - `Public History` (Keep as is)
- **Tags**: Translate descriptive tags.
  - e.g., `Prompting` (keep), `Bias` -> `Biais`, `Privacy` -> `Datenschutz`.

## 3. Workflow Steps

1. **Read Source**: Read the full content of the source file.
2. **Generate Translation**: Create the target file content.
   - Ensure `lang: xx` is correct in YAML.
   - Do not translate `date` or `id`.
   - Keep structure (Section levels `##`) identical.
3. **Write/Update**: Overwrite the stub or outdated file.

## 4. Quality Check

- Do all three files have the same number of sections?
- Are citations identical?
- Is the YAML valid?
