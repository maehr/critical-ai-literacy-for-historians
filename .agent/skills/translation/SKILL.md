---
name: Translation
description: Guidelines for translating content from German into English and French, with parallel structure and synchronized metadata.
---

# Translation Skill

German leads. `de/` is the reference version. Translate from German into English and into French. Do not translate in the other direction.

`AGENTS.md` is the contract. If this skill contradicts `AGENTS.md`, follow `AGENTS.md`.

## 1. Scenarios

- New exercise: one complete German file and two stubs exist. Create the full English version and the full French version.
- Sync update: the German file changed. Apply the same change to the English file and to the French file.

## 2. Process

1. Read the complete German file.
2. Translate the title, the subtitle, the description, and the tags. Keep a tag that has no translation, for example `Prompting`.
3. Map the category with the table in `AGENTS.md` section 4. Do not invent a category. Ethics is a tag, and not a category.
4. Translate the body text and keep the section levels identical.
5. Check whether each referenced resource exists in the target language. If it does not exist, flag it with `(GERMAN only)`. Propose a localized alternative when one exists.
6. Keep these items unchanged: the YAML keys, the `date` value, the code blocks, and the citation keys `[@ref]`.
7. Set `lang` to `en` or to `fr`, and set `date-modified` to the current date.
8. Point an internal link at the translated file in the same language directory.
9. Add the callout below after the front matter, with the correct relative path to the German original.
10. Overwrite the stub or the outdated file.

```markdown
::: callout-warning

## Automated Translation

This exercise was translated automatically from the [German original](../../de/exercises/source-file.qmd) and can contain errors. Consult the original version in case of doubt.
:::
```

Do not translate these field values, because they are machine values:

- `difficulty`: `Beginner`, `Intermediate`, or `Advanced`
- `time_estimate`: for example `'60 min'` or `'2 d'`

## 3. Terminology

- Do not name an AI product, an AI vendor, or a model. Describe the capability that the tool needs.
- The German term for the audit trail is KI-Protokoll. Use "AI log" in English and "journal IA" in French. Name the German term once in each translated file.
- Caution: `callout-info` is not valid. Use only `note`, `tip`, `important`, `caution`, and `warning`.
- The glossary is `de/glossary.qmd`. Point a glossary link at the translated glossary of the same language.

## 4. Quality Check

- Do the three files have the same number of sections?
- Are the citations identical, and is the YAML valid?
- Does the category match the table in `AGENTS.md` section 4?
- Check the result with `quarto preview`. `npm run check` does not read `.qmd` files.
