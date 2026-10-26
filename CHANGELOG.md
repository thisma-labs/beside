# Changelog — Beside

All notable changes to **Beside** are documented in this file.
The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [0.1.1] - 2026-10-26

### Added
- **On-Demand License Status Verification**: Added "Check Status" action in Settings and Pro Upgrade sheets to query `/api/v1/validate` on demand and instantly synchronize remote slot deactivations while preserving the 14-day offline grace period.
- **Automated Uninstaller Deactivation Hook**: Inno Setup Windows uninstaller cleanly notifies license server on uninstall to free device slot.
- **Automated SourceForge Release Mirroring**: Added `.github/workflows/sync-sourceforge.yml` workflow for automated asset mirroring and SHA-256 verification.
- **Enhanced Activation Error Guidance**: Actionable modal and inline notifications for license activation errors with direct link to the self-service Device Manager portal.

### Changed
- **Commercial Price Standardization**: Standardized Beside Pro lifetime license price to $14.99 USD across in-app purchase sheets, web templates, and storefronts.
- **Distribution Roles Harmonization**: Designated Gumroad as the sole authorized merchant for Beside Pro lifetime licenses; itch.io and SourceForge configured as $0 free community download mirrors.
- **TLS Exporter Label Parity**: Unified RFC 8446 / RFC 5705 TLS Key Exporter label across protocol documentation, web security disclosures, and client/core implementations (`EXPORTER-beside-pairing-v1`).
- **Direct SourceForge FRS Redirection**: Web worker `/download/sourceforge` now redirects directly to SourceForge File Release System latest download endpoint.

### Fixed
- Fixed Inno Setup Pascal Script type mismatch during Windows setup packaging.
- Resolved static analysis warnings in desktop UI and active device test suites.

---

## [0.1.0] - 2026-10-24

### Initial Stable Release

#### Core Transfer Engine
- **Direct Local Peer-to-Peer**: Wire-speed streaming over local Wi-Fi, phone hotspots, or USB tethering without passing through any cloud servers or relay networks.
- **Bounded 64 KB Memory Engine**: Streams arbitrary file sizes (from small snippets to multi-gigabyte files) with a constant 64 KB RAM footprint.
- **Streaming Cryptographic Integrity**: Continuous on-the-fly SHA-256 calculation and verification before finalizing temporary `.part` files.
- **Collision-Safe File System Handling**: Incoming files never overwrite existing files; clean numeric suffixing (`name (1).ext`) is applied automatically.
- **Batch & Recursive Folder Transfers**: Support for sending multiple files and preserved recursive directory trees (Pro).
- **In-Memory Instant Text Sharing**: Direct transfer of commands, code snippets, and text without disk staging.

#### Security & Cryptography
- **Strict Mutual TLS 1.3**: Built with Rust (`tokio-rustls` + `ring`), using self-signed Ed25519 device certificates and pinned SHA-256 Subject Public Key Info (SPKI) fingerprints. Legacy TLS versions and insecure ciphers are strictly rejected.
- **8-Digit SAS MITM Defense**: Visual Short Authentication String derived from RFC 8446 / RFC 5705 TLS Exporters (`EXPORTER-beside-pairing-v1`) with single-attempt 60-second pairing windows to eliminate Man-in-the-Middle attacks on public networks.
- **Hardware-Protected Storage at Rest**: Device identity keys encrypted via Windows DPAPI on Windows and hardware-backed Android Keystore AES-256-GCM on Android.
- **Path Sanitization**: Rejection of path traversal (`..`), null bytes, absolute paths, and Windows reserved device names (`CON`, `PRN`, `AUX`, `NUL`, etc.).
- **Real Available Space Verification**: Pre-checks available disk capacity prior to accepting incoming transfers.

#### Windows Desktop Integration
- **Win32 System Tray**: Background tray execution with close-to-tray, status badge, and quick menu (`Open`, `Pause receiving`, `Auto-accept`, `Send files...`, `Settings`, `Quit`).
- **Start with Windows**: Native registry startup shortcut (`HKCU\Software\Microsoft\Windows\CurrentVersion\Run\Beside --minimized`).
- **Explorer Context Menu & SendTo**: Right-click **"Send with Beside"** and `SendTo` shortcut with 220ms path coalescing.
- **Interactive WinRT Toast Notifications**: Native Windows toast alerts with `Accept`, `Decline`, `Copy`, and `Show in folder` buttons, plus a 60-second pending queue.
- **Single-Instance IPC**: Named Pipe architecture (`\\.\pipe\Beside_IPC_<UserSID>`) forwarding CLI or Explorer paths to running instances.

#### Android Mobile Integration
- **System Share Sheet Integration**: Deep integration with Android Share Sheet (`ACTION_SEND` / `ACTION_SEND_MULTIPLE`) for photos, videos, documents, and text.
- **Automatic Media Gallery Indexing**: Scans transferred media into Android's MediaStore immediately upon arrival.
- **Foreground Transfer Service**: High-priority background transfer service preventing OS task killer termination, with real-time notification progress.
- **Android 14 Permissions**: Runtime notification permissions handling on Android 13+.

#### Licensing & Update Delivery
- **Beside Free**: Fully functional for everyday quick transfers with zero ads, zero accounts, and unlimited receiving from Pro users.
- **Beside Pro (Lifetime Unlock)**: Unlimited transfer sizes, multi-file batches, folder structures, unlimited trusted peers, and zero-click Auto-Accept. Verified 100% offline via Ed25519 digital signatures.
- **Privacy-Preserving Updater**: In-app GitHub Releases update checker with cryptographic checksum verification against `SHA256SUMS.txt`.

#### Distribution Binaries
- Windows x64 Inno Setup Installer: `Beside-Setup-v0.1.0-x64.exe` (SHA-256: `ca5194c5923e7b2cbd4939d61195c2c9488e46a83a37a983fe0ae187754ac29c`)
- Windows x64 Portable Archive: `Beside-v0.1.0-Windows-x64.zip` (SHA-256: `2344e158997fe31788af0903c58a7b7ad6d6de05117d150fac96f88728ff861d`)
- Android Release APK: `Beside-v0.1.0-Android-arm64.apk` (SHA-256: `3138b55a6bab78fde0fae171afce5009d1d9587b7362b33a177679153fb507b4`)
- Checksums Manifest: `SHA256SUMS.txt`
