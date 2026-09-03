# Changelog

All notable changes to **USAFCACARS** are documented in this file.

USAFCACARS is proprietary software developed for USA Flight Club. The application is currently in **active alpha development**. Desktop release `1.1.5` is available; this repository also documents unreleased development work separately.

This changelog follows the general structure of [Keep a Changelog](https://keepachangelog.com/en/1.1.0/) and uses version numbers compatible with Semantic Versioning where practical.

> [!IMPORTANT]
> A version number does not indicate that USAFCACARS is production-ready.
>
> Alpha releases may contain incomplete systems, disabled controls, compatibility limitations, breaking configuration changes, or defects. The release notes attached to each downloadable build remain the authoritative record of what was tested and included in that build.

---

## Unreleased — aircraft catalog/cache checkpoint

- Production World activation is confirmed: 3,329 published schedules and 46,606
  reviewed-window departures. A read-only comparison is investigating remaining
  field differences between environments; equal counts are not claimed as full parity.

- Added a narrowly reviewed way to unpublish deferred flights with unused departure
  rows while preserving those rows and blocking operational history changes.

- Bound World activation to its reviewed held-flight identities and routes, so
  incomplete destination aircraft metadata cannot silently release deferred flights.
  The exact hold set is checked; production acceptance remains pending.

- Corrected a guarded schedule activation blocker for an exact aircraft-assignment
  repair with mixed unused cancelled and scheduled departures. Operational history remains protected;
  production activation verification is still pending. No desktop release change.

- Activated 3,329 validated World schedules on development and reconciled 46,606
  dated departures in the reviewed 14-day window. Repeat activation makes no
  changes. Added guarded server activation and portable comparison reports;
  production activation still requires its own receipt. Twenty-eight definitions
  remain held for deferred rotorcraft scope or range validation.

- Fixed a legacy unknown-duration compatibility issue in World schedule transfer.
  The published-production subset now passes the development rollback preview;
  production acceptance and new-service publication remain pending.

- Combined the development/server World schedule definitions without replacing
  existing flight history. Development import and repeat definition checks pass;
  private server transfer instructions are included with the implementation.
  Production publication and matching Dispatch occurrence counts are not yet
  verified. No new aircraft artwork or desktop release is claimed by this update.

- Added a guarded server activation procedure for restored PNG pilot avatars;
  existing pilot records and image files are preserved. Live-server visual
  verification remains required.

- Added the confirmed flight-source lettering contract for new flight identifiers:
  F (Free Flight), C (Charter), B (SimBrief), O (Open), S (Scheduled), T (Tour),
  independently of the trailing operational-type letter. Pilot-created Free
  Flight and append-to-bids behavior remain intact. Existing-data reconciliation
  and production acceptance are still pending; this is not a new desktop release.

- Corrected missing flight-type suffixes in development World schedules and added
  a journaled server migration with duplicate protection. Production flight parity
  and server acceptance remain pending; this does not announce a desktop release.

- Fixed the server's exact ATR 42-600 legacy identity to resolve its existing approved
  artwork and verified reference. Other ATR variants remain excluded; no image or
  operational performance limit was replaced.

- Verified one-to-one coverage of all 195 active aircraft identities across the
  captured development/server inventories using eight reviewed legacy aliases.
  Retired records remain preserved; this is not full profile/artwork or flight parity.

- Prepared a tested add-only legacy profile importer that allocates destination IDs,
  rejects conflicting existing records and preserves technical JSON. The four verified
  server-only legacy profiles have now been imported into development, retaining
  source data gaps honestly and leaving existing records/history untouched.

- Added a read-only, narrowly scoped legacy aircraft profile transfer for
  reconciliation, retaining source technical data without copying operational IDs
  or pilot records. Import remains a separate reviewed step.

- Simulator discovery no longer overwrites existing aircraft registration owners,
  reviewed catalog links, nicknames or approval states, and preserves retired
  registrations. Only genuinely missing registrations are created automatically.

- Restored five existing development legacy aircraft to match verified active
  server identities, preserving original records and history. Full World transfer
  preview completed locally and rolled back; nothing was implicitly published.

- Corrected 24 development PC-6 schedule assignments and their untouched scheduled
  occurrences while preserving IDs and history. The complete transfer plan now
  builds locally; production import and publication remain separately reviewed.

- Deployment planning now identifies the schedule key for conflicting aircraft
  assignments or unresolved subfleets; it still refuses unreviewed replacement.

- Removed automatic catalog retirement and simulator-row deletion from normal
  simulator discovery imports, preserving legacy records for explicit review.

- Repaired the development A400M simulator association and restored its existing
  catalog entry, retaining aircraft IDs and historical/configuration links.

- Corrected three exact legacy aircraft identity aliases and the Beechjet/A400M
  transfer association. The complete schedule candidate now resolves against the
  received server inventory; live import and publication remain separate checks.
- Prevented simulator imports from matching numeric model fragments inside another
  aircraft identifier, and rejected ambiguous catalog matches.

- Added a read-only two-way aircraft identity comparison for deployment review,
  preserving historical aircraft and flagging mismatched simulator associations.
  This diagnostic does not import or publish flight schedules.

- Fixed site lookup of restored pilot PNG avatars when the stored avatar path is
  blank or still points to a missing JPEG. Existing custom/remote avatars are
  preserved; no pilot database migration or original-image replacement.

- Corrected 24 PC-6 bush-route aircraft associations in the private World-network
  transfer candidate, retaining all 2,805 definitions. Local hard facility failures
  are cleared; destination matching and range/clearance review remain outstanding.
  This candidate is not a published network update.

- Added an explicitly reviewed missing-reference option for installations whose
  catalog lacks a packaged aircraft. Only named absent keys may be omitted;
  mismatched models, unexpected missing keys and stale acknowledgements still
  abort atomically. Successful partial coverage is reported visibly.

- Added Saab 340B manufacturer references with explicit equipment options;
  44 packages now match 47 development catalog records. Runtime limits and the
  issued deployment pins are unchanged.

- Added an A310-300 reference with exact-model safeguards and historical Airbus
  source conditions: 43 packaged references now match 46 development records.
  This follow-up does not change the already-issued bounded deployment pins.

- Built private test candidate 1.1.6-rc.4 from the latest flight readiness and
  control-release verification source. Automated reference/cache, readiness,
  control-state, icon and published-executable fixture checks pass. Live simulator
  and installer acceptance remain outstanding; no public update is promoted.

- Completed the bounded server deployment handoff for reviewed site, aircraft
  references and existing artwork. Unresolved World-network activation and
  desktop installer promotion remain excluded; this is not a claim of production
  acceptance or a new automatic desktop update.

- Corrected the abbreviated C207 catalog association to the package-verified
  T207A Turbo Stationair, not a normally aspirated 207. Historical FAA reference
  data retains seating, power-duration and source-currency boundaries. An exact
  erroneous generated description is repaired without replacing custom text.
  Development now has 42 packaged
  references matching 45 catalog records; this does not change simulator limits
  or claim complete aircraft artwork coverage.

- Completed site/data checkpoint transfer is now documented for authenticated
  server retrieval. Deployment acceptance remains separate; the older private
  desktop candidate must not be promoted as the current automatic update.

- Added read-back verification after simulator slew/freeze release commands,
  with bounded retries and failure on unconfirmed state. Automated verification
  tests pass; this is not yet proof of physical controller operation.

- Flight-workflow candidate: Start requires a confirmed simulator load of the
  current flight; the next step flashes, active tracking stays steady, and all
  quick-action buttons remain visible. Cancellation now requests a return to the
  simulator planner, with explicit retry on incomplete return. Build/readiness
  contracts pass; live planner-return and all-flight-type acceptance are pending.
  See [candidate testing](docs/flight-workflow-candidate.md).

- Hardened window-icon assignment for late-created/loaded Windows handles and
  retained old icon handles until replacements are assigned. A Windows lifecycle
  contract passes; taskbar appearance still requires visual confirmation.

- A private Windows x64 1.1.6-rc.1 installer/portable candidate now builds from
  current source; reference and persistent-cache contracts pass. It is unsigned,
  not on the update feed, and still requires installed-app/simulator acceptance.

- Added read-only flight-fleet reconciliation reporting that lists every missing
  or ambiguous aircraft association and its affected schedules before import.

- Current deployment preparation includes completed aircraft details and imagery;
  unfinished aircraft artwork is a later update, not a release prerequisite.
  Reviewed flight imports now have a tested apply command with backup/checksum
  acknowledgements and retained receipts. Production activation is still pending.

- Added a reviewed Stemme S12-G manufacturer reference with variant boundaries
  and performance caveats. This is catalog development, not a new installer or
  a declaration that aircraft imagery coverage is complete.

- Verified gate overlap protection with two independent MySQL booking processes.
  AI leasing now rechecks current session, flight status and pilot ownership under
  locks, preventing stale search results from creating leases for claimed flights.

- Gate reservations now recheck occupancy after obtaining the gate lock, handling
  stale availability results. Tests cover overlap, adjacent bookings, helipad
  allocation and an intervening reservation; multi-process verification is pending.

- Published-flight reconciliation and preview-command tests now pass on isolated
  MySQL tables. Fixed JSON formatting differences that incorrectly rejected repeat
  imports; meaningful JSON content changes remain protected. Production concurrency
  and final deployment acceptance are still pending.

- Prepared checksummed private delivery of the network definition candidate,
  removing the need for manual file copying. It remains unapproved for production
  import; no private package or operational data is included in this public repository.

- Completed a rolled-back reconciliation preview on development MySQL and verified
  protected data hashes remained unchanged. Draft services stayed unpublished.
  Batched history checks reduce repeated queries while retaining operational guards.

- Verified the additive date-offset migration on development MySQL after a full
  backup, with original flight, pilot and history data unchanged. Local definition
  review now succeeds; production migration and final acceptance are still pending.

- Added database-engine preflight for development reconciliation, rejecting
  nontransactional or missing tables, views and detected triggers before staging
  writes. Production permissions and concurrency checks remain outstanding.

- Added a private transactional reconciliation preview command with verified
  input/review files, explicit UTC windows and overwrite protection. Tests confirm
  rollback and rejected invalid inputs. Production application remains unavailable.

- Strengthened development reconciliation safeguards for assigned aircraft,
  registrations, estimated times and pilot-selected gates/routes, even before a
  flight leaves scheduled status. Independent operational-field tests pass.

- Added internal integration tests for reviewed definition and future-flight
  reconciliation together, including rollback, stale approvals, repeat imports
  and unpublished-leg protection. Production command and acceptance remain pending.

- The corrected development generator passed an isolated full-candidate audit
  covering 1,402 rotations and more than one million dated legs, with both
  predecessor and successor timing checks. Aircraft/facility validation and the
  controlled production migration remain incomplete; this is not deployment approval.

- Development connected-flight generation now chains legs from actual arrivals
  and planned turnaround/layover times. Isolated seasonal, hourly, date-line and
  three-leg tests pass, including preservation of completed flights on repeat.
  Full-network validation and deployment acceptance remain incomplete.

- Development schedule generation now rejects nonexistent spring-forward local
  times instead of silently shifting departures. Seasonal connection corrections
  and full migration acceptance are still pending; this is not a deployed fix.

- Expanded development rotation checks across recurring dates and daylight-saving
  transitions. Seasonal connection defects remain under correction; the network
  migration has not been accepted or deployed.

- Tightened 787-10 reference model matching while preserving its existing
  specifications and verified simulator-package alias. Other 787 variants and
  unreviewed conversions cannot inherit the reference through a name suffix.

- Added an internal, preview-first future-occurrence reconciler with protection for
  pilot history, active traffic and gate reservations. Repeat and rollback tests
  pass in isolation; production import integration remains unfinished.

- Corrected development occurrence generation to retain its rotation and selected
  subfleet associations, with checks against ambiguous or cross-airline ownership.
  Existing occurrence reconciliation remains unfinished; no production data was
  regenerated as part of this change.

- Added qualified Cessna 404 Titan authority-reference data and model-boundary
  checks. Installed cabin and simulator limits remain unchanged. Its artwork card
  is already available; the separate side profile remains unfinished.

- Added a development-only, read-only reconciliation review command with file
  checksum verification, private output and stale-plan detection. It does not
  import, publish or deploy schedules; the complete migration remains unfinished.

- Added development-only reconciliation tests for aircraft assignments, subfleets,
  connected rotation legs and repeat imports. Server-specific identities are
  resolved locally; conflicting assignments require review. This is not a completed
  migration handoff or a new desktop release.

- In development: corrected scheduled-flight time calculations and added reconciliation safety tests for existing flight history and AI reservations. This is unfinished server work, not a released desktop update or completed deployment handoff.

- World Schedules reconciliation remains under review. Development and production data differ; the diagnostic handoff does not publish schedules or replace production flight history. No desktop update is included in this documentation change.

- Added separate USAFC Cessna 207 and 404 Titan artwork cards to cache discovery after image review. Their transparent side profiles remain unfinished.

- Removed the generic "Simulator Aircraft" prefix from catalog titles and aircraft dossier headings, retaining real manufacturer names and saved identity data.
- Added a USAFC C90GTx card to image-cache discovery. The separate side profile remains unfinished.

- Added manufacturer-backed C90GTx reference data with separate original and upgraded performance figures. Exact model matching prevents other King Air variants from inheriting it; simulator limits remain unchanged.

- Added separate USAFC cards for the original E190, ATR 72-600 and ATR 42-600 using manufacturer imagery. All three are included in cache discovery; separate side views remain unfinished.

- Tightened reviewed aircraft-reference matching so similar names cannot silently inherit ceo, regional-jet or passenger data belonging to a different variant. Existing reviewed associations remain valid.

- Added qualified original E190 authority references, separating weight variants and passenger maxima. Conflicting landing-weight conversions are excluded; no simulator configuration is assigned.

- Added separate reviewed USAFC ERJ135 and ERJ145 art cards to cache discovery. The ERJ145 uses its manufacturer's reference image; separate transparent side profiles remain unfinished.

- Added qualified ERJ135 ER/LR reference data and alternative example cabin layouts. An inconsistent performance-column heading is excluded, and no simulator cabin or operating limits are changed.

- Added ERJ145 EP/LR reference figures with separate weights and fuel capacities. Example seating and conditional performance remain references, not simulator assignments.

- Added reviewed USAFC A318, A319 and A330-300 cards to cache discovery, retaining individual reference shapes. Separate side views remain unfinished.

- Added reviewed USAFC A330-200 artwork to cache discovery, preserving the -200 reference shape. Its separate side view remains unfinished.

- Added qualified A330-200/-300 references without changing operational limits. Conflicting A330-200 range, typical seating and weight figures are excluded pending configuration-specific evidence.

- Added reviewed USAFC A321ceo artwork with its distinct door configuration to cache discovery. The separate side view remains unfinished; existing neo artwork is unchanged.

- Added reviewed USAFC A320ceo artwork to catalog cache discovery. Its separate side profile remains unfinished; the approved A320neo card is unchanged.

- Added qualified A320ceo and A321ceo references. Sharklet range/dimensions and configuration maxima do not replace simulator limits. Conflicting A321 typical seating figures are excluded.

- Added an A318 passenger reference preserving separate weight variants and excluding corporate-jet fuel configuration. Published seating and dimensions do not overwrite the simulator cabin or operating limits.

- Added qualified A319ceo manufacturer reference data. Sharklet range, weight options, maximum seating and fuel capacity remain references rather than simulator configuration assignments.

- Added the reviewed airborne USAFC C-17 artwork card to cache discovery. Its separate side profile remains outstanding; this is not an installed simulator repaint.

- Added a qualified USAF C-17 reference with exact simulator-package matching. Cargo, troop and medical layouts remain separate; conditional range is not an operational fuel setting.

- Added separate ATR 42-600 and 72-600 manufacturer references with qualified runway, range, fuel-mass and seating-layout figures. Ambiguous ATR and earlier/freighter variants are excluded.

- Added the reviewed USAFC CH-47D artwork card to catalog cache discovery. Its separate side profile remains unfinished; no simulator repaint is installed.

- Added a historical CH-47D reference with exact simulator-package matching. Site and desktop reference displays identify military-operator sources and preserve publisher, period and configuration qualifications; operational limits remain unchanged.

- Added a USAFC Bell 47J Ranger art card to cache discovery. The transparent side profile remains unfinished; no simulator repaint is installed.

- Added qualified Bell 47J-2-series reference data with exact simulator-package matching. Passenger count, variant weights and modified-aircraft exclusions remain explicit.

- Added USAFC Bell 222 artwork and a transparent side profile to the catalog cache checkpoint. These illustrations do not install a simulator repaint.

- Added original Bell 222 authority reference data with serial-dependent fuel and external-cargo qualifications. No helicopter artwork or simulator configuration is inferred from this reference.

- Added reviewed USAFC 787-10 artwork to the catalog cache. The separate transparent side profile remains outstanding.

- Added Boeing 787-10 planning reference data, preserving separate weight options and seating/fuel conditions. Full-fleet audit now checks verified simulator aliases consistently with installation.

- Added explicit simulator-package checks for reviewed catalog reference aliases, retaining strict variant matching. No new aircraft data is assigned by this change alone.

- Added Cessna 152 authority reference data with seating and electrical qualifications. Its transparent side profile remains unfinished.

- Added a Cessna 310 family authority reference with explicit variant qualifications; no automatic changes to dispatch limits or passenger capacity.

- Added a matching transparent USAFC Cessna 310 side profile to the catalog cache checkpoint. This remains an unreleased partial-fleet update.

- Added correctly identified USAFC Cessna 310 artwork, replacing a mismatched development preview association. Aircraft variant and operational specifications are unchanged.

- Development preview matching now rejects numeric-name collisions and ambiguous image sources while preserving approved artwork. Existing identity discrepancies still need reconciliation; no corrected fleet coverage is claimed.

- Strengthened side-profile acceptance checks to reject empty or faint-only transparent images. Existing reviewed profiles still pass; this is not complete fleet or live-client acceptance.

- Added a reviewed transparent USAFC King Air 350i side profile to cache discovery. The asset is a catalog illustration, not a simulator repaint; fleet coverage remains incomplete.

- Added a serial-qualified King Air 350i reference with separate mission ranges, speed conditions and documented source conflicts. Existing operational limits are unchanged.

- Added reviewed USAFC King Air 350 promotional artwork to cache discovery. This does not provide a side profile, a simulator repaint, or complete fleet coverage.

- Added a configuration-qualified CJ4 technical reference, retaining distinct range assumptions and excluding inconsistent gear-speed conversions. Operational values remain unchanged.

- Added reviewed USAFC Citation CJ4 artwork to the catalog cache. No side profile or new aircraft performance values are implied by this card.

- Catalog card and side-image downloads now honor cancellation during HTTP transfer without reporting user cancellation as an artwork failure. Transport regression checks pass; live UI acceptance is still pending.

- Fixed an ACARS livery-side display path that required a simultaneous default-card download. Available side images can now update independently; interactive release verification remains pending.

- Added reviewed USAFC SkyCourier freighter artwork to cache discovery. Transparent side-profile coverage remains incomplete.

- Added a SkyCourier reference with separate passenger/freighter figures and visible source conflicts. Existing operational limits are unchanged.

- Added reviewed USAFC ICON A5 artwork to cache discovery; the card preserves its amphibian configuration. Side-profile coverage remains incomplete.

- Added reviewed USAFC Vision Jet artwork to the catalog cache collection. Full-fleet artwork and side-profile coverage remain incomplete.

- Added a type-certificate-based Vision Jet reference with serial-dependent altitude, seating and equipment qualifications. Newer-generation performance and a conflicting source dimension were not inferred.

- Catalog image serving now verifies review status, manifest membership, file type and checksum before exposing an image to the site or ACARS cache. Corrected files can recover without stale resolver results.

- Legacy type-reference imports now stop before writing when model identity is mismatched or ambiguous. Previously imported catalog conflicts still require reconciliation; this does not change flight history or aircraft identifiers.

- Added reviewed USAFC SR22 artwork and a 2022 normally aspirated SR22 manufacturer reference; SR22T figures and unconfirmed installed options remain excluded. The separate side view is still outstanding.

- Added a qualified C172/172S manufacturer reference, with unresolved simulator subtype stated explicitly and conflicting source weight figures excluded. Existing aircraft values remain unchanged.

- Added reviewed PC-24 USAFC artwork to the development catalog and checksum-based cache collection. Its separate side profile remains outstanding.

- Added configuration-qualified PC-24 reference data, including separate takeoff balanced-field and landing criteria. No simulator weight, seating or operational limit is overwritten.

- Added ICON A5 manufacturer references separating land/water performance, engine takeoff/continuous ratings and total seats from passengers. Existing simulator limits are unchanged.

- Added reviewed USAFC Bonanza G36 artwork to the checksum-based catalog cache collection; separate side-view coverage remains incomplete.

- Added a Bonanza G36 manufacturer reference with serial/configuration applicability and performance conditions; ambiguous source conversions were excluded, and simulator limits remain unchanged.

- Added a full-catalog prerequisite check that fails on missing artwork, side profiles, descriptions or reviewed references for any catalog row. Passing partial-image tests does not indicate a complete collection.

- Added reviewed USAFC TBM 930 and Grand Caravan EX artwork to the development collection and checksum-based cache manifest. Their side views remain outstanding.

- Added source-qualified TBM 930 and Grand Caravan EX references, retaining configuration qualifications and existing operational values.

- Added reviewed Citation Longitude artwork and manufacturer reference data to the development catalog. Full-fleet imagery remains incomplete; no new installer is implied.

- Fixed duplicate startup-image downloads and loss of successful partial downloads after a failed batch. Retries preserve completed files; cancellation now reaches active transfers.
- Added automated service-level cache lifecycle checks with two banners, disk-index reuse, empty/corrupt downloads and retries. Real application login/restart checks remain outstanding.

- Added a reviewed PC-12 NGX art card and variant-specific manufacturer references. Reference displays now include general configuration notes and supporting sources; rejected opaque side-view drafts remain excluded.
- Cruise references distinguish normal knots, maximum KTAS and decimal Mach without changing operational settings.

- Display reviewed aircraft references with source/configuration conditions while preserving operational values.
- Expanded reviewed catalog references for the A321LR and A380-800, retaining tank, cabin and weight-variant qualifications. This is partial fleet coverage, not a new desktop build.
- Added a reviewed USAFC Boeing 747-8 Intercontinental art card and manufacturer reference. Fleet-wide imagery and interactive cache testing remain incomplete.
- Distinguish unknown passenger capacity from non-passenger aircraft.
- Verify aircraft-image checksums and reject empty or corrupt downloads. Background artwork failures warn without treating a successful login as failed.
- Added focused reference, cache and catalog-manifest checks. Full interactive restart testing and fleet imagery completion remain outstanding.
- No new installer is published by this documentation checkpoint.

## [1.1.5] - 2026-09-02

- GitHub release assets include Windows setup, portable, full/delta update packages and update metadata.
- This entry records verified artifact availability, not acceptance of all alpha functionality.

## [1.1.0] - 2026-08-30

### Added

- Added private Free Flight planning with unrestricted pilot-entered flight details and APPEND TO BIDS. These pilot-owned plans appear only in My Bids and PIREPs, remain eligible for flight credit, and never enter available-flight search.
- Added a compact flight-strip color legend and source-aware inner borders for Scheduled, Charter, Tour, SimBrief, and Free Flight records, with a silver outer bid frame and a green started-flight status treatment.
- Added a General Settings option to start Microsoft Flight Simulator 2024 after ACARS signs in and is running; an already-running simulator is detected and left untouched.
- Added focused planner tabs and a full-area Map & Tools overlay whose close action returns directly to Timing.

### Changed

- Reordered planner workflow buttons to Free Flight, Charter, SimBrief, Scheduled, and Tours.
- Renamed PIREP filters to All PIREPs, Charters, and Tours.
- Changed tour flight strips to show the tour name and leg number.
- Changed Scheduled planner navigation to open the complete Search Flights workspace with its Scheduled filter and application tab preserved.
- Changed active bid presentation so IN FLIGHT appears in green only after the flight actually starts; cancellation returns the bid to normal and filing the PIREP removes it.

### Added — earlier unreleased work

- Added an aircraft-aware live cabin and payload workspace with built-in airframe profiles, a custom cabin-layout editor, seating and facility layers, passenger manifests, boarding progress, baggage/cargo controls, and SimConnect payload application.
- Added resilient MSFS 2024 EFB bridge handling for current-aircraft identification, exact artwork selection, cabin/load presentation, and simulator aircraft-loading workflows.
- Added per-pilot Pilot Social appearance control: pilots can synchronize Social with the website Dark/Light preference or disable synchronization and retain an independent remembered Social theme. The cockpit-style switch and purpose-built illuminated steel-blue treatment cover feeds, profile rails, cards, forms, menus, dialogs, and settings while media viewers remain dark for accurate image and video contrast.
- Added a compact directly editable Network composer: the visible transmission field is the real text area and expands in place while the pilot types without opening posting options. Only the dedicated settings gear opens or closes the full option section; media shortcuts act directly, and the emoji picker opens below the editor without covering written text.
- Rebuilt the phpVMS appearance system with an explicit, persistent Dark/Light selector and a dark-first default; the new light presentation retains the signature gray wood navigation and 3D aviation hardware while illuminating a richer blue canvas with concealed white/ice-blue edge lighting beneath the top bar, side navigation, and footer, plus readable light-side cards, forms, tables, and home content.
- Added compact remembered INFO/NAV tabs to the Pilot Social left rail on the website and in USAFCACARS. INFO is the default and presents privacy-controlled birthday details, favorite-aircraft text, and linked social icons beneath the years-of-service record; NAV contains the Social destinations, with a reserved invisible scrollbar gutter preventing width changes between tabs.
- Redesigned contextual Pilot Social profile summaries as instrument-style records with the selected pilot's assigned DIVISION card and real logo, home/current locations, country code with real flag, permission-aware SUPER ADMIN/staff/ACTIVE PILOT role, and profile-only join-date service stars (gold for completed years and silver for the year in progress).
- Added native Pilot Social pilot activity and awards pages, linked profile KPIs, assigned-airline branding, rank progression, private finance summaries, and collapsible landing trends on the website and in USAFCACARS.
- Added fully contextual public pilot profiles: both navigation rails, profile links, KPI destinations, activity, awards, airline identity, country flag, and rank data now follow the pilot being viewed while owner-only settings and private finance remain protected.
- Restyled Pilot Social rank identity headers as dark recessed aviation panels with the rank artwork enlarged and flush left, the rank name aligned right, and the redundant pilot ID removed.
- Added independent optional-module capability discovery: when USAFCSocial is missing, disabled, or awaiting migrations, ACARS hides all actionable Social controls and returns safely to Dashboard; a freshly installed module is detected automatically while signed in.
- Moved Pilot Social rank artwork directly beneath each pilot avatar in both the website and USAFCACARS feeds, keeping author metadata aligned and eliminating the detached far-right rank badge.
- Added responsive in-feed players for YouTube videos/live links, Twitch live/VOD/clips, Vimeo, Dailymotion, TikTok, Instagram, Streamable, Rumble, Loom, Kick, and web-native direct MP4/M4V/WebM/OGG links; formats browsers cannot decode inline open through the system player, while ordinary websites retain safe rich preview cards.
- Added a physically bundled Twemoji stylesheet and searchable 1,697-entry emoji catalog, presented through compact smiley dropdowns for posts, comments, private messages, and reactions.
- Added synchronized scheduled-Twitch premiere cards on the site and in USAFCACARS with a large countdown, animated full-frame aviation/radar background, automatic zero-time player transition, and persistent Watch Live access.
- Added playable Facebook post/video cards to Pilot Social on the website and in USAFCACARS, including safe iframe-code normalization, canonical post links, responsive containment, and backward-compatible rendering of existing Facebook shares.
- Fixed Facebook pcb multi-video posts being treated as a single video; their official two-tile split player is now preserved on the website and desktop while ordinary Facebook videos and reels use the dedicated player.
- Fixed Facebook shares falling back to clickable image cards in currently installed ACARS clients by publishing them through the established playable-video preview contract.
- Added the shared **Pilot Social notification center** on the website and in USAFCACARS, including unread counts, category filters, read/unread and dismiss actions, pilot avatars/ranks, destination actions, and user-controlled notification preferences governed by administrator availability.
- Added native Unicode emoji entry for Pilot Social posts, comments, and private transmissions plus expressive Like, Love, Laugh, Celebrate, and Wow reactions.
- Added optional birthday profiles and privacy-aware reminders with independent birthday visibility, year visibility, and notification controls.
- Added the server-authoritative **Toss Paper Airplane** buddy game with one-toss-per-target hourly cooldowns, randomized humorous outcomes, immutable scoring, return tosses, current-period/all-time leaderboards, durable aggregate statistics, and configurable detailed-history cleanup.
- Added a clean Pilot Social event-publisher contract and flight-completion listener so meaningful phpVMS/module events can reach the shared activity feed without coupling unrelated controllers to social rendering.

- Added the full **Weather Operations Center**, opened from the left weather card, with synchronized departure/arrival summaries, selectable en-route METAR stations, route-aware station sampling, Esri satellite imagery, animated RainViewer precipitation, infrared imagery, a live SimConnect aircraft marker, explicit refresh, and last-valid-snapshot retention.
- Added the aircraft operations page and persistent MSFS 2024 aircraft catalog, including installed/streamed/Official/Community discovery, exact active-title/livery matching, cached model cards, aircraft library browsing, operational data, and an official blue ACARS image-unavailable fallback.
- Added 24 physically bundled MSFS 2020 aircraft presentation assets, resolved by ICAO without mapping or depending on the external source folder; each internal image is decoded and reused once across matching variants.
- Added the private MSFS 2024 EFB bridge workflow for acknowledged planner transfer, presentation-card discovery, aircraft matching, direct-load state selection, and Community-package installation path handling.
- Added the unified instrument-style Flight Planner for Scheduled, SimBrief, Free Flight, Charter, and Tours workflows with route, weather, fuel, aircraft, NOTAM, ATC/frequency, document, procedure, gate, and simulator-load tools.
- Added a redesigned Tours workspace with cached rotating banners, horizontal image flight strips, robust flexible tour parsing, dynamic airline wording, achievement artwork, leg progress, and unified-planner launch.
- Added persistent Horizon Explorer bookmark folders, optional stable-gutter bookmark bars, current-page bookmarking, removal, Chrome/Edge/HTML import, and matching bookmark access in detached browser windows.
- Added real Workspace Manager layouts, named profiles, window bounds/state capture, profile restore/delete, off-screen clamping, safe reset, atomic persistence, and functional autosave/layout/monitor/tool/Horizon restore preferences.
- Added the in-app Release Center with documentation/changelog/repository access, update checks, a development track, sanitized diagnostics, and prefilled bug reporting.
- Added the searchable Help & Support Center with workflow/error keyword search, contextual HD illustrations, connection checks, sanitized diagnostics, and operating guidance for the major ACARS systems.
- Added site-side Charter route generation, manual planning, MSFS PLN/PnL/FLT import, distance/time/cruise estimation, approval policy handling, and approved-charter synchronization into phpVMS flights and bids.
- Added USAFCACARS Map Settings for selecting the live real-world aircraft provider, including ADSB.lol, ADSB.fi, and OpenSky fallback support.

### Changed

- Extended ACARS telemetry acknowledgement time for busy cruise and phase-transition updates while preserving the same idempotent update identifier across retries.
- Unified the Aircraft, Aircraft Control, and Aircraft Catalog workspaces under the same riveted Aircraft Operations header. The selected destination now retains a full-bright green active lamp, and the Aircraft Control header provides working direct navigation back to Current Aircraft or the Catalog without covering its live WebView instruments.

- Changed the Aircraft Catalog to group exact simulator models by ICAO, present installed liveries as switchable tabs, and load the currently viewed livery. The full live inventory remains searchable while card realization and image decoding are bounded for stable memory use.
- Changed aircraft artwork synchronization to cache-first operation with silent MSFS installation-change detection, pilot approval, an in-window progress instrument, and one shared internal asset per ICAO.

- Changed center-workspace expansion into a single remembered pilot preference across Dashboard, Bids, Tours, Flight Tracking, Live Map, Weather Center, Profile, Aircraft, Pilot Social, Settings, Help, Release Center, and internal page transitions. A fresh launch still presents Dashboard collapsed without overwriting the saved preference; navigating away and returning applies the remembered expanded/collapsed state.
- Rebuilt the phpVMS top-navigation world clocks as clean, legible aviation chronometers with machined multi-ring bezels, deep illuminated dials, four cardinal numerals, eight baton markers, dimensional hands, restrained glass reflections, smooth sweep seconds, and live six-zone timekeeping; a newly polished USAFC logo with a cold graphite/blue-steel heat-stamp impression and the clocks now share one continuous boarded-metal instrument plate on desktop, the same plate wraps evenly around the logo when clocks hide on tablet, and its mobile width reserves an even gap for the menu control without shifting the logo. Red city names use a recessed heat-stamped treatment and each digital readout sits in a compact charred inset window fully below the board seams.

- Changed site navigation so current destinations remain visible across landing and child routes: standalone/module links use the blood-red active state, while links inside an already-active dropdown use gold across desktop, mini, and mobile navigation.
- Refined the phpVMS top navigation into a compact instrument-style command bar with unified control sizing, cleaner spacing, aligned icons and dropdowns, a deep blood-red current-page state, responsive mobile behavior, and preserved module, language, theme, session, dashboard, and administrator actions.
- Restyled the existing phpVMS left navigation in its original sidebar template and CSS with recessed blue-black instrument buttons, blood-red active/open states, cyan icon accents, refined nested navigation, horizontally and vertically centered full and mini division/wordmark branding, matching pilot and Crew Mail panels, a separate service-years card, and the original borderless rank presentation with a centered silver-first service-star configuration, true optical centering for injected module icons, keyboard focus treatment, hover-revealed blood-red scrolling, and proportional full/mini-sidebar layouts without changing the menu hierarchy or destinations.
- Changed Pilot Social image handling to detect and cache JPG, JPEG, PNG/APNG, GIF, WebP, AVIF, BMP, ICO, SVG, image-CDN URLs, and extensionless image responses; modern formats retain animation where supported or normalize to PNG for cross-client display.
- Changed Twitch live broadcasts to render through the secure Pilot Social player on the website and USAFCACARS, start muted autoplay when the broadcast is live, preserve manual replay playback, and use the browser timezone for scheduled countdowns.
- Changed direct linked-image previews to retain long source URLs and cache validated remote images locally so expiring social-media CDN URLs no longer produce blank cards.
- Changed Pilot Social feeds to preserve composer text and independent column scroll positions while silently merging refreshed network data; the feed viewport no longer extends behind the application status bar.
- Changed current-style app menu and tab active states to a deeper blood-red illuminated treatment while preserving the existing hover behavior.
- Changed app voice-bubble hover help to open beside the actual pointer instead of appearing remotely from the hovered control.

- Changed the left weather card from a refresh-only card into the entry point for the synchronized Weather Operations Center; page refresh updates both views from the same source.
- Changed Workspace Manager controls from preview-only behavior to real detached-window layout operations.
- Changed completed-flight handling so a successfully filed PIREP removes the matching pilot bid and refreshes bid state.
- Changed Tours and Charter language to use the connected airline/module configuration instead of hard-coded USAFC wording where satellite airlines are supported.
- Changed local settings persistence to atomic UTF-8 writes with automatic empty/NUL/invalid JSON recovery and timestamped diagnostic backups.

### Fixed

- Prevented an optional automated-ATC phase advisory failure from turning an already committed telemetry update into an API failure, and surfaced the server failure reason in the in-flight tracking status when a request genuinely fails.
- Fixed MSFS 2024 paintjob artwork regression by treating each catalog row's exact simulator imagePath as authoritative, bounding every VFS transfer so damaged packages cannot stall the catalog, and invalidating the prior artwork-cache generation so stale generic/default cards are recached automatically. Live verification returned different VFS paths, byte counts, and SHA-256 hashes for two EC-135 paintjobs.
- Restored the official USAFC ACARS application icon for the Windows taskbar and authenticated main window by applying one explicit shell application identity and the embedded icon to every top-level window.

- Fixed the remaining Aircraft Catalog artwork delay and page-to-page memory growth: catalog updates now finish every available persistent display thumbnail before reporting completion, existing local caches self-complete silently in the background, completed thumbnails are never regenerated, the in-memory bitmap cache is bounded, and off-screen page/paintjob images are released while their local thumbnails remain immediately reusable. Runtime stress verification covered 25 forward pages plus 25 cached return pages with the client responsive and memory stable.

- Fixed slow/blank Aircraft Catalog artwork by removing API/simulator discovery from image realization, proactively hydrating each visible page and paintjob selector from the app-local cache, decoding on bounded background STA workers, persisting 512-pixel thumbnails across sessions, deduplicating simultaneous image requests, and indexing nested MSFS Official `OneStore` packages. Explicit catalog updates now allow larger packages enough time to complete without blocking the UI.
- Fixed Aircraft Catalog paintjob identity so the simulator default remains the default, named variants display only their own exact cached artwork, previously captured MSFS repaint cards remain reusable, and selecting a paintjob closes the selector without changing the default card.
- Fixed incomplete aircraft-artwork caching and catalog stalls by replacing the serial all-variant package crawl with a bounded background cache scan, shared package-directory indexing, per-item time limits, incremental progress, and explicit exact-artwork/pending counts.
- Fixed the Aircraft Catalog presentation to show exactly five responsive aircraft strips per page, keep all five strips and paging controls fully visible in the expanded 1080p workspace, enlarge readable model/ICAO/paintjob labels, show default and selected artwork side by side, arrange paintjob controls in equal three-button rows, and center equal-size **LOAD IN SIM** controls. Simulator discovery now requests aircraft and helicopters only instead of the MSFS `ALL` object class, preventing animals and ground vehicles from entering the aircraft inventory.

- Fixed Aircraft Catalog ICAO normalization for Airbus A330 variants: A330-200 and A330-300 packages now resolve and group under `A330`, while the unrelated Extra 330 remains `E330`.
- Fixed Aircraft Catalog responsiveness with a finite virtualized viewport, true vertical scrolling, full-width aircraft strips, consolidated same-ICAO variants/liveries, compact unclipped controls, cache-first page loading, paged realization, and an explicit update workflow that performs simulator discovery only after pilot confirmation.
- Fixed incomplete SimConnect aircraft-catalog responses being discarded when the simulator timed out after returning valid partial results.
- Fixed the Aircraft Catalog trapping pilots without a return control, and fixed hidden/thousands-of-card artwork realization causing excessive memory use.

- Fixed Weather Center **FIT ROUTE** so it re-centers the complete loaded route after airport or station exploration.
- Fixed the live aircraft marker intercepting airport clicks; departure and arrival station reports remain selectable when the aircraft occupies the same coordinates.
- Fixed silent arrival/en-route ATIS, AWOS, and ASOS reception with supplemental local weather audio when MSFS has no native station audio; receiver mute state and delayed SimConnect frequency telemetry no longer cancel the broadcast.
- Moved route summary, departure/arrival observations, selected-station identity, and raw METAR computer data into black riveted instrument windows.
- Restored the approved USAFC logo optical scale, left inset, and vertical baseline inside the top chronometer board without moving the board or clocks; tablet and mobile keep their prior responsive positioning.
- Fixed Pilot Social profile settings silently rejecting and clearing birthday/website entries when the optional favorite-aircraft row was blank; website domains are normalized to HTTPS, failed submissions retain entered values, and validation errors are now shown.
- Fixed older saved image/video posts remaining generic or blank by repairing stale preview metadata in place, with no repost required; redirecting website links now resolve through public-address-validated hops.
- Fixed Facebook posts showing copyright-blocked direct-player errors by using Facebook's official full-post widget at a larger responsive height so multi-video posts and native controls remain together when Facebook permits embedding; Facebook Story URLs use an explicit sign-in-aware external card because Facebook provides no Story embed player.
- Fixed copied direct image links—including Facebook CDN JPEGs—being discarded as generic non-HTML links; supported image URLs now render responsively in the website lightbox and desktop feed.
- Fixed blank Twitch live and replay posts by adding host-verified HTTPS player embeds on the website, native secure Twitch playback in USAFCACARS, responsive minimum player sizing, and a visible Watch Live fallback for the HTTP-only local development site.
- Fixed the Pilot Social admin control-center Blade crash caused by a malformed Laravel `Str` class reference, and replaced adjacent damaged separator glyphs with encoding-stable HTML bullets.
- Fixed a dashboard startup crash caused by the EFB toolbar icon being present on disk but omitted from WPF packaged resources; toolbar icon loading now uses an embedded resource plus a nonfatal fallback.
- Fixed Pilot Social notification filter mapping for aviation/flight activity, corrected timestamp separators, and aligned informational birthday priority with non-intrusive notification behavior.
- Fixed Pilot Social content being clipped at the bottom of the desktop center workspace.

- Fixed duplicate site bid insertion by serializing UI submissions, routing Tours through the core bid service, deduplicating existing user/flight pairs, and enforcing a unique database index.
- Fixed PIREP Submit visibility and authorization so it appears only to the owning pilot after a genuinely completed, unfiled flight with blocks-on/arrival state.
- Fixed flexible Tour JSON parsing when numeric values arrive as strings, nulls, or mixed server representations.
- Fixed completed bids remaining visible in ACARS after successful PIREP completion.
- Fixed corrupt settings files producing raw `0x00` JSON errors instead of recovering safely.
- Fixed visible replacement-character text discovered during the site/documentation audit.

### Security and Packaging

- Kept the proprietary USAFCACARS phpVMS module/API and MSFS 2024 bridge/package source out of the public Releases repository.
- Added private, credential-audited source backups to the private site repository so excluded integration source is recoverable without public disclosure.

### In Active Development

- Reworked MSFS 2024 aircraft artwork handling around a persistent ACARS aircraft catalog populated from SimConnect's installed-aircraft inventory.
- Added exact live aircraft-title and livery matching through the private in-sim VFS bridge, with on-demand presentation-card caching for immediate reuse after aircraft changes.
- Removed synthetic aircraft-card fallbacks and the local radar test contact so unavailable or live data is never represented as genuine simulator/network data.
- Continued integration of the USAFCACARS Windows desktop application with the proprietary USAFCACARS phpVMS API module.
- Continued work on the complete flight lifecycle:
  - Pilot authentication
  - Bid retrieval
  - Flight selection
  - Flight start
  - SimConnect telemetry
  - Live flight updates
  - Flight completion
  - PIREP submission
  - Flight cancellation
- Continued stabilization of simulator connectivity and aircraft telemetry.
- Continued development of the expandable center-workspace system.
- Continued development of live map, flightboard, weather, charts, voice communications, ATC, TRACON, Horizon Explorer, Workspace Manager, Music & Radio, Aircraft Control, Community, Support, and Passenger Operations.
- Continued improvement of alpha diagnostics, logging, testing, release packaging, and documentation.

### Planned Before Beta

- Complete end-to-end flight testing with valid USAFC pilot accounts.
- Complete Debug and Release builds without critical errors.
- Validate Microsoft Flight Simulator 2020 and Microsoft Flight Simulator 2024 compatibility.
- Stabilize SimConnect reconnect and shutdown behavior.
- Prevent duplicate flight-start, flight-finish, and PIREP submissions.
- Complete voice communications device testing and audio routing.
- Complete live-map and flightboard synchronization.
- Complete airport support for both three-character and four-character identifiers.
- Complete update checking against the official USAFC release records.
- Expand automated API and integration testing.
- Finish high-priority accessibility, scaling, and multi-monitor corrections.

---

## [1.0.17] - 2026-08-12

### Added

- Added native Pilot Social pilot activity and awards pages, linked profile KPIs, assigned-airline branding, rank progression, private finance summaries, and collapsible landing trends on the website and in USAFCACARS.
- Added independent optional-module capability discovery: when USAFCSocial is missing, disabled, or awaiting migrations, ACARS hides all actionable Social controls and returns safely to Dashboard; a freshly installed module is detected automatically while signed in.
- Added responsive in-feed players for YouTube videos/live links, Twitch live/VOD/clips, Vimeo, Dailymotion, TikTok, Instagram, Streamable, Rumble, Loom, Kick, and direct MP4/M4V/WebM/OGG/MOV links, while ordinary websites retain safe rich preview cards.
- Added a physically bundled Twemoji stylesheet and searchable 1,697-entry emoji catalog, presented through compact smiley dropdowns for posts, comments, private messages, and reactions.
- Added the responsive, instrument-panel-inspired right operations rail with populated pilot, operations-grid, quick-action, and ACARS flight-data sections.
- Added separate **Load Flight to Planner** and **Load Flight Directly** controls with high-definition icons and independent active/progress states.
- Added configurable direct-load startup states for cold and dark, ready for engine start, engines running, and ready for taxi.
- Added the fixed lower-left airport/weather card with live airport context, NOAA METAR data, click-to-refresh behavior, and flight-aware departure/arrival transitions.
- Added high-definition day, night, sunrise, sunset, cloud, rain, snow, and thunderstorm artwork plus calculated moon-phase rendering.
- Added the approved left-navigation and right-operations-panel design references to the public documentation.

### Changed


- Changed Pilot Social image handling to detect and cache JPG, JPEG, PNG/APNG, GIF, WebP, AVIF, BMP, ICO, SVG, image-CDN URLs, and extensionless image responses; modern formats retain animation where supported or normalize to PNG for cross-client display.
- Rebuilt the right-side quick actions as riveted, dark-gunmetal cockpit controls with stable labels, icons, indicator lamps, and responsive sizing.
- Limited left-rail scrolling to the navigation links so connection, airport/weather, and version cards remain visible at normal application sizes.
- Made the airport weather strip fit its complete flight category, wind, visibility, temperature, altimeter, condition, and moon-phase text without right-edge truncation.
- Made weather overlays mutually exclusive so clear reports show the appropriate lighting/moon scene without false cloud artwork.
- Enabled the local development endpoint in Release builds only when ACARS is running on the authorized development machine or explicitly enabled by its development environment setting.
- Improved cached image reuse and window-control glyph rendering to prevent visual flashing and corrupted minimize/maximize/close symbols.

### Fixed

- Fixed the remaining Aircraft Catalog artwork delay and page-to-page memory growth: catalog updates now finish every available persistent display thumbnail before reporting completion, existing local caches self-complete silently in the background, completed thumbnails are never regenerated, the in-memory bitmap cache is bounded, and off-screen page/paintjob images are released while their local thumbnails remain immediately reusable. Runtime stress verification covered 25 forward pages plus 25 cached return pages with the client responsive and memory stable.

- Fixed Weather Center **FIT ROUTE** so it re-centers the complete loaded route after airport or station exploration.
- Fixed the live aircraft marker intercepting airport clicks; departure and arrival station reports remain selectable when the aircraft occupies the same coordinates.
- Fixed silent arrival/en-route ATIS, AWOS, and ASOS reception with supplemental local weather audio when MSFS has no native station audio; receiver mute state and delayed SimConnect frequency telemetry no longer cancel the broadcast.
- Moved route summary, departure/arrival observations, selected-station identity, and raw METAR computer data into black riveted instrument windows.
- Fixed older saved image/video posts remaining generic or blank by repairing stale preview metadata in place, with no repost required; redirecting website links now resolve through public-address-validated hops.
- Fixed flight cancellation so the lower-left airport card returns from the arrival target to the pilot's actual/last airport context.
- Fixed quick-action start/load visual-state updates so labels remain visible and the correct button stays illuminated.
- Fixed the pilot/operations rail layout so populated live data does not resize, clip, or force unnecessary scrolling at the normal application size.

---
## [1.0.16] - 2026-08-11

### Added

- Added native Pilot Social pilot activity and awards pages, linked profile KPIs, assigned-airline branding, rank progression, private finance summaries, and collapsible landing trends on the website and in USAFCACARS.
- Added independent optional-module capability discovery: when USAFCSocial is missing, disabled, or awaiting migrations, ACARS hides all actionable Social controls and returns safely to Dashboard; a freshly installed module is detected automatically while signed in.
- Added responsive in-feed players for YouTube videos/live links, Twitch live/VOD/clips, Vimeo, Dailymotion, TikTok, Instagram, Streamable, Rumble, Loom, Kick, and direct MP4/M4V/WebM/OGG/MOV links, while ordinary websites retain safe rich preview cards.
- Added a physically bundled Twemoji stylesheet and searchable 1,697-entry emoji catalog, presented through compact smiley dropdowns for posts, comments, private messages, and reactions.
- Added the first operational Communications Station with independent COM1 and COM2 selection.
- Added active/standby frequency transfer, mouse tuning, and two-way SimConnect radio synchronization.
- Added global push-to-talk that remains available while USAFCACARS is not focused.
- Added real microphone, transmit, receive, and spectrum metering.
- Added nearby-airport discovery, airport-category filters, published frequencies, and temporary open channels.
- Added public and private communications rooms with room creation, joining, disconnecting, rosters, and locked-room visibility.
- Added configurable Discord microphone-mute coordination during ACARS transmission.
- Added current and design-reference Communications Station images to the README.
- Added GitHub-compatible tab-style README navigation for major documentation sections.

### Changed


- Changed Pilot Social image handling to detect and cache JPG, JPEG, PNG/APNG, GIF, WebP, AVIF, BMP, ICO, SVG, image-CDN URLs, and extensionless image responses; modern formats retain animation where supported or normalize to PNG for cross-client display.
- Improved microphone normalization, receive buffering, and stale-packet handling to reduce low or garbled voice playback.
- Updated Communications Station, installation, testing, troubleshooting, and support documentation.
- Preserved the expanded communications-center artwork and roadmap as explicitly planned concepts beyond the current radio implementation.

---

## [1.0.4] - 2026-08-06

### Release Status

- **Development stage:** Alpha
- **Platform:** Windows desktop
- **Primary simulator integration:** Microsoft Flight Simulator through SimConnect
- **Server integration:** USA Flight Club phpVMS through the proprietary USAFCACARS API module
- **Recommended use:** Authorized testing and continued development
- **Production readiness:** Not yet production-ready

### Added

- Added native Pilot Social pilot activity and awards pages, linked profile KPIs, assigned-airline branding, rank progression, private finance summaries, and collapsible landing trends on the website and in USAFCACARS.
- Added independent optional-module capability discovery: when USAFCSocial is missing, disabled, or awaiting migrations, ACARS hides all actionable Social controls and returns safely to Dashboard; a freshly installed module is detected automatically while signed in.
- Added responsive in-feed players for YouTube videos/live links, Twitch live/VOD/clips, Vimeo, Dailymotion, TikTok, Instagram, Streamable, Rumble, Loom, Kick, and direct MP4/M4V/WebM/OGG/MOV links, while ordinary websites retain safe rich preview cards.
- Added a physically bundled Twemoji stylesheet and searchable 1,697-entry emoji catalog, presented through compact smiley dropdowns for posts, comments, private messages, and reactions.
#### Application Foundation

- Established the current USAFCACARS `1.0.4` development baseline.
- Continued the unified USA Flight Club desktop operations-center design.
- Added and expanded the persistent application shell with:
  - Left-side feature navigation
  - Pilot and account information
  - Current-flight information
  - Simulator connection status
  - Server connection status
  - Quick operational actions
  - Expandable center workspaces
  - Right-side operational panels
- Added alpha-state messaging and project documentation clarifying that concept graphics do not represent completed functionality.

#### USA Flight Club Account Integration

- Added the application structure for USA Flight Club pilot authentication.
- Added pilot-profile retrieval and dashboard population.
- Added support for pilot information including:
  - Pilot name
  - Pilot ID
  - Callsign
  - Avatar
  - Airline or division
  - Airline logo
  - Rank
  - Rank image
- Added authenticated client-to-server request handling.
- Added the foundation for secure API token/session use.
- Added error-state handling for invalid credentials and unavailable servers.

#### Flights and Bids

- Added the developing flight and bid workflow.
- Added support for:
  - Available flights
  - My Flights
  - Completed flights
  - Flight search
- Added selected-flight briefing data.
- Added departure and arrival airport presentation.
- Added route, aircraft, registration, altitude, distance, and duration data where available.
- Added support direction for valid three-character airport identifiers such as `81R`.
- Added selected-flight state management for the briefing and tracking workflow.

#### Flight Briefing

- Added the developing Pilot Briefing workspace.
- Added briefing sections for:
  - Flight summary
  - Route
  - Departure airport
  - Arrival airport
  - Alternate airport where available
  - Weather
  - Charts
  - NOTAM information
  - Fuel and weight information
  - Aircraft information
  - Operational checklists
- Added the briefing-map foundation.
- Added route and airport-marker display direction.
- Added clearing and replacement of stale selected-flight content as a required behavior.

#### SimConnect and Aircraft Telemetry

- Added the current SimConnect integration foundation.
- Added 64-bit simulator connectivity direction.
- Added telemetry structures for:
  - Latitude
  - Longitude
  - Altitude
  - Ground speed
  - Heading
  - Vertical speed
  - On-ground state
  - Fuel
  - Gear
  - Flaps
  - Lights
  - Engine state
  - Aircraft identity
  - Landing rate
- Added separation between simulator connection state and server connection state.
- Added the foundation for reconnect behavior after simulator interruption.
- Added aircraft-dependent integration planning for complex add-on aircraft.

#### Flight Lifecycle

- Added the developing full-flight workflow:
  - Select flight
  - Start flight
  - Initialize active session
  - Connect simulator
  - Send telemetry
  - Update live data
  - Detect flight phase
  - Complete flight
  - Submit PIREP
  - Close active session
- Added cancellation workflow direction.
- Added duplicate-submission prevention requirements.
- Added final-state handling for:
  - At Gate
  - Shutdown
  - Completed
- Added the phase-engine structure for:
  - Preflight
  - Boarding
  - Pushback
  - Taxi Out
  - Takeoff
  - Initial Climb
  - Climb
  - Cruise
  - Descent
  - Approach
  - Landing
  - Taxi In
  - At Gate
  - Shutdown
  - Completed

#### USAFCACARS API Module

- Continued development of the proprietary phpVMS API module.
- Added or maintained the API contract for:
  - Ping
  - Login
  - Logout
  - Me
  - Bids
  - Start
  - Update
  - Finish
  - Cancel
  - Live
- Added module direction for:
  - Weather
  - Airport information
  - Charts
  - Communications
  - Flightboard
  - ATC
  - Live-map data
  - Application settings
  - Version and update information
- Added server-side validation direction for authenticated pilot sessions.
- Added database and migration requirements for non-destructive upgrades.
- Added API-response consistency requirements.
- Added server-side protection against duplicate and unauthorized flight updates.

#### Live Operations Map

- Added and expanded the live-map development plan.
- Added support direction for:
  - USAFC aircraft
  - Departure airports
  - Arrival airports
  - Planned routes
  - Traveled trails
  - Smooth aircraft interpolation
  - Pilot and aircraft selection
  - Aircraft information
  - Pilot and flight information
  - Weather overlays
  - Airspace
  - Navigation layers
  - ATC coverage
  - External traffic sources
- Added support direction for ADS-B, VATSIM, and IVAO traffic.
- Added pop-out map and panel behavior.
- Added independent map-instance and saved-layer-profile direction.
- Added Zulu clock and range/compass requirements.
- Added the official live-map link:
  - `https://usaflightclub.net/usafcacars/live`

#### Flightboard

- Added the developing split-flap Flightboard workspace.
- Added board views:
  - Current
  - Departures
  - Arrivals
- Added traffic-source direction:
  - USAFC
  - ADS-B
  - VATSIM
  - IVAO
- Added flightboard columns for:
  - Phase
  - Status
  - Flight number
  - Departure
  - Arrival
  - Departure time
  - Estimated arrival
  - Altitude
  - Speed
  - Heading
  - Aircraft type and registration
  - Pilot
- Added independent changed-character animation direction.
- Added requirements to prevent unchanged values and entire rows from flashing.

#### Weather and Airport Information

- Added the developing Weather Center structure.
- Added weather-layer direction for:
  - METAR
  - TAF
  - Radar
  - Clouds
  - Wind
  - Temperature
  - Pressure
  - Precipitation
  - Visibility
  - Lightning
  - SIGMET and AIRMET information
- Added airport-information direction for:
  - Airport name
  - Identifier
  - Coordinates
  - Elevation
  - Runways
  - Taxiways
  - Frequencies
  - Weather
  - Navigation information
- Added chart-viewer direction for:
  - Thumbnails
  - Full-page viewing
  - Zoom
  - Zoom percentage
  - Reset
  - Pop-out windows

#### Voice Communications

- Added and expanded the developing Voice Communications system.
- Added communication concepts for:
  - Airport frequency rooms
  - UNICOM
  - ATC rooms
  - Private crew rooms
  - Open group rooms
  - Push-to-talk
  - Mute
  - Deafen
  - Room rosters
  - Active frequencies
  - Automatic room transitions
- Added audio-device discovery and selection direction.
- Added microphone-level monitoring.
- Added microphone playback-test requirements.
- Added speaker-test requirements.
- Added scrollable Voice Communications and Voice & Radio Settings pages.
- Added USAFC styling requirements for dropdowns, text blocks, and scrollbars.

#### ATC and TRACON

- Added the advanced ATC and TRACON development direction.
- Added support concepts for:
  - Radar scope
  - Layered 3D airspace
  - Glowing vector corridors
  - Animated traffic trails
  - Tactical aircraft data blocks
  - Range rings
  - Sector boundaries
  - Weather returns
  - SID and STAR layers
  - Airport, VOR, and NDB symbols
  - Obstacles
  - ATC coverage
  - Aircraft selection
  - Handoffs
  - Vector commands
- Added synchronized aircraft, pilot-panel, data-block, bubble, and strip selection.
- Added the complete ATC workspace concept with radar, commands, frequencies, airport operations, weather, and coordination.

#### Flight Strips

- Added the developing Flight Strips workspace.
- Added strip categories for:
  - Arrivals
  - Departures
  - Ground
  - Active
  - Hold
  - Bin/Archive
- Added strip fields and workflow direction for:
  - Callsign
  - Aircraft type
  - Registration
  - Route
  - Altitude
  - Squawk
  - Assigned runway
  - Controller remarks
  - Clearance state
  - Handoffs
  - Hold queues
  - Controller annotations
- Added synchronization requirements between flight strips and map targets.

#### Airport and Taxi Management

- Added the advanced airport-selection and taxi-management concept.
- Added support direction for:
  - Airport selection
  - Favorites
  - Live airport status
  - Active runways
  - Airport diagrams
  - Gates
  - Ramp traffic
  - Pushback requests
  - Taxi queues
  - Taxi routes
  - Hold-short commands
  - Runway occupancy
  - Gate management
  - Ramp congestion
  - Arrival and departure queues
  - ATIS
  - Ground frequencies
  - Runway-incursion warnings
  - Taxi-conflict alerts
  - 3D ground-operations view

#### Horizon Explorer

- Added and expanded Horizon Explorer as an integrated aviation research studio.
- Added support direction for:
  - Multiple tabs
  - Pinned resources
  - Full-page charts
  - Terminal diagrams
  - NOTAM workspaces
  - Aircraft manuals
  - Route plans
  - Airport documents
  - Search
  - Printing
  - Downloading
  - Draggable panels
  - Pop-out windows
- Added WebView lifecycle and cleanup requirements.

#### Workspace Manager

- Added and expanded Workspace Manager.
- Added layout concepts for:
  - Grid
  - Rows
  - Columns
  - Stacks
  - BSP
  - Ultrawide
  - Floating windows
  - Multi-monitor workspaces
- Added layout persistence.
- Added saved window positions and sizes.
- Added fullscreen and restore behavior.
- Added disconnected-monitor and off-screen-window recovery requirements.

#### Aircraft Control

- Added the advanced Aircraft Control concept.
- Added support direction for displaying and controlling supported SimConnect aircraft systems:
  - Flight instruments
  - Engine instruments
  - Fuel
  - Electrical systems
  - Hydraulics
  - Pneumatics
  - Pressurization
  - Landing gear
  - Flaps
  - Spoilers
  - Trim
  - Speed brake
  - Parking brake
  - Exterior lights
  - Cabin lights
  - Seatbelt sign
  - No-smoking sign
  - Batteries
  - Generators
  - Avionics
  - External power
  - Engine start
  - APU
  - Anti-ice
  - Pitot heat
  - Radios
  - Transponder
  - Doors
  - Ground services
- Added aircraft-specific adapter direction for add-on aircraft that do not expose systems through standard SimConnect variables and events.
- Added the **Aircraft Control** navigation concept.

#### Passenger Operations

- Added the Passenger Operations concept as a future USAFC-owned passenger and cabin simulation system.
- Added support direction for:
  - Aircraft cabin configuration
  - Seat-map editing
  - Passenger manifest
  - Seat assignment
  - Boarding
  - Baggage and payload
  - Passenger comfort
  - Passenger satisfaction
  - Special-service requests
  - Cabin announcements
  - Meal and beverage service
  - Movie and entertainment service
  - Cabin-service timeline
  - Seatbelt sign
  - No-smoking sign
  - Cabin lighting
  - Cabin temperature
  - Passenger and cargo doors
  - Jetway and stairs
  - Incidents
  - Arrival and deboarding
  - Final service scoring

#### Music and Radio

- Added and expanded the Music & Radio Center concept.
- Added application tabs for:
  - Music Player
  - Radio Scanner
  - Music Radio Player
- Added support direction for:
  - Local playlists
  - Favorites
  - Now-playing queue
  - Album artwork
  - Play, pause, stop, previous, and next
  - Shuffle and repeat
  - Equalizer
  - Audio visualization
  - Audio-output selection
  - USAFC Radio
  - Aviation radio presets
  - Live transmissions
  - Squelch
  - Independent volume controls

#### Pilot Profile

- Added the expanded Pilot Profile and career-command-center concept.
- Added support direction for:
  - Pilot identity
  - Rank
  - Rank progression
  - Level and experience
  - Total hours
  - Flights and landings
  - Distance
  - Recent flights
  - Route history
  - Monthly activity
  - Aircraft time
  - Ratings
  - Endorsements
  - Certifications
  - Type qualifications
  - Achievements
  - Badges
  - Career milestones
  - Logbook
  - Connected services

#### Community Hub

- Added the Community Hub concept.
- Added support direction for:
  - Community feed
  - Groups
  - Events
  - Gallery
  - Discord integration
  - Leaderboards
  - Online members
  - Live pilot status
  - Community chat
  - Group flights
  - Event RSVP
  - Announcements
  - Achievements
  - Screenshot sharing

#### Help and Support

- Added the integrated Help and Support Center concept.
- Added support direction for:
  - Help search
  - Getting-started guides
  - Knowledge base
  - Video tutorials
  - Downloads
  - System status
  - Support tickets
  - Contact support
  - Troubleshooting
  - Connection tests
  - System diagnostics
  - Log viewer
  - Settings reset
  - Add-on management
  - Popular topics
  - Current ticket status

#### Release Repository and Documentation

- Added a complete GitHub README for the USAFCACARS Releases repository.
- Added concept graphics throughout the README.
- Added prominent alpha-development warnings.
- Added the official live-map link.
- Added proprietary licensing documentation.
- Added an Alpha Testing guide.
- Added installation, troubleshooting, security, privacy, and issue-reporting direction.
- Added repository structure guidance for public release assets.
- Added checksum-verification instructions.
- Added release-channel definitions.
- Added guidance to distribute installers through GitHub Releases rather than normal Git history.

### Changed


- Changed Pilot Social image handling to detect and cache JPG, JPEG, PNG/APNG, GIF, WebP, AVIF, BMP, ICO, SVG, image-CDN URLs, and extensionless image responses; modern formats retain animation where supported or normalize to PNG for cross-client display.
- Clarified that USAFCACARS is proprietary software and is not open source.
- Standardized the Composer license direction as:

```json
"license": "proprietary"
```

- Clarified that concept images represent intended scope and design direction, not completed release functionality.
- Clarified that a `1.x` version number does not mean the current alpha build is stable or production-ready.
- Consolidated application, simulator, server, live-map, ATC, communications, and future passenger-operation plans into one documented project scope.
- Improved documentation for safe testing of:
  - Authentication
  - SimConnect
  - Flight lifecycle
  - Live map
  - Flightboard
  - Weather
  - Voice communications
  - Aircraft controls
  - Passenger operations
  - Multi-monitor workspaces
- Improved documentation separating current implementation, active development, and long-term concept features.

### Security

- Added proprietary licensing restrictions against unauthorized redistribution, modification, rebranding, resale, and use by unrelated organizations.
- Added requirements not to expose:
  - Passwords
  - Authentication tokens
  - API keys
  - Database credentials
  - Private certificates
  - Private pilot records
  - Private voice communications
  - Unredacted logs
- Added direction for private security-vulnerability reporting.
- Added server-side authorization requirements for protected communications rooms and active flight sessions.
- Added controlled update and download requirements.
- Added checksum-verification guidance for release packages.

### Known Limitations

The following systems may be incomplete, experimental, partially implemented, aircraft-dependent, or unavailable in the `1.0.4` alpha build:

- Complete end-to-end flight submission under every simulator condition
- Microsoft Flight Simulator 2024 compatibility across all supported aircraft
- Complex third-party aircraft system control
- Aircraft-specific SimConnect adapters
- Automatic reconnection under every network interruption
- Live-map smoothing and all planned layers
- Full flightboard animation and external traffic sources
- Some weather layers and weather-provider integrations
- Complete airport chart coverage
- Complete voice communications and room transitions
- Microphone loopback under every audio-device configuration
- Full ATC command processing
- Layered 3D TRACON display
- Complete flight-strip workflow
- Airport taxi-management automation
- Passenger Operations
- Full Community Hub integration
- Full Help and Support ticket integration
- Automatic self-updating
- Complete automated test coverage
- Stable long-duration performance across every multi-monitor configuration

### Testing Notes

Testers should verify the exact features listed in the release notes for the downloadable `1.0.4` build.

At minimum, reports should include:

- USAFCACARS version
- Windows version
- MSFS 2020 or MSFS 2024
- Simulator build
- Aircraft and add-on version
- Steps to reproduce
- Expected result
- Actual result
- Sanitized logs
- Screenshots or video where useful

Do not post passwords, authentication tokens, private communications, or sensitive pilot information.

---

## Earlier Versions

Versions `1.0.0` through `1.0.3` predate this formal public changelog.

Detailed historical entries have not been invented or reconstructed without evidence. They should be added later from authoritative sources such as:

- Existing Git tags
- GitHub Releases
- Commit history
- Archived release notes
- Build folders
- Installer metadata
- Application version history
- Development notes

Until that work is completed, version `1.0.4` is the documented public baseline for the current USAFCACARS alpha project.

---

## Release Entry Template

Use this template for future versions:

```markdown
## [1.0.5] - YYYY-MM-DD

### Release Status

- Development stage:
- Supported simulator:
- Required runtime:
- Mandatory update:
- Tested environment:

### Added

- Added native Pilot Social pilot activity and awards pages, linked profile KPIs, assigned-airline branding, rank progression, private finance summaries, and collapsible landing trends on the website and in USAFCACARS.
- Added independent optional-module capability discovery: when USAFCSocial is missing, disabled, or awaiting migrations, ACARS hides all actionable Social controls and returns safely to Dashboard; a freshly installed module is detected automatically while signed in.
- Added responsive in-feed players for YouTube videos/live links, Twitch live/VOD/clips, Vimeo, Dailymotion, TikTok, Instagram, Streamable, Rumble, Loom, Kick, and direct MP4/M4V/WebM/OGG/MOV links, while ordinary websites retain safe rich preview cards.
- Added a physically bundled Twemoji stylesheet and searchable 1,697-entry emoji catalog, presented through compact smiley dropdowns for posts, comments, private messages, and reactions.
- New features

### Changed


- Changed Pilot Social image handling to detect and cache JPG, JPEG, PNG/APNG, GIF, WebP, AVIF, BMP, ICO, SVG, image-CDN URLs, and extensionless image responses; modern formats retain animation where supported or normalize to PNG for cross-client display.
- Behavior or interface changes

### Fixed

- Fixed the remaining Aircraft Catalog artwork delay and page-to-page memory growth: catalog updates now finish every available persistent display thumbnail before reporting completion, existing local caches self-complete silently in the background, completed thumbnails are never regenerated, the in-memory bitmap cache is bounded, and off-screen page/paintjob images are released while their local thumbnails remain immediately reusable. Runtime stress verification covered 25 forward pages plus 25 cached return pages with the client responsive and memory stable.

- Fixed Weather Center **FIT ROUTE** so it re-centers the complete loaded route after airport or station exploration.
- Fixed the live aircraft marker intercepting airport clicks; departure and arrival station reports remain selectable when the aircraft occupies the same coordinates.
- Fixed silent arrival/en-route ATIS, AWOS, and ASOS reception with supplemental local weather audio when MSFS has no native station audio; receiver mute state and delayed SimConnect frequency telemetry no longer cancel the broadcast.
- Moved route summary, departure/arrival observations, selected-station identity, and raw METAR computer data into black riveted instrument windows.
- Fixed older saved image/video posts remaining generic or blank by repairing stale preview metadata in place, with no repost required; redirecting website links now resolve through public-address-validated hops.
- Corrected defects

### Security

- Security-related improvements

### Deprecated

- Features scheduled for removal

### Removed

- Removed features

### Known Limitations

- Remaining defects or incomplete systems

### Upgrade Notes

- Installation or migration instructions

### Checksums

- `USAFCACARS-Setup-1.0.5.exe`
  - SHA-256: ``
```

---

## Version Links

- **USA Flight Club:** [https://usaflightclub.net](https://usaflightclub.net)
- **Official Downloads:** [https://usaflightclub.net/downloads](https://usaflightclub.net/downloads)
- **USAFCACARS Live Map:** [https://usaflightclub.net/usafcacars/live](https://usaflightclub.net/usafcacars/live)
- **Latest GitHub Release:** [View latest release](../../releases/latest)
- **Alpha Testing Guide:** [docs/ALPHA-TESTING.md](docs/ALPHA-TESTING.md)

---

```text
Copyright © 2026 USA Flight Club.
All rights reserved.

USAFCACARS is proprietary software.
```
