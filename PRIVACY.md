# Privacy Policy — InfoPeek

_Last updated: 2026-08-07_

InfoPeek is a browser extension that helps developers manage cookies and view/edit JSON. **Your data never leaves your browser.**

## What InfoPeek does with your data

- **Cookies, JWT contents, and JSON** you view or edit are processed **entirely locally**, inside your browser. They are never uploaded, transmitted, collected, sold, or shared with the developer or any third party.
- InfoPeek performs **no analytics, no telemetry, no tracking**, and contains no advertising.
- Your **settings** (interface language, JWT field names, value-masking toggle, JSON preferences) are stored using the browser's own `storage.sync` API. They sync through your browser account (Google/Firefox), never through any InfoPeek server — the developer cannot see them.

## Network requests

InfoPeek makes **no network requests on its own**. It never fetches, prefetches, or "phones home" to any endpoint, and it has no servers of its own. There are exactly **two cases** where a request happens, both driven entirely by you:

- **Request Replay** (the Replay tab). When you paste a cURL command and click **Send**, InfoPeek sends that one request to the address you supplied, using your browser's existing cookies for that site. Nothing is sent anywhere else, and nothing is sent to the developer. Requests happen only on an explicit click — there is no auto-send, no retry, no polling, and no replay when the page loads. The request list is kept in browser session memory only and is erased when you close your browser; it is never written to disk or synced to your account.
- **Remote media rendering** in the JSON list view. This is **disabled by default**. Only if you explicitly enable it in Settings (or via the inline **Show media** button, which shows the same warning) will the list view load image/video/audio resources from URLs contained in the JSON you are viewing — a request that goes directly from your browser to those media servers. Media is first requested without credentials; if that server rejects the anonymous request, it is retried as an ordinary load, which may include your cookies for that server. Enabling it shows a warning covering this first. When disabled (the default), no such requests are ever made.

## Permissions and why they are requested

| Permission | Purpose |
|---|---|
| `cookies` | Read and edit cookies for the site(s) you explicitly authorize — the core feature. |
| `activeTab` | Read the current tab's URL to determine which site's cookies to show. |
| `storage` | Save your settings locally (synced by your browser account). |
| `downloads` | Export cookies/JSON to files you choose to save. |
| `scripting` | On sites you have authorized, replace a raw JSON response page with the local JSON viewer. |
| `declarativeNetRequestWithHostAccess` | Apply the request headers you typed (such as `Cookie` or `User-Agent`) to a single request you send from the Replay tab. The rule exists only for the duration of that one request, matches only the extension's own request (never anything a web page sends), and works only on sites you have authorized. No rules are ever created in the background. |
| Host access (`<all_urls>`, optional) | Requested **at runtime, per site, only when you ask** — never granted at install time. You can revoke it any time in Settings. |

InfoPeek requests **no host permissions at install time**. Site access is always granted on demand and can be revoked at any time.

## Data retention & deletion

InfoPeek stores nothing on any server, so there is nothing for us to retain or delete. Uninstalling the extension removes its local settings from your browser.

## Contact

Questions about this policy: open an issue at <https://github.com/posuihushui/InfoPeek/issues>.

---

# 隐私政策 — InfoPeek

_最后更新：2026-08-07_

InfoPeek 是一款帮助开发者管理 Cookie、查看/编辑 JSON 的浏览器扩展。**你的数据永不离开浏览器。**

## InfoPeek 如何处理你的数据

- 你查看或编辑的 **Cookie、JWT 内容、JSON**，全部在浏览器**本地处理**，绝不上传、传输、收集、出售或分享给开发者或任何第三方。
- InfoPeek **不做任何分析、遥测、追踪**，不含广告。
- 你的**设置**（界面语言、JWT 字段名、值打码开关、JSON 偏好）使用浏览器自带的 `storage.sync` 存储，通过你的浏览器账号（Google/Firefox）同步，绝不经过任何 InfoPeek 服务器——开发者无法看到。

## 网络请求

InfoPeek **自身不发起任何网络请求**，不抓取、不预取、不"回传"，也没有任何自有服务器。仅有**两种由你主动触发**的情况会产生请求：

- **请求重放**（重放 Tab）。当你粘贴一条 cURL 命令并点击**发送**时，InfoPeek 会用你浏览器中该站点的现有 Cookie，向你自己填入的地址发出这一次请求。不会发往其他任何地方，也不会发给开发者。请求只在你显式点击时发生——没有自动发送、没有失败重试、没有轮询、页面加载时也不会自动重放。请求列表只保存在浏览器会话内存中，关闭浏览器即清空，绝不写入磁盘、也不同步到你的账号。
- JSON 列表视图的**远程媒体渲染**。此功能**默认关闭**。只有当你在设置中显式开启后（或通过列表里的 **显示媒体** 按钮开启，弹出同一句警告），列表视图才会加载 JSON 中 URL 指向的图片/视频/音频资源——该请求由你的浏览器直接发往这些媒体服务器。媒体先以不带凭证的方式请求；若该服务器拒绝匿名请求，会退回普通方式重试一次，那次可能带上你在该服务器的 Cookie。开启前的警告已写明这一点。关闭时（默认）永不发起此类请求。

## 权限及申请理由

| 权限 | 用途 |
|---|---|
| `cookies` | 读取/编辑你明确授权站点的 Cookie —— 核心功能。 |
| `activeTab` | 读取当前标签 URL，以确定展示哪个站点的 Cookie。 |
| `storage` | 本地保存你的设置（由浏览器账号同步）。 |
| `downloads` | 将 Cookie/JSON 导出为你选择保存的文件。 |
| `scripting` | 在你已授权的站点上，把原始 JSON 响应页替换为本地 JSON 查看器。 |
| `declarativeNetRequestWithHostAccess` | 把你自己填写的请求头（如 `Cookie`、`User-Agent`）应用到你从重放 Tab 发出的那一次请求上。规则只在该次请求期间存在、只匹配扩展自己发出的那个请求（绝不影响网页发出的任何请求）、且只在你已授权的站点上生效。后台绝不创建任何规则。 |
| 主机访问（`<all_urls>`，可选） | **运行时按站点、仅在你请求时**申请，安装时绝不授予；可随时在设置中撤销。 |

InfoPeek 安装时**不申请任何主机权限**，站点访问始终按需授予、可随时撤销。

## 数据留存与删除

InfoPeek 不在任何服务器存储数据，因此没有需要留存或删除的内容。卸载扩展即从浏览器移除其本地设置。

## 联系方式

关于本政策的疑问，请在 <https://github.com/posuihushui/InfoPeek/issues> 提交 issue。
