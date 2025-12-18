# Asymmetric Cryptography – Practical Guide

> A beginner‑friendly, real‑world oriented summary of **asymmetric cryptography**, based on hands‑on learning and practical understanding.

---

## 1. What Is Asymmetric Cryptography?
Asymmetric cryptography is a cryptographic system that uses **two mathematically related keys**:

- **Public Key** → can be shared with anyone
- **Private Key** → kept secret by the owner

### Core idea
```
Public key  → Encrypt / Verify
Private key → Decrypt / Sign
```

This solves the **key‑sharing problem** of symmetric encryption.

---

## 2. Why Asymmetric Cryptography Is Needed

Problems it solves:
- Secure communication over an **insecure network**
- Identity verification
- Secure key exchange
- Digital signatures

Used everywhere:
- HTTPS / TLS
- Secure messaging
- Certificates
- Software updates

---

## 3. How Asymmetric Encryption Works (High Level)

1. Receiver generates **public & private key**
2. Sender encrypts data using **public key**
3. Ciphertext is sent over network
4. Receiver decrypts using **private key**

Important rule:
> Anyone can encrypt, only the private key owner can decrypt.

---

## 4. RSA (Rivest–Shamir–Adleman)

### What RSA Is
- Asymmetric algorithm
- Can **encrypt** and **sign**
- Based on **prime number factorization**

### RSA Key Concept
- Public key → `(e, n)`
- Private key → `(d, n)`

### RSA Uses
- Encrypt small data (like AES keys)
- Digital signatures
- Certificates

### Limitations
- Very slow
- Cannot encrypt large data
- Large key sizes

> RSA is mainly used to protect **keys**, not files.

---

## 5. ECC (Elliptic Curve Cryptography)

ECC is a **cryptographic system**, not a single algorithm.

### What ECC Is Used For
- **ECDH** → Key exchange
- **ECDSA / EdDSA** → Digital signatures

### Why ECC Is Better Than RSA
| Feature | RSA | ECC |
|------|-----|-----|
| Key size | Very large | Very small |
| Speed | Slow | Fast |
| Mobile / IoT | ❌ | ✅ |
| Forward secrecy | ❌ | ✅ |

ECC provides **same security with much smaller keys**.

---

## 6. Diffie‑Hellman & ECDH (Key Exchange)

### What Key Exchange Means
Securely agreeing on a **shared secret key** over an insecure network.

### Important
- ❌ Does NOT encrypt data
- ✅ Only creates a shared secret

### Real‑world flow
```
ECDH → Shared secret
AES  → Encrypt data
```

Used in:
- TLS 1.2 / 1.3
- HTTPS
- VPNs

---

## 7. Why Hybrid Encryption Is Used

Asymmetric encryption is slow.

### Real‑world solution
```
Asymmetric (RSA / ECDH) → Secure AES key
AES → Encrypt actual data
```

Used in:
- HTTPS
- Secure file storage
- Messaging apps

Rule to remember:
> RSA/ECC protect keys, AES protects data.

---

## 8. Digital Signatures (Short Overview)

Digital signatures provide:
- Authentication
- Integrity
- Non‑repudiation

They do **NOT** hide data.

### Signature Flow
```
Message → Hash → Sign (Private key)
Message + Signature → Verify (Public key)
```

---

## 9. RSA vs DSA vs ECDSA (Signatures)

| Algorithm | Encrypt | Sign | Status |
|--------|--------|------|------|
| RSA | ✅ | ✅ | Legacy / still used |
| DSA | ❌ | ✅ | Deprecated |
| ECDSA | ❌ | ✅ | Modern |
| EdDSA | ❌ | ✅ | Modern & secure |

DSA is **signature‑only** and mostly replaced by ECDSA/EdDSA.

---

## 10. Common Beginner Mistakes

❌ Encrypting files directly with RSA  
❌ Trying to decode ciphertext as text  
❌ Losing private key  
❌ Implementing crypto math manually

✅ Use libraries  
✅ Use hybrid encryption  
✅ Store keys securely

---

## 11. Real‑World Mapping

| Purpose | Algorithm |
|------|----------|
| Key exchange | ECDH |
| Data encryption | AES |
| Digital signature | ECDSA / RSA |
| Certificates | RSA / ECC |
| Password storage | Hashing |

---

## 12. Final Summary

- Asymmetric cryptography uses **two keys**
- It solves **secure communication & trust**
- It is **not used for bulk data encryption**
- Modern systems use **ECC + AES**

> Cryptography in the real world is about **privacy, trust, and secure communication**.

---

## 📌 One‑Line GitHub Description
A practical beginner‑friendly guide to asymmetric cryptography, covering RSA, ECC, ECDH, hybrid encryption, and digital signatures with real‑world context.

