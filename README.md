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
4. **Optionally add a `resources.md`** alongside `project.md` listing
   recommended reading and references.
5. **Open a pull request** against `main`. A maintainer will review and merge it.

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
    project.md      ← required: structured frontmatter + readable description
    resources.md    ← optional: recommended reading list and references
    materials/      ← optional: supplementary files, PDFs, data samples
```

---

## `project.md` schema

A `project.md` is a Markdown file with a small YAML frontmatter block followed
by the human-readable project description as the body of the file.

```markdown
---
title: "Human-readable project title"
pi: "pi-github-username"
goals:
  - "Understand X at a working level"
  - "Reproduce result Y from the paper"
  - "Extend the approach to Z"
---

# Project description

Write the project description as the body of this Markdown file. This is what
the student reads when choosing a project — and what the coach reads to
understand the project context.

Use whatever Markdown structure makes the description clear and readable:
sections, sub-headings, bullet lists, equations, links. Be concrete about what
the student will actually do and what a successful outcome looks like.
```

### Frontmatter fields

| Field   | Required | Notes |
|---------|----------|-------|
| `title` | yes      | Human-readable project title. |
| `pi`    | yes      | The PI's GitHub username (lowercase, no `@`). |
| `goals` | optional but strongly encouraged | A list of concrete, checkable outcomes the student should be able to demonstrate. |

The frontmatter is intentionally small. Long-form content — the project
narrative, methodology, deliverables, suggested workflow, and so on — belongs
in the Markdown body, not in YAML.

### Body (the description)

The body of `project.md` is the project description. There is no required
internal structure — write whatever Markdown reads well to a motivated
undergrad who is *not yet* an expert in the area.

A good body usually answers, somewhere within it:

1. **What is the scientific question?** What phenomenon, dataset, or system
   is being studied?
2. **What will the student actually do?** Concretely — implement X, reproduce
   result Y, analyze dataset Z. Avoid vague verbs like "explore" or
   "investigate" without saying what they look like in practice.
3. **What does success look like?** A working script, a plot, a model, a
   short report — something the student can picture finishing.

---

## `resources.md` (optional)

A freeform Markdown file that lives alongside `project.md` and lists the
recommended reading, datasets, tools, and references for the project. There is
no required structure — use sections, bullet lists, tables, or annotated
bibliographies as appropriate.

The platform fetches `resources.md` (when present) alongside `project.md` and
makes both available to the coach, so anything you put here is part of the
coach's working context for the project.

Use `resources.md` for:

- Annotated reading lists (a sentence or two per item)
- Multiple categories of references (background reading, primary papers,
  software tools, datasets)
- Links that are too peripheral or numerous to belong in the project body

---

## PR workflow

- PRs are reviewed by a maintainer for completeness and basic quality.
- The slug must not conflict with an existing project directory.
- Once merged to `main`, the project is live immediately.
- To update a project, open a new PR editing the relevant `project.md` (and
  `resources.md`, if applicable).
- To retire a project, open a PR removing the directory and note the reason
  in the PR description.
