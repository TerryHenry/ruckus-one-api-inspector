# Release Notes — v2.11.7

## Added (opt-in, defaults unchanged)
- **Mask email addresses in exports** (Settings → Capture & export options). Replaces email-shaped strings with `[email]` in exports, backups and generated snippets. Stored captures are not modified. Off by default.
- **Max captured response size**: 120 KB (default), 500 KB, 1 MB or 2 MB. Applies to new captures; reload open RUCKUS One tabs after changing. Larger limits use more browser storage.

## Fixed
- Text-fallback redaction used an unbounded pattern that scaled quadratically on long alphanumeric runs (for example large non-JSON bodies), which could freeze the page. The key-name match is now bounded.

## Known limitations
- iframes are not captured; early page requests may be missed; the page bridge cannot authenticate messages.
- Live testing against a real tenant of the new settings has not been performed.
