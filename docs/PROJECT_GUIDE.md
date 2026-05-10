# SPRK Welcome Project Guide

This guide is for SPRK maintainers, SPRKAdmin, SPRKTeacher, AgentDraven, and Codex.

## Master Table Of Contents

- [Document Roles](#document-roles)
- [Governance](#governance)
- [Repository Purpose](#repository-purpose)
- [Baseline Structure](#baseline-structure)
- [AURAVYBE Organization Links](#auravybe-organization-links)
- [Access And Approval Flow](#access-and-approval-flow)
- [Documentation Principles](#documentation-principles)
- [Formative Insights](#formative-insights)
- [Diagram Standard](#diagram-standard)
- [Classroom Network Strategy](#classroom-network-strategy)
- [Release Flow](#release-flow)

## Document Roles

- `README.md`: public front door.
- `docs/USER_GUIDE.md`: public doorway guide for starting from SPRK-Welcome.
- `docs/SPRK_Git_Repository_UserGuide.md`: master GitHub accounts, access requests, branches, commits, pushes, and Pull Requests guide.
- `docs/SPRK_CodeSpaces_UserGuide.md`: master Codespaces runtime levels, safe checks, and graphics limits guide.
- `docs/SPRK_Classroom_Network_Test_Guide.md`: classroom backend-host, device, and network validation guide.
- `docs/SPRK_VSCode_UserGuide.md`: master VS Code Markdown preview/editing, Mermaid, and extension guide.
- `docs/PROJECT_GUIDE.md`: maintainer path for governance and repository operations.
- `docs/CHANGELOG.md`: version history.
- `LICENSE`: MERIT/AURAVYBE license terms.
- `VERSION`: current version.

## Governance

This repository is owned by `Mr-PI-Bala`.

Inside this repository, governance stops at `Mr-PI-Bala`. AgentDraven acts as `SPRKAdmin` when performing operational work for this repository.

Role categories:

- `SPRKAdmin`: administrative and repository-governance execution.
- `SPRKTeacher`: classroom/staff review, feedback, and student support.
- `SPRKStudent`: student learner, tester, contributor, and critique voice.

## Repository Purpose

`SPRK-Welcome` is the public doorway for SPRK. It should stay public, simple, and student-facing.

It advertises available SPRK paths and explains how students request access to private working repositories.

## Baseline Structure

Official SPRK repositories should use this baseline unless there is a deliberate reason to differ:

```text
README.md
LICENSE
VERSION
docs/
  USER_GUIDE.md
  SPRK_Git_Repository_UserGuide.md
  SPRK_CodeSpaces_UserGuide.md
  SPRK_Classroom_Network_Test_Guide.md
  SPRK_VSCode_UserGuide.md
  PROJECT_GUIDE.md
  CHANGELOG.md
.vscode/
  settings.json
  extensions.json
```

New repository creation settings:

- Add README: off
- Add `.gitignore`: none
- Add license: none
- Jumpstart with Copilot: leave blank unless there is an approved short operational prompt

Reason:

The first committed files should come from the SPRK baseline so license, docs, VS Code settings, and governance are consistent.

## AURAVYBE Organization Links

AURAVYBE is the future organization home for cleaner SPRK access control. Current SPRK repositories may remain under `Mr-PI-Bala` until they are deliberately moved or recreated.

Use these links when setting up or reviewing access:

- AURAVYBE members: `https://github.com/orgs/AURAVYBE/people`
- AURAVYBE teams: `https://github.com/orgs/AURAVYBE/teams`
- AURAVYBE repositories: `https://github.com/orgs/AURAVYBE/repositories`
- SPRK-Welcome personal-repo collaborators: `https://github.com/Mr-PI-Bala/SPRK-Welcome/settings/access`

Planned teams:

- `SPRKAdmins`
- `SPRKTeachers`
- `SPRKStudents`

Until SPRK repositories move into AURAVYBE, repository access for `Mr-PI-Bala` personal repositories is still managed from each repository's collaborator settings.

## Access And Approval Flow

```text
Student opens SPRK-Welcome
  |
  v
Student requests access to a private SPRK repository
  |
  v
SPRKTeacher or SPRKAdmin reviews the request
  |
  v
Approved student receives access
  |
  v
Student works in their branch
```

Students should usually receive write access to create and push their own branches. `main` should be protected in working repositories.

## Documentation Principles

These principles apply to SPRK-Welcome and to shared SPRK guide content copied into other repositories.

### Generalize First

Write instructions so they work for the reader's account and repository unless the section is explicitly about a named persona.

Use placeholders in reusable snippets:

- `<YourName>-SPRK`
- `<yourname-sprk>`
- `<repository-owner>`
- `<repository-name>`

Then provide one nearby example:

```text
Requester: <YourName>-SPRK (example: Maya-SPRK)
Branch: <yourname-sprk> (example: maya-sprk)
```

Avoid hard-coding `Mr-PI-Bala`, `Maya-SPRK`, or `AgentDraven` unless the section is specifically about that account.

### Account Context Comes Before Screen Diagnosis

When a student or maintainer cannot find a GitHub button or tab, check the signed-in account and permission level before assuming the screen is too narrow or the UI changed.

Example:

```text
If you do not see Settings, check whether you are signed in as the repository owner or an account with admin permission.
```

General wording:

```text
For delete, visibility, repository settings, and access-management actions, sign in as the repository owner/admin account.

If this is your own repository, sign in as your own <FirstName>-SPRK account.

If this is a repository owned by another account, you need that owner/admin account or delegated admin permission.
```

### Name The Screen Areas

When teaching GitHub, Codespaces, or VS Code, identify the screen area first.

Use these labels:

- Browser toolbar: address bar and browser buttons.
- GitHub global header: GitHub logo, search, plus button, profile avatar.
- Repository identity: `<repository-owner> / <repository-name>`.
- Repository top bar: `Code`, `Issues`, `Pull requests`, `Actions`, `Settings`, and related repo tabs.
- File toolbar: branch selector, file search, green `Code` button.
- Right sidebar: About, Releases, Packages, Contributors, Languages.

The visual orientation cheatsheet for this work is tracked in issue #5.

### Repository Docs Are The Source Of Truth

Codex memory can help continuity, but durable decisions belong in repository docs.

Use this order:

1. Capture the live learning in a GitHub issue or issue comment.
2. Move stable lessons into `docs/PROJECT_GUIDE.md`.
3. Move student-facing instructions into the correct user guide or cheatsheet.
4. Keep changelog entries for released documentation changes.

## Formative Insights

### Missing Settings Can Mean Missing Permission

Finding:

A user looking at a repository may not see `Settings` even when the repository top bar is visible.

Learning:

This can happen because the signed-in account does not own or administer the repository. For example, a SPRKStudent account viewing a repository owned by another account may see `Code`, `Issues`, and `Pull requests`, but not `Settings`.

Action:

Teach account context explicitly before giving delete, visibility, or access-management instructions.

### Examples Should Not Become Accidental Values

Finding:

If snippets say `Maya-SPRK` everywhere, students may copy Maya's value instead of replacing it with their own account.

Learning:

Reusable snippets should use placeholders first and a single nearby example second.

Action:

Use `<YourName>-SPRK` and `<yourname-sprk>` in snippets, then add examples in parentheses or a short example block.

### Issue Comments Are Good Capture, Not Final Documentation

Finding:

Real workflow lessons often appear first in chat or issue comments.

Learning:

Issue comments are useful for not losing the lesson, but they are not the final student-facing guide.

Action:

Promote stable issue-comment lessons into `PROJECT_GUIDE.md`, `USER_GUIDE.md`, or the shared SPRK toolchain guides.

### Multiplayer Classroom Tests Need A Host Laptop

Finding:

Browser-based class collaboration needs a backend host that other student devices can reach.

Learning:

A school Chromebook, iPad, iPhone, or Android device can be a good frontend device, but the first reliable backend-host should be a laptop that can run Python or Node, bind to `0.0.0.0`, and allow local network traffic through the firewall.

Action:

Use `docs/SPRK_Classroom_Network_Test_Guide.md` before a live class activity. Test school Wi-Fi first, then the `SPRK Laptop Network`, then fallback to projector/shared-laptop roles if networking blocks device-to-device traffic.

## Diagram Standard

Use Mermaid first for diagrams.

Reasons:

- GitHub renders Mermaid diagrams directly in Markdown.
- Students do not need a Mermaid account.
- Diagrams stay text-based and version-controlled.

Use ASCII charts beside Mermaid when the flow must be easy to copy and paste in plain text.

## Classroom Network Strategy

SPRK classroom apps should support a low-friction collaboration pattern:

```text
Backend host laptop
  |
  v
School Wi-Fi or SPRK Laptop Network
  |
  v
Student browsers on Chromebooks, iPads, phones, and laptops
```

`SPRK-Hello-Repo` should use this pattern for browser-visible projects that can run in solo mode and then grow into multiplayer classroom mode.

Network order:

1. School Wi-Fi.
2. `SPRK Laptop Network`, started from the backend-host laptop.
3. Projector/shared laptop fallback.

The TCL LINKPORT IK511 should be treated as internet for the backend-host laptop, not as a direct multi-student Wi-Fi hotspot by itself. If needed, the host laptop can try to share that connection as the `SPRK Laptop Network`.

Before using a classroom multiplayer project, validate with:

- one backend-host laptop
- one school Chromebook
- one iPad
- one iPhone or Android phone

Use [SPRK_Classroom_Network_Test_Guide.md](SPRK_Classroom_Network_Test_Guide.md) as the test script.

## Release Flow

Use `major.minor.patch` versions.

Early setup releases use `0.0.x`.

Before release:

```bash
git status
git add .
git commit -m "Describe the change"
git tag v0.0.x
git push origin main
git push origin v0.0.x
```
