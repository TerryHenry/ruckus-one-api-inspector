# RUCKUS One API Inspector

A browser extension for observing and visualizing API requests made by the RUCKUS One web interface.

## Current build: 2.11.4

v2.11.4 is a hardening release (see `RELEASE_NOTES_v2.11.4.md`): fixes fetch capture blocking streaming responses, fixes lost records under concurrent traffic, restricts capture to RUCKUS hosts, and replaces regex-only redaction with structured JSON redaction.

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


Captured traffic may include tenant identifiers, personal information, internal URLs, or authentication-related material. Treat captures as sensitive operational data. Review and sanitize captures before sharing them. Never commit credentials, tokens, browser profiles, or real tenant traffic.

## Validation

The v2.11.4 package passed JavaScript syntax checks and mock-based tests of the page hook (redaction, streaming responses, host filtering) and background write queue (200 concurrent captures, none lost). Live testing in Chrome against a real RUCKUS One tenant has not been performed.

## Disclaimer

This is an independent utility and is not an official RUCKUS product. RUCKUS and RUCKUS One are trademarks of their respective owners.
