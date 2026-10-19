# AI Development Manual

**Version:** 1.0\
**Purpose:** A reusable, project-independent standard for developing
software with AI assistance.\
**Language:** This manual is written in English-independent, practical
terms so it can be reused across projects and AI tools.

------------------------------------------------------------------------

## 1. Purpose and Core Principles

Use AI as a development partner for requirements, design,
implementation, testing, documentation, and maintenance---not merely as
a code generator.

Follow these principles:

1.  **Clarify the outcome first.** Define the goal, scope, and
    acceptance criteria before implementation.
2.  **Inspect before changing.** Review relevant files, architecture,
    current behavior, and project conventions before proposing edits.
3.  **Work in small steps.** Prefer changes that can be reviewed and
    tested independently.
4.  **Preserve existing behavior.** Do not make unrelated changes or
    silently alter established requirements.
5.  **Separate facts from assumptions.** State uncertainty, assumptions,
    and evidence clearly.
6.  **Verify claims.** Never report a test, command, deployment, or
    change as completed unless it was actually verified.
7.  **Protect data and secrets.** Never expose credentials, tokens,
    private keys, or sensitive user data.
8.  **Record decisions.** Keep project requirements, important technical
    decisions, and progress up to date.
9.  **Reuse successful workflows.** Turn recurring tasks into templates
    and improve them when failures reveal gaps.
10. **Keep the human in control.** Ask before consequential,
    destructive, costly, public, or security-sensitive actions.

## 2. Standard AI Collaboration Instructions

Use the following section as the default instruction for a new
AI-assisted development project.

### Role

Act as a senior software engineer and pragmatic project partner. Help me
plan, implement, test, document, and maintain this project. Explain
important decisions in clear language, and adapt the depth of
explanation to my experience.

### Before starting work

-   Restate the goal and define what "done" means.
-   Inspect the relevant project files and current implementation when
    available.
-   Check existing project documentation and decisions before proposing
    alternatives.
-   Identify dependencies, risks, and affected areas.
-   Ask only for missing information that materially affects the
    solution. For minor gaps, state a reasonable assumption and proceed.
-   Propose a small, reviewable plan before making broad changes.

### While implementing

-   Follow the project's existing architecture, style, naming, and
    conventions unless there is a clear reason to change them.
-   Make the smallest coherent change that solves the stated problem.
-   Identify the files to be changed and why.
-   Avoid unrelated refactors, dependency changes, and scope expansion.
-   Provide complete, applicable code or precise patches and explain
    where they belong.
-   Consider error handling, validation, accessibility, responsiveness,
    security, performance, and maintainability where relevant.
-   Never invent file contents, command output, test results, or
    deployment status.
-   Do not expose secrets. Use environment variables and safe
    configuration practices.
-   Do not perform destructive or externally visible actions without
    appropriate confirmation.

### Verification

-   Choose checks appropriate to the change: tests, linting, type
    checks, builds, manual checks, or security review.
-   Run checks when tools and environment permit.
-   Clearly distinguish **passed**, **failed**, **not run**, and **not
    applicable**.
-   If a check cannot be run, provide the exact command or manual steps
    for the user.
-   Check for regressions in related functionality.
-   Do not claim the task is complete while known acceptance criteria
    remain unmet.

### Communication

For each meaningful step, report as appropriate:

1.  Goal of the step
2.  Proposed change and rationale
3.  Files affected
4.  Commands or actions to perform
5.  Expected result
6.  Verification result
7.  Remaining risks or open questions
8.  Recommended next step

Work incrementally. When the user wants step-by-step guidance, give one
actionable step at a time and wait for confirmation before proceeding.

### End-of-task report

Summarize:

-   What changed
-   Files changed
-   Checks performed and their results
-   What remains unverified
-   Known limitations or follow-up work
-   Whether a Git commit or push is appropriate
-   The recommended next step

## 3. Project Brief Template

Create a project-specific brief for each application. Leave undecided
fields blank rather than guessing.

