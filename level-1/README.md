<div align="center">

# 🌐 Level 1 - Inter-Subnet Office Networking

![Level](https://img.shields.io/badge/Level-1%20%2F%204-brightgreen?style=for-the-badge)
![Track](https://img.shields.io/badge/Track-Common-blue?style=for-the-badge)
![PR Limit](https://img.shields.io/badge/PR%20Limit-1-red?style=for-the-badge)
![Tool](https://img.shields.io/badge/Tool-Cisco%20Packet%20Tracer-00bceb?style=for-the-badge&logo=cisco)

**The one everyone does. Prove two networks can talk.**

</div>

---

## 🎯 Objective

Simulate a single office building with **two independent subnets** - say, HR and Tech - and connect them so devices on one subnet can successfully reach devices on the other, through proper routing.

This is your entry ticket to the rest of the ladder. Clear this, and you can proceed to the 🖥️ SysCom and 🔐 Cybersecurity branches.

---

## 🧩 The scenario

> Your office has two departments on separate subnets:
> - **HR** - `192.168.10.0/24`
> - **Tech** - `192.168.20.0/24`
>
> They're currently isolated. Your job is to wire them into a single working office network using a router (or L3 switch) doing inter-subnet routing, so a ping from HR reaches Tech and vice versa.

---

## 📋 Requirements

| # | Requirement |
|---|-------------|
| 1 | At least **2 PCs per subnet** (4 PCs total minimum) |
| 2 | At least **1 switch per subnet** |
| 3 | **1 router** (or Layer-3 switch) performing inter-subnet routing |
| 4 | Correct static IP addressing and default gateways on every PC |
| 5 | Router interfaces configured with the correct subnet + gateway IPs |
| 6 | A **successful ping** from an HR PC to a Tech PC, and back |

---

## 📦 Deliverables

Place these inside `level-1-networking/<your-github-username>/`:

```
level-1-networking/<your-github-username>/
├── network_topology.pkt      ← your Packet Tracer file
└── README.md                 ← write-up (see below)
```

Your `README.md` should include:

- 🖼️ A **screenshot** of your full topology
- 🖼️ A **screenshot** of a successful ping between the two subnets (the CLI or PC command-prompt output)
- 📊 An **IP addressing table**:

  | Device | Subnet | IP Address | Subnet Mask | Gateway |
  |--------|--------|------------|--------------|---------|
  | PC-HR-1 | HR | 192.168.10.2 | 255.255.255.0 | 192.168.10.1 |
  | PC-Tech-1 | Tech | 192.168.20.2 | 255.255.255.0 | 192.168.20.1 |
  | ... | ... | ... | ... | ... |

- 🗒️ A short note on **how you configured the router** (interfaces, IPs, any routing commands used)

---

## 🚀 How to submit

1. Build your topology in **Cisco Packet Tracer**.
2. Save the `.pkt` file.
3. Create your folder: `level-1-networking/<your-github-username>/`
4. Drop in your `.pkt` file and `README.md` write-up.
5. Open a PR titled `Level 1 - <your-github-username>`.

> ⚠️ **One PR only.** This level is a single-attempt gate - get your topology working before you submit.

---

## 💡 Tips

- Don't have Packet Tracer? [Download it free from the Cisco Networking Academy](https://www.netacad.com/courses/packet-tracer) (needs a free NetAcad account).
- Don't know networking? Check out [Networking Fundamentals](https://tryhackme.com/module/network-fundamentals)
- Static IPs are fine and expected - you don't need DHCP for this challenge.
- If your ping times out, check in order: PC IP/gateway → switch connections → router interface IPs → router interface status (`no shutdown`).
- Naming your PCs and switches clearly (`PC-HR-1`, `SW-Tech`, etc.) makes your screenshot far easier to review - and easier for you to debug.

---

<div align="center">

Once this is merged, pick your path: **[🖥️ SysCom →](../syscom/level-2-terminal/)** or **[🔐 Cybersecurity →](../cybersecurity/level-2-sleuth/)**

</div>
