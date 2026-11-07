# Beside v0.2.0 — Public Release Notes (Legacy Unified Repository)

**Target Repository**: `https://github.com/thisma-labs/beside`  
**Milestone Tag**: `v0.2.0`  
**Distribution Portal**: `https://beside-license-worker.khthisald.workers.dev` (beside.app)  

---

## Important Notice: Transition to Dedicated Support Repositories

Starting with release **v0.2.0**, Thisma Labs has organized customer support, release feeds, and issue tracking into two dedicated, platform-specific public repositories:

- **Windows Desktop Support**: [`https://github.com/thisma-labs/beside-windows-support`](https://github.com/thisma-labs/beside-windows-support)  
  *Live Help Center: [https://thisma-labs.github.io/beside-windows-support](https://thisma-labs.github.io/beside-windows-support)*
- **Android Mobile Support**: [`https://github.com/thisma-labs/beside-android-support`](https://github.com/thisma-labs/beside-android-support)  
  *Live Help Center: [https://thisma-labs.github.io/beside-android-support](https://thisma-labs.github.io/beside-android-support)*

This unified repository (`thisma-labs/beside`) continues to serve as an umbrella archive and general release distribution mirror.

---

## What is Beside?

Beside is an ultra-fast, local-first file, folder, and text sharing application designed specifically for **Windows 10 / 11 (64-bit)** and **Android 8.0+ (arm64)**.

Transfers travel machine-to-machine strictly within your local Wi-Fi network at full wire speed (up to 110 MB/s). No cloud servers, no account registration, zero telemetry, and flat 64 KB memory consumption regardless of file size.

---

## What's New in v0.2.0

### 1. Dual-Platform UI Redesign with Light & Dark Theme Support
- Both Windows and Android applications feature authentic, refreshed user interfaces with automatic and manual light/dark theme switching.
- **Windows Desktop**: 3-column architecture designed for widescreen desktop workstations with concentric radar, drag-and-drop dropzone, and active transfer docks.
- **Android Mobile**: 4-tab bottom navigation (Home, Activity, Trusted Devices, Settings) engineered for one-handed touch ergonomics.

### 2. High-Performance Wire-Speed File & Folder Streaming
- Direct peer-to-peer TCP streaming using a bounded 64 KB RAM buffer.
- Complete nested directory tree streaming without compression latency.
- Automatic non-destructive collision avoidance: existing local files are never overwritten.

### 3. Mutual TLS 1.3 Encryption & 8-Digit SAS Pairing
- Every local connection is secured with Mutual TLS 1.3 using ephemeral pinned device certificates.
- Zero-MITM Short Authentication String (SAS): an unforgeable 8-digit visual code derived from the TLS 1.3 Key Exporter to authenticate new peers in coffee shops, hotels, and universities.
- Hardware key vaults: device identity keys are encrypted using Windows DPAPI and Android Keystore (TEE / StrongBox).

### 4. Direct LAN Text Messaging
- Send text snippets, terminal commands, URLs, and clipboard notes directly across devices without cloud messengers.
- One-tap clipboard copy on received notifications.

### 5. Multi-Storefront Commercial Availability
- **Beside Free ($0 forever)**: 1 device, 1 MB outgoing file cap, unlimited incoming files at full wire speed.
- **Beside Pro ($14.99 one-time lifetime)**: Unlimited outgoing file sizes, up to 3 personal devices.
- Available through Gumroad, itch.io, and SourceForge File Release System (FRS).

---

## Download Mirrors & Binary Checksums

### Windows 10 / 11 (64-bit x64)
- **Setup Installer (Recommended)**: `Beside-Setup-v0.2.0-x64.exe` (12.25 MB)  
  `SHA-256: 1f2f28b7e404519de9e5b836940315be26306a8b6f3c222762a6d67dc753ff8e`
- **Portable ZIP Archive**: `Beside-v0.2.0-Windows-x64.zip` (14.57 MB)  
  `SHA-256: bca3db28d780790797a4123f157bca3587243c6f581a1388b24975ab6cb467d9`

### Android 8.0+ (arm64-v8a)
- **Release APK**: `Beside-v0.2.0-Android-arm64.apk` (33.30 MB)  
  `SHA-256: 8867cc2d82309f42cfdad3b1779114dd64b1be5bac59e8549a0d163199858c06`
- **Signing Certificate Fingerprint (SHA-256)**:
  `A5:C7:E2:61:74:93:18:2B:6F:AA:CD:D1:49:10:85:3E:04:7B:6C:59:71:03:62:38:29:1A:F3:49:EE:12:08:52`

---

## Verifying Downloaded Binaries

**Windows (PowerShell)**:
```powershell
Get-FileHash -Algorithm SHA256 Beside-Setup-v0.2.0-x64.exe
```

**Linux / macOS (Terminal)**:
```bash
sha256sum Beside-v0.2.0-Android-arm64.apk
```
