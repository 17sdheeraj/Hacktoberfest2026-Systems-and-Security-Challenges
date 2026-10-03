# Sample Report - Hash Cracking

> ⚠️ **This is a formatting reference only.** The hash, tool output, and
> password below are fictional and unrelated to `hash.txt` in this repo's
> `artifacts/` folder.

---

## Hash Provided

```
5f4dcc3b5aa765d61d8327deb882cf99
```

## Step 1 - Identifying the Algorithm

The hash is 32 hex characters long, which narrows it down immediately -
that length is characteristic of one specific common algorithm family.

```bash
$ hashid '5f4dcc3b5aa765d61d8327deb882cf99'
Analyzing '5f4dcc3b5aa765d61d8327deb882cf99'
[+] MD2
[+] MD5
[+] MD4
```

Given the length and the lack of any prefix (like `$2y$` for bcrypt or
`$6$` for SHA-512crypt), I concluded this was a straightforward **MD5**
hash - no salt, no iteration count, just a raw digest.

## Step 2 - Choosing a Cracking Tool and Wordlist

I used **Hashcat** with mode `0` (MD5) against the standard `rockyou.txt`
wordlist that ships with Kali:

```bash
$ hashcat -m 0 -a 0 my_hash.txt /usr/share/wordlists/rockyou.txt.gz
```

- `-m 0` tells Hashcat which algorithm to target (MD5 in this example).
- `-a 0` selects a straight dictionary attack - no rules or masks needed
  for a wordlist-based crack like this one.

## Step 3 - Result

```
5f4dcc3b5aa765d61d8327deb882cf99:REDACTED_EXAMPLE_PASSWORD
```

**Cracked password:** `REDACTED_EXAMPLE_PASSWORD` *(placeholder - this is
where your real recovered password goes)*

## Notes

- Always confirm your guess about the algorithm before you spend an hour
  cracking against the wrong mode - a quick `hashid` or `hash-identifier`
  check up front saves a lot of wasted GPU time.
- If a wordlist attack fails, don't jump straight to brute force - try
  Hashcat's built-in rule sets (`-r rules/best64.rule`) against the same
  wordlist first. Rules mutate each wordlist entry (capitalization,
  appended digits, leetspeak) and catch a surprising number of real-world
  passwords that a raw dictionary attack misses.

---

*Your actual report should follow this same shape: identify → tool +
command → result → what you learned. Swap every value above for your
own findings against the real `hash.txt`.*
