<div align="center">

# 🕹️ Enigma Hacktoberfest 2026

### Systems and Security - one repo, one ladder, four levels.

![Hacktoberfest](https://img.shields.io/badge/Hacktoberfest-2026-blueviolet?style=for-the-badge&logo=hacktoberfest&logoColor=white)
![Made by Enigma](https://img.shields.io/badge/Made%20by-Enigma%20CS%20Club-000000?style=for-the-badge)
![PRs Welcome](https://img.shields.io/badge/PRs-Welcome-brightgreen?style=for-the-badge)
![Levels](https://img.shields.io/badge/Levels-4-orange?style=for-the-badge)

</div>

---

## 📖 What is this?

This is **Enigma's official Hacktoberfest 2026 challenge repository for the Systems and Security sub-committee**, merging what used to be two separate committees - **SysCom** and **Cybersecurity** - into a single ladder anyone can climb.

You start together, then pick your path:

```
                    ┌─────────────────────────┐
                    │   Level 1 - Networking  │
                    │   (everyone, together)  │
                    └────────────┬────────────┘
                                 │
                  ┌──────────────┴──────────────┐
                  ▼                              ▼
        🖥️  SYSCOM BRANCH                🔐  CYBERSECURITY BRANCH
        Level 2 → Terminal Trivia         Level 2 → Digital Sleuth
        Level 3 → System Inspector        Level 3 → Crack the Vault
        Level 4 → The Toolkit (multi-PR)  Level 4 → HTB Arena (multi-PR)
```

---

## 🧭 How the levels work

| Level | Scope | PR limit | Difficulty |
|:-----:|-------|:--------:|:-----------|
| 🟢 **1** | Common - Networking | **1 PR** | Beginner |
| 🟡 **2** | Branch - Terminal Trivia / Digital Sleuth | **1 PR** | Beginner |
| 🟠 **3** | Branch - System Inspector / Crack the Vault |**1 PR/ 2 PRs** | Intermediate |
| 🔴 **4** | Branch - Toolkit / HTB Arena | **Multiple PRs** | Increasingly hard |

> ⚠️ **Levels 1–3 are strictly single-attempt.** One PR per participant, per level (with an exception for Cybersecurity **only**). This keeps the early ladder fair - everyone gets exactly one shot to prove they've cleared it, no farming easy points.
>
> 🚀 **Level 4 is where you go wild.** Multiple PRs are allowed, but each one must be **harder than your last**. Coast at the easy tier forever, and your later PRs simply won't count - see each Level 4 README for its own difficulty tiers.

---

## 📁 Repository structure

```
.
├── README.md
├── level-1/
│   └── <github-username>/
├── level-2/
│   ├── Cybersecurity/<github-username>/
│   └── SysCom/<github-username>/
├── level-3/
│   ├── Cybersecurity/<github-username>/
│   └── SysCom/<github-username>/
└── level-4/
    ├── Cybersecurity/<github-username>/
    └── SysCom/<github-username>/
 ```

Every submission lives in a folder named **exactly** after your GitHub username. This is non-negotiable - it's how we track progression and enforce PR limits.

---

## 🚦 Getting started

1. **Fork** this repository and clone it locally.
2. **Pick your level.** Everyone starts at Level 1. After that, branch into 🖥️ SysCom or 🔐 Cybersecurity - or both, if you're feeling ambitious.
3. **Read that level's README** inside its folder - each one has the full challenge spec, deliverables, and grading notes.
4. **Create your folder**: `<branch>/<level>/<your-github-username>/`
5. **Do the challenge**, drop your deliverables in, and open a PR.
6. **Wait for review** - a maintainer (me) will check your submission against that level's checklist and merge or request changes.

---

## ✅ Contribution rules

- One PR = one level attempt, for Levels 1–3. A second PR to a level you've already submitted to will be closed (with the exception being **only** for Cybersecurity).
- Your submission folder name **must match your GitHub username exactly**.
- No AI-generated write-ups pretending to be your own investigation - we can tell, and it's not the point of the exercise.
- Anything involving scanning, exploitation, or cracking stays **inside the provided artifacts / your own lab / HTB's own infrastructure**. Never point these tools at anything you don't own or haven't been explicitly given permission to test.

---

## 🏆 Why bother?

- Level 4 is a genuine skill ladder: finish it and you'll have touched shell scripting, process monitoring, environment automation, packet analysis, hash cracking, web exploitation, and real HackTheBox machines.
- Bragging rights. Obviously.

---

<div align="center">

**Questions?** Ping me in the the Enigma Discord (@the_sun_god) or open an issue.
Good luck, and welcome to the Hacktoberfest. 🕹️

</div>
