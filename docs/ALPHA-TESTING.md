# USAFCACARS Alpha Testing Guide

USAFCACARS is currently in **active alpha development**.

Alpha builds are provided so authorized testers can help identify defects, validate features, confirm simulator compatibility, and improve the application before broader beta and stable releases.

This document explains how to install, test, document, and report issues found in an alpha build.

> [!IMPORTANT]
> Alpha builds are incomplete and may contain disabled controls, placeholder content, unfinished integrations, breaking configuration changes, visual defects, crashes, or data-loss bugs.
>
> Do not rely on an alpha build as the only record of an important flight.

> [!NOTE]
> Interface images, roadmap descriptions, and concept graphics shown in the repository represent the intended direction of USAFCACARS. They do not guarantee that every displayed feature is already implemented in the current alpha release.

---

## 1. Purpose of Alpha Testing

Alpha testing is intended to help verify the behavior of the current development build in real operating conditions.

Testers may be asked to evaluate:

- Application startup and shutdown
- USA Flight Club account authentication
- Pilot profile loading
- Flight and bid retrieval
- Flight selection and briefing
- SimConnect connection
- Aircraft telemetry
- Flight-phase detection
- Live map updates
- Flightboard updates
- Weather and airport data
- Charts
- Voice communications
- Audio-device behavior
- Horizon Explorer
- Workspace Manager
- Aircraft-specific compatibility
- Flight completion and PIREP submission
- Update detection
- Error handling
- Performance and stability

Some advanced systems may remain concept-only, experimental, partially implemented, or unavailable in a particular alpha build.

---

## 2. Who Should Use Alpha Builds

Alpha builds are intended for users who:

- Understand that the application is unfinished
- Are comfortable troubleshooting Windows applications
- Can provide clear reproduction steps
- Can identify their simulator and aircraft versions
- Are willing to review logs
- Will avoid publishing passwords, tokens, or private data
- Can reinstall or reset the application when required
- Understand that features may change or be removed

Alpha builds are not recommended for users who need a fully stable and complete ACARS client.

---

## 3. Before Installing

Before installing an alpha build:

1. Read the GitHub release notes.
2. Review the list of implemented features.
3. Review known issues and limitations.
4. Confirm the supported simulator version.
5. Confirm the required .NET runtime.
6. Confirm whether Microsoft Edge WebView2 Runtime is required.
7. Confirm whether SimConnect dependencies are bundled.
8. Close any running copy of USAFCACARS.
9. Back up the current application settings when instructed.
10. Complete or cancel any active flight before updating.
11. Confirm the release file checksum when provided.

Do not install an alpha build over a running copy of the application.

---

## 4. Supported Test Environment

The exact supported environment may change by release.

General target environment:

| Component | Target |
|---|---|
| Operating system | Windows 10 or Windows 11 |
| Architecture | 64-bit Windows |
| Simulator | Microsoft Flight Simulator 2020 and/or Microsoft Flight Simulator 2024 |
| Simulator connection | SimConnect |
| USAFC account | Active USA Flight Club pilot account |
| Internet connection | Required for connected features |
| Browser runtime | Microsoft Edge WebView2 where required |
| Audio | Microphone and speakers/headset for communications testing |

Always include the exact environment used when reporting a defect.

---

## 5. Release Verification

Before launching the installer, verify the checksum when one is published.

PowerShell example:

```powershell
Get-FileHash .\USAFCACARS-Setup.exe -Algorithm SHA256
```

Compare the returned value with the checksum included in the release notes.

Do not install the file if the checksum does not match.

---

## 6. Installation

Typical installation steps:

1. Download the current alpha release.
2. Verify the checksum.
3. Close USAFCACARS.
4. Close any stale USAFCACARS background process in Task Manager.
5. Run the installer.
6. Install required prerequisites if prompted.
7. Launch USAFCACARS.
8. Confirm the displayed version matches the release.
9. Sign in with an authorized USA Flight Club pilot account.
10. Review simulator, audio, API, and workspace settings.

