# Research Projects Repo — Agent Context

This repository is the public project listing for the
[AI Research Coach](https://airesearchcoach.org). Each directory under
`projects/` holds a single `project.md` that a student reads when choosing a
project, and that the coach reads as part of its working context. Quality
here matters: a vague or poorly-structured description makes the coach's job
harder and the student's experience worse.

---

## Writing a `project.md`

### Schema

A `project.md` is a Markdown file with a small YAML frontmatter block
followed by the project description as the body of the file. The body is the
description — there is no `description:` field in the frontmatter.

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

The body of the file is the human-readable project description. Use whatever
Markdown structure makes it clear and easy to read.
```

`title` and `pi` are required. `goals` is optional but strongly encouraged.
The body is required and is the project description.

A project directory may also include an optional `resources.md` — a freeform
Markdown file holding the recommended reading list and references. See the
[Resources file](#resources-file) section below.

### What makes a good description

The body of `project.md` is the description. A student reads it cold, with no
other context. Write it so a motivated undergrad who is *not yet* an expert
in the area can answer three questions after reading it:

1. **What is the scientific question?** State the phenomenon, dataset, or
   system being studied. Avoid jargon without a brief gloss.
2. **What will the student actually do?** Be concrete — "implement X",
   "reproduce result Y from the paper", "analyze dataset Z". Avoid vague
   phrases like "explore" or "investigate" without saying what that looks
   like in practice.
3. **What does success look like?** The student should be able to picture a
   finished product: a working script, a plot, a model, an analysis, a
   report.

**Length:** A few short sections (or two to four paragraphs) is the target.
A single sentence is too sparse; a wall of text is hard to skim.

**Structure:** Use Markdown freely — headings, sub-headings, bullet lists,
inline equations, links. The body should read well on its own.

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
- Putting the description back into a `description:` YAML field (the new
  schema treats the body of the file as the description)

### Goals

Each goal in the `goals:` frontmatter list should be a concrete, checkable
outcome — something you could ask the student to demonstrate. Good goals
start with verbs like "Implement", "Reproduce", "Explain", "Produce",
"Analyze", "Extend".

### Resources file

`resources.md` is a freeform Markdown file that lives alongside `project.md`.
It has no required structure. Use it for the canonical reading list and
references the student needs — papers, textbook chapters, datasets, tools,
external tutorials.

The platform fetches `resources.md` (when present) alongside `project.md` and
makes both available to the coach, so anything you put here becomes part of
the coach's working context for the project.

When writing or reviewing a `resources.md`, check that:

- It is valid Markdown and renders cleanly
- Links are real and point to the intended resources
- It is written for a student audience, not a grant committee
- It does not duplicate content already in `project.md`'s body

There is no `materials:` YAML field in the new schema — references and
reading lists belong in `resources.md` (or, in passing, in the body of
`project.md`). Older `materials:` lists should be migrated to `resources.md`.

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
- [ ] The YAML front matter parses without errors (no missing `---`
      delimiters, no malformed fields).
- [ ] `title` and `pi` fields are present and non-empty.
- [ ] The body of `project.md` (after the frontmatter) is non-empty.

### 2. Content quality (hard block if failing)

- [ ] The body answers all three questions: what is the scientific question,
      what will the student do, what does success look like?
- [ ] The body is written in English, in complete sentences, and is free of
      placeholder text.
- [ ] The body is at least a few paragraphs or short sections — a single
      sentence is not acceptable.

### 3. Content quality (soft block — request improvements, but use judgment)

- [ ] Goals (if listed) are concrete and checkable, not vague restatements
      of the description.
- [ ] If a `resources.md` is present, references are real and accessible
      (arXiv links should resolve; textbook titles should be specific).
- [ ] The body uses plain, accessible language in the first paragraph — no
      unexplained field-specific jargon in the opening sentence.
- [ ] Active voice is used for what the student will do.

### 4. Housekeeping (comment, do not block)

- [ ] No unrelated files are modified (e.g., no edits to `README.md` or
      other projects).
- [ ] Any files in `materials/` are supplementary documents, not executables
      or binaries.
- [ ] If a `resources.md` is included, it is valid Markdown, all links look
      real, and it is written for a student audience.
- [ ] The frontmatter does not include a `description:` or `materials:`
      field (these are not part of the current schema — the body is the
      description and references go in `resources.md`).

### Suggested review comment templates

**Vague description:**
> The body mostly covers background science but doesn't yet say what the
> student will concretely do or what a finished product looks like. Could
> you add a paragraph describing the specific task (e.g., "you will
> implement X" or "you will produce Y") and what a successful result looks
> like?

**Goals are restatements:**
> The goals look like a summary of the description rather than distinct,
> checkable outcomes. Good goals start with action verbs and describe
> something you could ask the student to demonstrate — for example,
> "Reproduce Figure 3 from the paper" or "Explain why the optimization
> converges for this class of inputs."

**Old-schema fields:**
> The frontmatter still has a `description:` (or `materials:`) field. In
> the current schema, the body of the file is the description, and
> references belong in a sibling `resources.md`. Could you migrate the
> content out of the YAML and remove the field?

**Slug issue:**
> The directory name `<slug>` contains characters not allowed by the slug
> rules (lowercase letters, digits, and hyphens only, 1–64 characters).
> Please rename the directory to something like `<suggested-slug>`.
