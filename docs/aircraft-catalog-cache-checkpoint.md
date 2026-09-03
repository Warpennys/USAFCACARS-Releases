# Aircraft catalog and cache — development checkpoint

These changes are unreleased. Existing screenshots and installers do not prove
that this checkpoint has been installed. No private server source or package is
distributed through this documentation repository.

## Expected behavior

A320 and A321 entries now have qualified ceo references. Sharklet dimensions and
range, maximum weights, fuel and seating are configuration references, not
installed equipment or dispatch limits. The source's conflicting A321 typical
seating figures are excluded; no engine subtype or neo/LR/XLR values are inferred.

A318 reference data retains separate passenger weight variants. Its passenger
fuel capacity is not the corporate-jet tank installation, and standard seating
is not a verified cabin layout. Wing-tip-fence dimensions retain configuration
qualifications. No engine choice or runway performance is inferred.

The generic A319 entry can display an explicitly qualified A319ceo reference.
Published Sharklet range and maximum fuel/weight/seating figures do not establish
its installed equipment. No engine subtype, cabin, ACJ or neo configuration is
inferred. Maximum operating Mach is not presented as cruise speed.

C-17 data is attributed to the U.S. Air Force, not labeled as manufacturer data.
Its unrefueled range retains the published payload and altitude conditions.
Maximum cargo, troop seating and medical layouts are not simultaneous capacity
assignments. The reference does not authorize short-runway operations or change
simulator fuel, cabin or dispatch limits. The reviewed airborne C-17 card is
included in cache discovery; its separate side profile remains unfinished.

ATR 42-600 and 72-600 references are matched separately. Fuel figures are mass,
not gallons. Published takeoff/landing distances are conditional figures, not
universal runway requirements. Alternative seating layouts do not change the
simulator cabin. Earlier -500, freighter and generic ATR entries remain separate.

The CH-47D reference describes a historical U.S. Army configuration, not current
CH-47F or MH-47 specifications. The site and desktop label it as a military
operator reference and retain its publisher and period. Verify those labels in
the desktop tooltip; historical troop capacity is not an installed cabin layout.
A reviewed CH-47D USAFC artwork card is now included in cache discovery. Its
separate side profile remains unfinished; no simulator repaint is installed.

The Bell 47J simulator entry uses a reviewed 47J-2-series reference only with an
exact model/package match. Four seats includes the pilot; 47J-2A weight and a
historical converted aircraft's engine must not become default simulator limits.
Its USAFC card is included. Its side profile remains outstanding because the
generated candidates failed transparency checks; those candidates are excluded.

The Bell 222 reference applies to the original wheeled model, not the 222B,
222U, 230 or 430. Fuel capacity depends on serial/modification status; external
cargo weight and maximum passenger seating are not automatic dispatch or cabin
settings. A USAFC art card and transparent side profile are now included; verify
both views and disk-cache reuse in the client. These are not simulator repaints.

The 787-10 reference preserves both published weight options without selecting
one for the simulator. Example seating is not an installed cabin assignment.
Its USAFC artwork card is now included; no completed transparent side profile is claimed.

Generic simulator display names can use a reviewed reference alias only when
the exact name, simulator platform and package match. Similar names alone do
not qualify, and installed-reference verification checks this identity too.

The C152 reference distinguishes total seats from passenger capacity and system
voltage from battery voltage. Operational settings remain separate.

The Cessna 310 catalog card depicts a piston twin with wingtip tanks, not an
Airbus preview. It is a 310R-family illustration, not a simulator variant or
performance-data assignment. A matching transparent USAFC side profile is now
included in the source checkpoint; it is not a new desktop installer.

Its family reference keeps original, later and turbocharged engine/weight data
separate. Unidentified simulator variants do not inherit those dispatch limits.

Development preview imports must not confuse aircraft sharing a model number or
replace approved artwork. Exact identity matching prevents new fuzzy matches;
previously misidentified images still need separate review and correction.

Side-profile validation requires visible aircraft content as well as transparent
background corners. Blank or faint-only cutouts fail acceptance; visual geometry
and livery review remain separate requirements.

The King Air 350i now has a transparent USAFC side-profile asset as well as its
art card. Verify side-view selection and persistent cache reuse in the client;
server image-integrity tests do not replace that interactive check.

King Air 350i reference data retains the 2015 configuration and does not adopt
ER/360 specifications. Range profiles stay separate, and a conflicting metric
wingspan is reported rather than silently selected.

The King Air 350 promotional card is included in cache discovery. It depicts
the simulator-reference configuration in USAFC paint, not an installed repaint.
Transparent side-profile coverage and full-fleet acceptance remain incomplete.

CJ4 reference data retains its 2015 configuration and mission assumptions.
The high-speed mission range is distinct from the fact-book maximum range;
inconsistent gear-speed conversions do not become operational limits.

The Citation CJ4 promotional card follows the simulator reference without tall
winglets. It is included in cache discovery, not a replacement for a side profile.

Closing the catalog selector cancels its image transfers instead of only
discarding downloaded results. User cancellation should not show an artwork error.

An available livery side image must display even when no default art card is
downloaded in the same request. Verify this on a non-default USAFC livery and
check that closing the selector prevents a cancelled late image update.

SkyCourier artwork now depicts the freighter configuration from the simulator
reference. This card is not a passenger-configuration or transparent-side asset.

SkyCourier reference figures identify passenger versus freighter configuration.
Conflicting payload and occupant labels do not become operational assignments.

The ICON A5 promotional card is now included in the reviewed cache collection.
It does not substitute for a missing transparent side profile.

The reviewed Vision Jet artwork is included in cache discovery. Its promotional
card is not a side profile; the missing side profile is not marked complete.

The Vision Jet reference separates type limitations from cruise performance and
preserves the authority's configuration-dependent altitude and seating criteria.
It does not identify the simulator's serial or assume newer-generation equipment.

Only reviewed, manifest-listed PNG files with matching checksums are served as
catalog artwork or side profiles. Loose, draft or corrupted files are excluded
from the aircraft cache collection; this does not fill still-missing imagery.

Legacy reference imports must not assign a different model solely because an
ICAO key matches. Conflicts now stop preflight, including with forced replacement.
Existing historical catalog conflicts still need separate reconciliation.

The SR22 card is included in the checksum-based image collection. Its reference
describes the 2022 normally aspirated model, not the turbocharged SR22T, and does
not overwrite simulator limits or assume optional equipment. Side view pending.

The C172 reference describes the current 180-hp Skyhawk. It does not establish the
catalog's unspecified 172 subtype or replace existing aircraft range and limits.

The PC-24 reference identifies the current higher-weight manufacturer configuration;
it does not assume the simulator has that upgrade. Takeoff balanced-field length
and landing distance retain their different obstacle heights and test conditions.
Its reviewed USAFC artwork is included in the development image collection;
the separate side profile remains outstanding.

The ICON A5 reference preserves runway versus water distances and engine power
duration limits. The manufacturer's newer propeller/weight option is not assumed
to be the installed simulator configuration.

The Bonanza G36 reference identifies the manufacturer's June 2022 configuration;
it is not confirmation of the installed simulator serial or weight variant.
Its USAFC artwork card now uses the conventional-tail, single-engine G36 shape,
not the V-tail Bonanza or twin-engine Baron. The side view is still outstanding.

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