``` text
# Project Brief

## Overview
- Project name:
- Purpose:
- Problem being solved:
- Intended users:
- Target platforms:
- Current status:

## Scope
### Must-have features
-
### Later features
-
### Explicitly out of scope
-

## User experience
- Design direction:
- Accessibility requirements:
- Responsive/mobile requirements:
- Reference products or examples:

## Technical decisions
- Frontend:
- Backend:
- Database/storage:
- Authentication/authorization:
- External services/APIs:
- Hosting/deployment:
- Version control:
- Testing approach:

## Data and security
- Data collected or stored:
- Data sensitivity:
- Permissions and roles:
- Secrets/configuration approach:
- Backup/recovery expectations:
- Privacy or compliance constraints:

## Acceptance criteria
- [ ]
- [ ]
- [ ]

## Constraints and assumptions
- Constraints:
- Assumptions:
- Open questions:

## Decision log
| Date | Decision | Reason | Impact |
|---|---|---|---|
| | | | |

## Current milestone
- Goal:
- Completed:
- In progress:
- Blocked by:
- Next step:
```

## 4. Task Templates

Use only the template relevant to the current task. Fill in the details
that matter; partial answers are acceptable.

### 4.1 New Feature

``` text
Implement a new feature.

Goal:
[What should the feature accomplish?]

User flow / expected behavior:
[Inputs, actions, outputs, and edge cases]

Existing behavior that must remain unchanged:
[Requirements and related features]

Acceptance criteria:
[Observable conditions for completion]

First inspect the relevant implementation and project conventions. Then propose a small implementation plan, affected files, and verification steps. After the plan is agreed, implement the smallest coherent change and verify it. Report anything not verified.
```

### 4.2 Bug Fix

``` text
Investigate and fix this bug.

Observed behavior:
[What happens?]

Expected behavior:
[What should happen?]

Steps to reproduce:
[Exact steps]

Errors/logs:
[Relevant messages; remove secrets and personal data]

Recent changes or context:
[If known]

Inspect the relevant code and trace the likely cause before editing. Separate evidence from hypotheses. Explain the cause and smallest safe fix, implement it, and run a reproduction test plus relevant regression checks. If the cause is uncertain, propose the next diagnostic step instead of guessing.
```

### 4.3 UI / UX Improvement

``` text
Improve the following UI/UX without unintentionally changing existing functionality.

Screen/component:
[Name, route, screenshot, or files]

Current problem:
[What is confusing, difficult, or visually inconsistent?]

Desired outcome:
[Style, hierarchy, behavior, reference examples]

Must preserve:
[Existing interactions, design system, content, or constraints]

Inspect the current implementation first. Propose the smallest useful change, then implement it after agreement. Check responsive behavior, keyboard/accessibility basics, and relevant interactions.
```

### 4.4 Code Review

``` text
Review the following code or project area.

Scope:
[Files, feature, or diff]

Context:
[Purpose and important constraints]

Focus:
[Correctness, security, performance, maintainability, accessibility, etc.]

Prioritize findings by severity. For each finding, identify the affected code, explain the risk and triggering conditions, and recommend a concrete fix. Distinguish confirmed defects from suggestions. Do not modify files unless asked.
```

### 4.5 Test Planning / Release Readiness

``` text
Create and perform an appropriate test plan for this change or release.

Scope:
[Features and environment]

Recent changes:
[Summary or commit/diff]

Include relevant normal cases, error cases, boundary values, authorization, data persistence, regressions, responsive behavior, and deployment configuration.

Run checks that are available. Report each as PASS, FAIL, NOT RUN, or NOT APPLICABLE, with evidence. Do not claim full release readiness if important checks remain unverified.
```

### 4.6 Refactoring

``` text
Refactor the following area without changing its externally observable behavior.

Scope:
[Files/components]

Motivation:
[Duplication, complexity, maintainability, performance, etc.]

Behavior that must remain unchanged:
[Requirements]

Before editing, identify the current behavior and propose a bounded plan. Avoid unrelated changes. Use existing tests where possible, add tests when justified, and compare behavior before and after.
```

### 4.7 Resume Work / Continue in a New Chat

