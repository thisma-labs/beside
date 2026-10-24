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
  - Context: `EXPORTER-beside-pairing-sas-v1`
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
ca5194c5923e7b2cbd4939d61195c2c9488e46a83a37a983fe0ae187754ac29c  Beside-Setup-v0.1.0-x64.exe
2344e158997fe31788af0903c58a7b7ad6d6de05117d150fac96f88728ff861d  Beside-v0.1.0-Windows-x64.zip
3138b55a6bab78fde0fae171afce5009d1d9587b7362b33a177679153fb507b4  Beside-v0.1.0-Android-arm64.apk
```

---

## 🚨 Reporting a Vulnerability

If you discover a security issue or vulnerability in Beside, please report it responsibly:

- **Email**: Send vulnerability reports directly to `contact@thismalabs.com` (or open a confidential security advisory on GitHub).
- Please include reproduction steps, environment details (OS, network topology), and any packet captures or stack traces.
- We acknowledge security reports within 48 hours and work with you on a coordinated fix.
