# Changelog

All notable changes to InfoPeek. Dates are release dates.

## v1.1.2 — 2026-08-07

### Fixed

- Remote media in the JSON views could not be displayed at all for many URLs.
  - Media elements were always loaded with `crossorigin="anonymous"`, which turns the
    load into a CORS request. Servers that do not send `Access-Control-Allow-Origin` —
    most image CDNs — simply failed. Media is now requested anonymously first and
    retried as an ordinary load if that is rejected. The retry may include your cookies
    for that server; the warning shown when enabling remote media now says so.
  - Choosing **Image / Video / Audio** from a field's display-type menu did nothing
    unless remote media had already been enabled in Settings. An explicit per-field
    choice now renders directly, after the same one-time confirmation. Automatically
    detected media is still governed by the Settings toggle and remains off by default.

### Added

- Remote media can be enabled where you need it, without a trip to Settings: from a
  **Show media** button next to a media URL, or by picking a media display type for a
  field. Both show the same warning as the Settings toggle.

### Changed

- The privacy policy now describes the `declarativeNetRequestWithHostAccess` rule
  accurately: it matches only the extension's own replay request, never anything a web
  page sends.

## v1.1.1 — 2026-08-06

### Fixed

- Popup: cookie names were cut off mid-character instead of being ellipsised. The name
  cell is a flex container, where `text-overflow: ellipsis` has no effect — the text now
  sits in its own layer, and hovering a name shows it in full.
- Popup: the back button took a row of its own above the site header, wasting vertical
  space in a 580px-tall surface. It now sits inside the header of the cookie list.
- Popup: the cookie list carried its own `max-height` on top of the popup's, so a long
  list could overflow past the popup's own bounds. Height is now owned by one place.

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
