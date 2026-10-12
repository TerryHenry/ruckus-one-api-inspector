# Release Notes — v2.11.10

## Changed (still opt-in via Settings → Mask client identifiers; default off)
- Also masks guest and contact fields: `mobilePhoneNumber`, `phoneNumber`, `fullName`, `firstName`, `lastName`, `notes` and `hostApprovalEmail` become stable pseudonyms (`phone-…`, `name-…`, `note-…`, `email-…`).
- `name` is masked **only inside guest-style objects** (objects that also carry guest fields such as `mobilePhoneNumber`, `guestStatus`, `guestType`, `devicesMac`). Venue, WLAN and SSID names stay readable.
- Phone numbers in international `+E.164` form are masked wherever they appear in a body, even outside named fields.
- JSON bodies are now masked structurally (parse, walk, re-serialize); non-JSON or truncated bodies fall back to the previous pattern-based masking.

## Tested
- Replayed a real Wi-Fi clients capture: the guest phone number, all 6 guest names, first/last names and notes are masked; venue, WLAN and SSID names are preserved; default (off) output is unchanged; output remains valid JSON.

## Known limitations
- Only the listed field names (and `name` in guest-style objects) are masked by key. Names in other fields, free text, or JSON nested inside strings may remain; review exports before sharing. Tenant IDs and SSID/venue names are not masked.
- Phone numbers not in `+E.164` form and outside the named fields are not detected.
- iframes are not captured; early page requests may be missed; the page bridge cannot authenticate messages.
- Live testing against a real tenant has not been performed.
