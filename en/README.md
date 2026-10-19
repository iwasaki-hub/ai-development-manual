# AI Development Manual

A reusable, project-independent workflow for developing software with AI
assistance.

## Contents

-   `AI_DEVELOPMENT_MANUAL.md` --- the full standard, reusable prompt,
    project brief, task templates, handoff notes, Git workflow, and
    checklists.

## Project start prompt

Use the [English Project Start Prompt](../templates/PROJECT_START_PROMPT.en.md)
to start either a new or an existing project. Fill in what you know; leave
undecided fields blank and discuss important unknowns with the AI. Do not
include actual passwords, tokens, or private keys.

For an existing project, provide the repository or working directory and
let the AI inspect its instructions (such as `AGENTS.md`), README, relevant
code, and Git status. For a new project, use the prompt to clarify the goal,
users, scope, constraints, and acceptance criteria.

## How to use this manual

### For a new project

1.  Use the [English Project Start Prompt](../templates/PROJECT_START_PROMPT.en.md)
    as the opening instruction. Follow Section 2 of the manual for
    additional collaboration guidance.
2.  Fill out the **Project Brief** in Section 3 as information becomes
    available; discuss important unknowns instead of guessing.
3.  Use the universal checklist in Section 7 to track progress.
4.  Select the relevant task template in Section 4 for each task.
5.  Update the handoff record in Section 5 before pausing or changing
    chats.

### For an existing project

1.  Use the [English Project Start Prompt](../templates/PROJECT_START_PROMPT.en.md).
    Read the project's instructions (such as `AGENTS.md`) and current
    documentation, and inspect its code and Git status.
2.  Record the existing decisions and constraints in a project brief.
3.  Apply the common instructions without overriding established
    project-specific rules.
4.  Use the bug-fix, code-review, or resume-work template as
    appropriate.

### Recommended repository layout

Keep this manual in its own repository so it can be reused by unrelated
projects:

``` text
ai-development-manual/
├── README.md
├── AI_DEVELOPMENT_MANUAL.md
└── .gitignore
```

For each application, optionally copy or adapt the manual into the
application's `docs/` folder if the project needs a versioned snapshot
of its rules:

``` text
your-app/
└── docs/
    ├── AI_DEVELOPMENT_MANUAL.md
    ├── PROJECT_BRIEF.md
    └── DEVELOPMENT_HANDOFF.md
```

The standalone manual repository is the source of truth.
Project-specific documents should contain only the decisions and
adaptations needed by that application.

## Important

This manual and its prompts provide reusable guidance; they do not create
a GitHub repository or upload anything automatically. Review the files,
then use your chosen Git client to create or publish a repository when
you are ready.
