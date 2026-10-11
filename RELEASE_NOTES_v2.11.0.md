# v2.11.0 Release Notes

## Workflow Trace cleanup

- Removed the remaining manual action-marker display from discovered workflow cards and exported workflow summaries.
- Workflow Discovery and Visual API Flow continue to use the captured request stream.
- Kept the Live Capture timeline and API Relationships features.

## Browser packages

Two local ZIP packages were regenerated for this revision:
- Chrome / Edge: `ruckus_one_api_inspector_chrome_v2.11.0.zip`
- Firefox: `ruckus_one_api_inspector_firefox_v2.11.0.zip`

JavaScript syntax checks passed for the modified side-panel and background scripts. This is not a claim of live-browser validation. Firefox behavior still needs a manual test in Firefox.

## Important publication status

The source cleanup and ZIP packages are present in the working session, but the GitHub connector available for this repository does not provide a direct binary release-asset upload action. The ZIP files have therefore **not** been attached as GitHub Release assets, and the modified extension source files have **not** yet been committed to this repository. Only the README update and these release notes are being committed through the available GitHub text-file API.
