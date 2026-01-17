---
name: Setup New Exercise
description: Step-by-step guide to creating a new exercise in all three languages, ensuring correct metadata and structure.
---

# Setup New Exercise Skill

Use this skill when the user asks to "create a new exercise" or "add a module".

## 1. Preparation

- **Determine Topic**: Choose a unique slug (e.g., `exercise-bias-in-ocr`).
- **Select Metadata**:
  - **Category**: Pick ONE from `AI Literacy`, `Source Criticism`, `Ethics`, `Methods`.
  - **Tags**: Pick 2-4 from approved list.
  - **Difficulty**: `Beginner`, `Intermediate`, or `Advanced`.

## 2. File Creation

Create three files simultaneously:

1. `en/exercises/SLUG.qmd`
2. `de/exercises/SLUG.qmd`
3. `fr/exercises/SLUG.qmd`

## 3. Template

Use this template for each file:

```yaml
---
lang: [en|de|fr]
title: "Title in Language"
description: "Description in Language"
author:
  - name: "Your Name"
    affiliation: "Institution"
date: "YYYY-MM-DD"
date-modified: "YYYY-MM-DD"
categories: [CategoryInLanguage]
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

[Activity steps]

## Reflection

*   Question 1

## References

::: {#refs}
:::
```

## 4. Registering

- Add the new exercise to the appropriate listing or index page if manual addition is required (usually Quarto handles listings automatically).
