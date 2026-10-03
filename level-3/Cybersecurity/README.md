<div align="center">

# 🔐 Cybersecurity · Level 3 - Crack the Vault & Web Basics

![Level](https://img.shields.io/badge/Level-3%20%2F%204-orange?style=for-the-badge)
![Track](https://img.shields.io/badge/Track-Cybersecurity-8a2be2?style=for-the-badge)
![PR Limit](https://img.shields.io/badge/PR%20Limit-2-red?style=for-the-badge)
![Difficulty](https://img.shields.io/badge/Difficulty-Intermediate-orange?style=for-the-badge)

**Break a hash. Break a login. Welcome to offensive security.**

</div>

---

## 🎯 Objective

Two classic beginner offensive-security skills: cracking a password hash offline, and exploiting basic SQL injection on a legal, purpose-built practice target.

---

## 🔓 Part 1 - Hash Cracking

You're given `hash.txt`, containing a single password hash.

**Your task:**
1. Identify **which hashing algorithm** produced it (length and format are your clues - tools like `hashid` can help confirm).
2. Crack it using **John the Ripper** or **Hashcat**, against the `rockyou.txt` wordlist.
3. Recover the **plaintext password**.

---

## 🌐 Part 2 - Web SQL Injection

Complete **two Apprentice-level labs** on PortSwigger's free **Web Security Academy**:

1. **"SQL injection vulnerability in WHERE clause allowing retrieval of hidden data"**
2. **"SQL injection vulnerability allowing login bypass"**

Both are free, hosted, and legal to attack - that's the entire point of the Academy.

🔗 Start here: [PortSwigger Web Security Academy - SQL Injection](https://portswigger.net/web-security/sql-injection)
🔗 Find the labs [here](https://portswigger.net/web-security/all-labs)

---

## 📂 Provided artifacts

```
cybersecurity/level-3-vault/artifacts/
└── hash.txt
```

---

## 📦 Deliverables

Place this inside `cybersecurity/level-3-vault/<your-github-username>/`:

```
cybersecurity/level-3-vault/<your-github-username>/
└── report.md
```

Your `report.md` must include:

- 🧪 The **hash algorithm identified** and how you determined it
- 🔑 The **cracked password** and the exact command you ran
- 💉 The **SQLi payloads** used in each lab, with a short explanation of *why* each one works
- 🖼️ **Screenshots** of both labs' "Congratulations, you solved this lab" banners

---

## 🚀 How to submit

1. Crack the hash.
2. Solve both PortSwigger labs.
3. Create your folder: `cybersecurity/level-3-vault/<your-github-username>/`
4. Write up everything in `report.md`, with screenshots included or linked.
5. Open a PR titled `Cybersecurity L3 - <your-github-username>`.

> ⚠️ **Two PRs only** for this level (1 for the hash cracking, 1 for the PortSwigger Labs).

---

## 💡 Tips

- `hashcat --example-hashes` or `hashid hash.txt` will help you identify the algorithm before you burn time on the wrong cracking mode.
- `rockyou.txt` ships with most pentesting distros (Kali/Parrot) at `/usr/share/wordlists/rockyou.txt.gz` - remember to `gunzip` it first.
- PortSwigger's labs are entirely legal and self-contained - but the instinct you're building (try the payload, read the error, adjust) is one you should **only** ever point at systems you own or are explicitly authorized to test.
- Stuck on a lab? PortSwigger's own "View solution" links exist for a reason - using them and understanding *why* the fix works still counts as learning.

---

<div align="center">

Cleared this? **[On to Level 4 - HTB Starting Point Arena →](../../level-4/Cybersecurity/)**

</div>