``` text
Resume work on this project.

Current goal:
[Goal]

Known completed work:
[Summary or link to project notes]

Open issues:
[Known unfinished work]

Important decisions and constraints:
[Do not violate these]

Inspect available project notes, relevant files, and current version-control status before continuing. Confirm what is actually present, distinguish verified state from the notes, and identify the highest-priority next step. Do not repeat completed work unnecessarily.
```

## 5. Progress and Handoff Record

Update this record at the end of a meaningful milestone or before
pausing work.

``` text
# Development Handoff

Date:
Project:
Current branch:

## Goal for this milestone
-

## Completed
- [ ]

## Files changed
| File | Change | Reason |
|---|---|---|
| | | |

## Verification
- Checks run:
- Results:
- Not run / unverified:

## Current issues and risks
-

## Decisions that must be preserved
-

## Git status
- Uncommitted changes:
- Last commit:
- Pushed to remote:
- Working tree reviewed:

## Next steps
1.
2.
3.

## Resume instruction
Read this handoff, inspect the current project and version-control state, and continue from the highest-priority unfinished item. Do not assume the notes are more current than the actual files.
```

## 6. Git and GitHub Workflow

Use GitHub Desktop or another Git client consistently with the project's
workflow.

### Before working

1.  Open the correct repository.
2.  Confirm the branch.
3.  Review uncommitted changes.
4.  Read relevant project instructions and notes.
5.  Preserve user changes; never discard or overwrite them without
    permission.

### Commit checkpoints

Consider committing after: - Initial project setup is verified - A
feature is implemented and checked - A bug fix is verified - A
meaningful design change is checked - A stable state is reached before a
risky change

Keep commits focused and use descriptive messages, for example: -
`Set up project structure` - `Add memo creation and listing` -
`Fix saved memo persistence` - `Improve responsive layout`

### Before pushing

-   Review the diff and included files.
-   Check for secrets, credentials, personal data, and unintended files.
-   Confirm the target repository and branch.
-   Confirm that the content is appropriate for the repository's
    visibility.
-   Push only when appropriate.

A local commit is not the same as pushing to GitHub. Pushing to GitHub
is not the same as deploying a live application.

## 7. Universal Development Checklist

### Planning

-   [ ] Goal and acceptance criteria are clear.
-   [ ] Scope and exclusions are clear.
-   [ ] Existing implementation and decisions have been reviewed.
-   [ ] Risks and dependencies are identified.

### Implementation

-   [ ] Changes are limited to the agreed scope.
-   [ ] Existing conventions are followed.
-   [ ] Errors and input validation are handled where relevant.
-   [ ] Security and privacy implications are considered.
-   [ ] Documentation is updated if behavior or setup changes.

### Verification

-   [ ] Relevant tests or manual checks are performed.
-   [ ] Results are recorded accurately.
-   [ ] Related functionality is checked for regressions.
-   [ ] Unverified items are explicitly listed.

### Handoff and version control

-   [ ] Progress notes are updated.
-   [ ] Remaining issues are recorded.
-   [ ] Diff is reviewed.
-   [ ] Commit is made when appropriate.
-   [ ] Push/deployment is performed only when intended and authorized.

### Release, when applicable

-   [ ] Production configuration is checked.
-   [ ] Secrets are configured safely.
-   [ ] Build and key flows are verified.
-   [ ] Data backup/recovery is considered where relevant.
-   [ ] Post-release monitoring or rollback steps are understood.

## 8. Continuous Improvement

Treat this manual as a living standard.

When a recurring problem or missed check occurs:

1.  Record the failure and its impact.
2.  Identify the root cause when possible.
3.  Add or improve a checklist item or task template.
4.  Keep the rule concise and broadly reusable.
5.  Validate the change in a later project.
6.  Update the version and change log.

Do not add rules merely for the sake of length. Prefer rules that
prevent real mistakes or improve repeatability.

## 9. Version History

  Version   Changes
  --------- -------------------------------------------------------
  1.0       Initial reusable standard for AI-assisted development
