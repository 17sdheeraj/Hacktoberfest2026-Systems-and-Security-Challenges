<div align="center">

# 🕵️ Cybersecurity · Level 2 - Digital Sleuth

![Level](https://img.shields.io/badge/Level-2%20%2F%204-yellow?style=for-the-badge)
![Track](https://img.shields.io/badge/Track-Cybersecurity-8a2be2?style=for-the-badge)
![PR Limit](https://img.shields.io/badge/PR%20Limit-1-red?style=for-the-badge)
![Difficulty](https://img.shields.io/badge/Difficulty-Beginner-brightgreen?style=for-the-badge)

**A packet capture and a photo. Two mysteries, one report.**

</div>

---

## 🎯 Objective

Get hands-on with the two most fundamental forms of digital forensics: reading raw network traffic, and pulling hidden data out of a file's metadata. No exploitation here - just careful looking.

---

## 🧩 Part 1 - PCAP Analysis

You're given `capture.pcap`, a network traffic capture. Somewhere in it, a login happened over **plain, unencrypted HTTP**.

**Your task:**
1. Open `capture.pcap` in **Wireshark**.
2. Filter for HTTP traffic (`http` display filter is a good start).
3. Find the request where login credentials were submitted in the clear.
4. Extract the **username and password**.

---

## 🖼️ Part 2 - Image Forensics

You're given `evidence.jpg`. It looks like an ordinary photo - but its metadata knows more than it's letting on.

**Your task:**
1. Run `exiftool evidence.jpg` (or any metadata reader of your choice).
2. Extract the **GPS coordinates** embedded in the file.
3. Note the **camera make/model and software** used to create or edit it.

---

## 📂 Provided artifacts

```
cybersecurity/level-2-sleuth/artifacts/
├── capture.pcap
└── evidence.jpg
```

Don't modify these - copy them locally if you need to, but the originals in `artifacts/` stay untouched for everyone else.

---

## 📦 Deliverables

Place this inside `cybersecurity/level-2-sleuth/<your-github-username>/`:

```
cybersecurity/level-2-sleuth/<your-github-username>/
└── report.md
```

Your `report.md` must include:

- 🔑 The **extracted credentials** from the PCAP (username + password)
- 📍 The **GPS coordinates** from the image, plus what location they resolve to (a quick reverse-geocode lookup is fine)
- 📷 The **camera/software details** found in the metadata
- 🛠️ The **exact Wireshark filter(s)** and **exiftool/tool commands** you used

---

## 🚀 How to submit

1. Grab the artifacts and work through both parts.
2. Create your folder: `cybersecurity/level-2-sleuth/<your-github-username>/`
3. Write up your findings in `report.md`.
4. Open a PR titled `Cybersecurity L2 - <your-github-username>`.

> ⚠️ **One PR only** for this level.

---

## 💡 Tips

- Wireshark's `http.request.method == "POST"` filter narrows things down fast if the plain `http` filter gives you too much noise.
- `exiftool` is free and cross-platform - [ExifTool by Phil Harvey](https://exiftool.org/) - or use any online EXIF viewer if you'd rather not install anything.
- This is about developing an eye for what's hiding in plain sight - both skills come up constantly in real incident response and OSINT work.

---

<div align="center">

Cleared this? **[On to Level 3 - Crack the Vault & Web Basics →](../level-3-vault/)**

</div>
