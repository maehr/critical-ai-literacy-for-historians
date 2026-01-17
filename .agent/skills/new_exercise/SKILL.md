---
name: Setup New Exercise
description: Create a new exercise in one primary language and generate stubs for the others.
---

# Setup New Exercise Skill

Use this skill when the user asks to "create a new exercise" or "add a module".

## 1. Preparation

- **Determine Topic**: Choose a unique slug (e.g., `exercise-bias-in-ocr`).
- **Select Primary Language**: Ask the user which language they want to draft in (`en`, `de`, or `fr`).
- **Select Metadata**:
  - **Category**: Pick ONE.
    - EN: `AI Literacy`, `Source Criticism`, `Ethics`, `Methods`
    - DE: `KI & Digitale Methoden`, `Quellen`, `Ethik`, `Methoden`
    - FR: `Littératie IA`, `Critique des sources`, `Éthique`, `Méthodes`
  - **Tags**: Pick 2-4.
- **Resource Localization**: Favor resources available in all three languages. If using language-specific resources, prepare to flag them or provide alternatives for the other language versions.

## 2. File Creation

Create three files: **one primary draft** and **two stubs**.

### A. Primary Draft (Full Template)

File: `[lang]/exercises/[slug].qmd`

```yaml
---
lang: [lang]
title: "Title"
description: "Description"
author:
  - name: "Your Name"
    affiliation: "Institution"
date: "today"
date-modified: "today"
categories: [Category]
tags: [Tag1, Tag2]
difficulty: [Difficulty]
time_estimate: "45 minutes"
draft: true
---

# Title

## Learning Objectives

*   Objective 1
*   Objective 2

## Introduction

[Content]

## Exercise

### Step 1

[Instructions]

### Step 2

[Instructions]

## Reflection

*   Question 1

## References

::: {#refs}
:::
```

### B. Language Stubs (Placeholders)

For the other two languages, create a file with minimal content to establish file parity.

File: `[other_lang]/exercises/[slug].qmd`

```yaml
---
lang: [other_lang]
title: "TRANSLATION NEEDED: [Original Title]"
description: "Translation needed"
draft: true
---

:::{.callout-warning}
# Translation Needed

This exercise is currently only available in [Primary Language].
:::
```

## 3. Next Steps

- Inform the user that the primary draft and stubs are created.
- Suggest running the **Translation** skill to generate the missing versions.
