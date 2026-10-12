# Release Notes — v2.11.4

## Fixed
- **Streaming responses no longer hang the page.** The fetch hook previously awaited the full response body before returning to the page; it now reads a clone in the background and skips `text/event-stream`.
- **No more lost records.** Captures are queued and written in serialized batches instead of per-request read-modify-write on `chrome.storage.local`.
- **Capture limited to RUCKUS hosts** (`*.ruckus.cloud`, `*.ruckusone.com`); third-party calls (analytics etc.) are no longer recorded.
- **Redaction hardened.** JSON bodies are parsed and any key matching token/secret/password/jwt/session/credential/etc. is masked (covers camelCase such as `accessToken`, and `id_token`, `jwt`); the text fallback handles quoted values containing spaces; sensitive URL query parameters are masked; request/response headers use one shared rule for fetch and XHR. The side panel's export redaction uses the same rules.

## Removed
- Unused popup files (`popup.html/js/css`); the toolbar icon opens the side panel.

## Known limitations
- iframes are not captured; requests made before the capture state reaches the page at `document_start` are missed.
- The page-to-extension bridge cannot authenticate messages from page scripts.
- Live browser testing against a real tenant has not been performed.
