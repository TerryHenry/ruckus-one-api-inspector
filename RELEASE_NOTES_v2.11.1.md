# v2.11.1 — Capture and workflow discovery fix

- Workflow Discovery now analyzes the captured dataset instead of inheriting Live Capture list filters.
- Added timestamp fallback handling and a result summary to make discovery easier to diagnose.
- Stop Live Capture now handles messaging failures defensively and re-reads the persisted capture flag before reporting a problem.
- Both Chrome/Edge and Firefox ZIP packages were regenerated.
- JavaScript syntax checks and ZIP integrity checks passed.
- Live browser testing remains outstanding.

Packages generated in the working session:
- `ruckus_one_api_inspector_chrome_v2.11.1.zip`
- `ruckus_one_api_inspector_firefox_v2.11.1.zip`

The available GitHub connector can commit text files, but does not provide direct binary release-asset upload. These ZIPs are not attached as GitHub Release assets by this commit.
