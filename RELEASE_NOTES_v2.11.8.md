# Release Notes — v2.11.8

## Fixed
- **Settings tab added.** The two options introduced in v2.11.7 (mask emails in exports; max captured response size) had no way to be opened: the Settings view was hidden by CSS and had no nav button. They now live in a new **Settings** tab (Live Capture · Visual API Flow · API Relationships · Settings). The old Projects & backup panel stays hidden.

## Removed
- The hidden **Projects & backup** panel and its backup/import handlers' wiring (the UI was already hidden by CSS and unreachable).
- The stray **Live request timeline** heading and its "N shown" counter.

## Options (defaults unchanged)
- **Mask email addresses in exports** — off by default.
- **Max captured response size** — 120 KB default; 500 KB, 1 MB, 2 MB. Applies to new captures; reload open RUCKUS One tabs after changing.

## Includes v2.11.7
- Bounded the text-redaction regex that could freeze the page on large non-JSON bodies.

## Known limitations
- iframes are not captured; early page requests may be missed; the page bridge cannot authenticate messages.
- Live testing against a real tenant has not been performed.
