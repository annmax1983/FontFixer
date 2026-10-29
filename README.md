# FontFixer

English | [中文](languages/README_zh.md) | [Español](languages/README_es.md) | [Deutsch](languages/README_de.md) | [日本語](languages/README_ja.md) | [Français](languages/README_fr.md)

A lightweight browser extension that optimizes webpage fonts for comfortable reading. Change font family, size, and text colors with one click.

> Chrome · Edge · Firefox · Manifest V3 · Minimal Permissions · No Tracking

---

## Why FontFixer?

Many websites use small, blurry, or hard-to-read fonts. FontFixer lets you adjust webpage fonts with your preferred typeface, adjust font size, and customize text/link colors — all in real-time, with zero page reload.

| Advantage | Detail |
|-----------|--------|
| 🔤 **Local Font Support** | Reads fonts installed on your device via `queryLocalFonts` API (Chrome / Edge only — Firefox doesn't expose this API yet) |
| ⚡ **Real-Time Preview** | All changes apply instantly as you adjust — no page refresh |
| 💾 **Per-Site Memory** | Saves different font settings for different websites |
| ⚙️ **Auto Apply** | Re-apply saved settings automatically every time you visit a configured site |
| 🔒 **Permissions** | `storage` + `scripting` + `activeTab`; `<all_urls>` host access only to inject fonts on sites you configure |

---

## Features

### 🆓 Free

| Feature | Description |
|---------|-------------|
| 🔤 **Font Selection** | Choose from 3 built-in fonts (Noto Sans, Source Han Sans, Arial) or — on Chrome / Edge — any font installed on your device |
| 📏 **Font Size Scaling** | Adjust from 50% to 500% with a slider |
| 🎨 **Text Color** | Custom text color with color picker |
| 🔗 **Link Color** | Separate link color for better readability |
| 🔄 **Auto Apply** | Re-apply settings automatically on every visit to a configured site |
| 💾 **Auto-Save** | Settings persist automatically per site (up to 5 sites) |
| ↺ **One-Click Reset** | Restore original page fonts instantly |
| 🌍 **6 Languages** | English, Chinese, Japanese, Spanish, German, French |

### ⭐ Pro (License Required)

| Feature | Description |
|---------|-------------|
| ♾️ **Unlimited Configs** | Save font settings for unlimited websites |
| 📤 **Import / Export** | Backup and restore your font configurations across devices |

---

## Preview

<p align="center">
  <img src="icons/icon128.png" alt="FontFixer Icon" width="80">
</p>

---

## Supported Browsers

| Browser | Status | Notes |
|---------|--------|-------|
| Google Chrome | ✅ Fully supported | Manifest V3 |
| Microsoft Edge | ✅ Fully supported | Manifest V3 |
| Mozilla Firefox | ✅ Fully supported | Manifest V3, Firefox 140+ (desktop) |
| Other Chromium-based browsers | ✅ Should work | Manifest V3 |

> **Feature parity:** the only difference is local (system) font detection. Chrome and Edge expose the Local Font Access API (`queryLocalFonts`), so the **🔄** button can load every font installed on your device. Firefox does not implement that API, so the button is hidden there and you choose from the 3 built-in fonts instead. Font size, text colour, link colour, per-site memory, Auto Apply and Reset behave identically on all three browsers.

---

## Installation

| Store | Link |
|---|---|
| Chrome Web Store | [Install for Chrome](https://chromewebstore.google.com/detail/fdcanpeipbhjnjimogebfdfkmmchoiib) |
| Microsoft Edge Add-ons | [Install for Edge](https://microsoftedge.microsoft.com/addons/detail/npoflpnnknpmehccioccmhifddfaeahj) |
| Firefox Add-ons (AMO) | 🔜 Under review — link will be added once the listing is live |

> Install only from the official stores above — avoid third-party download sites.

---

## Usage

### Change Fonts

1. Click the FontFixer icon in your toolbar
2. Select a font from the dropdown — 3 built-in fonts are always available; on Chrome / Edge click **🔄** to load fonts installed on your device (Firefox has no font-enumeration API, so the **🔄** button is not shown there)
3. Adjust font size with the slider (50%–500%)
4. Optionally tick **Text Color** / **Link Color** to override colors (off = never touch page colors)
5. Click **Apply & Save** — settings apply instantly and are stored for this site

### Auto Apply

- Turn on the **Auto Apply** switch to automatically re-apply this site's saved settings every time you visit it
- With Auto Apply off, settings only apply when you open the popup and click **Apply & Save**

### Reset

- Click **Reset** to remove the current site's settings and restore its original fonts

---

## How It Works

1. Pick a font, then tune size and colours in the popup.
2. Click **Apply & Save** — the page restyles straight away, no reload.
3. Your settings are stored in your browser, one set per site.
4. With **Auto Apply** on, that site's settings are re-applied every time you visit it.

All style processing happens locally in your browser. Two network requests can happen: the **optional** licence check — when you activate a Pro licence key, FontFixer contacts the licence server with your key and basic browser metadata (browser, language, timezone) — and, on the Firefox build only, the download of the two bundled webfonts (Noto Sans, Source Han Sans) from the jsDelivr CDN when you select them for the first time. No webpage content is ever read or uploaded.

**Note for Local Font Access:** Local fonts use the Local Font Access API — no manifest permission needed. Chrome and Edge show a permission prompt at runtime, and the API only runs during a user click, so open the popup and click the **🔄 refresh button** to load your local fonts. Only font display names are read — font source files are not extracted, copied or uploaded. You can revoke the grant in browser settings at any time. Firefox does not implement this API, so that button is hidden and only the 3 built-in fonts are offered; no font-related permission is requested at all on Firefox.

**Auto Apply Rule:** Automatic style injection is per site. Turn on the **Auto Apply** switch in the popup to re-apply that site's settings on every visit; with it off, settings apply only when you click **Apply & Save**.

---

## Font Copyright Notice

FontFixer does not bundle any font files. Noto Sans and Source Han Sans are open-source typefaces available under the SIL Open Font License; Arial is a commercial typeface owned by Monotype and is offered only as a font-family choice when it is already installed on your system. All rights in installed fonts remain with their respective owners. On Firefox the two webfonts are fetched from the jsDelivr CDN at runtime instead of being bundled with the extension — the font files themselves are never uploaded, copied or modified by the extension.

The extension only reads the name list of fonts installed on your local device via browser standard API, and will not extract, copy or upload any local font files. All rights of system fonts belong to their respective copyright holders.

---

## Privacy

- `storage` — Saves your font preferences locally. No webpage content is stored.
- `scripting` — Injects CSS to change page fonts. Does not read page text or data.
- `activeTab` — Only accesses the current tab when you interact with the extension.
- `<all_urls>` — Lets the extension re-apply your saved font styles automatically on sites you've configured. It never reads or uploads page content.
- **Local Font Access** — Chrome / Edge only. No manifest permission; access is granted at runtime via a browser prompt. Reads only display names, never font files. Can be revoked at any time. Firefox does not offer this API, so nothing is requested there.
- **Firefox** — the same core permissions apply (`storage`, `scripting`, `activeTab`, `<all_urls>`), plus `https://api.annmax1983.com/*` for licence checks and `https://cdn.jsdelivr.net/*` to load the two built-in webfonts. Firefox shows them in *Add-ons Manager → Permissions* where you can review or revoke them.
- No tracking, no analytics. The only network requests are license activation/validation when you use a Pro license key, and — on Firefox — the one-off download of the two built-in webfonts from jsDelivr.

---

## Copyright Disclaimer

This extension only locally adjusts the visual rendering style of web pages for users' comfortable reading experience. All text, images and content copyright of the website belong to the original publisher. Modifying page display styles does not grant users any copyright authorization for the website content. Users shall abide by local intellectual property laws when browsing web pages.

---

## License

Copyright © 2026 FontFixer. All rights reserved.

---

## ❤️ Support

If you find FontFixer helpful, consider supporting the project!

**[👉 Get a License Key](https://www.annmax1983.com/checkout.html?plugin=fontfixer)**

---

> **Note:** This repository is a project showcase. The full source code is not published here.
