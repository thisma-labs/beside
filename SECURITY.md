<!-- GENERATED FROM release.json, DO NOT EDIT. -->

# Security & Cryptography Policy — Beside

Beside is designed from the ground up for strict local-network privacy and cryptographic defense against eavesdropping, active interception, and network spoofing.

---

## 🔐 Cryptographic Architecture

### 1. Transport Layer Security (Mutual TLS 1.3 Only)
- Beside enforces **TLS 1.3 exclusively** using the audited, memory-safe Rust library `rustls` with the `ring` cryptographic provider.
- Insecure ciphers, SSL 3.0, TLS 1.0, 1.1, and 1.2 are rejected.
- Connections enforce **Mutual TLS**: both sender and receiver present self-signed X.509 device certificates. Certificates are bound to ephemeral or hardware-protected device keypairs and validated against pinned SHA-256 Subject Public Key Info (SPKI) fingerprints in the local `TrustStore`.

### 2. 8-Digit Short Authentication String (SAS)
- Pairing derives an 8-digit verification code using the **RFC 8446 / RFC 5705 TLS Keying Material Exporter**:
  - Context: `EXPORTER-beside-pairing-v1`
  - Eliminates modulo bias by sampling a 64-bit integer exporter output.
  - Enforces a 60-second single-attempt pairing window with commitment exchanges to prevent Man-in-the-Middle (MITM) attacks on untrusted Wi-Fi networks.

### 3. Key Storage at Rest
- **Windows**: Identity keys are encrypted using the Windows Data Protection API (**Windows DPAPI**).
- **Android**: Identity keys are encrypted using hardware-backed **Android Keystore AES-256-GCM**.

### 4. Transfer Protocol & Memory Bounds
- All file chunks are streamed in **bounded 64 KB buffers** to prevent memory exhaustion / DoS attacks.
- Transfers calculate SHA-256 digests on-the-fly and verify against the transfer manifest before moving the temporary `.part` file to the final destination.
- Received files never overwrite existing files; collision protection automatically applies clean numeric suffixes.

### 5. Ed25519 Hardware-Bound Offline Licenses
- Beside Pro license certificates use the canonical protocol format:
  `BESIDE-LICENSE-v1:<license_id>:<device_fingerprint>:<tier>:<issued_at>:<expires_at>`
- The signature is generated via vendor Ed25519 private keys and verified 100% offline against the production vendor public key embedded in the native binary. Licenses bound to one device cannot be copied or transferred to another device without deactivation.

---

## 🔍 Verifying Release Artifacts

Every official Beside binary is hashed before distribution. Checksums are published in `SHA256SUMS.txt`:

```text
cc8646d4fb618f429743e3006d8f7abb03141e036faad87840e62815b98ab685  Beside-Setup-v0.3.0-x64.exe
a0d0fd7fd6af7517246e1c34bc1d20fb34705bf38d05b2057cb074ed6df50727  Beside-v0.3.0-Windows-x64.zip
c4caf733ec9f407ab45e79b3aa34d5ad524471b93ed4c1654fb6c49725dbeae8  Beside-v0.3.0-Android-arm64.apk
```

---

## 🚨 Reporting a Vulnerability

If you discover a security issue or vulnerability in Beside, please report it responsibly:

- **Email**: Send vulnerability reports directly to `contact@thismalabs.com` (or open a confidential security advisory on GitHub).
- Please include reproduction steps, environment details (OS, network topology), and any packet captures or stack traces.
- We acknowledge security reports within 48 hours and work with you on a coordinated fix.
