# Beside v0.3.0 — High-Speed Local File Transfer (Windows & Android)

**Target Repository**: `https://github.com/thisma-labs/beside`  
**Milestone Tag**: `v0.3.0`  
**Official Portal**: [https://beside-license-worker.khthisald.workers.dev](https://beside-license-worker.khthisald.workers.dev)  
**Release Date**: 2026-11-12  

---

## What is Beside?

Beside is a local-first, peer-to-peer sharing application built for **Windows 10 / 11 (64-bit)** and **Android 8.0+ (arm64)**.

Transfers travel machine-to-machine strictly over your local Wi-Fi network at full wire speed. No cloud servers, no account registration, zero telemetry, and a constant 64 KB RAM streaming footprint regardless of whether you are sending a 2 KB note or a 50 GB directory tree.

---

## What's New in v0.3.0

### 1. Up to 3.85x Faster Multi-File & Folder Transfers
- **Kernel-Level Atomic Finalization**: On Android devices, incoming files are finalized using native non-overwriting kernel renames (`renameat2`), bypassing secondary userland copies and filesystem syncs.
- **Physical Test Results**: Transferring a folder of 50 small files completes in **5.5 seconds** (down from 21.2 seconds on v0.2.0) — a **74% latency reduction**.

### 2. Zero-Lag Control Framing (`TCP_NODELAY`)
- Per-file transfer acknowledgments and control headers stream with sub-millisecond turnarounds, eliminating 40–200 ms TCP Nagle packet delays on wireless stacks.
- Phone-to-PC uploads of large files are up to **2.63x faster** (`11.57s` -> `4.40s` on 10 MB).

### 3. Simultaneous Multi-Device Sharing & Custom Device Groups (Beside Pro)
- **Concurrent Multi-Peer Streaming**: Select multiple paired devices and stream files, folders, or snippets simultaneously over isolated Mutual TLS 1.3 streams.
- **Custom Named Device Groups**: Create and manage local device groups (e.g., `Workstations`, `Living Room`, `Family`) stored in `device_groups.json` with zero cloud dependencies.
- **Resilient Offline Handling**: Automatically skips offline group members without stalling and tracks per-peer delivery progress.

### 4. Hardened Collision Safety & Dedicated Support Portals
- Atomic non-overwriting guarantees: incoming files never overwrite existing files; duplicate names safely auto-suffix (`document (1).pdf`).
- **Windows Desktop Support**: [https://github.com/thisma-labs/beside-windows-support](https://github.com/thisma-labs/beside-windows-support)
- **Android Mobile Support**: [https://github.com/thisma-labs/beside-android-support](https://github.com/thisma-labs/beside-android-support)

---

## Download Artifacts & SHA-256 Checksums

### Windows 10 / 11 (64-bit x64)
| Package | File Name | Size | SHA-256 Digest |
| :--- | :--- | :--- | :--- |
| **Inno Setup Installer** | `Beside-Setup-v0.3.0-x64.exe` | 12.40 MB | `cc8646d4fb618f429743e3006d8f7abb03141e036faad87840e62815b98ab685` |
| **Portable Archive** | `Beside-v0.3.0-Windows-x64.zip` | 14.81 MB | `a0d0fd7fd6af7517246e1c34bc1d20fb34705bf38d05b2057cb074ed6df50727` |

- SourceForge Mirror: [https://sourceforge.net/projects/beside-windows](https://sourceforge.net/projects/beside-windows)

### Android 8.0+ (arm64-v8a)
| Package | File Name | Size | SHA-256 Digest |
| :--- | :--- | :--- | :--- |
| **Signed Release APK** | `Beside-v0.3.0-Android-arm64.apk` | 27.78 MB | `c4caf733ec9f407ab45e79b3aa34d5ad524471b93ed4c1654fb6c49725dbeae8` |

- SourceForge Mirror: [https://sourceforge.net/projects/beside-android](https://sourceforge.net/projects/beside-android)

### Verify Checksums
```powershell
# Windows
Get-FileHash -Algorithm SHA256 Beside-Setup-v0.3.0-x64.exe
```
```bash
# Android / Linux / macOS
sha256sum Beside-v0.3.0-Android-arm64.apk
```

---

## Pricing & Availability
- **Beside Free**: 100% free forever for 1-to-1 file transfers up to 1 MB, unlimited incoming wire-speed transfers, and zero telemetry.
- **Beside Pro ($14.99 USD Lifetime)**: Unlimited file sizes, recursive directory trees, multi-device fanout sharing, and custom device groups on up to 3 personal devices. Available exclusively on [Gumroad](https://thismalabs.gumroad.com/l/beside-pro).
