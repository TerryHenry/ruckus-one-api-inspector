# Release Notes — v2.11.9

## Added (opt-in, off by default)
- **Mask client identifiers in exports** (Settings → Capture & export options). Applies to JSON/CSV exports, backups and generated snippets; stored captures are not changed.
  - MAC addresses (any `aa:bb:..` / `aa-bb-..` form, plus bare 12-hex values in MAC fields) keep their vendor prefix (OUI); the last three octets become a pseudonym.
  - Private IPv4 addresses (10.x, 172.16–31.x, 192.168.x) keep their first two octets; the rest becomes a pseudonym. Public IPs and version strings such as `7.0.0.104` are left alone.
  - Values of `hostname`, `username`, `userName`, `clientName`, `deviceName`, `identityName`, `ipAddress`, `ipv6Address`, `ipv6Ip`, `macAddress` and `mldMacAddress` fields in JSON bodies become stable pseudonyms such as `host-a1b2c3`.
  - Pseudonyms use a random per-session salt: the same client maps to the same pseudonym within one panel session (records stay correlatable) but not across sessions, and cannot be reversed by hashing a known MAC list.

## Known limitations
- Only the field names listed above are masked by key; client names embedded elsewhere (for example nested JSON strings, or free-text fields) are not. Review exports before sharing.
- iframes are not captured; early page requests may be missed; the page bridge cannot authenticate messages.
- Live testing against a real tenant of this option has not been performed (tested by replaying a real 71-request Wi-Fi clients capture).
