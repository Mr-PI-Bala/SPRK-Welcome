# SPRK Welcome Project Guide

This guide is for SPRK maintainers, SPRKAdmin, SPRKTeacher, AgentDraven, and Codex.

## Master Table Of Contents

- [Document Roles](#document-roles)
- [Governance](#governance)
- [Repository Purpose](#repository-purpose)
- [Baseline Structure](#baseline-structure)
- [AURAVYBE Organization Links](#auravybe-organization-links)
- [Access And Approval Flow](#access-and-approval-flow)
- [Diagram Standard](#diagram-standard)
- [Release Flow](#release-flow)

## Document Roles

- `README.md`: public front door.
- `docs/USER_GUIDE.md`: student path for accounts, access, Codespaces, branches, and Pull Requests.
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

## Diagram Standard

Use Mermaid first for diagrams.

Reasons:

- GitHub renders Mermaid diagrams directly in Markdown.
- Students do not need a Mermaid account.
- Diagrams stay text-based and version-controlled.

Use ASCII charts beside Mermaid when the flow must be easy to copy and paste in plain text.

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
