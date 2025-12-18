# Symmetric Cryptography – Complete Notes

This document explains **symmetric cryptography** in a simple and structured way, covering:
- What it is
- How it works
- Block vs Stream ciphers
- AES, DES, 3DES
- Modes of operation
- Modern practices
- Advantages and limitations

---

## 1. What is Symmetric Cryptography?

Symmetric cryptography is an encryption method where:
- The **same secret key** is used for both encryption and decryption
- Both sender and receiver must know the key

Symmetric Encryption
├── Block Ciphers
└── Stream Ciphers

---

## 4. Block Cipher

### What is a Block Cipher?
A block cipher encrypts data in **fixed-size blocks**.

Examples:
- AES
- DES
- 3DES

---

### Block Cipher Characteristics
- Fixed block size (AES = 128 bits)
- Data split into blocks
- Padding added if needed
- Multiple rounds of transformations
- Requires a **mode of operation**

---

### Block Cipher Process (Generic)

1. Plaintext → binary
2. Split into fixed-size blocks
3. Padding added (if required)
4. **Key Expansion**
   - One master key → many round keys
5. Multiple rounds per block:
   - Substitution (S-box)
   - Permutation / Mixing (ShiftRows, MixColumns)
   - XOR with round key
6. Output ciphertext blocks

> Decryption uses the **same key** with inverse operations.

---

### AES (Advanced Encryption Standard)

- Block size: **128 bits**
- Key sizes: **128 / 192 / 256 bits**
- Rounds: 10 / 12 / 14
- Design: Substitution–Permutation Network (SPN)
- Status: ✅ Secure and modern

AES uses:
- SubBytes (substitution)
- ShiftRows (permutation)
- MixColumns (diffusion)
- AddRoundKey (XOR with key)

---

### DES (Data Encryption Standard)

- Block size: 64 bits
- Key size: 56 bits
- Status: ❌ Broken

**Why DES is legacy:**
- Small key size → brute-force attacks
- Small block size → pattern leakage
- Designed for 1970s hardware

---

### 3DES (Triple DES)

- DES applied **three times**
- Effective key ≈ 112 bits
- Still uses 64-bit block size
- Very slow
- Status: ❌ Deprecated

---

## 5. Stream Cipher

### What is a Stream Cipher?
A stream cipher encrypts data **bit-by-bit or byte-by-byte** using a **keystream**.

Examples:
- ChaCha20
- Salsa20
- RC4 (broken)

---

### Stream Cipher Characteristics
- No fixed block size
- No padding
- Uses XOR only for encryption
- Very fast
- Encryption and decryption are identical

---

### Stream Cipher Process

1. Secret key is generated (system-generated)
2. A **nonce** (number used once) is chosen
3. Key + nonce initialize the cipher
4. Cipher generates a **pseudo-random keystream**
5. Encryption:
6. Decryption

---

### Important Rules (Stream Ciphers)

- Keystream is **NOT the key**
- Keystream is generated from key + nonce
- **Never reuse the same key + nonce**
- Reuse breaks security completely

---

## 6. XOR and Substitution (Important Difference)

### XOR
- Bitwise operation
- Used to mix key with data
- Reversible
- Linear

### Substitution (S-box)
- Table-based value replacement
- Non-linear
- Provides confusion
- Used in block ciphers like AES

> **The direct mathematical connection between data and key is usually done using XOR.**

---

## 7. Modes of Operation (Block Ciphers)

Block ciphers need modes to encrypt large data.

### ECB (❌ Insecure)
- Same plaintext → same ciphertext
- Reveals patterns

### CBC (⚠️ Old)
- Chains blocks with IV
- No authentication
- Padding oracle attacks

### CFB / OFB (⚠️ Old)
- Stream-like behavior
- No authentication

### CTR (⚠️ Incomplete)
- Converts block cipher to stream cipher
- Fast
- No authentication

### GCM (✅ Modern & Secure)
- Uses CTR for encryption
- Adds authentication (AEAD)
- Protects confidentiality + integrity

**Recommended modes today:**
- AES-GCM
- ChaCha20-Poly1305

---

## 8. Modern Symmetric Cryptography

Modern symmetric crypto uses:
- Large random keys
- Nonces / IVs
- AEAD modes
- Hardware acceleration

Modern operations:
- XOR
- Substitution
- Permutation / diffusion
- ARX (Add, Rotate, XOR)

---

## 9. Advantages of Symmetric Cryptography

- Very fast
- Efficient for large data
- Strong security with modern algorithms
- Widely supported
- Low computational cost

---

## 10. Limitations of Symmetric Cryptography

- Key distribution problem
- Key management complexity
- No authentication by default
- No non-repudiation
- Incorrect nonce/IV reuse breaks security

---

## 11. Real-World Usage

- HTTPS (TLS)
- VPNs
- Disk encryption (LUKS, BitLocker)
- Wi-Fi (WPA2/WPA3)
- Databases
- Cloud security

---

## 12. Final Summary

> **Symmetric cryptography uses a single secret key to securely transform plaintext into ciphertext using reversible operations. Block ciphers transform data in fixed-size blocks, while stream ciphers mask data with a keystream. Modern systems rely on AES-GCM and ChaCha20-Poly1305 for secure and authenticated encryption.**

---

## Author
Cybersecurity learner  
Notes on symmetric cryptography fundamentals
