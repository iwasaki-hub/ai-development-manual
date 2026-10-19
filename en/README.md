# AI Development Manual

A reusable, project-independent workflow for developing software with AI
assistance.

## Contents

-   `AI_DEVELOPMENT_MANUAL.md` --- the full standard, reusable prompt,
    project brief, task templates, handoff notes, Git workflow, and
    checklists.

## How to use this manual

### For a new project

1.  Copy the common instructions from **Section 2** into the opening
    message of your AI development chat.
2.  Fill out the **Project Brief** in Section 3.
3.  Use the universal checklist in Section 7 to track progress.
4.  Select the relevant task template in Section 4 for each task.
5.  Update the handoff record in Section 5 before pausing or changing
    chats.

### For an existing project

1.  Read the project's current documentation and inspect its code and
    Git status.
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

This package prepares files for you to add to GitHub; it does not create
a GitHub repository or upload anything automatically. Review the files,
then create a repository with GitHub Desktop and publish it when you're
ready.
