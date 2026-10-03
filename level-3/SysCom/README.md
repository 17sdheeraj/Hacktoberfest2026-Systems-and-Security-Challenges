<div align="center">

# 🩺 SysCom · Level 3 - System Health Inspector

![Level](https://img.shields.io/badge/Level-3%20%2F%204-orange?style=for-the-badge)
![Track](https://img.shields.io/badge/Track-SysCom-2ea44f?style=for-the-badge)
![PR Limit](https://img.shields.io/badge/PR%20Limit-1-red?style=for-the-badge)
![Difficulty](https://img.shields.io/badge/Difficulty-Intermediate-orange?style=for-the-badge)

**Your first real script. Ten-ish lines, one job: report on the machine's health.**

</div>

---

## 🎯 Objective

Write a Bash script, `sys_check.sh`, that reports on the health of the machine it's run on - uptime, disk usage, RAM usage, and who's logged in where. This is your first proper "I wrote a tool" moment in the repo.

---

## 🧾 Requirements

Your script must print, in a readable format:

| Info | Command to base it on |
|------|------------------------|
| ⏱️ System uptime | `uptime` |
| 💾 Disk usage (human-readable) | `df -h` |
| 🧠 RAM usage (human-readable) | `free -h` |
| 👤 Current user | `whoami` |
| 🖥️ Hostname | `hostname` |

Format is up to you - headers, colored `echo` output, emoji, ASCII dividers, whatever makes it pleasant to read. This is meant to be simple, not stressful.

---

## 📦 Deliverables

Place these inside `syscom/level-3-inspector/<your-github-username>/`:

```
syscom/level-3-inspector/<your-github-username>/
├── sys_check.sh       ← your executable script
└── output.txt         ← output from running it (or a screenshot works too)
```

---

## 🚀 How to submit

1. Write `sys_check.sh` covering all five pieces of info above.
2. Make it executable: `chmod +x sys_check.sh`
3. Run it and capture the output - paste it into `output.txt`, or include a screenshot instead.
4. Create your folder: `syscom/level-3-inspector/<your-github-username>/`
5. Add both files.
6. Open a PR titled `SysCom L3 - <your-github-username>`.

> ⚠️ **One PR only** for this level.

---

## ✅ Example skeleton

```bash
#!/bin/bash
echo "===== SYSTEM HEALTH REPORT ====="
echo "Hostname : $(hostname)"
echo "User     : $(whoami)"
echo ""
echo "--- Uptime ---"
uptime
echo ""
echo "--- Disk Usage ---"
df -h
echo ""
echo "--- Memory Usage ---"
free -h
```

Feel free to go further - colorized sections, a summary line, whatever you like. It just needs to run cleanly and cover the five items.

---

## 💡 Tips

- Test your script on a clean terminal before submitting - a typo that only breaks on your machine's specific setup is an easy thing to miss.
- `free -h` isn't available on macOS by default - if you're on macOS, either script around it (`vm_stat`) or just run this on a Linux VM/WSL.
- Comment your script briefly - maintainer (and future-you) will thank you.

---

<div align="center">

Cleared this? **[On to Level 4 - The Systems Toolkit →](../level-4/SysCom/)**

</div>
