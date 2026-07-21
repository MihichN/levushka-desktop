# What to publish on GitHub

This guide is for maintainers deciding how much of Levushka VPN Desktop to expose publicly.

## Three common models

### 1. Showcase only (recommended to start)

**Public:** README, screenshots, changelog, issue tracker, [GitHub Releases](https://docs.github.com/en/repositories/releasing-projects-on-github) with `.dmg` / `.exe` / `.apk` attachments or links to `app.levushka.app`.

**Private:** Full source, signing keys, `scripts/signing/`, release automation, subscription backend.

**Used by:** Many commercial VPN and messenger clients. Users see *what* the product is; you keep operational security.

**Pros:** Simple, no risk of leaking keys or helper install logic.  
**Cons:** Less community trust than open source; no external code review.

---

### 2. Open-source client, closed backend

**Public:** Application source (Tauri + Rust + React), build instructions without secrets, CONTRIBUTING.md.

**Private:** `subs`, billing, node provisioning, signing keys, encrypted `crypt1` production key.

**Used by:** Mullvad app, some WireGuard GUIs, community VPN clients.

**Pros:** Transparency, easier audits, community PRs for UI/bugs.  
**Cons:** Competitors can fork UI; you must scrub secrets before every push.

**If you choose this later:** publish from a sanitized branch; never commit:

- `scripts/signing/`
- `LEVUSHKA_CRYPT_KEY_B64` / production crypt key
- Ed25519 private keys for manifests
- Apple / Windows code-signing certificates

---

### 3. Full monorepo public

Rare for VPN products with a paid backend. Usually unnecessary unless the whole service is open source.

---

## What this `github/` folder is for

Contents here are meant to be the **root of a separate public repository**, e.g. `levushka-vpn-desktop`:

```bash
# Example: create public repo from this folder
cd github
git init
git add .
git commit -m "docs: initial public showcase"
git remote add origin git@github.com:YOUR_ORG/levushka-desktop.git
git push -u origin main
```

The private dev repo (`levushka-desktop`) stays where you build and sign releases.

---

## Checklist before first public push

- [ ] Confirm download URLs on `app.levushka.app` work
- [ ] Enable GitHub Issues (and optionally Discussions)
- [ ] Upload release artifacts or link to CDN in GitHub Releases
- [ ] Verify no secrets in committed files (`git secrets` / manual review)

---

## What users expect on GitHub

| Artifact | Showcase | Open client |
|----------|----------|-------------|
| README (RU/EN) | Yes | Yes |
| Screenshots / demo GIF | Yes | Yes |
| Changelog | Yes | Yes |
| Download / Releases | Yes | Yes |
| LICENSE | Yes (proprietary or OSS) | Yes (OSS) |
| SECURITY.md | Recommended | Yes |
| Source code | No | Yes |
| Build instructions | Optional | Yes |
| Issue templates | Yes | Yes |

---

## Releases workflow (showcase)

1. Build signed/notarized installers (and Android APK) in the private repo.
2. Upload to `app.levushka.app` (primary CDN):
   - macOS → `desktop/macos/`
   - Windows → `desktop/windows/`
   - Android → `desktop/android/`
3. Create a GitHub Release tag (e.g. `v0.4.0`) with:
   - Notes from `CHANGELOG.md`
   - Attachments **or** links to CDN (attachments have size limits).

Users often discover the app via GitHub README → Releases → download.
