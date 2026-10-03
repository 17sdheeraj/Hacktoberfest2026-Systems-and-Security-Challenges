# Sample Report - HTB Machine Writeup

> ⚠️ **This is a formatting reference only.** "Sandbox-01" is a fictional,
> made-up machine - it is not Meow, Fawn, Dancing, or Redeemer, and
> nothing below tells you how to solve any of those. It exists purely to
> show the *shape* a good report takes: what sections to include, how
> much detail to show your work with, and how to present a scan and a
> flag. Your actual report needs to reflect your own enumeration and
> exploitation of the real assigned machine.

---

## Machine: Sandbox-01 *(fictional example)*
**OS:** Linux ;
**Tier:** Example / Entry ;
**Service in scope:** SNMP

---

## 1. Reconnaissance

Every writeup should start with a full port scan - don't skip straight
to the service you already suspect is interesting, since a real
assessment (and a real reviewer) wants to see that you checked
everything first.

```bash
$ nmap -sC -sV -p- 10.10.10.XX -oN nmap/initial.txt

Starting Nmap 7.94 ( https://nmap.org )
Nmap scan report for 10.10.10.XX
Host is up (0.031s latency).

PORT    STATE SERVICE  VERSION
161/udp open  snmp     SNMPv1 server (example output)

Nmap done: 1 IP address (1 host up) scanned in 12.4 seconds
```

**Observation:** a single interesting service on a non-default port is
usually the intended path - but note it, don't assume it, until you've
tried interacting with it.

---

## 2. Enumeration

```bash
$ snmpwalk -v1 -c public 10.10.10.XX
```

*(In a real report: paste the actual command output here, or a relevant
excerpt of it - not just the command.)*

**Observation:** the service responded to a default/guessable community
string, meaning it may not be requiring proper authentication. This is
the kind of finding you'd note down and investigate further, rather than
immediately assume you know the fix for - every machine has its own
specific quirks.

---

## 3. Exploitation

*(This is where a real report walks through, step by step, what you
actually did to move from "found a weakness" to "got a shell" or
"recovered the flag" - commands run, output observed, and your reasoning
at each decision point. Because this is a fictional example, this
section is intentionally left generic: don't copy this structure with
placeholder text - fill it in with your own real steps.)*

```bash
$ <your actual command here>
<your actual output here>
```

---

## 4. Flag

```
[REDACTED IN THIS SAMPLE]
```

In your real submission, this is where the actual flag string goes -
along with a screenshot showing your terminal, the target IP, and your
active HTB session, as the Level 4 README requires.

---

## What a Good Report Includes

- ✅ Full scan output, not a cherry-picked single line
- ✅ Every command you ran, in the order you ran it - reviewers should be
  able to reproduce your path exactly
- ✅ Brief reasoning at each step: *why* you tried what you tried, not
  just *what* you tried
- ✅ The actual flag and a screenshot proving it was captured live
- ❌ No copy-pasted steps from someone else's public writeup - I
  can tell, and it defeats the entire point of the exercise

---

*Use this structure - Recon → Enumeration → Exploitation → Flag - for
your real machine. The sections above are a skeleton; the content has to
be yours.*
