---
name: Sync Exercises
description: Audit the repository to ensure all exercises exist in all three languages (EN, DE, FR) and are in sync.
---

# Sync Exercises Skill

Use this skill to check for missing files or synchronization issues between languages.

## 1. Audit Process

1. **List Files**: Get a list of all exercise files in each language directory:
   - `en/exercises/`
   - `de/exercises/`
   - `fr/exercises/`
2. **Compare**: Create a matrix of existences.
   - Does `exercise-A` exist in EN? DE? FR?

## 2. Identify Issues

- **Missing Stub**: File exists in 1 language, missing in 2.
- **Partial Translation**: File exists in 2 languages, missing in 1.
- **Content Drift**: Files exist in all 3, but timestamps/versions differ significantly (optional advanced check).

## 3. Sync Actions

For each missing file:

1. **If it's a new exercise (1 language only)**:
   - Create **Stubs** in the missing languages (see `New Exercise` skill).
   - OR use `Translation` skill to generate full content immediately.

2. **If it's a missing translation**:
   - Use `Translation` skill to generate the file from the existing source.

## 4. Reporting

- Provide a summary of missing files to the user.
- Ask for confirmation before creating/translating multiple files.
