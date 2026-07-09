# Changelog

All notable user-facing changes to Levushka VPN Desktop.

Format based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

## [0.3.5] — 2026-07-08

### Fixed
- **macOS TUN**: fixed DNS/routing loop that caused total internet loss while UI showed “Connected”
- VPN server bypass routes and DNS upstream handling for stable connectivity

### Added
- Windows port foundation (TUN helper, xray, wintun) — in development

## [0.3.3] — 2026-07

### Added
- xray 26.3.27 with macOS TUN support
- Route readiness check before marking connection as successful
- Subscription stored in protected Application Support (fewer Keychain prompts)
- Helper reinstall only when protocol/binary changes

### Fixed
- Release build: skip xray re-download when checksum matches; correct DMG naming

## Earlier versions

Internal beta releases before 0.3.3 focused on subscription import, VLESS connect, routing presets, tray UI, and auto-updates.

[0.3.5]: https://github.com/MihichN/levushka-desktop/releases/tag/v0.3.5
[0.3.3]: https://github.com/MihichN/levushka-desktop/releases/tag/v0.3.3
