# RUCKUS One API Inspector

A browser extension for observing and visualizing API requests made by the RUCKUS One web interface. It helps network engineers and support teams understand request patterns and the sequence of calls associated with UI workflows.

## Features

- Capture API requests while navigating RUCKUS One.
- Review captured requests in a timeline.
- Explore relationships and call sequences with the Visual API Flow view.
- Inspect request details to support troubleshooting and API discovery.

## Install

1. Download and extract the extension package from this repository.
2. Open `chrome://extensions` in Chrome or `edge://extensions` in Microsoft Edge.
3. Enable **Developer mode**.
4. Select **Load unpacked** and choose the extension folder containing `manifest.json`.
5. Open RUCKUS One in a browser tab, open the extension, and start capture.
6. Navigate through the workflow you want to examine, then review the captured requests and visual flow.

## Documentation

See the `docs/` folder for the User Guide and Getting Started guide.

## Security and privacy

Captured traffic may include tenant identifiers, user information, internal URLs, or authentication-related material. Treat captures as sensitive operational data. Review and redact captures before sharing them, and never commit credentials, tokens, or real tenant traffic to this repository.

Use the extension only with systems and accounts you are authorized to access, and follow your organization's security policies and the applicable service terms.

## Project status

This repository tracks the RUCKUS One API Inspector extension and its supporting documentation. Check the repository's releases or versioned package names for the applicable version.

## Disclaimer

This is an independent utility and is not an official RUCKUS product. RUCKUS and RUCKUS One are trademarks of their respective owners.
