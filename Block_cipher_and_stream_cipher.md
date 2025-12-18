# Symmetric Encryption: Block Cipher vs Stream Cipher

This document explains **block ciphers** and **stream ciphers** in a simple and clear way, focusing on how they work internally.

---

## 1. What is Symmetric Encryption?

- Uses **one secret key** for both encryption and decryption
- Same key is shared by sender and receiver
- Works on **binary data (bits/bytes)**

---

## 2. Block Cipher

### What is a Block Cipher?
A block cipher encrypts data in **fixed-size blocks** using a secret key and multiple transformation rounds.

### Key Points
- Fixed block size  
  - AES: **128 bits**
  - DES: **64 bits**
- Data is split into blocks
- Padding is added if data is smaller than block size
- Uses **multiple rounds** of operations
- Requires a **mode of operation** (ECB, CBC, GCM, etc.)

---

### Block Cipher Process (Example: AES)

1. Plaintext is converted to **binary**
2. Data is split into **fixed-size blocks**
3. Padding is added (if needed)
4. **Key Expansion**
   - One master key → many round keys
5. Each block goes through multiple rounds:
   - **Substitution** (S-box)
   - **Permutation / Diffusion**
     - ShiftRows
     - MixColumns
   - **XOR with round key** (AddRoundKey)
6. Final output becomes ciphertext

> Decryption uses the **same key** and inverse operations.

---

### Common Block Ciphers
- AES (secure, modern)
- DES (broken)
- 3DES (deprecated)
- Blowfish
- Twofish

---

## 3. Stream Cipher

### What is a Stream Cipher?
A stream cipher encrypts data **bit by bit or byte by byte** by XORing it with a **keystream**.

### Key Points
- No fixed block size
- No padding required
- Uses **keystream + XOR**
- Very fast
- Encryption and decryption are identical (XOR)

---

### Stream Cipher Process

1. A **secret key** is generated (system-generated, not user-typed)
2. A **nonce (number used once)** is chosen
   - Public
   - Must be unique for each encryption
3. Key + nonce initialize the cipher
4. Cipher generates a **pseudo-random keystream**
5. Encryption:
6. Decryption:

---

### Important Rule
🚨 **Never reuse the same key + nonce**
- Reusing keystream breaks security

---

### Common Stream Ciphers
- ChaCha20 (secure, modern)
- Salsa20
- RC4 (broken)

---

## 4. Substitution vs XOR (Important Difference)

### Substitution
- Uses a lookup table (S-box)
- Replaces one value with another
- Non-linear
- Used in block ciphers (AES)

### XOR
- Bitwise operation
- Linear
- Reversible using same value
- Used in stream ciphers and key mixing

---

## 5. Block Cipher vs Stream Cipher (Comparison)

| Feature | Block Cipher | Stream Cipher |
|------|-------------|---------------|
| Data handling | Fixed-size blocks | Continuous stream |
| Padding | Required | Not required |
| Core idea | Transform data | Mask data with keystream |
| Speed | Fast | Very fast |
| Examples | AES | ChaCha20 |

---

## 6. Important Notes

- Block ciphers hide data by **transforming the data itself**
- Stream ciphers hide data by **masking it with a keystream**
- AES can act like a stream cipher in modes like **CTR** and **GCM**
- Modern systems use:
- **AES-GCM**
- **ChaCha20-Poly1305**

---

## 7. One-Line Summary

> **Block ciphers encrypt fixed-size blocks using multiple transformation rounds, while stream ciphers encrypt data by XORing it with a pseudo-random keystream generated from a secret key and nonce.**

---

## Author
Cybersecurity learner  
Learning cryptography fundamentals