Portable builds should be extracted into a new folder unless the release notes explicitly allow an in-place update.

---

## 7. First Launch Checklist

On the first launch, verify:

- The application starts without an unhandled exception.
- The login screen appears correctly.
- USAFC branding and resources load.
- Text is readable.
- Buttons and controls are not clipped.
- The application displays the expected version.
- The configured API environment is correct.
- Server connection status is visible.
- The application remains responsive.
- No unexpected administrator prompt appears.
- Closing the application ends all USAFCACARS processes.

Record any startup error exactly as shown.

---

## 8. Authentication Testing

Test the following:

### Valid login

- Enter valid USAFC pilot credentials.
- Confirm login succeeds.
- Confirm the dashboard opens.
- Confirm the pilot profile loads.
- Confirm the correct pilot ID, name, airline, rank, and avatar appear.
- Confirm no password or token appears in the user interface or logs.

### Invalid login

- Enter an incorrect password.
- Confirm the application displays a clear invalid-credentials message.
- Confirm the application does not crash.
- Confirm the login button becomes usable again.

### Server unavailable

- Disconnect the network temporarily or use the provided test method.
- Confirm the application distinguishes a server-connection error from invalid credentials.
- Confirm the application remains responsive.

### Logout

- Log out.
- Confirm the active session is cleared.
- Confirm the application returns to the login screen.
- Confirm protected data is no longer accessible.

Never include real credentials in screenshots, videos, or issue reports.

---

## 9. Pilot Profile Testing

Verify that the pilot dashboard and profile display the correct available information:

- Pilot name
- Pilot ID
- Callsign
- Division or airline
- Rank
- Rank image
- Avatar
- Flight hours
- Completed flights
- Current airport
- Current status
- Current flight
- Network status
- On Comms status

Also test missing or incomplete profile content:

- Missing avatar
- Missing rank image
- Missing airline logo
- Missing optional fields

The application should use a clean fallback rather than show a broken image or crash.

---

## 10. Flight and Bid Testing

Test:

- Bid list loading
- Available flights
- My Flights
- Completed flights
- Flight search
- Tab counts
- Empty states
- Error states
- Refresh behavior
- Flight selection
- Route display
- Aircraft assignment
- Departure and arrival airport information

Confirm that valid three-character airport identifiers, such as `81R`, are handled correctly and are not automatically converted into invalid four-character identifiers.

---

## 11. Pilot Briefing Testing

For a selected flight, verify:

- Flight number
- Departure airport
- Arrival airport
- Alternate airport where available
- Route
- Distance
- Planned altitude
- Estimated duration
- Aircraft type
- Registration
- Weather
- Airport information
- Route map
- Charts
- NOTAM information
- Fuel information
- Weight information
- Checklists

Test selecting a second flight and confirm that the briefing updates completely without retaining stale data from the prior selection.

---

## 12. SimConnect Testing

Before testing:

1. Start Microsoft Flight Simulator.
2. Load fully into an aircraft.
3. Wait until the cockpit is interactive.
4. Start or reconnect USAFCACARS.

Verify:

- SimConnect status changes to connected.
- The correct aircraft is identified where supported.
- Position data updates.
- Altitude updates.
- Speed updates.
- Heading updates.
- Vertical speed updates.
- On-ground status updates.
- Fuel data updates.
- Gear, flaps, lights, and other supported states update.
- Disconnecting or closing the simulator does not crash USAFCACARS.
- Reconnecting restores telemetry where supported.

Record the exact aircraft and add-on version used.

Some complex add-on aircraft may require custom adapters and may not expose all systems through standard SimConnect variables.

---

## 13. Flight Lifecycle Testing

Test the complete workflow when the release supports it:

