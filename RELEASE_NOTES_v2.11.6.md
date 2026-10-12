# Release Notes — v2.11.6

## Changed
- Capture now ignores `splitproxy.*` (Split.io feature-flag proxy) and static files: any `.json` path or `/locales/` path outside `/api/`. Replaying a real 41-request Venues-page capture through the new filter keeps 34 records and cuts stored response bodies from about 507 KB to 154 KB.
- Real API calls such as `/allowedOperations` and `/analytics/api/...` are still captured.

## Includes
- v2.11.5: POST read queries no longer counted as writes; exports report the correct version.
- v2.11.4: streaming-fetch fix, batched writes, RUCKUS-host scoping, structured redaction.

## Known limitations
- iframes are not captured; early page requests may be missed; the page bridge cannot authenticate messages.
- Bodies over 120 KB are still truncated (for example `/allowedOperations`).
- Live testing against a real tenant has not been performed.
