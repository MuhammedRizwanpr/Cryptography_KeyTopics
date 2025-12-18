# 🔐 Encryption vs 🔄 Encoding vs #️⃣ Hashing

Understanding the difference between **Encryption**, **Encoding**, and **Hashing** is **fundamental in cybersecurity**.  
Although they all transform data, **their purpose and security properties are completely different**.

---

## 📌 Quick Summary Table

| Feature | Encryption | Encoding | Hashing |
|------|----------|---------|--------|
| Purpose | Protect data | Data formatting & compatibility | Data integrity & verification |
| Reversible | ✅ Yes (with key) | ✅ Yes | ❌ No |
| Key Used | ✅ Yes | ❌ No | ❌ No |
| Security | 🔐 High | ❌ None | 🔒 Medium (one-way) |
| Output Size | Same or larger | Usually larger | Fixed length |
| Main Use | Confidentiality | Transmission & storage | Integrity & authentication |

---

## 🔐 Encryption

### What is Encryption?
Encryption converts **plaintext into ciphertext** using a **key** so that **only authorized users** can read the data.

### Why Encryption?
- Protect sensitive data
- Prevent unauthorized access
- Ensure confidentiality

### Types of Encryption
- **Symmetric Encryption**
  - Same key for encrypt & decrypt
  - Example: AES, DES, 3DES
- **Asymmetric Encryption**
  - Public key & private key
  - Example: RSA, ECC

### Example
Text: HELLO
Base64 :SEVMTE8=


### Key Point ⚠️
> **Anyone can decode encoded data. Encoding provides NO security.**

### Real-World Uses
- Email attachments
- Web data transmission
- File formats
- APIs

---

## #️⃣ Hashing

### What is Hashing?
Hashing converts data into a **fixed-length value** using a **hash function**.  
It is **one-way** and **cannot be reversed**.

### Why Hashing?
- Verify data integrity
- Store passwords securely
- Detect changes in data

### Common Hash Algorithms
- MD5 ❌ (Broken)
- SHA-1 ❌ (Broken)
- SHA-256 ✅
- SHA-3 ✅
- Bcrypt / Argon2 (password hashing)

### Example
Input: HELLO
Hash: 185F8DB32271FE25F561A6FC938B2E264306EC304EDA518007D1764826381969


### Real-World Uses
- Password storage
- File integrity checks
- Digital signatures
- Blockchain

---

## 🧠 Core Differences (Simple Words)

| Question | Encryption | Encoding | Hashing |
|-------|-----------|---------|--------|
| Can I get original data back? | ✅ Yes (with key) | ✅ Yes | ❌ No |
| Is it secure? | ✅ Yes | ❌ No | 🔒 Yes (one-way) |
| Used for secrecy? | ✅ Yes | ❌ No | ❌ No |
| Used for verification? | ❌ No | ❌ No | ✅ Yes |

---

## 🧪 Cybersecurity Interview Tip

👉 **Encoding ≠ Encryption**  
👉 **Hashing ≠ Encryption**  

- **Encryption** → Protect data  
- **Encoding** → Transport data  
- **Hashing** → Verify data  

---

## 📚 Quick Real-World Mapping

| Scenario | Technique |
|------|---------|
| Secure website (HTTPS) | Encryption |
| Email attachment | Encoding |
| Login password storage | Hashing |
| File integrity check | Hashing |
| API data transfer | Encoding |

---

## ✅ Final Takeaway

> **Encryption hides data**  
> **Encoding changes data format**  
> **Hashing fingerprints data**

Mastering this difference is **mandatory for cybersecurity, cryptography, and interviews**.

---

### ⭐ Suggested Next Topics
- Symmetric vs Asymmetric Encryption  
- AES vs RSA  
- Salted Password Hashing  
- HMAC  
- Digital Signatures  

---

📌 *Author: Cybersecurity Learner*  
📌 *Purpose: Learning & GitHub Notes*
