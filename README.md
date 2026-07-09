# Levushka VPN Desktop

<p align="center">
  <strong>Desktop client for <a href="https://levushka.app">Levushka VPN</a></strong><br>
  macOS · Windows · TUN · VLESS
</p>

<p align="center">
  <a href="README.ru.md">Русский</a> ·
  <a href="README.en.md">English</a> ·
  <a href="CHANGELOG.md">Changelog</a>
</p>

<p align="center">
  <a href="https://app.levushka.app/desktop/macos/">Download macOS</a> ·
  <a href="https://app.levushka.app/desktop/windows/">Download Windows</a> ·
  <a href="https://my.levushka.app">Personal account</a>
</p>

---

**Levushka VPN** is a native desktop app for the Levushka VPN service. It connects through a full-system **TUN tunnel** (not just a browser proxy), so Telegram, games, and other apps that ignore system proxy settings work correctly.

| | |
|---|---|
| **Stack** | Tauri 2 · React · Rust · [Xray-core](https://github.com/XTLS/Xray-core) |
| **Platforms** | macOS (Apple Silicon) · Windows 10/11 x64 |
| **Protocol** | VLESS subscription from `subs.levushka.app` |
| **Current version** | 0.3.5 |

### Highlights

- Import subscription by URL, token, or `levushka://` deep link
- Server list, TCP ping, traffic stats from subscription headers
- Routing presets: all traffic via VPN, Russia direct, custom domain lists
- Auto-updates, tray icon, connect on launch
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

1. Download the installer for your OS from [app.levushka.app](https://app.levushka.app).
2. Open the app and import your subscription (link from bot or [my.levushka.app](https://my.levushka.app)).
3. Choose a server and tap **Connect**. macOS/Windows may ask for administrator permission once to install the network helper.

### Support

- Website: [levushka.app](https://levushka.app)
- Personal account: [my.levushka.app](https://my.levushka.app)
- Bugs and feature requests: [GitHub Issues](https://github.com/MihichN/levushka-desktop/issues)

### License

Client binaries are distributed by Levushka. This repository contains documentation and release metadata unless otherwise noted. See [LICENSE](LICENSE).
