# FontFixer

English | [中文](languages/README_zh.md) | [Español](languages/README_es.md) | [Deutsch](languages/README_de.md) | [日本語](languages/README_ja.md) | [Français](languages/README_fr.md)

A lightweight browser extension that optimizes webpage fonts for comfortable reading. Change font family, size, and text colors with one click.

> Chromium-based · Manifest V3 · Minimal Permissions · No Tracking

---

## Why FontFixer?

Many websites use small, blurry, or hard-to-read fonts. FontFixer lets you adjust webpage fonts with your preferred typeface, adjust font size, and customize text/link colors — all in real-time, with zero page reload.

| Advantage | Detail |
|-----------|--------|
| 🔤 **Local Font Support** | Reads fonts installed on your device via `queryLocalFonts` API |
| ⚡ **Real-Time Preview** | All changes apply instantly as you adjust — no page refresh |
| 💾 **Per-Site Memory** | Saves different font settings for different websites |
| ⚙️ **Auto Apply** | Re-apply saved settings automatically every time you visit a configured site |
| 🔒 **Permissions** | `storage` + `scripting` + `activeTab`; `<all_urls>` host access only to inject fonts on sites you configure |

---

## Features

### 🆓 Free

| Feature | Description |
|---------|-------------|
| 🔤 **Font Selection** | Choose from 3 built-in fonts (Noto Sans, Source Han Sans, Arial) or any font installed on your device |
| 📏 **Font Size Scaling** | Adjust from 80% to 160% with a slider |
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

| Browser | Status |
|---------|--------|
| Google Chrome | ✅ Fully supported |
| Microsoft Edge | ✅ Fully supported |
| Other Chromium-based browsers | ✅ Should work |

---

## Installation

1. Open your browser's extension page:
   - **Chrome**: `chrome://extensions/`
   - **Edge**: `edge://extensions/`
2. Enable **Developer mode** (top-right toggle)
3. Click **Load unpacked** and select the `font-fixer` folder
4. Click the 🔤 FontFixer icon in your toolbar to start

---

## Usage

### Change Fonts

1. Click the FontFixer icon in your toolbar
2. Select a font from the dropdown — 3 built-in fonts are always available; click **🔄** to load fonts installed on your device
3. Adjust font size with the slider (80%–160%)
4. Optionally change text and link colors
5. Click **Apply & Save** — settings apply instantly and are stored for this site

### Auto Apply

- Turn on the **Auto Apply** switch to automatically re-apply this site's saved settings every time you visit it
- With Auto Apply off, settings only apply when you open the popup and click **Apply & Save**

### Reset

- Click **Reset** to remove the current site's settings and restore its original fonts

---

## How It Works

```
Select font & adjust settings
       ↓
Click Apply & Save
       ↓
CSS injected via chrome.scripting.insertCSS
       ↓
Page fonts change instantly
       ↓
Settings saved to chrome.storage.local
       ↓
(Auto Apply on) re-applied automatically on your next visit
```

All style processing happens locally in your browser. The only network request is **optional** — when you activate a Pro license key, FontFixer contacts the license server with your key and basic browser metadata (browser, language, timezone). No webpage content is ever read or uploaded.

**Note for Local Font Access:** Local fonts use the Local Font Access API — no manifest permission needed. Chrome shows a permission prompt at runtime, and the API only runs during a user click, so open the popup and click the **🔄 refresh button** to load your local fonts. Only font display names are read — font source files are not extracted, copied or uploaded. You can revoke the grant in browser settings at any time.

**Auto Apply Rule:** Automatic style injection is per site. Turn on the **Auto Apply** switch in the popup to re-apply that site's settings on every visit; with it off, settings apply only when you click **Apply & Save**.

---

## Font Copyright Notice

Three built-in typefaces (Noto Sans, Source Han Sans, Arial) are distributed under SIL Open Font License, which allows personal and commercial use without extra authorization.

The extension only reads the name list of fonts installed on your local device via browser standard API, and will not extract, copy or upload any local font files. All rights of system fonts belong to their respective copyright holders.

---

## Privacy

- `storage` — Saves your font preferences locally. No webpage content is stored.
- `scripting` — Injects CSS to change page fonts. Does not read page text or data.
- `activeTab` — Only accesses the current tab when you interact with the extension.
- `<all_urls>` — Lets the extension re-apply your saved font styles automatically on sites you've configured. It never reads or uploads page content.
- **Local Font Access** — No manifest permission; access is granted at runtime via a browser prompt. Reads only display names, never font files. Can be revoked at any time.
- No tracking, no analytics. The only network request is license activation/validation when you use a Pro license key.

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

> **Note:** This repository is for **project showcase purposes only**. It does not contain the full source code, manifest, icons, or build scripts. Full source code will **not** be published here.
