# SPRK Git Repository User Guide
This is the master SPRK guide for GitHub accounts, repository access, branches, commits, pushes, and pull requests.

## Table Of Contents
- [SPRK GitHub Account Pattern](#sprk-github-account-pattern)
- [Find A Repository](#find-a-repository)
- [Request Access To A Working Repository](#request-access-to-a-working-repository)
- [Accept A Pending Invitation](#accept-a-pending-invitation)
- [Create Your Branch](#create-your-branch)
- [Commit And Push](#commit-and-push)
- [Open A Pull Request](#open-a-pull-request)
- [Personal Repository Permissions](#personal-repository-permissions)
- [Organization Repository Permissions](#organization-repository-permissions)

## SPRK GitHub Account Pattern
SPRK member accounts use a consistent clan-style identity.

- Public profile name: `FirstName SPRK`
- GitHub username: `FirstName-SPRK`
- Email pattern when available: `firstname.SPRK@gmail.com`
- Branch name: GitHub username in lowercase, such as `<yourname-sprk>`

Example:

- Public profile name: `Maya SPRK`
- GitHub username: `Maya-SPRK`
- Email: `maya.SPRK@gmail.com` when available
- Branch name: `maya-sprk`

In copy/paste snippets, replace `<YourName>-SPRK` and `<yourname-sprk>` with your own values. For Maya, those values are `Maya-SPRK` and `maya-sprk`.

If you convert an existing GitHub account, update old bookmarks, Codespaces sign-in, local remotes, and connected tools. If the account already has important prior work, create a new SPRK account instead.

## Find A Repository
Start from the public doorway:

```text
https://github.com/Mr-PI-Bala/SPRK-Welcome
```

Working repositories use normal GitHub URLs:

```text
https://github.com/<owner>/<repository>
```

Clone URLs add `.git`:

```text
https://github.com/<owner>/<repository>.git
```

## Request Access To A Working Repository
Use GitHub Issues so the request is visible and trackable.

Steps:

1. Open the working repository.
2. Click `Issues`.
3. Click `New issue`.
4. Use a clear title.
5. Explain who you are, which branch you will use, and what access you need.
6. Submit the issue.

Example title:

```text
Access request: <YourName>-SPRK branch access for SPRK-Hello-Repo
```

Example body:

~~~md
## Access Request
Requester: `<YourName>-SPRK` (example: `Maya-SPRK`)
Repository: `Mr-PI-Bala/SPRK-Hello-Repo`
Requested access: `Write`
Branch name: `<yourname-sprk>` (example: `maya-sprk`)

## Why this access is needed
I am testing the SPRKStudent workflow and need to push my own branch for review.

## Boundaries
I will not push to `main`.
I will not merge pull requests.
I will open a Pull Request for SPRKTeacher or SPRKAdmin review.

## Owner Action
Open repository access settings:

https://github.com/Mr-PI-Bala/SPRK-Hello-Repo/settings/access

Add `<YourName>-SPRK` as collaborator.
~~~

## Accept A Pending Invitation
After the owner adds you, GitHub may show a pending invitation.

Open the invitation from GitHub notifications or email, then accept it before trying to push.

If using GitHub CLI, check permission:

```bash
gh repo view Mr-PI-Bala/SPRK-Hello-Repo --json viewerPermission
```

## Create Your Branch
Pull the latest `main`, then create your branch.

```bash
git pull
git checkout -b <yourname-sprk>
```

Use your own GitHub username in lowercase as the branch name.

## Commit And Push
Run the repository check first.

```bash
python -m core.main --check
git status
git add .
git commit -m "Describe your change"
git push -u origin <yourname-sprk>
```

Commit messages should explain what changed. Use commits as checkpoints while learning.

## Open A Pull Request
After pushing your branch, open a Pull Request into `main`.

`SPRKTeacher` or `SPRKAdmin` reviews the work before it enters `main`.

## Personal Repository Permissions
For repositories under a personal GitHub account, adding a collaborator usually gives broad collaborator access. That is workable for trusted staff, but it is not ideal for fine-grained student roles.

For student workflows, keep `main` protected and require Pull Requests before merging.

## Organization Repository Permissions
For stronger role control, use an organization such as `AURAVYBE`.

Organization repositories can support clearer roles such as:

- Read
- Triage
- Write
- Maintain
- Admin

SPRK may later move working repositories into an organization when role-based controls become more important than personal-repo simplicity.
