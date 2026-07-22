# Privacy Policy — InfoPeek

_Last updated: 2026-07-22_

InfoPeek is a browser extension that helps developers manage cookies and view/edit JSON. **Your data never leaves your browser.**

## What InfoPeek does with your data

- **Cookies, JWT contents, and JSON** you view or edit are processed **entirely locally**, inside your browser. They are never uploaded, transmitted, collected, sold, or shared with the developer or any third party.
- InfoPeek performs **no analytics, no telemetry, no tracking**, and contains no advertising.
- Your **settings** (interface language, JWT field names, value-masking toggle, JSON preferences) are stored using the browser's own `storage.sync` API. They sync through your browser account (Google/Firefox), never through any InfoPeek server — the developer cannot see them.

## Network requests

InfoPeek makes **no network requests** as part of its normal operation. There is exactly **one optional exception**:

- **Remote media rendering** in the JSON list view. This is **disabled by default**. Only if you explicitly enable it in Settings will the list view load image/video/audio resources from URLs contained in the JSON you are viewing — a request that goes directly from your browser to those media servers. Enabling it shows a warning first. When disabled (the default), no such requests are ever made.

InfoPeek does not fetch, prefetch, or "phone home" to any endpoint under any circumstances.

## Permissions and why they are requested

| Permission | Purpose |
|---|---|
| `cookies` | Read and edit cookies for the site(s) you explicitly authorize — the core feature. |
| `activeTab` | Read the current tab's URL to determine which site's cookies to show. |
| `storage` | Save your settings locally (synced by your browser account). |
| `downloads` | Export cookies/JSON to files you choose to save. |
| `scripting` | On sites you have authorized, replace a raw JSON response page with the local JSON viewer. |
| Host access (`<all_urls>`, optional) | Requested **at runtime, per site, only when you ask** — never granted at install time. You can revoke it any time in Settings. |

InfoPeek requests **no host permissions at install time**. Site access is always granted on demand and can be revoked at any time.

## Data retention & deletion

InfoPeek stores nothing on any server, so there is nothing for us to retain or delete. Uninstalling the extension removes its local settings from your browser.

## Contact

Questions about this policy: open an issue at <https://github.com/posuihushui/InfoPeek/issues>.

---

# 隐私政策 — InfoPeek

_最后更新：2026-07-22_

InfoPeek 是一款帮助开发者管理 Cookie、查看/编辑 JSON 的浏览器扩展。**你的数据永不离开浏览器。**

## InfoPeek 如何处理你的数据

- 你查看或编辑的 **Cookie、JWT 内容、JSON**，全部在浏览器**本地处理**，绝不上传、传输、收集、出售或分享给开发者或任何第三方。
- InfoPeek **不做任何分析、遥测、追踪**，不含广告。
- 你的**设置**（界面语言、JWT 字段名、值打码开关、JSON 偏好）使用浏览器自带的 `storage.sync` 存储，通过你的浏览器账号（Google/Firefox）同步，绝不经过任何 InfoPeek 服务器——开发者无法看到。

## 网络请求

InfoPeek 在正常使用中**不发起任何网络请求**。仅有**一个可选例外**：

- JSON 列表视图的**远程媒体渲染**。此功能**默认关闭**。只有当你在设置中显式开启后，列表视图才会加载 JSON 中 URL 指向的图片/视频/音频资源——该请求由你的浏览器直接发往这些媒体服务器。开启前会先弹出警告。关闭时（默认）永不发起此类请求。

InfoPeek 在任何情况下都不会向任何端点抓取、预取或"回传"数据。

## 权限及申请理由

| 权限 | 用途 |
|---|---|
| `cookies` | 读取/编辑你明确授权站点的 Cookie —— 核心功能。 |
| `activeTab` | 读取当前标签 URL，以确定展示哪个站点的 Cookie。 |
| `storage` | 本地保存你的设置（由浏览器账号同步）。 |
| `downloads` | 将 Cookie/JSON 导出为你选择保存的文件。 |
| `scripting` | 在你已授权的站点上，把原始 JSON 响应页替换为本地 JSON 查看器。 |
| 主机访问（`<all_urls>`，可选） | **运行时按站点、仅在你请求时**申请，安装时绝不授予；可随时在设置中撤销。 |

InfoPeek 安装时**不申请任何主机权限**，站点访问始终按需授予、可随时撤销。

## 数据留存与删除

InfoPeek 不在任何服务器存储数据，因此没有需要留存或删除的内容。卸载扩展即从浏览器移除其本地设置。

## 联系方式

关于本政策的疑问，请在 <https://github.com/posuihushui/InfoPeek/issues> 提交 issue。
