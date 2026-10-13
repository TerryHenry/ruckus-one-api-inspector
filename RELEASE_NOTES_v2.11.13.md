# Release Notes — v2.11.13

## Changed
- **Site access narrowed to `https://*.ruckus.cloud/*`.** `https://*.ruckusone.com/*` is no longer in `host_permissions`, no longer a content-script match (both injected scripts), no longer targeted when the capture toggle is relayed to open tabs, and no longer accepted by the page hook's host filter. Chrome will not run the extension on `ruckusone.com`, and any request to a `ruckusone.com` host is ignored.
- The (hidden) sequence-execution host allow-list and the safe-request preview warning also dropped `ruckusone.com`.

## Documentation
- Getting Started and User Guide updated for v2.11.13: version strings and the capture-scope wording (`ruckus.cloud` only). Hand edits made to the v2.11.12 guides are preserved.

## Tested
- Host filter: `*.ruckus.cloud` hosts captured; `ruckusone.com`, `notruckus.cloud`, and `ruckus.cloud.evil.example` ignored. Existing redaction, noise-filter, streaming, concurrent-write, and write-classification tests pass.

## Known limitations
- iframes are not captured; early page requests may be missed; the page bridge cannot authenticate messages.
- A tenant ID is replaced in masked exports only once it has been seen in a processed record.
- Live testing against a real tenant has not been performed.
