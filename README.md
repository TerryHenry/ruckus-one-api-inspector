# RUCKUS One API Inspector

A browser extension for observing and visualizing API requests made by the RUCKUS One web interface.

## Current fix build: 2.11.1

This build addresses two problems reported in v2.11.0:

- Workflow discovery now analyzes the captured request dataset independently of the Live Capture list filters (including the Active tab checkbox), so filters no longer accidentally hide requests from discovery.
- The Stop Live Capture control now handles background-message failures defensively, re-reads the saved capture state, and reports a warning rather than failing silently.

Core capabilities:
- **Live Capture** — observe API requests while navigating RUCKUS One.
- **Workflow Discovery** — group captured calls into time-based windows.
- **Visual API Flow** — visualize the chronological order of observed calls.
- **API Relationships** — inspect endpoint and field relationships inferred from captured traffic.

## Install in Chrome or Edge

1. Download and extract the Chrome/Edge ZIP package.
2. Open `chrome://extensions` in Chrome or `edge://extensions` in Edge.
3. Enable **Developer mode**.
4. Select **Load unpacked** and choose the extracted folder containing `manifest.json`.
5. Open RUCKUS One, start Live Capture, navigate through a workflow, then select Discover workflows.

## Install in Firefox

1. Download and extract the Firefox ZIP package.
2. Open `about:debugging#/runtime/this-firefox`.
3. Select **Load Temporary Add-on** and choose the extension's `manifest.json`.
4. Open RUCKUS One and test Live Capture, Workflow Discovery, and Visual API Flow.

Temporary Firefox add-ons normally need to be loaded again after Firefox restarts.

## Security and privacy

Captured traffic may include tenant identifiers, personal information, internal URLs, or authentication-related material. Treat captures as sensitive operational data. Review and sanitize captures before sharing them. Never commit credentials, tokens, browser profiles, or real tenant traffic.

## Validation

The JavaScript files pass Node syntax checks and both ZIP archives pass ZIP integrity checks. Live browser testing is still required; these checks do not prove that capture works in every browser or RUCKUS One tenant.

## Disclaimer

This is an independent utility and is not an official RUCKUS product. RUCKUS and RUCKUS One are trademarks of their respective owners.
