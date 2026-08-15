---
name: Translation
description: Guidelines for translating content from German into English and French, with parallel structure and synchronized metadata.
---

# Translation Skill

This skill gives the instructions to translate content in the `critical-ai-literacy-for-historians` repository.

German leads. `de/` is the reference version. Translate from German into English and into French. Do not translate in the other direction.

`AGENTS.md` is the contract. If this skill contradicts `AGENTS.md`, follow `AGENTS.md`.

## 1. Scenarios

### A. New Exercise Translation

- Input: one complete German file, for example `de/exercises/schreiben.qmd`, and two stubs.
- Goal: create the full English version and the full French version.
- Process:
  1. Read the German file.
  2. Translate the title, the subtitle, the description, and the tags. Map the category with the table in section 2.
  3. Translate the body text and keep the section levels.
  4. Check whether each referenced resource exists in the target language. If it does not exist, flag it with `(GERMAN only)`. Propose a localized alternative when one exists.
  5. Keep these items unchanged: the YAML keys, the `date` value, the code blocks, and the citation keys `[@ref]`.
  6. Point an internal link at the translated file in the same language directory.
  7. Add the automated-translation callout after the front matter, with the correct relative path to the German original.

     ```markdown
     ::: callout-warning

     ## Automated Translation

     This exercise was translated automatically from the [German original](../../de/exercises/source-file.qmd) and can contain errors. Consult the original version in case of doubt.
     :::
     ```

### B. Sync Update

- Input: the German file changed, and the two translations are outdated.
- Goal: apply the same change to the English file and to the French file.

## 2. Metadata Translation Guide

Map the category strictly. These four categories are the complete list.

| German                 | English              | French                   |
| ---------------------- | -------------------- | ------------------------ |
| KI & Digitale Methoden | AI & Digital Methods | IA & Méthodes numériques |
| Quellen                | Sources              | Sources                  |
| Methoden               | Methods              | Méthodes                 |
| Public History         | Public History       | Public History           |

Do not invent a category. Ethics is a tag, and not a category.

Translate the tags, for example `Quellenkritik` to `Source Criticism` and to `Critique des sources`. Keep a tag that has no translation, for example `Prompting`.

Do not translate these field values, because they are machine values:

- `difficulty`: `Beginner`, `Intermediate`, or `Advanced`
- `time_estimate`: for example `'60 min'` or `'2 d'`

## 3. Terminology

- Do not name an AI product, an AI vendor, or a model. Describe the capability that the tool needs.
- The German term for the audit trail is KI-Protokoll. Use one term in each target language. Use "AI log" in English and "journal IA" in French. Name the German term once in each translated file.
- Use only the five Quarto callout types: `note`, `tip`, `important`, `caution`, and `warning`.
- Caution: `callout-info` is not a valid type. Quarto renders such a block without a title bar.
- The glossary is `de/glossary.qmd`. Point a glossary link at the translated glossary of the same language.

## 4. Workflow Steps

1. Read the complete German file.
2. Write the target file.
   - Set `lang` to `en` or to `fr`.
   - Keep the section levels identical.
   - Set `date-modified` to the current date.
3. Overwrite the stub or the outdated file.

## 5. Quality Check

- Do the three files have the same number of sections?
- Are the citations identical?
- Is the YAML valid?
- Does the category match the table in section 2?
- Check the result with `quarto preview`. `npm run check` does not read `.qmd` files.
