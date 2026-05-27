---
name: git-commit
description: 'Generate structured git commit messages from staged files. Use when: writing commit messages, committing code, preparing commits, git commit, describing changes.'
argument-hint: 'Optionally describe the intent or context of the changes'
---

# Git Commit Message Generator

## Commit Message Template

```
Subject line (max 80 chars)

Purpose/rationale/reason for this commit. Why is this change needed?

Detailed description of changes made.
file-name (just file name with extension, no path)
- Describe the change
```

## Procedure

1. **Gather changes**: Run `git diff --cached --stat` and `git diff --cached` to inspect staged changes. If nothing is staged warn the user.
   - for each files in staged changes, list the file path and a brief description of what changed (e.g., "added new function", "updated logic in existing function", "refactored code structure", "fixed bug in function X")

2. **Compose the subject line**:
   - Max 80 characters
   - Use imperative mood (e.g., "Add", "Fix", "Refactor", "Update", "Remove")
   - Summarize the overall change concisely
   - Do NOT end with a period

3. **Write the rationale paragraph**:
   - One short paragraph explaining **why** this change is needed
   - Focus on motivation, not mechanics

4. **List per-file changes**:
   - Group by file path
   - Under each file, add bullet points describing what changed (max 100 characters per bullet)
   - Keep descriptions concise but specific
   - Omit trivially obvious changes (e.g., "updated import" when adding a new function that requires it)

## Quality Checks
- Subject line is ≤ 80 characters
- Blank line separates subject from body
- Rationale answers "why", not "what"
- Every changed file is listed
- No trailing whitespace or periods on subject line

## Example Output

```
Add bike sharing demand prediction model

Implement regression model for bike rental demand prediction
as part of ML assignment 1 using training and test datasets.

assingment1/submition.ipynb
- Add data loading and preprocessing pipeline
- Implement feature engineering for datetime columns
- Train gradient boosting regressor
- Generate predictions on test set

assingment1/data/Submission.csv
- Add predicted demand values for test dataset
```