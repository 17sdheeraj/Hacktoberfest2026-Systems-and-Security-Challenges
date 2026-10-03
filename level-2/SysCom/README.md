<div align="center">

# 🖥️ SysCom · Level 2 - Linux Systems & Terminal Trivia

![Level](https://img.shields.io/badge/Level-2%20%2F%204-yellow?style=for-the-badge)
![Track](https://img.shields.io/badge/Track-SysCom-2ea44f?style=for-the-badge)
![PR Limit](https://img.shields.io/badge/PR%20Limit-1-red?style=for-the-badge)
![Difficulty](https://img.shields.io/badge/Difficulty-Beginner-brightgreen?style=for-the-badge)

**Five questions. One terminal. One flag.**

</div>

---

## 🎯 Objective

Get comfortable moving around a Linux system - the filesystem hierarchy, key config files, and the search commands you'll use constantly for the rest of this repo. You'll answer five trivia questions **by actually inspecting a Linux system**, not by guessing or Googling the flag format.

---

## 🕵️ The five questions

| # | Clue | What you're finding |
|---|------|----------------------|
| 1 | A dynamic pseudo-filesystem directory holding live process and hardware info | A special top-level directory |
| 2 | A configuration file inside `/etc` that stores user account information | A specific file |
| 3 | The command-line tool used to search for text matching a pattern | A specific command |
| 4 | The directory containing system admin binaries meant for root | A specific `/` subdirectory |
| 5 | The environment variable that stores executable search paths | A specific environment variable name |

> 💡 You genuinely need a Linux terminal for this - a VM, WSL, a cloud shell, or a Raspberry Pi all work fine.

---

## 🚩 Flag format

Combine your five answers, lowercase, separated by underscores:

```
ans1_ans2_ans3_ans4_ans5
```

**Example shape** (not the real answer - go find it yourself):
```
proc_passwd_grep_sbin_PATH
```

---

## 📦 Deliverables

Place this inside `syscom/level-2-terminal/<your-github-username>/`:

```
syscom/level-2-terminal/<your-github-username>/
└── solution.txt
```

Your `solution.txt` **must** contain:

```
Line 1:  your combined flag
Line 2+: verification - the actual commands you ran to arrive at each answer
```

Example structure:

```
proc_passwd_grep_sbin_PATH

Q1: ls / → confirmed /proc exists, cat /proc/cpuinfo shows live hardware info
Q2: cat /etc/passwd → shows username:x:UID:GID:...
Q3: man grep → "print lines matching a pattern"
Q4: ls / → /sbin present, confirmed via man hier
Q5: echo $PATH → shows the executable search path
```

---

## 🚀 How to submit

1. Open a terminal on any Linux system (or WSL/VM/cloud shell).
2. Work through all five clues - actually run the commands, don't just recall them.
3. Create your folder: `syscom/level-2-terminal/<your-github-username>/`
4. Add your `solution.txt` with the flag on line 1 and your verification trail below it.
5. Open a PR titled `SysCom L2 - <your-github-username>`.

> ⚠️ **One PR only** for this level. Get all five right before you submit.

---

## 💡 Tips

- `man <command>` and `man hier` (filesystem hierarchy) are your best friends here.
- No Linux machine handy? [WSL](https://learn.microsoft.com/en-us/windows/wsl/install) on Windows, or any free-tier cloud shell, gets you there in minutes.

---

<div align="center">

Cleared this? **[On to Level 3 - System Health Inspector →](../level-3/SysCom/)**

</div>
