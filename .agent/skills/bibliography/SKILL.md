---
name: Bibliography Management
description: Instructions for managing the bibliography and converting formats.
---

# Bibliography Management Skill

This skill handles citation management and format conversion.

## 1. Primary Source

- **File**: `bibliography.bib` (BibTeX format) is the master source for citations.

## 2. Citation Keys

- **Format**: `authorYEARkeyword` (lowercase).
  - Example: `mitchell2019artificial`, `bolukbasi2016debiasing`.
- **Unique**: Ensure keys are unique.

## 3. Conversion (BibTeX <-> CSL YAML)

To convert between BibTeX and CSL YAML (often used in Quarto frontmatter):

- **Use Pandoc** (if more than 10 citations) or `quarto pandoc`:
  - `quarto pandoc bibliography.bib -t csljson -o bibliography.json`
  - `quarto pandoc bibliography.bib -t markdown -o bibliography.md`
- **Manual**: If a specific CSL YAML file is needed (e.g., `references.yml`), manual entry might be required if automated tools aren't configured.

## 4. Maintenance

- **Review**: Periodically check that all entries in `bibliography.bib` are cited in at least one exercise.
- **DOIs**: Ensure DOIs are present for all journal articles and books where available.
- **Localization**: When adding or updating entries, check for available translations or language-specific editions. Prefer multilingual sources when possible.
