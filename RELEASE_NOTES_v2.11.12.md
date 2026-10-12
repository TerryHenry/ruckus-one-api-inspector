# Release Notes — v2.11.12

## Fixed
- **Settings tab layout.** The panel had no padding and the long “Mask client identifiers” label overflowed the side panel. It now has padding, wraps correctly, and the select no longer crowds the label.
- **Leftover support-notes box.** An unstyled “What were you doing?” text box remained at the bottom of the Visual API Flow tab after the support-notes section was removed in 2.11.3. It is gone.

## Documentation
- Getting Started and User Guide rewritten for v2.11.12 with screenshots regenerated from the current UI (four tabs, Settings tab, schema-based endpoint descriptions, troubleshooting/baselines, API Relationships, masking options, how capture works, a changelog since 2.10.1).
- The v2.10.1 guides were replaced.

## Notes
- The exported support bundle’s `notes` field is now always empty because the notes box was removed.

## Known limitations
- iframes are not captured; early page requests may be missed; the page bridge cannot authenticate messages.
- A tenant ID is replaced in masked exports only once it has been seen in a processed record.
- Live testing against a real tenant has not been performed.