1. Log in.
2. Load bids.
3. Select a flight.
4. Review the briefing.
5. Start the flight.
6. Connect to the simulator.
7. Begin movement.
8. Confirm telemetry updates.
9. Confirm flight phases change.
10. Confirm the flight appears in live data.
11. Confirm the live map updates.
12. Confirm the flightboard updates.
13. Complete the flight.
14. Park and shut down.
15. Submit the final flight.
16. Confirm the PIREP is created.
17. Confirm the active live session closes.
18. Confirm the application returns to a stable post-flight state.

Record the point at which the workflow fails if it does not complete.

---

## 14. Flight Phase Testing

Expected phase concepts may include:

```text
PREFLIGHT
BOARDING
PUSHBACK
TAXI OUT
TAKEOFF
INITIAL CLIMB
CLIMB
CRUISE
DESCENT
APPROACH
LANDING
TAXI IN
AT GATE
SHUTDOWN
COMPLETED
```

Watch for:

- Incorrect phase order
- Rapid phase switching
- Repeated phase changes while stationary
- Landing detected during a brief runway bounce
- Cruise detected too early
- Shutdown detected before engines are off
- Final phase not reaching completed
- On-ground state remaining incorrect

Include relevant altitude, speed, gear, engine, and on-ground information in the report when possible.

---

## 15. Live Map Testing

Official live map:

