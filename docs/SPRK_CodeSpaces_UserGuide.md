# SPRK CodeSpaces User Guide

This is the master SPRK guide for GitHub Codespaces.

## Table Of Contents

- [What Codespaces Is](#what-codespaces-is)
- [Open Codespaces](#open-codespaces)
- [Runtime Levels](#runtime-levels)
- [Safe Project Check](#safe-project-check)
- [Graphics And Desktop App Limits](#graphics-and-desktop-app-limits)
- [Copilot Chat Took Too Long](#copilot-chat-took-too-long)
- [Classroom Device Testing](#classroom-device-testing)

## What Codespaces Is

Codespaces is a cloud development machine that runs in the browser. It is useful for students on Chromebooks, iPads, shared computers, or machines where Python setup is hard.

Codespaces is good for:

- Reading code and Markdown.
- Editing files.
- Running safe checks.
- Committing and pushing branches.
- Opening Pull Requests.

Codespaces is not always good for:

- Showing a desktop graphics window from a 3D engine or desktop app.
- Testing 3D controls that require a visible app window.

## Open Codespaces

From a GitHub repository:

1. Click `Code`.
2. Open the `Codespaces` tab.
3. Create or open a Codespace.
4. Read `README.md`.
5. Read the repository-specific user guide.
6. Run the safe check.

## Runtime Levels

Different devices support different levels of testing.

```text
Level A - Code/check only
Use Codespaces to read, edit, and run the safe check.
No visible desktop graphics window.

Level B - Headless graphics
Codespaces runs a fake X11 display such as Xvfb.
This can prove a graphics engine starts, but the student still may not see the window.

Level C - Dual-device visual test
Student codes in Codespaces.
SPRKTeacher or SPRKAdmin pulls the student branch on a graphics-capable laptop and runs the visible app.

Level D - Browser-visible virtual desktop
Codespaces runs a virtual desktop such as noVNC.
The student sees the desktop app window in the browser, but this is the most advanced and fragile path.
```

Start with Level A. Use Level C when a Chromebook, iPad, phone, or school-managed device cannot show the graphical app directly.

## Safe Project Check

For the primary browser-visible `SPRK-Hello-Repo`, use the check command documented inside that repository.

For Python repositories that provide a safe check, the command usually looks like:

```bash
python -m core.main --check
```

The check should validate project structure without opening a desktop graphics window.

## Graphics And Desktop App Limits

If Codespaces shows this:

```text
Exception: No graphics pipe is available!
```

that means the app cannot find a graphical display.

Use the safe check in Codespaces:

```bash
python -m core.main --check
```

Run visible desktop or 3D apps on a graphics-capable laptop:

```powershell
python -m core.main
```

## Copilot Chat Took Too Long

Symptom:

```text
Chat took too long to get ready. Please ensure you are signed in to GitHub and that the extension GitHub.copilot-chat is installed and enabled.
```

What we learned:

- The Codespaces account can be correct while Chat still fails.
- The right-side Chat panel can exist even when the Copilot Chat provider extension is missing or not activated.
- Installing `GitHub Copilot Chat` fixed the issue.
- The older/general `GitHub Copilot` extension path may be deprecated or not enough for this setup.

Fix:

1. Confirm Codespaces is signed in as the expected GitHub account.
2. Open Extensions with `Ctrl+Shift+X`.
3. Search for `GitHub Copilot Chat`.
4. Install or enable `GitHub Copilot Chat`.
5. Reload the window with `Ctrl+Shift+P`, then `Developer: Reload Window`.
6. Click `Restart` in the Chat panel if the warning remains.

Terminal check:

```bash
code --list-extensions --show-versions | grep -i copilot
```

Expected useful result:

```text
GitHub.copilot-chat@...
```

## Classroom Device Testing

Codespaces is not required for every student in the first classroom multiplayer test.

For browser-visible projects in `SPRK-Hello-Repo`, one backend-host laptop can run the backend while students join from browsers on Chromebooks, iPads, iPhones, Android phones, or other laptops.

Use the dedicated classroom guide:

```text
docs/SPRK_Classroom_Network_Test_Guide.md
```
