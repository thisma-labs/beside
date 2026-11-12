<p align="center">
  <img src="assets/logo.png" alt="Beside Logo" width="96" height="96"/>
</p>

<h1 align="center">Beside</h1>

<p align="center">
  <strong>Direct local file, folder &amp; text sharing between Windows and Android over Wi-Fi.</strong><br>
  <em>Fast. Private. Together. — Send it. It's there.</em><br>
  <sub>Engineered by <a href="https://github.com/thisma-labs">Thisma Labs</a></sub>
</p>

<p align="center">
  <a href="https://github.com/thisma-labs/beside/releases"><img src="https://img.shields.io/badge/release-v0.3.0-emerald?style=flat-square" alt="Release"></a>
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

## 📌 Dedicated Support Repositories

Starting with release **v0.2.0** and continuing in **v0.3.0**, issues, updates, and help documentation are maintained in platform-specific repositories:

- **Windows Desktop Support**: [`thisma-labs/beside-windows-support`](https://github.com/thisma-labs/beside-windows-support) | *SourceForge: [beside-windows](https://sourceforge.net/projects/beside-windows/)*
- **Android Mobile Support**: [`thisma-labs/beside-android-support`](https://github.com/thisma-labs/beside-android-support) | *SourceForge: [beside-android](https://sourceforge.net/projects/beside-android/)*

---

## ⚡ Key Highlights

- **Wire-Speed Gigabit LAN**: Direct peer-to-peer transfers over local Wi-Fi, mobile hotspot, or USB tethering without passing through the internet.
- **Kernel-Level Atomic Finalization (v0.3.0)**: Up to 3.85x faster folder transfers on Android using native `renameat2(RENAME_NOREPLACE)` and Win32 `MoveFileExW` without userland copy overhead.
- **Zero-Lag Control Framing (v0.3.0)**: Global `TCP_NODELAY` avoids Nagle's 40–200 ms ACK delay penalty on per-file control frames.
- **Mutual TLS 1.3 Only**: Every transfer is encrypted end-to-end with TLS 1.3 and pinned X.509 SPKI SHA-256 device key fingerprints (`rustls` + `ring`).
- **8-Digit SAS MITM Defense**: Visual SAS pairing derived from RFC 8446 / RFC 5705 TLS Exporter (`EXPORTER-beside-pairing-v1`) to prevent interception on public Wi-Fi.
- **Hardware Keystore Protection**: Private keys are encrypted at rest via **Windows DPAPI** and **Android Keystore AES-256-GCM**.
- **Bounded 64 KB RAM Streaming**: Stream multi-gigabyte video or archive files with a flat memory footprint, streamed SHA-256 integrity checks, and atomic `.part` promotion.
- **Zero-Config Local Discovery**: Automatic `_beside._tcp.local.` discovery with QR code and manual IP:port fallback.

---

## 📥 Downloads (`v0.3.0`)

| Platform | Package | Format | Direct Download |
| :--- | :--- | :--- | :--- |
| **Windows 10 / 11** | Installer (Recommended) | `.exe` (12.40 MB) | [**Download Beside-Setup-v0.3.0-x64.exe**](https://github.com/thisma-labs/beside/releases/download/v0.3.0/Beside-Setup-v0.3.0-x64.exe) |
| **Windows 10 / 11** | Portable Archive | `.zip` (14.81 MB) | [**Download Beside-v0.3.0-Windows-x64.zip**](https://github.com/thisma-labs/beside/releases/download/v0.3.0/Beside-v0.3.0-Windows-x64.zip) |
| **Android 8.0+** | Signed Release APK | `.apk` (27.78 MB) | [**Download Beside-v0.3.0-Android-arm64.apk**](https://github.com/thisma-labs/beside/releases/download/v0.3.0/Beside-v0.3.0-Android-arm64.apk) |

> Checksums and cryptographic signatures are published with every release in [`SHA256SUMS.txt`](SHA256SUMS.txt).  
> Mirrors also available on **SourceForge**: [Beside for Windows](https://sourceforge.net/projects/beside-windows/) and [Beside for Android](https://sourceforge.net/projects/beside-android/).

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
| **Simultaneous Multi-Send** | 1 recipient at a time | **Simultaneous multi-device fanout** |
| **Device Groups** | 0 groups (1:1 only) | **Unlimited** custom device groups |
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
- [**SourceForge Windows**](https://sourceforge.net/projects/beside-windows/)
- [**SourceForge Android**](https://sourceforge.net/projects/beside-android/)
- [**itch.io**](https://thisma-labs.itch.io/beside) (Community Free Edition / Optional Donation)

---

## 🔒 Verification & Checksums

Always verify the integrity of downloaded binaries before executing:

### Windows (PowerShell)
```powershell
Get-FileHash -Algorithm SHA256 Beside-Setup-v0.3.0-x64.exe
# Expected: cc8646d4fb618f429743e3006d8f7abb03141e036faad87840e62815b98ab685

Get-FileHash -Algorithm SHA256 Beside-v0.3.0-Windows-x64.zip
# Expected: a0d0fd7fd6af7517246e1c34bc1d20fb34705bf38d05b2057cb074ed6df50727
```

### Android (Linux / macOS / Termux)
```bash
sha256sum Beside-v0.3.0-Android-arm64.apk
# Expected: c4caf733ec9f407ab45e79b3aa34d5ad524471b93ed4c1654fb6c49725dbeae8
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