[https://usaflightclub.net/usafcacars/live](https://usaflightclub.net/usafcacars/live)

Verify:

- The page loads.
- Active USAFC flights appear.
- The correct pilot and flight appear.
- Departure airport appears.
- Arrival airport appears.
- The route appears.
- Aircraft position updates.
- Aircraft movement is smooth.
- Aircraft heading is reasonable.
- Stale aircraft are removed.
- Pilot selection opens the correct information.
- Weather layers align geographically.
- Layer toggles work.
- Pop-out behavior works where enabled.
- No major browser-console errors occur.

When reporting a map issue, include the browser, page zoom, and whether the issue also appears inside the desktop application.

---

## 16. Flightboard Testing

Verify:

- Current, Departures, and Arrivals tabs
- USAFC source
- Other enabled traffic sources
- Correct flight number
- Correct departure and arrival
- Correct phase
- Correct status
- Correct altitude
- Correct speed
- Correct heading
- Correct aircraft and registration
- Correct pilot
- Row alignment
- Scrolling
- Reset to 100% zoom
- Character animation
- No flashing of unchanged values
- No whole-row blinking
- No duplicate rows
- No missing rows after refresh

Report whether the issue occurs only during animation or remains after the board becomes stable.

---

## 17. Weather Testing

Test available weather features:

- METAR
- TAF
- Airport weather
- Radar
- Clouds
- Wind
- Temperature
- Pressure
- Precipitation
- Visibility
- Lightning
- SIGMET/AIRMET information
- Weather thumbnails
- Saved layer settings

Watch for:

- Block-shaped weather tiles
- Visible seams
- Incorrect transparency
- Incorrect geographic alignment
- Stale data
- Blank layers
- Repeated loading
- High CPU or memory use
- Application freezes

Record the airport, region, layer, date, and approximate time of the test.

---

## 18. Airport and Chart Testing

Verify:

- Three-character identifiers
- Four-character identifiers
- Airport name
- Coordinates
- Elevation
- Runway data
- Frequency data
- Weather
- Chart thumbnails
- Full-page chart display
- Zoom controls
- Zoom percentage
- Reset zoom
- Chart pop-out
- Selecting another airport clears the previous chart

Do not include copyrighted chart files in public issue reports unless redistribution is permitted.

---

## 19. Voice Communications Testing

Test with a headset when possible.

Verify:

- Communications Station opens and fits the normal application workspace.
- COM1 and COM2 selection changes the illuminated radio state.
- Active and standby frequencies transfer correctly.
- Frequency tuning controls change the selected standby channel.
- Simulator COM changes update the Communications Station through SimConnect.
- Communications Station changes update the simulator where supported.
- Global push-to-talk works while another application has focus.
- Configured push-to-talk press and release are both detected reliably.
- Microphone device list loads.
- Speaker device list loads.
- Live microphone spectrum and MIC meter respond to real input.
- TX responds only while transmitting and RX responds to received audio.
- Microphone and speaker volume controls change real audio levels.
- Microphone test captures and plays back audio locally.
- Speaker test is audible.
- Mute blocks outgoing audio.
- Nearby airports and category filters return appropriate results.
- Airport channels display the correct frequency and status.
- Public and private rooms can be created, joined, and disconnected.
- Private rooms display a lock and enforce their access code.
- Active room, room members, and connection status remain accurate.
- Discord microphone-mute coordination works globally when configured.
- Device changes are applied and disconnecting a device is handled.
- Closing the application releases the audio device and global PTT hook.

Do not record or publish private communications without all required permissions.

---

## 20. Horizon Explorer Testing

Verify:

- Horizon Explorer opens.
- New tabs open.
- Tabs close.
- Pinned resources load.
- Navigation controls work.
- Loading indicators appear.
- Charts and documents display.
- External pages open safely.
- Pop-out behavior works where enabled.
- Closing a tab releases resources.
- Reopening the panel does not create duplicate browser processes.
- The application remains responsive during slow page loads.

Record the page address only when it does not contain private or account-specific information.

---

## 21. Workspace Manager Testing

Test:

- Grid layouts
- Rows
- Columns
- Stacks
- BSP layouts
- Ultrawide layouts
- Floating windows
- Saved window positions
- Saved window sizes
- Fullscreen
- Restore
- Reset
- Multi-monitor arrangements
- Disconnected-monitor recovery
- Application restart

Verify that no restored window becomes permanently inaccessible off-screen.

---

## 22. Aircraft Control Testing

Aircraft Control is an advanced and aircraft-dependent feature.

Test only controls enabled by the current build.

Potential systems include:

- Lights
- Landing gear
- Flaps
- Spoilers
- Trim
- Parking brake
- Seatbelt sign
- No-smoking sign
- Doors
- Batteries
- Generators
- Avionics
- Anti-ice
- Pitot heat
- Radios
- Transponder
- Engine start
- APU
- Ground services

Before testing:

- Use a safe simulator environment.
- Do not test during an important online flight.
- Confirm the correct aircraft is loaded.
- Verify each command visually in the simulator.
- Check whether a control is read-only or command-capable.
- Test one control at a time.

Report:

- Aircraft
- Add-on developer
- Aircraft version
- Simulator version
- Control used
- Expected simulator result
- Actual simulator result
- Whether the displayed state updated afterward

Never use USAFCACARS to control real aircraft or real equipment.

---

## 23. Passenger Operations Testing

Passenger Operations is a planned advanced simulation system and may be unavailable or incomplete in early alpha releases.

When enabled, test:

- Aircraft cabin configuration
- Seating layout
- Passenger roster
- Seat assignment
- Boarding
- Baggage and payload
- Door status
- Seatbelt sign
- No-smoking sign
- Cabin lighting
- Cabin temperature
- Meal service
- Beverage service
- Movie or entertainment service
- Announcements
- Passenger comfort
- Passenger satisfaction
- Special-service requests
- Incidents
- Arrival and deboarding
- Final service score

Verify that passenger-service actions do not incorrectly change unrelated simulator systems.

---

## 24. Music and Radio Testing

Verify:

- Music Player tab
- Radio Scanner tab
- Music Radio Player tab
- Play
- Pause
- Stop
- Next
- Previous
- Volume
- Shuffle
- Repeat
- Playlist selection
- Stream selection
- Audio-output selection
- Equalizer
- No duplicate playback
- No audio continuing after shutdown

Confirm that music playback does not interfere with voice communications or microphone testing.

---

## 25. Community and Support Testing

When enabled, verify:

- Community feed
- Online members
- Groups
- Events
- Chat
- Discord links
- Achievements
- Support search
- Knowledge base
- Downloads
- System status
- Diagnostics
- Ticket links
- Log viewer

Do not include private community or support information in public reports.

---

## 26. Performance Testing

Watch for:

- High CPU use
- High memory use
- Slow startup
- UI freezing
- Map stuttering
- Flightboard animation lag
- Repeated WebView processes
- Audio delay
- Telemetry backlog
- Excessive disk logging
- Timers continuing after panels close
- Stale processes after application exit

Include Task Manager observations when useful.

A strong report identifies:

- What feature was open
- How long the app had been running
- Whether MSFS was running
- Approximate CPU use
- Approximate memory use
- Whether performance recovered after closing the feature

---

## 27. Network Interruption Testing

When safe to do so:

1. Start a test session.
2. Disconnect the network briefly.
3. Observe application behavior.
4. Restore the network.
5. Confirm the application reconnects.

Verify:

- The app does not crash.
- The pilot is informed that connectivity was lost.
- SimConnect remains separate from server status.
- Telemetry resumes.
- Duplicate flight-finish requests are not created.
- The live map eventually updates.
- The application does not flood the logs.

Do not interrupt the network during an important or irreplaceable flight.

---

## 28. Shutdown Testing

Close the application and confirm:

- The main window closes.
- Pop-out windows close.
- SimConnect polling stops.
- API timers stop.
- Weather updates stop.
- Audio capture stops.
- Audio playback stops.
- Communications disconnect.
- WebView resources close.
- No USAFCACARS process remains in Task Manager.
- Settings are saved only when expected.

Report any process that remains active after the interface closes.

---

## 29. What Makes a Good Bug Report

A useful bug report contains:

### Summary

A clear one-sentence description.

Example:

```text
Flightboard arrival rows flash continuously after a live-data refresh.
```

### Environment

Include:

- USAFCACARS version
- Release channel
- Windows version
- MSFS 2020 or 2024
- Simulator build
- Aircraft
- Aircraft add-on version
- Display resolution
- Windows scaling
- Number of monitors
- Audio device where relevant

### Steps to reproduce

Numbered and specific.

Example:

```text
1. Launch USAFCACARS.
2. Log in as a test pilot.
3. Open Flightboard.
4. Select Arrivals.
5. Wait for the second automatic refresh.
6. Observe all rows flashing.
```

### Expected result

Explain what should have happened.

### Actual result

Explain what happened instead.

### Frequency

State whether it occurs:

- Every time
- Often
- Occasionally
- Once
- Only after a specific action

### Evidence

Include:

- Screenshot
- Short screen recording
- Sanitized log excerpt
- Exact error message
- Relevant timestamps

Never include passwords, full tokens, API secrets, private messages, or sensitive pilot data.

---

## 30. Bug Report Template

```markdown
## Summary

Describe the problem in one or two sentences.

## USAFCACARS Version

Example: 0.1.0-alpha.3

## Environment

- Windows:
- Simulator:
- Simulator version:
- Aircraft:
- Aircraft version:
- Monitors:
- Resolution:
- Windows scaling:
- Audio device:
- Network type:

## Steps to Reproduce

1.
2.
3.
4.

## Expected Result

Describe the expected behavior.

## Actual Result

Describe the actual behavior.

## Frequency

Every time / Often / Occasionally / Once

## Error Message

Paste the exact error message, if available.

## Logs

Attach or paste only sanitized excerpts.

## Screenshots or Video

Attach supporting evidence if useful.

## Additional Information

Include anything else that may help.

## Privacy Confirmation

- [ ] I removed passwords, authentication tokens, API credentials, private communications, and sensitive personal data.
```

---

## 31. Feature Request Template

```markdown
## Feature Summary

Describe the requested feature.

## Problem It Solves

Explain why the feature is useful.

## Suggested Workflow

Describe how the feature should work.

## Related USAFCACARS Area

Dashboard / Tracking / Map / Flightboard / Briefing / Weather / ATC /
Comms / Aircraft Control / Passenger Operations / Horizon Explorer /
Workspace Manager / Music & Radio / Community / Support / Other

## Simulator or Aircraft Dependency

State whether the request depends on a simulator, aircraft, add-on, or API.

## Concept Reference

Link to an existing concept image or roadmap section if relevant.

## Additional Notes

Add any limitations, examples, or compatibility concerns.
```

---

## 32. Log Collection

Only provide logs requested by USAFC support or maintainers.

Before sharing a log:

- Open it in a text editor.
- Search for your email.
- Search for your pilot ID.
- Search for `token`.
- Search for `authorization`.
- Search for `password`.
- Search for private URLs.
- Search for private chat or voice information.
- Remove unrelated personal information.

Do not publicly upload a complete log when a smaller excerpt demonstrates the issue.

---

## 33. Security Issues

Do not report security vulnerabilities through a public issue.

Examples include:

- Authentication bypass
- Token exposure
- Credential leakage
- Unauthorized admin access
- Private data exposure
- Remote code execution
- Insecure update behavior
- Unauthorized communications access

Report security concerns privately through the official USA Flight Club support channel or website:

[https://usaflightclub.net](https://usaflightclub.net)

---

## 34. Privacy Rules for Testers

Do not publish:

- Passwords
- Authentication tokens
- API keys
- Administrator credentials
- Private pilot records
- Private voice communications
- Private chat messages
- Personal email addresses without permission
- Unredacted diagnostic logs
- Private server paths
- Database information
- Security-sensitive configuration

Use a test account when one is provided.

---

## 35. Known Alpha Limitations

The exact known limitations are documented with each release.

Common alpha limitations may include:

- Missing features
- Incomplete pages
- Placeholder controls
- Experimental aircraft support
- Aircraft-specific SimConnect incompatibilities
- Temporary UI layouts
- Incomplete voice communications
- Missing weather layers
- Incomplete chart sources
- Unfinished update logic
- Temporary debug controls
- Limited error messages
- Database or API changes between builds

Do not assume a limitation remains valid after updating. Recheck the current release notes.

---

## 36. Tester Conduct

Alpha testers are expected to:

- Test in good faith
- Provide accurate reports
- Avoid intentionally disrupting USAFC services
- Avoid sharing private builds without permission
- Avoid publishing restricted source code
- Avoid redistributing installers
- Protect credentials
- Respect private communications
- Follow USA Flight Club rules
- Clearly distinguish concept features from implemented features

Access to alpha builds may be revoked for misuse, unauthorized redistribution, security violations, or abuse of USAFC services.

---

## 37. Alpha Completion Goals

A feature is not considered ready merely because it appears visually complete.

Before moving toward beta, critical systems should demonstrate:

- Reliable startup
- Reliable login
- Stable API connection
- Stable SimConnect connection
- Correct telemetry
- Correct phase tracking
- Correct flight completion
- Reliable PIREP submission
- Controlled retry behavior
- No duplicate submissions
- Stable live-map updates
- Stable flightboard updates
- Safe audio-device handling
- Safe shutdown
- Protected credentials
- Useful error messages
- Repeatable installation
- Acceptable performance

---

## 38. Official Links

- **USA Flight Club:** [https://usaflightclub.net](https://usaflightclub.net)
- **USAFCACARS Live Map:** [https://usaflightclub.net/usafcacars/live](https://usaflightclub.net/usafcacars/live)
- **Official Downloads:** [https://usaflightclub.net/downloads](https://usaflightclub.net/downloads)
- **Latest GitHub Release:** [View latest release](../../releases/latest)
- **Issue Tracker:** [View issues](../../issues)

---

## 39. Final Reminder

USAFCACARS is proprietary software in active alpha development.

Alpha access is an opportunity to help shape the application, not a guarantee of stability, completion, compatibility, or continued availability.

Test carefully, document clearly, protect private information, and always consult the release notes for the exact status of the build being tested.

```text
Copyright © 2026 USA Flight Club.
All rights reserved.
```
