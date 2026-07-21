# Levushka VPN

<p align="center">
  <strong>Official client for <a href="https://levushka.app">Levushka VPN</a></strong><br>
  macOS · Windows · Android · TUN · VLESS
</p>

<p align="center">
  <a href="README.ru.md">Русский</a> ·
  <a href="README.en.md">English</a> ·
  <a href="CHANGELOG.md">Changelog</a>
</p>

<p align="center">
  <a href="https://app.levushka.app/desktop/macos/">Download macOS</a> ·
  <a href="https://app.levushka.app/desktop/windows/">Download Windows</a> ·
  <a href="https://app.levushka.app/desktop/android/">Download Android</a> ·
  <a href="https://my.levushka.app">Personal account</a>
</p>

---

**Levushka VPN** is a native app for the Levushka VPN service on **macOS**, **Windows**, and **Android**. It connects through a full-system **TUN tunnel** (not just a browser proxy), so Telegram, games, and other apps that ignore system proxy settings work correctly.

| | |
|---|---|
| **Stack** | Tauri 2 · React · Rust · [Xray-core](https://github.com/XTLS/Xray-core) |
| **Platforms** | macOS (Apple Silicon) · Windows 10/11 x64 · Android 8+ |
| **Protocol** | VLESS subscription from `subs.levushka.app` |
| **Versions** | macOS / Windows **0.3.5** · Android **0.4.0** |

### Download

| Platform | Version | Link |
|----------|---------|------|
| macOS (Apple Silicon) | 0.3.5 | [app.levushka.app/desktop/macos](https://app.levushka.app/desktop/macos/) |
| Windows 10/11 x64 | 0.3.5 | [app.levushka.app/desktop/windows](https://app.levushka.app/desktop/windows/) |
| Android 8+ (APK) | 0.4.0 | [app.levushka.app/desktop/android](https://app.levushka.app/desktop/android/) |

All platforms: [app.levushka.app](https://app.levushka.app)

### Highlights

- Import subscription by URL, token, or `levushka://` deep link
- Server list, TCP ping, traffic stats from subscription headers
- Routing presets: all traffic via VPN, Russia direct, custom domain lists
- Auto-updates; tray icon and connect on launch (desktop)
- Full-tunnel VPN on Android via VpnService + xray + hev-socks5-tunnel
- Compatible with Happ-style subscription metadata (`profile-title`, `subscription-userinfo`, …)

### Screenshots

| Connected | Server list |
|:---:|:---:|
| ![Main screen — connected](assets/screenshots/main-connected.png) | ![Server list with ping](assets/screenshots/server-list.png) |

| Routing | Import |
|:---:|:---:|
| ![Routing presets](assets/screenshots/settings-routing.png) | ![Subscription import](assets/screenshots/import.png) |

### Repository model

This public repository is a **product showcase**: documentation, changelog, issue tracker, and release downloads.

The full application source code, signing keys, and release automation live in a **private** development repository. See [docs/publishing.md](docs/publishing.md) for what is usually published on GitHub and why.

### Quick start (users)

1. Download the installer / APK for your OS from [app.levushka.app](https://app.levushka.app).
2. Open the app and import your subscription (link from bot or [my.levushka.app](https://my.levushka.app)).
3. Choose a server and tap **Connect**. macOS/Windows may ask for administrator permission once to install the network helper; Android asks for VPN permission.

### Support

- Website: [levushka.app](https://levushka.app)
- Personal account: [my.levushka.app](https://my.levushka.app)
- Bugs and feature requests: [GitHub Issues](https://github.com/MihichN/levushka-desktop/issues)

### License

Client binaries are distributed by Levushka. This repository contains documentation and release metadata unless otherwise noted. See [LICENSE](LICENSE).
