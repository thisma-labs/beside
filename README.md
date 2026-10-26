<!-- GENERATED FROM release.json, DO NOT EDIT. -->

<p align="center">
  <img src="assets/logo.svg" alt="Beside Logo" width="96" height="96"/>
</p>

<h1 align="center">Beside</h1>

<p align="center">
  <strong>Direct local file, folder &amp; text sharing between Windows and Android over Wi-Fi.</strong><br>
  <em>Fast. Private. Together. — Send it. It's there.</em><br>
  <sub>Engineered by <a href="https://github.com/thisma-labs">Thisma Labs</a></sub>
</p>

<p align="center">
  <a href="https://github.com/thisma-labs/beside/releases"><img src="https://img.shields.io/badge/release-v0.1.1-emerald?style=flat-square" alt="Release"></a>
  <a href="https://github.com/thisma-labs/beside/releases"><img src="https://img.shields.io/badge/Windows-10%20%7C%2011%20(x64)-blue?style=flat-square&logo=windows" alt="Windows"></a>
  <a href="https://github.com/thisma-labs/beside/releases"><img src="https://img.shields.io/badge/Android-8.0%2B%20(arm64)-green?style=flat-square&logo=android" alt="Android"></a>
  <a href="SECURITY.md"><img src="https://img.shields.io/badge/Security-Mutual%20TLS%201.3-success?style=flat-square" alt="Security"></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/License-Freemium%20%2F%20Proprietary-lightgrey?style=flat-square" alt="License"></a>
</p>

<p align="center">
  <img src="assets/beside-hero.png" alt="Beside — Wire-Speed Local Peer Sharing by Thisma Labs" width="850"/>
</p>

**Beside** is a local-first, peer-to-peer file, folder, and text sharing application for **Windows 10/11 (x64)** and **Android 8.0+ (arm64-v8a)**.

Transfers stay strictly inside your local Wi-Fi network at wire speed. No cloud servers, no accounts, no subscriptions, and zero tracking.

---

## ⚡ Key Highlights

- **Wire-Speed Gigabit LAN**: Direct peer-to-peer transfers over local Wi-Fi, mobile hotspot, or USB tethering without passing through the internet.
- **Mutual TLS 1.3 Only**: Every transfer is encrypted end-to-end with TLS 1.3 and pinned X.509 SPKI SHA-256 device key fingerprints (`rustls` + `ring`).
- **8-Digit SAS MITM Defense**: Visual SAS pairing derived from RFC 8446 / RFC 5705 TLS Exporter (`EXPORTER-beside-pairing-v1`) to prevent interception on public Wi-Fi.
- **Hardware Keystore Protection**: Private keys are encrypted at rest via **Windows DPAPI** and **Android Keystore AES-256-GCM**.
- **Bounded 64 KB RAM Streaming**: Stream multi-gigabyte video or archive files with a flat memory footprint, streamed SHA-256 integrity checks, and atomic `.part` promotion.
- **Zero-Config Local Discovery**: Automatic `_beside._tcp.local.` discovery with QR code and manual IP:port fallback.

---

## 📥 Downloads (`v0.1.1`)

