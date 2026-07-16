# FontFixer

English | [中文](languages/README_zh.md) | [Español](languages/README_es.md) | [Deutsch](languages/README_de.md) | [日本語](languages/README_ja.md) | [Français](languages/README_fr.md)

A lightweight browser extension that optimizes webpage fonts for comfortable reading. Change font family, size, and text colors with one click.

> Chromium-based · Manifest V3 · Minimal Permissions · Fully Local

---

## Why FontFixer?

Many websites use small, blurry, or hard-to-read fonts. FontFixer lets you adjust webpage fonts with your preferred typeface, adjust font size, and customize text/link colors — all in real-time, with zero page reload.

| Advantage | Detail |
|-----------|--------|
| 🔤 **Local Font Support** | Reads fonts installed on your device via `queryLocalFonts` API |
| ⚡ **Real-Time Preview** | All changes apply instantly as you adjust — no page refresh |
| 💾 **Per-Site Memory** | Saves different font settings for different websites |
| 🌐 **Global Mode** | Apply one font configuration across all websites |
| 🔒 **Minimal Permissions** | Only `storage` + `scripting` + `activeTab` — no `<all_urls>` |

---

## Features

| Feature | Description |
|---------|-------------|
| 🔤 **Font Selection** | Choose from 3 built-in fonts (Noto Sans, Source Han Sans, Arial) or any font installed on your device |
| 📏 **Font Size Scaling** | Adjust from 80% to 160% with a slider |
| 🎨 **Text Color** | Custom text color with color picker |
| 🔗 **Link Color** | Separate link color for better readability |
| 🔄 **Scope Control** | Apply to current site only or all websites |
| 💾 **Auto-Save** | Settings persist automatically per site |
| ↺ **One-Click Reset** | Restore original page fonts instantly |
| 🌍 **6 Languages** | English, Chinese, Japanese, Spanish, German, French |

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
2. Select a font from the dropdown (or click a built-in font chip)
3. Adjust font size with the slider
4. Optionally change text and link colors
5. Click **Apply** — changes take effect instantly

### Per-Site vs Global

- **This Site** (default): Settings only apply to the current website
- **All Sites**: Settings apply to every website you visit
- Switch between modes using the scope buttons


### Reset

- Click **Reset** to restore the current site's original fonts

---

## How It Works

```
Select font & adjust settings
       ↓
Click Apply
       ↓
CSS injected via chrome.scripting.insertCSS
       ↓
Page fonts change instantly
       ↓
Settings saved to chrome.storage.local
```

All processing happens locally in your browser. No network requests, no data upload.

**Note for Local Font Access:** The browser will pop up a permission request window when reading your installed font list for the first time. Only font display names are read — font source files are not extracted, copied or uploaded. You may revoke this permission in browser settings at any time.

**Global Mode Rule:** When enabling "All Sites", style injection only triggers after you click the extension icon. Style injection only triggers after you click the extension icon.

---

## Font Copyright Notice

Three built-in typefaces (Noto Sans, Source Han Sans, Arial) are distributed under SIL Open Font License, which allows personal and commercial use without extra authorization.

The extension only reads the name list of fonts installed on your local device via browser standard API, and will not extract, copy or upload any local font files. All rights of system fonts belong to their respective copyright holders.

---

## Privacy

- `storage` — Saves your font preferences locally. No webpage content is stored.
- `scripting` — Injects CSS to change page fonts. Does not read page text or data.
- `activeTab` — Only accesses the current tab when you click Apply.
- No tracking, no analytics, no external connections.

---

## Copyright Disclaimer

This extension only locally adjusts the visual rendering style of web pages for users' comfortable reading experience. All text, images and content copyright of the website belong to the original publisher. Modifying page display styles does not grant users any copyright authorization for the website content. Users shall abide by local intellectual property laws when browsing web pages.

---

## License

Copyright © 2026 FontFixer. All rights reserved.

---

## ❤️ Support

If you find FontFixer helpful, consider supporting the project!

**[👉 Click here to support](https://annmax1983.github.io/FontFixer/)**

---

> **Note:** This repository is for **project showcase purposes only**. It does not contain the full source code, manifest, icons, or build scripts. Full source code will **not** be published here.
