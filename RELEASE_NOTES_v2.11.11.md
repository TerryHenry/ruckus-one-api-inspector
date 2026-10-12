# Release Notes — v2.11.11

## Changed (still opt-in via Settings → Mask client identifiers; default off)
- **Organization and account names** become stable pseudonyms: `companyName`, `tenantName` (customer/MSP delegations), and the `name` of tenant/account-style objects (for example the account list in the analytics user profile and `/tenants/self`).
- **Account and tenant identifiers** are masked: `accountId`, `externalId`, `entitlementId`, `userId`, `tenantId`, `resourceGroupId` and the `id` of those tenant/account objects; `tenantEmail` is masked; `displayName` and `identityGroupName` are masked.
- **Tenant IDs are replaced everywhere they appear**, including URLs and `pageUrl` (for example `ruckus.cloud/<tenantId>/t/...`), with a stable `tenant-…` pseudonym. IDs are learned from page URLs, `/tenants/<id>` paths, `tenantId` fields and tenant-style objects.
- Venue, AP, WLAN, SSID, guest-pass IDs and names, region names (Asia/EU/US), firmware versions and feature-flag names are left readable.

## Why
- `/delegations/query` returns real customer organization names, tenant IDs and contact emails, and the analytics user-profile response lists every account/org the user can access. These were readable in all earlier masked exports.

## Tested
- Replayed a real Wi-Fi clients capture with the option on: all customer/org/account/tenant values listed above were gone, URLs no longer contained the tenant ID, venue/WLAN/SSID/region names were preserved, default (off) output was unchanged, output remained valid JSON.

## Known limitations
- A tenant ID is only replaced in records processed after it has been learned; the user's own tenant ID is learned from the first record's page URL. Customer tenant IDs are learned from the delegation response, so they could remain in an earlier record that references them without that response.
- Only the listed fields (and tenant/account-style objects) are masked by key; names elsewhere or in free text may remain. Review exports before sharing.
- iframes are not captured; early page requests may be missed; the page bridge cannot authenticate messages.
- Live testing against a real tenant has not been performed.
