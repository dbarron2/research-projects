# Research Projects

This repository contains project descriptions submitted by PIs (principal
investigators) for use with the [AI Research Coach](https://airesearchcoach.org).
Each project is a directory under `projects/` with a `project.md` file.

---

## For PIs: How to submit a project

1. **Fork this repository** on GitHub.
2. **Create a directory** under `projects/` named with your project's slug
   (see slug rules below).
3. **Add a `project.md`** file in that directory following the schema below.
4. **Open a pull request** against `main`. A maintainer will review and merge it.

Once merged, the project will appear in the app's project picker automatically.

---

## Slug rules

A slug is the directory name and the identifier used throughout the system.

- Lowercase letters, digits, and hyphens only
- No spaces or underscores
- 1–64 characters
- Examples: `rna-folding-dynamics`, `galaxy-morphology-cnn`, `climate-downscaling`

---

## Folder layout

```
projects/
  <slug>/
    project.md      ← required
    resources.md    ← optional: freeform reading list, links, notes for the student
    materials/      ← optional: supplementary files, PDFs, data samples
```

---

## `project.md` schema

```yaml
---
title: "Human-readable project title"
pi: "pi-github-username"
description: |
  One or more paragraphs describing the project for a prospective student.
  This is what the student reads when choosing a project. Be concrete about
  what the student will actually do.
materials:
  - "https://arxiv.org/abs/..."       # links to papers, datasets, etc.
  - "A textbook or chapter reference"
goals:
  - "Understand X at a working level"
  - "Reproduce result Y from the paper"
  - "Extend the approach to Z"
---
```

All fields except `materials` and `goals` are required. The `description` field
supports multi-line text; indent continuation lines by two spaces.

### `resources.md` (optional)

If the project has a richer set of references than fits naturally in the
`materials` list, you may add a freeform `resources.md` alongside `project.md`.
This file has no required structure — use any Markdown you like: sections,
bullet lists, tables, annotated bibliographies. It is displayed to the student
alongside the main project description.

Use `resources.md` for:
- Annotated reading lists that benefit from a sentence or two of context per item
- Multiple categories of references (background, primary papers, tools, datasets)
- Links that are useful but too peripheral for the short `materials` list

---

## PR workflow

- PRs are reviewed by a maintainer for completeness and basic quality.
- The slug must not conflict with an existing project directory.
- Once merged to `main`, the project is live immediately.
- To update a project, open a new PR editing the relevant `project.md`.
- To retire a project, open a PR removing the directory and note the reason
  in the PR description.
