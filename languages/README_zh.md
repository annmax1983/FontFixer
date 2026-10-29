# FontFixer
[English](../README.md) | 中文 | [Español](README_es.md) | [Deutsch](README_de.md) | [日本語](README_ja.md) | [Français](README_fr.md)

一款轻量级浏览器扩展，优化网页字体以获得舒适阅读体验。一键更换字体、调整字号和文字颜色。

> Chrome / Edge / Firefox · Manifest V3 · 最小权限 · 无追踪

---

## 功能特性

### 🆓 免费版

| 功能 | 说明 |
|------|------|
| 🔤 **字体选择** | 3 种内置字体（Noto Sans、Source Han Sans、Arial）或（仅 Chrome / Edge）设备上安装的任意字体 |
| 📏 **字号缩放** | 50% 至 500% 滑动调节 |
| 🎨 **文字颜色** | 取色器自定义文字颜色 |
| 🔗 **链接颜色** | 单独设置链接颜色，提升可读性 |
| 🔄 **自动应用** | 每次访问时自动重放已保存的设置 |
| 💾 **自动保存** | 按站点自动持久化设置（最多 5 个站点） |
| ↺ **一键重置** | 即时恢复原始页面字体 |
| 🌍 **6 种语言** | 英文、中文、日文、西班牙文、德文、法文 |

### ⭐ 付费版（需激活密钥）

| 功能 | 说明 |
|------|------|
| ♾️ **无限配置** | 为任意数量的网站保存字体设置 |
| 📦 **导入 / 导出** | 导出配置并在其他设备上导入 |

---

## 支持的浏览器

| 浏览器 | 状态 |
|--------|------|
| Google Chrome | ✅ 完全支持 |
| Microsoft Edge | ✅ 完全支持 |
| Mozilla Firefox | ✅ 完全支持 |
| 其他 Chromium 内核浏览器 | ✅ 应该可用 |

> **Firefox 说明：** Firefox 不提供 `queryLocalFonts`，无法读取本地字体列表，只能使用内置字体。其余功能与 Chrome / Edge 一致。Firefox 版的两款内置网页字体（Noto Sans、思源黑体）会在首次使用时从 jsDelivr CDN 下载，其余处理全部在本地完成。

---

## 安装

| 商店 | 链接 |
|---|---|
| Chrome 应用商店 | [在 Chrome 中安装](https://chromewebstore.google.com/detail/fdcanpeipbhjnjimogebfdfkmmchoiib) |
| Microsoft Edge 加载项 | [在 Edge 中安装](https://microsoftedge.microsoft.com/addons/detail/npoflpnnknpmehccioccmhifddfaeahj) |
| Firefox 附加组件（AMO） | 🔜 审核中，上架后补充链接 |

> 请只通过上方官方商店安装，避免使用第三方下载站。

---

## 使用方法

1. 点击 FontFixer 图标
2. 从下拉菜单选择字体（或点击内置字体标签）
3. 滑动调整字号
4. 可选：勾选**文字颜色**或**链接颜色**后自定义（不勾选则完全不改动页面颜色）
5. 点击 **应用** — 即时生效

### 自动应用

- 开启**自动应用**开关后，每次访问该站点都会自动重放保存的设置
- 关闭自动应用时，设置仅在打开弹窗并点击**应用**后生效

---

## 隐私

- `storage` — 本地保存字体偏好，不存储网页内容
- `scripting` — 注入 CSS 更改页面字体，不读取页面文本或数据
- `activeTab` — 仅在您与扩展交互时访问当前标签页
- `<all_urls>` — 用于在您已配置的网站上自动重放已保存的字体样式。它从不读取或上传网页内容。
- **本地字体访问** — 仅 Chrome / Edge。无需清单权限；通过浏览器运行时提示授权。仅读取字体显示名称，从不读取字体文件，可随时撤销。Firefox 不提供该 API，因此不申请任何相关权限。
- 无追踪、无分析。网络请求只有两处：使用 Pro 授权密钥时的授权激活/验证，以及 Firefox 版首次使用内置网页字体时从 jsDelivr 下载字体文件。

---

## 源码说明

> ⚠️ **此处不发布源码。** 本仓库仅提供使用说明、更新日志和留言支持服务。扩展程序仅通过 Chrome Web Store、Microsoft Edge Add-ons 与 Firefox 附加组件（AMO） 分发，不提供离线安装包或终端用户源代码。

---

## 许可证

Copyright © 2026 FontFixer. 保留所有权利。
