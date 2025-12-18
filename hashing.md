# 🔐 Hashing in Cybersecurity – Complete Notes

This document explains **hashing concepts**, **hash algorithms**, **hash tables**, **attacks**, and **HMAC**, written for cybersecurity learners.

---

## 1. What is Hashing?

Hashing is a **one-way process** that converts **input data of any size** into a **fixed-size output** called a **hash value (digest)**.

- One-way (cannot be reversed)
- No secret key
- Same input → same output

Used for:
- File integrity
- Password storage
- Digital signatures
- Malware identification

---

## 2. Core Properties of Hash Functions

### 2.1 Deterministic
Same input always produces the same hash.

---

### 2.2 Fixed Output Size
No matter how large the input is, the output size is always the same.

Examples:
- SHA-256 → 256 bits
- SHA-3-256 → 256 bits

---

### 2.3 Avalanche Effect
A very small change in input causes a **completely different hash output**.

This prevents guessing and pattern detection.

---

### 2.4 Collision Resistance
It should be **computationally infeasible** to find two different inputs that produce the same hash.

---

## 3. How Hashing Works (High Level)

1. Input data is converted to binary
2. Padding is added
3. Data is split into fixed-size blocks
4. Blocks are mixed using complex operations
5. Final fixed-size hash is produced

Large files are hashed **block by block (streaming)**, not loaded fully into memory.

---

## 4. Operations Used in Hashing

Hash algorithms use multiple operations together:

- XOR
- AND
- OR
- NOT
- Bit shifts
- Bit rotations
- Modular addition
- Permutation

Security comes from **repeated mixing**, not from a single operation.

---

## 5. Common Hash Algorithms

| Algorithm | Status | Notes |
|--------|------|------|
| MD5 | ❌ Broken | Collisions found |
| SHA-1 | ❌ Broken | Collision attacks |
| SHA-256 | ✅ Secure | Widely used |
| SHA-512 | ✅ Secure | Larger word size |
| SHA-3 | ✅ Secure | Sponge construction |
| BLAKE2 / BLAKE3 | ✅ Secure | Fast & modern |

---

## 6. Hash vs Hash Table (Important Difference)

### Cryptographic Hash
- Used for security
- One-way
- Data cannot be recovered
- Example: SHA-256

### Hash Table
- Data structure (programming concept)
- Used for fast lookup
- Stores actual data (key → value)
- Data **can be retrieved**

Collision in hash tables happens when two keys map to the same index.

---

## 7. Hash Attacks

### 7.1 Collision Attack
Finding two different inputs with the same hash.

**Prevention:**  
Use SHA-256 or SHA-3.

---

### 7.2 Preimage Attack
Given a hash, trying to find the original input.

**Prevention:**  
Large hash size, slow password hashing.

---

### 7.3 Birthday Attack
Uses probability to find **any collision** faster than brute force.

- n-bit hash → collision in ~2ⁿᐟ² attempts

**Prevention:**  
Use 256-bit or higher hashes.

---

### 7.4 Length Extension Attack
Affects Merkle–Damgård hashes (MD5, SHA-1, SHA-256).

Allows attackers to:
- Append data
- Generate a valid new hash
- Without knowing the secret

**Root cause:**  
Using `hash(secret || message)` incorrectly.

---

## 8. HMAC (Hash-based Message Authentication Code)

### 8.1 What is HMAC?
HMAC combines:
- Hash function
- Secret key

Purpose:
- Integrity
- Authenticity

HMAC is **NOT encryption**.

---

### 8.2 How HMAC Works (Concept)

- Sender sends: `message + MAC`
- Receiver recomputes MAC using same key
- MACs are compared

If they match → message is valid and authentic.

---

### 8.3 Why HMAC is Secure

- Secret key is never sent
- Double hashing hides internal state
- Prevents length extension attacks
- Collision attacks are useless without the key

---

## 9. Hash vs HMAC

| Feature | Hash | HMAC |
|------|------|------|
| Uses secret key | ❌ | ✅ |
| Integrity | ✅ | ✅ |
| Authenticity | ❌ | ✅ |
| Prevents forgery | ❌ | ✅ |
| Prevents length extension | ❌ | ✅ |

---

## 10. How HMAC Keys Are Shared

- During setup or provisioning
- Using HTTPS / TLS
- Using key exchange (Diffie-Hellman, ECDH)
- Never sent in plain text

---

## 11. Key Takeaways

- Hashing is one-way and irreversible
- Hash tables are different from cryptographic hashes
- Collisions are mathematically possible but should be infeasible
- Length extension is a **design misuse**, not a hash failure
- HMAC fixes authentication weaknesses of hashes

---

## 12. Final One-Line Summary

> **Hashing ensures integrity, HMAC ensures integrity plus authenticity, and correct usage matters more than the algorithm itself.**

---

# Screenshot of file integrity by hash

![file integriyt](screenshot/)


📌 **Recommended Algorithms Today**
- General hashing: SHA-256, SHA-3
- Authentication: HMAC-SHA256
- Passwords: Argon2, bcrypt

