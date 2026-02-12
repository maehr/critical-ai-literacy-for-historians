---
name: Validate Scientific Backing
description: Check if an exercise has enough and good enough scientific backing (literature and citations).
---

# Validate Scientific Backing Skill

Use this skill to ensure exercises are grounded in scholarly literature and maintain academic integrity.

## 1. Evaluation Criteria

### A. Quantity (Enough Backing)

- **Minimum**: 3-5 high-quality sources per exercise.
- **Scope**: Must cover BOTH the historical topic/method AND the AI tool/method being used.
- **Localization**: Referenced resources should ideally be available in the language of the exercise. If they are not (e.g., source is in German but exercise is in English), they must be flagged (e.g., `(GERMAN only)`).
- **Citations**: Every source listed must be cited at least once in the text using `[@id]` syntax.

### B. Quality (Good Enough Backing)

- **Preferred Sources**: Peer-reviewed journal articles, scholarly books, or chapters from academic publishers.
- **Technical Documentation**: For AI tools, authoritative documentation (e.g., OpenAI, Anthropic, Meta) or foundational technical papers (e.g., "Attention Is All You Need") are acceptable for technical specifics.
- **Recency**: AI-related sources should ideally be from the last 2-3 years, unless they are foundational.
- **Relevance**: Sources must directly support the claims or methods described in the exercise steps.

## 2. Workflow

1. **Audit Bibliography**:
   - Check the YAML front matter for a `references:` field (inline bibliography).
   - Check the end of the document for a `## Bibliographie` or `## Referenzen` section.
2. **Verify Citations**:
   - Search the document for `[@` to find all citations.
   - Cross-reference these with the bibliography items.
3. **Assess Content**:
   - Read the titles and descriptions of sources to judge their scientific nature.
   - Check if the exercise reflects the complexity and critical perspective of the cited literature.
4. **Identify Gaps**:
   - Is there a source for the historical method?
   - Is there a source for the AI prompting/tool usage?
   - Are any "common knowledge" claims about AI unbacked?

## 3. Reporting

Provide the user with:

- A list of cited sources.
- A status (e.g., "Strongly Backed", "Needs More Sources", "Requires Better Quality").
- Specific recommendations for improvement (e.g., "Add a citation for the concept of 'Heuristic'").