| Platform | Package | Format | Direct Download |
| :--- | :--- | :--- | :--- |
| **Windows 10 / 11** | Installer (Recommended) | `.exe` (12.0 MB) | [**Download Beside-Setup-v0.1.1-x64.exe**](https://github.com/thisma-labs/beside/releases/download/v0.1.1/Beside-Setup-v0.1.1-x64.exe) |
| **Windows 10 / 11** | Portable Archive | `.zip` (14.3 MB) | [**Download Beside-v0.1.1-Windows-x64.zip**](https://github.com/thisma-labs/beside/releases/download/v0.1.1/Beside-v0.1.1-Windows-x64.zip) |
| **Android 8.0+** | Signed Release APK | `.apk` (32.5 MB) | [**Download Beside-v0.1.1-Android-arm64.apk**](https://github.com/thisma-labs/beside/releases/download/v0.1.1/Beside-v0.1.1-Android-arm64.apk) |

> Checksums and cryptographic signatures are published with every release in [`SHA256SUMS.txt`](https://github.com/thisma-labs/beside/releases/download/v0.1.1/SHA256SUMS.txt).  
> Mirrors also available on [**SourceForge**](https://sourceforge.net/projects/beside-app/).

---

## 💎 Beside Free vs. Beside Pro

Beside is freemium software. Beside Free is completely functional for everyday quick transfers with no ads or expiration. A single lifetime Pro license unlocks wire-speed power features for up to 3 personal devices.

<p align="center">
  <img src="assets/beside-pro-matrix.png" alt="Beside Free vs Beside Pro Feature Matrix" width="850"/>
</p>

| Capability | Beside Free | Beside Pro (Lifetime • 3 Devices) |
| :--- | :---: | :---: |
| **Max Outgoing File Size** | 1 MB (1,048,576 bytes) | **Unlimited** (Gigabit LAN speed) |
| **Files per Batch** | 1 file per transfer | **Unlimited** multi-file batches |
| **Recursive Folder Trees** | Locked | **Preserved relative paths** |
| **Instant Text & Snippets** | Up to 40 characters | **Unlimited** text & code snippets |
| **Trusted Paired Peers** | Up to 1 paired device | **Unlimited** trusted devices |
| **Zero-Click Auto-Accept** | Manual approval only | **Auto-accept from paired peers** |
| **Custom Save Directory** | Downloads/Beside | **Any folder** (Storage Access Framework) |
| **Background Listening** | Foreground only | **Listen while minimized** |
| **Appearance Themes** | Obsidian Dark | **Obsidian, Warm Alabaster, System** |
| **Receiving from Pro Users** | **Unlimited** | **Unlimited** |

### Where to Buy Beside Pro ($14.99 Lifetime):
- [**Gumroad**](https://thismalabs.gumroad.com/l/beside-pro) (Official Authorized Merchant — Credit Card, Apple Pay, PayPal)

### Free Community Downloads & Mirrors:
- [**GitHub Releases**](https://github.com/thisma-labs/beside/releases)
- [**SourceForge**](https://sourceforge.net/projects/beside-app/)
- [**itch.io**](https://thisma-labs.itch.io/beside) (Community Free Edition / Optional Donation)

---

## 🔒 Verification & Checksums

Always verify the integrity of downloaded binaries before executing:

### Windows (PowerShell)
```powershell
Get-FileHash -Algorithm SHA256 Beside-Setup-v0.1.1-x64.exe
# Expected: ca5194c5923e7b2cbd4939d61195c2c9488e46a83a37a983fe0ae187754ac29c

Get-FileHash -Algorithm SHA256 Beside-v0.1.1-Windows-x64.zip
# Expected: 2344e158997fe31788af0903c58a7b7ad6d6de05117d150fac96f88728ff861d
```

### Android (Linux / macOS / Termux)
```bash
sha256sum Beside-v0.1.1-Android-arm64.apk
# Expected: 3138b55a6bab78fde0fae171afce5009d1d9587b7362b33a177679153fb507b4
```

---

## ❓ Troubleshooting & Network Requirements

1. **Both devices must be on the same local subnet**:
   - Ensure both devices are connected to the same Wi-Fi router or phone hotspot.
2. **Wi-Fi Client Isolation (Guest Networks)**:
   - Some enterprise, coffee shop, or guest networks turn on "Client Isolation", which blocks devices from talking directly to each other. If peers cannot see each other, turn on a phone Hotspot or connect both to a standard private Wi-Fi network.
3. **Windows Defender Firewall**:
   - On first launch, Windows may show a prompt asking to allow Beside on Private networks. Check **Private networks** and click **Allow access** so local peer discovery (`_beside._tcp.local.`) can function.
4. **Manual Connection Fallback**:
   - If discovery is ever blocked by your router's multicast filtering, tap **Manual IP** or scan the sender's **QR code** in Beside to connect directly.

---

## 🛡️ Responsible Disclosure & Support

- **Bug Reports**: Open an issue on our [Issue Tracker](https://github.com/thisma-labs/beside/issues).
- **Security Inquiries**: See [SECURITY.md](SECURITY.md) for encrypted vulnerability reporting instructions.
- **License Server Portal**: [https://beside-license-worker.khthisald.workers.dev](https://beside-license-worker.khthisald.workers.dev)

---

© 2026 **Thisma Labs**. All rights reserved. Beside (`•—◎`) is a trademark of Thisma Labs.
