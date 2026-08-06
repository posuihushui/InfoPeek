<div align="center">
  <img src="assets/icon-128.png" width="96" height="96" alt="InfoPeek" />
  <h1>InfoPeek</h1>
  <p><strong>Peek into cookies &amp; JSON — 100% local, zero tracking.</strong></p>
  <p>Cookie 管理 + JSON 查看器，全本地运行，零数据上传。</p>
</div>

---

InfoPeek is a cross-browser (Chrome / Edge / Firefox) developer extension with three tools:

- **Cookie manager** — view, edit, import/export (JSON &amp; Netscape `cookies.txt`) the cookies of any site you authorize, with built-in JWT decoding.
- **JSON viewer** — view, edit, format, repair, search (JSONPath / key / value) JSON; table &amp; list views with smart rendering for arrays.
- **Request replay** — paste a cURL command copied from DevTools and replay it with your browser's current cookies attached automatically; swap the endpoint and resend while debugging; responses open straight into the JSON views.

**Privacy-first by design:** no analytics, no tracking, no servers of our own; dynamic per-site permissions; everything processed locally. The only network requests are the ones you explicitly trigger, to addresses you enter yourself. See [PRIVACY.md](./PRIVACY.md).

> This repository hosts **release artifacts and documentation only**. The source code is maintained privately.

## Install

_Store links will appear here once published._

- Chrome Web Store — _coming soon_
- Microsoft Edge Add-ons — _coming soon_
- Firefox Add-ons (AMO) — _coming soon_

Until then, grab a build from [**Releases**](https://github.com/posuihushui/InfoPeek/releases) and load it unpacked:

- **Chrome / Edge**: unzip `infopeek-1.1.1-chrome.zip`, open `chrome://extensions`, enable Developer mode, "Load unpacked".
- **Firefox**: open `about:debugging` → This Firefox → Load Temporary Add-on → pick the `manifest.json` inside `infopeek-1.1.1-firefox.zip`.

## Features

- Cookie list with masked values, expiry chips, JWT 🔑 decode panel
- Full cookie editor: all attributes, `__Host-`/`__Secure-` prefix locking, SameSite rules
- Import/export: JSON (EditThisCookie-compatible) &amp; Netscape `cookies.txt` (curl/yt-dlp compatible)
- JSON viewer: format / minify / auto-repair invalid JSON, JSONPath + key/value search
- JSON table &amp; list views with smart value rendering (timestamps → local time, booleans, colors, embedded JSON, JWT)
- Request replay: paste-to-create from cURL, per-endpoint request list, cookie diff (cURL vs browser), response headers &amp; cookie changes
- English &amp; 简体中文, light theme, Manifest V3

## Privacy

Your data never leaves your browser. No uploads, no tracking, no servers of our own. Network requests happen only when you trigger them yourself — sending a request from the Replay tab, or the optional remote-media rendering (off by default). Full policy: [PRIVACY.md](./PRIVACY.md).

## License

Proprietary — © 2026 posuihushui. **All rights reserved.** See [LICENSE](./LICENSE). The extension is distributed only through official browser-extension stores.
