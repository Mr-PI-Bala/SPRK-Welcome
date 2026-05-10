# SPRK CodeSpaces User Guide

This is the master SPRK guide for GitHub Codespaces.

## Table Of Contents

- [What Codespaces Is](#what-codespaces-is)
- [Open Codespaces](#open-codespaces)
- [Runtime Levels](#runtime-levels)
- [Safe Project Check](#safe-project-check)
- [Ursina Graphics Limits](#ursina-graphics-limits)
- [Copilot Chat Took Too Long](#copilot-chat-took-too-long)

## What Codespaces Is

Codespaces is a cloud development machine that runs in the browser. It is useful for students on Chromebooks, iPads, shared computers, or machines where Python setup is hard.

Codespaces is good for:

- Reading code and Markdown.
- Editing files.
- Running safe checks.
- Committing and pushing branches.
- Opening Pull Requests.

Codespaces is not always good for:

- Showing a desktop graphics window from Ursina/Panda3D.
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
No visible Ursina graphics window.

Level B - Headless graphics
Codespaces runs a fake X11 display such as Xvfb.
This can prove Ursina/Panda3D starts, but the student still may not see the window.

Level C - Dual-device visual test
Student codes in Codespaces.
SPRKTeacher or SPRKAdmin pulls the student branch on a graphics-capable laptop and runs the visible app.

Level D - Browser-visible virtual desktop
Codespaces runs a virtual desktop such as noVNC.
The student sees the Ursina window in the browser, but this is the most advanced and fragile path.
```

Start with Level A. Use Level C when a Chromebook, iPad, phone, or school-managed device cannot show the graphical app directly.

## Safe Project Check

For `SPRK-Hello-Ursina`, use:

```bash
python -m core.main --check
```

The check validates project structure and student-facing menu setup without opening the 3D window.

## Ursina Graphics Limits

If Codespaces shows this:

```text
Exception: No graphics pipe is available!
```

that means Ursina/Panda3D cannot find a graphical display.

Use the safe check in Codespaces:

```bash
python -m core.main --check
```

Run the visible app on a graphics-capable laptop:

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
