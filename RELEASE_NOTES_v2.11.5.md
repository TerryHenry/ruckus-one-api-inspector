# Release Notes — v2.11.5

## Fixed
- **Write-op classification.** POST was always treated as a write, so read queries (`/venues/query`, `*/query`, `featureFlagStates`, GraphQL queries) inflated the "Write ops" count, the WRITE OP tags and the write-like filters. POST is now a write unless the path is a known read-query endpoint; GraphQL POSTs count as writes only when the body contains `mutation`. PUT/PATCH/DELETE are always writes. The risk warnings on user-authored recipe requests stay conservative (any POST is still flagged).
- **Export version.** The JSON export reported `version: "2.0.0"`; all exports now report the build version.

## Known limitations
- Unchanged from v2.11.4: iframes are not captured, early page requests may be missed, the page bridge cannot authenticate messages, and live testing against a real tenant has not been performed.
- Static files and feature-flag (`splitproxy`) calls are still captured and add noise.
