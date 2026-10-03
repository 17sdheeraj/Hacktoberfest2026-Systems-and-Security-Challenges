<div align="center">

# 🧰 SysCom · Level 4 - The Systems Toolkit

![Level](https://img.shields.io/badge/Level-4%20%2F%204-red?style=for-the-badge)
![Track](https://img.shields.io/badge/Track-SysCom-2ea44f?style=for-the-badge)
![PR Limit](https://img.shields.io/badge/PR%20Limit-Multiple-9cf?style=for-the-badge)
![Difficulty](https://img.shields.io/badge/Difficulty-Escalating-critical?style=for-the-badge)

**The endgame. Multiple PRs allowed - but each one has to earn it.**

</div>

---

## 🎯 Objective

Build a small toolkit of real automation scripts. Unlike Levels 1–3, you can submit **more than one PR here** - but the whole point of Level 4 is that it gets **progressively harder**. You can't just resubmit three easy scripts and call it done.

---

## 📈 The progressive tiers

| PR | Tier | Task | Difficulty |
|:--:|------|------|:----------:|
| **Task 1** | 🟢 Entry | **File Organizer** - sorts a messy directory's contents into subfolders by file extension | ⭐ |
| **Task 2** | 🟡 Medium | **Process Monitor** - watches a given process, logs downtime/crash events to `alerts.log` | ⭐⭐ |
| **Task 3** | 🔴 Hard | **Environment Bootstrapper** - detects the OS/distro and non-interactively installs `git`, `curl`, `python3` | ⭐⭐⭐ |

> Only doing one tier? Totally fine - PR 1 alone is a valid, complete Level 4 contribution. Going further is the bonus round, not a requirement.

---

## 🗂️ Task details

### 🟢 Task 1 - File Organizer Script
**Goal:** Given a directory, sort its files into subfolders by extension (`.pdf` → `pdfs/`, `.png` → `images/`, etc.)

**Must handle:**
- A configurable target directory (argument or hardcoded path - your call)
- Grouping unknown extensions into a catch-all folder (e.g. `misc/`)
- Not crashing on directories that already have subfolders inside them

---

### 🟡 Task 2 - Process Monitor Script
**Goal:** Monitor a specified process by name or PID, and log an alert whenever it goes down.

**Must handle:**
- Accepting a process name (or PID) to watch
- Polling at a reasonable interval
- Writing timestamped entries to `alerts.log` when the process stops responding or disappears
- Exiting cleanly (Ctrl+C shouldn't leave orphaned background jobs)

---

### 🔴 Task 3 - Environment Bootstrapper
**Goal:** Detect the OS/distro (Ubuntu, Debian, Fedora, Arch, macOS, etc.) and install `git`, `curl`, and `python3` **non-interactively** - no prompts the user has to sit and answer.

**Must handle:**
- Correct package manager per distro (`apt`, `dnf`, `pacman`, `brew`, ...)
- Skipping packages that are already installed
- Failing gracefully with a clear message on an unsupported OS, rather than crashing silently

---

## 📦 Deliverables

Place scripts inside `syscom/level-4-toolkit/<your-github-username>/`, one file per PR:

```
syscom/level-4-toolkit/<your-github-username>/
├── file_sorter.sh
├── process_monitor.sh
└── env_setup.sh
```

Each script should include a short header comment explaining usage:

```bash
#!/bin/bash
# Usage: ./PR1_file_sorter.sh <target_directory>
# Sorts files in <target_directory> into subfolders by extension.
```

---

## 🚀 How to submit

1. Pick the tier that matches your PR number (your 1st PR here = Tier 1 or higher, your 2nd = Tier 2 or higher, and so on).
2. Write and test the script.
3. Add it to your folder alongside any previous Level 4 submissions.
4. Open a PR titled `SysCom L4 [PRn] - <your-github-username>` (e.g. `SysCom L4 [PR2] - thesungod07`).
5. In the PR description, note which tier you're submitting and confirm your prior Level 4 PR(s), if any.

> A maintainer checks that each new PR is at an equal-or-higher tier than your last merged Level 4 PR before merging.

---

## 💡 Tips

- Test your scripts in a disposable VM or container before running them on your real machine - especially PR 3, which installs things.
- `shellcheck` is a great free linter for catching common Bash mistakes before you submit.
- Comment generously.

---

<div align="center">

That's the full SysCom ladder. Nice work. 🕹️

</div>
