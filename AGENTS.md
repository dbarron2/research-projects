# Research Projects Repo — Agent Context

This repository is the public project listing for the
[AI Research Coach](https://airesearchcoach.org). Each directory under
`projects/` holds a single `project.md` that a student reads when choosing a
project. Quality here matters: a vague or poorly-structured description makes
the coach's job harder and the student's experience worse.

---

## Writing a `project.md`

### Schema

```yaml
---
title: "Human-readable project title"
pi: "pi-github-username"
description: |
  ...
materials:
  - "..."
goals:
  - "..."
---
```

`title`, `pi`, and `description` are required. `materials` and `goals` are
optional but strongly encouraged.

A project directory may also include an optional `resources.md` — a freeform
Markdown file for a richer reading list or annotated references. See the
[Resources file](#resources-file) section below.

### What makes a good description

The description is the most important field. A student reads it cold, with no
other context. Write it so a motivated undergrad who is *not yet* an expert in
the area can answer three questions after reading it:

1. **What is the scientific question?** State the phenomenon, dataset, or
   system being studied. Avoid jargon without a brief gloss.
2. **What will the student actually do?** Be concrete — "implement X",
   "reproduce result Y from the paper", "analyze dataset Z". Avoid vague
   phrases like "explore" or "investigate" without saying what that looks like
   in practice.
3. **What does success look like?** The student should be able to picture a
   finished product: a working script, a plot, a model, an analysis, a report.

**Length:** Two to four paragraphs is the target. One paragraph is usually too
sparse; five or more usually means the description is doing too much.

**Tone:** Clear, direct, and encouraging. Not a paper abstract; not a grant
proposal.

**Anti-patterns to avoid:**

- Descriptions that only state background science without saying what the
  student does ("This project is about dark matter. Dark matter accounts for
  27% of the universe...")
- Unexplained acronyms or field-specific terms in the first sentence
- Passive constructions that obscure who does what ("The code will be written
  to...") — prefer active voice ("You will write code to...")
- Goals that are restatements of the description rather than distinct,
  checkable outcomes

### Goals

Each goal should be a concrete, checkable outcome — something you could ask
the student to demonstrate. Good goals start with verbs like "Implement",
"Reproduce", "Explain", "Produce", "Analyze", "Extend".

### Materials

List the canonical references a student needs. Prefer specific chapters or
arXiv links over vague "see the literature" pointers. Two to five items is
typical. For a richer or annotated reading list, use `resources.md` instead
of (or in addition to) the `materials` field.

### Resources file

`resources.md` is a freeform Markdown file that lives alongside `project.md`.
It has no required structure. Use it when:

- References benefit from a sentence or two of annotation per item
- There are multiple categories worth separating (e.g., background reading,
  primary papers, software tools, datasets)
- The full list is too long for the `materials` YAML field but the PI still
  wants students to have easy access to it

When writing or reviewing a `resources.md`, check that:
- It is valid Markdown and renders cleanly
- Links are real and point to the intended resources
- It is written for a student audience, not a grant committee

### Slug (directory name)

Lowercase letters, digits, and hyphens only. Should be descriptive enough to
be recognizable out of context. Examples: `rna-folding-dynamics`,
`galaxy-morphology-cnn`, `climate-downscaling`.

---

## Reviewing a PR for a new project

When a PR adds a new project directory, check the following in order. Block
the PR (request changes) for any hard-block item; leave a comment for
soft-block items; approve if everything passes.

### 1. Structural checks (hard block if failing)

- [ ] PR adds exactly one new directory under `projects/`.
- [ ] The directory contains a `project.md` file.
- [ ] The slug (directory name) matches `[a-z0-9-]+` and is ≤ 64 characters.
- [ ] The slug does not duplicate an existing directory.
- [ ] The YAML front matter parses without errors (no missing `---` delimiters,
      no malformed fields).
- [ ] `title` and `pi` fields are present and non-empty.
- [ ] `description` is present and non-empty.

### 2. Content quality (hard block if failing)

- [ ] The description answers all three questions: what is the scientific
      question, what will the student do, what does success look like?
- [ ] The description is written in English, in complete sentences, and is
      free of placeholder text.
- [ ] The description is at least two paragraphs (one dense paragraph may be
      acceptable; one sentence is not).

### 3. Content quality (soft block — request improvements, but use judgment)

- [ ] Goals are concrete and checkable, not vague restatements of the
      description.
- [ ] Materials, if listed, point to real, accessible resources (arXiv links
      should resolve; textbook titles should be specific).
- [ ] The description uses plain, accessible language in the first paragraph —
      no unexplained field-specific jargon in the opening sentence.
- [ ] Active voice is used for what the student will do.

### 4. Housekeeping (comment, do not block)

- [ ] No unrelated files are modified (e.g., no edits to `README.md` or other
      projects).
- [ ] Any files in `materials/` are supplementary documents, not executables
      or binaries.
- [ ] If a `resources.md` is included, it is valid Markdown, all links look
      real, and it is written for a student audience.

### Suggested review comment templates

**Vague description:**
> The description mostly covers background science but doesn't yet say what
> the student will concretely do or what a finished product looks like. Could
> you add a paragraph describing the specific task (e.g., "you will implement
> X" or "you will produce Y") and what a successful result looks like?

**Goals are restatements:**
> The goals look like a summary of the description rather than distinct,
> checkable outcomes. Good goals start with action verbs and describe something
> you could ask the student to demonstrate — for example, "Reproduce Figure 3
> from the paper" or "Explain why the optimization converges for this class of
> inputs."

**Slug issue:**
> The directory name `<slug>` contains characters not allowed by the slug rules
> (lowercase letters, digits, and hyphens only, 1–64 characters). Please rename
> the directory to something like `<suggested-slug>`.
