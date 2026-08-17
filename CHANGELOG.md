# Changelog

All notable changes to **USAFCACARS** are documented in this file.

USAFCACARS is proprietary software developed for USA Flight Club. The application is currently in **active alpha development**. The latest documented desktop release is `1.0.17`.

This changelog follows the general structure of [Keep a Changelog](https://keepachangelog.com/en/1.1.0/) and uses version numbers compatible with Semantic Versioning where practical.

> [!IMPORTANT]
> A version number does not indicate that USAFCACARS is production-ready.
>
> Alpha releases may contain incomplete systems, disabled controls, compatibility limitations, breaking configuration changes, or defects. The release notes attached to each downloadable build remain the authoritative record of what was tested and included in that build.

---

## [Unreleased]

### Added

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
