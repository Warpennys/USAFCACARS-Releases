# Aircraft catalog and cache — development checkpoint

These changes are unreleased. Existing screenshots and installers do not prove
that this checkpoint has been installed. No private server source or package is
distributed through this documentation repository.

## Expected behavior

- Valid downloaded imagery persists between restarts.
- New aircraft imagery is checked against the server's advertised checksum.
- Corrupt or empty downloads must not be reported as ready.
- Successful files remain reusable after another download fails; retries do not
  restart the whole batch. Duplicate image destinations download only once.
- Cancelling synchronization cancels active transfers and preserves valid files.
- Reference performance values are labeled as references and retain their source
  and operating conditions. They do not override dispatch or simulator limits.
- Missing passenger-capacity data does not imply a non-passenger aircraft.
- Reference tooltips retain general configuration qualifications and supporting
  sources. Maximum cruise is marked KTAS MAX, and cruise Mach preserves decimals;
  neither becomes the aircraft's operational cruise setting.

## Testing before release

Check first login, repeat login with no changed imagery, newly published imagery,
missing files, same-size corruption and interrupted downloads. Confirm that retry
works, login remains usable after background artwork failure, and the catalog
uses the correct aircraft/livery images. Review reference text and conditions in
the actual desktop UI. These interactive checks remain outstanding.

Automated checks have covered reference preservation, manifest hashes, unchanged
manifest stability, anonymous denial, persistent-file reuse, missing files and
same-size corruption. They do not prove full fleet coverage or simulator behavior.

An isolated service-level lifecycle check now recreates the cache service from
its disk index, verifies both jumbotron banners, new-image plan flags, partial
failure/retry, empty responses, metadata-only refresh and active-transfer
cancellation. It uses an in-memory HTTP fixture, not the real app login window
or a real process restart, and does not replace the manual checks above.

## Support

For an artwork warning, retain the existing cache and retry synchronization.
Report the aircraft, selected livery, application version and whether the issue
occurred on first or repeated login. Do not send login tokens or private server
configuration. The complete aircraft image collection is still being produced;
the current snapshot is not a full-catalog acceptance release.
