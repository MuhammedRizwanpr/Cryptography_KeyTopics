# 🔐 Cryptography Roadmap for Cybersecurity

A complete, beginner-to-intermediate **cryptography learning roadmap** designed for **cybersecurity students, SOC analysts, and penetration testers**.

---

## 📌 What is Cryptography?
Cryptography is the science of protecting information by transforming readable data (**plaintext**) into an unreadable form (**ciphertext**) using mathematical algorithms and keys.

In cybersecurity, cryptography ensures:
- Secure communication
- Data protection
- User authentication
- Trust in digital systems

---

## 🎯 Core Security Goals (Features of Cryptography)
- **Confidentiality** – Prevents unauthorized access to data  
- **Integrity** – Detects unauthorized data modification  
- **Authentication** – Verifies identity  
- **Non-Repudiation** – Sender cannot deny actions  
- **Access Control** – Restricts unauthorized usage  

---

## 🧠 Cryptography Learning Roadmap

### 1️⃣ Cryptography Fundamentals
- Plaintext vs Ciphertext  
- Encryption vs Hashing vs Encoding  
- Keys and algorithms  
- Symmetric vs Asymmetric cryptography  
- Kerckhoffs’s Principle  
- Threat model basics  

---

### 2️⃣ Symmetric Key Cryptography
- Shared secret concept  
- Block cipher vs Stream cipher  

**Modes of Operation**
- ECB (insecure)
- CBC
- CTR
- GCM (recommended)

**Algorithms**
- AES (most important)
- DES (legacy)
- 3DES
- Blowfish
- ChaCha20

---

### 3️⃣ Asymmetric Key Cryptography
- Public key & private key  
- Key pair concept  
- Key exchange problem  
- Hybrid encryption  

**Algorithms**
- RSA  
- Diffie-Hellman (DH)  
- Elliptic Curve Cryptography (ECC)  
- ECDH  
- ECDSA  

---

### 4️⃣ Hash Functions
- One-way functions  
- Avalanche effect  
- Collision resistance  

**Algorithms**
- MD5 (broken)
- SHA-1 (broken)
- SHA-256 / SHA-512
- SHA-3
- BLAKE2 / BLAKE3

**Hash Attacks**
- Collision attack  
- Pre-image attack  
- Rainbow tables  
- Length extension attack  

---

### 5️⃣ Message Integrity & Authentication
- MAC (Message Authentication Code)  
- HMAC  
- Hash vs HMAC  
- Why hashing alone is not enough  

---

### 6️⃣ Digital Signatures
- Signing & verification process  
- Integrity + Authentication + Non-repudiation  

**Algorithms**
- RSA  
- DSA  
- ECDSA  
- EdDSA  

---

### 7️⃣ Key Management
- Key generation  
- Secure key storage  
- Key rotation  
- Key revocation  
- Key exchange mechanisms  
- Importance of strong randomness  

---

### 8️⃣ Cryptographic Protocols
- SSL vs TLS  
- TLS handshake  
- HTTPS  
- SSH  
- IPsec  
- WPA2 / WPA3  
- Kerberos  

---

### 9️⃣ Certificates & PKI
- X.509 certificates  
- Certificate Authority (CA)  
- Public Key Infrastructure (PKI)  
- Certificate chain  
- Root CA vs Intermediate CA  
- CRL & OCSP  

---

### 🔟 Password Security
- Password hashing vs encryption  
- Salting & peppering  
- Key stretching  

**Algorithms**
- bcrypt  
- scrypt  
- PBKDF2  
- Argon2  

---

### 1️⃣1️⃣ Cryptographic Attacks
- Brute force  
- Dictionary attack  
- Man-in-the-Middle (MITM)  
- Replay attack  
- Downgrade attack  
- Padding oracle attack  
- Side-channel attacks  
- Weak random number generation  

---

### 1️⃣2️⃣ Cryptography in Malware
- Encryption in malware  
- Ransomware crypto usage  
- Obfuscation vs encryption  
- Packed malware  
- Key storage in malicious code  

---

### 1️⃣3️⃣ Practical Cryptography (Hands-On)
- OpenSSL basics  
- File hashing  
- AES encryption/decryption  
- RSA key generation  
- Digital signature creation  
- TLS certificate inspection  

---

## 📸 RSA Demo – Screenshot Section

![RSA Key Generation](rsa_screenshot.png)

## Learning Resources
# Free Resources

- NIST Cryptography Standards

- OWASP Cryptographic Storage Cheat Sheet

- OpenSSL Documentation

- Cryptopals Crypto Challenges

## Books

- Cryptography and Network Security – William Stallings

- Serious Cryptography – Jean-Philippe Aumasson

- The Code Book – Simon Singh

## Practice Platforms

- TryHackMe (Cryptography rooms)

- Hack The Box (Crypto challenges)

- OverTheWire – Krypton

## Final Notes

Cryptography is not about memorizing algorithms.
It’s about understanding:

- Why cryptography is used

- Where it is used

- How it fails when misused

- This knowledge is essential for:

- Cybersecurity

- Penetration testing

- SOC analysis

- Malware analysis

- Incident response

