# Report - Hash Cracking

## Hash Provided

```text
5fcfd41e547a12215b173ff47fdd3739
```

---

## Step 1 - Identifying the Algorithm

The given hash is 32 hexadecimal characters (128 bits) in length. This immediate characteristic narrows the hash down to standard 128-bit digest functions. Furthermore, there is no salt identifier or standard Unix crypt/modular crypt prefix (such as `$1$`, `$5$`, `$6$`, or `$2y$`).

Running `hashid` against the hash signature confirms potential matches:

```bash
$ hashid '5fcfd41e547a12215b173ff47fdd3739'
Analyzing '5fcfd41e547a12215b173ff47fdd3739'
[+] MD2
[+] MD5
[+] MD4
```

Given the length, format, and common use in security challenges, the algorithm is identified as unsalted **MD5** (Raw Digest).

---

## Step 2 - Choosing a Cracking Tool and Wordlist

I used **Hashcat** targeting MD5 (`-m 0`) with a straight dictionary attack (`-a 0`) using the classic `rockyou.txt` wordlist:

```bash
$ hashcat -m 0 -a 0 ../../artifacts/hash.txt /usr/share/wordlists/rockyou.txt
```

### Execution Details
- `-m 0`: Tells Hashcat to target raw MD5 hashes.
- `-a 0`: Selects straight dictionary mode (wordlist attack without mutations).
- Hash file: `hash.txt` (`5fcfd41e547a12215b173ff47fdd3739`)
- Wordlist: `rockyou.txt`

Hashcat terminal output:

```text
Session..........: hashcat
Status...........: Cracked
Hash.Mode........: 0 (MD5)
Hash.Target......: 5fcfd41e547a12215b173ff47fdd3739
Time.Started.....: Wed Oct  7 11:03:03 2026 (0 secs)
Time.Estimated...: Wed Oct  7 11:03:03 2026 (0 secs)
Kernel.Feature...: Pure Kernel (password length 0-256 bytes)
Guess.Base.......: File (rockyou.txt)
Guess.Queue......: 1/1 (100.00%)
Speed.#01........: 3389.4 kH/s (1.12ms)
Recovered........: 1/1 (100.00%) Digests (total), 1/1 (100.00%) Digests (new)
Progress.........: 8192/14344384 (0.06%)
Restore.Point....: 0/14344384 (0.00%)
```

---

## Step 3 - Result

```text
5fcfd41e547a12215b173ff47fdd3739:trustno1
```

- **Cracked Password:** `trustno1`

### Verification

Verifying the digest using standard `md5sum`:

```bash
$ echo -n "trustno1" | md5sum
5fcfd41e547a12215b173ff47fdd3739  -
```

The computed digest matches `hash.txt` exactly.

---

## Notes & Key Learnings

- **Algorithm Identification:** Checking length (32 hex characters = 128 bits) and format eliminates slower key-derivation algorithms (bcrypt, Argon2, PBKDF2) right away and points to older algorithms like MD5.
- **Speed of Unsalted MD5:** Unsalted MD5 is computationally lightweight, allowing dictionary candidates to be tested within milliseconds (found at line ~1,000 of `rockyou.txt` almost instantaneously).
- **Security Implications:** Raw unsalted MD5 offers virtually zero protection against dictionary and precomputed rainbow table attacks. Modern applications must use salted, memory-hard key derivation functions such as Argon2id or bcrypt.
