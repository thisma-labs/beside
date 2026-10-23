# Changelog — Beside

All notable changes to the Beside application will be documented in this file.

---

## [0.1.0] - 2026-10-23

### Initial Release
- **Core Engine (`beside-core`)**:
  - Native Rust peer engine with `rustls`, `ring`, and pure-Rust `_beside._tcp.local.` mDNS discovery.
  - Mutual TLS 1.3 encryption with pinned X.509 SPKI SHA-256 fingerprints.
  - 8-digit SAS pairing (RFC 8446 / RFC 5705 TLS Exporter) for visual MITM authentication.
  - Bounded 64 KB RAM streaming engine with streaming SHA-256 validation and `.part` file finalization.
  - Automatic NTFS / EXT4 file collision prevention (never overwrites received files).
- **Cross-Platform UI (Windows + Android)**:
  - Flutter UI themed in Obsidian Dark (`#0C0D10`), Warm Alabaster, and System Match.
  - 3-column desktop layout with drag-and-drop file staging and instant clipboard snippet sharing.
  - Mobile bottom navigation, nearby radar radar view, and foreground service transfer notification.
- **Licensing & Offline Verification**:
  - Beside Free edition with no ads, no trackers, and unconstrained receiving from Pro senders.
  - Beside Pro lifetime unlock (up to 3 devices) featuring unlimited file streaming, recursive folder trees, and zero-click Auto-Accept.
  - Ed25519 offline hardware-bound certificate verification.
- **Distribution Packaging**:
  - Windows x64 Inno Setup installer (`Beside-Setup-v0.1.0-x64.exe`).
  - Windows x64 standalone portable archive (`Beside-v0.1.0-Windows-x64.zip`).
  - Android signed release APK (`Beside-v0.1.0-Android-arm64.apk`).
