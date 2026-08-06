# Changelog

All notable changes to InfoPeek. Dates are release dates.

## v1.1.0 — 2026-08-06

### Added

- **Request Replay** — a new tool alongside the cookie manager and JSON viewer.
  - Paste a cURL command copied from Chrome DevTools; it is parsed directly from the
    clipboard, no extra dialog.
  - Requests are sent with your browser's current cookies for that site attached
    automatically, including `HttpOnly` ones — no copying tokens around.
  - Per-endpoint request list grouped by origin. Each entry keeps its own body,
    headers, and cookie strategy, so switching between endpoints never loses your edits.
  - Cookie panel compares what the cURL command carried against what your browser
    currently holds, with JWT decoding and expiry.
  - Responses open in the same text / table / list views as the JSON viewer, or with
    one click into a full JSON Viewer tab.
  - Requests are sent **only when you click Send** — no auto-send, retry, or polling.
    The request list lives in browser session memory and is erased when you close the
    browser; it is never written to disk or synced.

### Changed

- Navigation moved from the manager page into the popup. The manager now opens as a
  single-purpose page; a floating logo (or `⌘/Ctrl + K`) switches pages.
- Browser tab titles now name the page, so multiple manager tabs are distinguishable.

### Permissions

- Added `declarativeNetRequestWithHostAccess`. It applies the request headers you typed
  (such as `Cookie` or `Origin`) to a single request you send from the Replay tab. The
  rule exists only for the duration of that request, applies only to the extension's own
  request, and works only on sites you have authorized. No rules are ever created in the
  background. This permission produces no install-time prompt.

### Fixed

- Settings: the About logo pointed at an icon that had been removed from the package.
