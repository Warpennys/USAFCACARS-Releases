# Aircraft catalog and cache — development checkpoint

These changes are unreleased. Existing screenshots and installers do not prove
that this checkpoint has been installed. No private server source or package is
distributed through this documentation repository.

## Expected behavior

The Bonanza G36 reference identifies the manufacturer's June 2022 configuration;
it is not confirmation of the installed simulator serial or weight variant.

The reviewed development collection now includes a Citation Longitude card and
source-qualified reference data. This is not a full-fleet image release, and its
side profile remains outstanding.

TBM 930 and Grand Caravan EX references now distinguish model/configuration
data, maximum versus normal cruise, and missing test conditions. They do not
change the simulator's installed seating, propeller, payload or operating limits.

Both turboprops now have reviewed USAFC artwork cards. The Caravan card uses the
three-blade propeller shown in the simulator reference, not the later factory
four-blade option. Separate side-profile imagery remains incomplete.

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

Full-catalog prerequisites are checked separately from tests of the images already
installed. The completeness check currently fails because collection work remains.
It includes every catalog row rather than hiding gaps behind shared image keys.
Even a future passing result still requires visual, livery, research and desktop
acceptance; it cannot alone establish release readiness.

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
