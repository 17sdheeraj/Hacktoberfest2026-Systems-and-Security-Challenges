<div align="center">

# 🏴 Cybersecurity · Level 4 - HTB Starting Point Arena

![Level](https://img.shields.io/badge/Level-4%20%2F%204-red?style=for-the-badge)
![Track](https://img.shields.io/badge/Track-Cybersecurity-8a2be2?style=for-the-badge)
![PR Limit](https://img.shields.io/badge/PR%20Limit-Multiple-9cf?style=for-the-badge)
![Difficulty](https://img.shields.io/badge/Difficulty-Escalating-critical?style=for-the-badge)
![Platform](https://img.shields.io/badge/Platform-HackTheBox-9fef00?style=for-the-badge&logo=hackthebox&logoColor=black)

**The endgame. Real machines, real flags - and it gets harder with every one you take.**

</div>

---

## 🎯 Objective

Enumerate and exploit real, intentionally vulnerable machines on **HackTheBox's Starting Point (Tier 0)** track. Like SysCom's Level 4, you can submit **multiple PRs here** - but each one must target a harder machine than your last.

---

## 📈 The progressive tiers

| PR | Tier | Machine | OS | Skill focus | Difficulty |
|:--:|------|---------|----|-------------|:----------:|
| **Task 1** | 🟢 Entry | **Meow** or **Fawn** | Linux | Telnet / FTP service enumeration | ⭐ |
| **Task 2** | 🟡 Medium | **Dancing** | Windows | Unauthenticated SMB share navigation | ⭐⭐ |
| **Task 3** | 🔴 Hard | **Redeemer** | Linux | Redis database exploitation | ⭐⭐⭐ |

> **The rule:** your *n*-th PR to this level must be at the *n*-th tier or higher. A second PR at Meow-level doesn't count as progress. One machine (PR 1) is a complete, valid Level 4 contribution on its own - going further is extra credit, not a requirement.

---

## 🗂️ Tier details

### 🟢 Task 1 - Meow *or* Fawn
Both are the traditional "first HTB box" - a service with no authentication at all handing you a flag almost immediately. The point isn't difficulty, it's learning the enumerate → connect → flag workflow you'll reuse for the rest of your career. You are free to do both.

### 🟡 Task 2 - Dancing
An unauthenticated SMB share on a Windows box. You'll practice `smbclient`/`smbmap`-style enumeration and navigating shares without credentials.

### 🔴 PR 3 - Redeemer
An exposed Redis instance with no authentication. This is your first real taste of exploiting a misconfigured service rather than just reading a banner.

---

## 📦 Deliverables

Place a `report.md` per machine, inside `cybersecurity/level-4-htb/<your-github-username>/<machine-name>/`:

```
cybersecurity/level-4-htb/<your-github-username>/
├── meow/
│   └── report.md
└── dancing/
    └── report.md
```

Each `report.md` must include:

- 🔎 **Full Nmap scan results** for the target
- 📝 A **step-by-step walkthrough** of your enumeration and exploitation process
- 🚩 The **recovered flags**
- 🖼️ A **screenshot showing your active HTB session / target IP**, proving the work was done live against the actual machine

---

## 🚀 How to submit

1. Spin up your HTB VPN connection and target the machine for your current tier.
2. Work through enumeration to flag.
3. Write your `report.md` in a folder named after the machine.
4. Open a PR titled `Cybersecurity L4 [PRn] - <your-github-username>` (e.g. `Cybersecurity L4 [PR2] - thesungod07`).
5. Note in the PR description which tier this is and confirm your prior Level 4 submission(s), if any.

> The maintainer (me) will check if each new PR targets an equal-or-higher tier than your last merged Level 4 submission before merging.

---

## ⚖️ Ground rules - read this one

- **Only attack the specific HTB machine assigned to your tier**, on HTB's own infrastructure, through your own HTB account and VPN.
- Never point any tool, technique, or script from this challenge at a system you don't own or haven't been explicitly authorized to test - that includes anything outside HTB.
- Sharing exact flag values publicly (outside your own PR, to someone else who hasn't solved it) isn't in the spirit of the challenge - write your own walkthrough.

---

## 💡 Tips

- **[HTB Starting Point](https://app.hackthebox.com/starting-point)** is free with a Hack The Box account - no subscription required for Tier 0.
- Always start enumeration with a full Nmap scan (`nmap -sC -sV -p- <target-ip>`) before reaching for any tool-specific tricks.
- Take notes *as you go*, not after - a report written from memory afterward always misses details a reviewer will ask about.
- Stuck? HTB's own community forum and the Starting Point track's built-in hints exist precisely so you don't need to look outside HTB for help.

---

<div align="center">

That's the full Cybersecurity ladder. Go get your flags. 🏴

</div>
