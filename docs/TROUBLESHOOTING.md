# USAFCACARS Troubleshooting Guide

**Last updated:** August 11, 2026
**Current documented release:** 1.0.16 Alpha
**Software status:** Proprietary software in active alpha development

This guide provides practical troubleshooting steps for the USAFCACARS Windows
desktop application and its connected USA Flight Club services.

Official USA Flight Club website:

[https://usaflightclub.net](https://usaflightclub.net)

Official downloads:

[https://usaflightclub.net/downloads](https://usaflightclub.net/downloads)

Official USAFCACARS live map:

[https://usaflightclub.net/usafcacars/live](https://usaflightclub.net/usafcacars/live)

> [!IMPORTANT]
> USAFCACARS is currently in active alpha development.
>
> Some controls may be incomplete, some integrations may be experimental, and
> some concept features may not yet be available in the current build.
>
> Always read the release notes before troubleshooting a feature.

> [!CAUTION]
> Do not repeatedly press **Start Flight**, **Finish Flight**, **Cancel Flight**,
> or similar operational buttons while the application appears delayed.
>
> Repeated actions may create duplicate requests or interfere with the active
> flight session.

---

# 1. Quick Troubleshooting Checklist

Before beginning detailed troubleshooting:

1. Confirm the installed USAFCACARS version.
2. Read the release notes for that version.
3. Confirm the feature is implemented in the current alpha build.
4. Restart USAFCACARS.
5. Restart Microsoft Flight Simulator if the problem is simulator-related.
6. Confirm internet access.
7. Confirm the USA Flight Club website loads.
8. Confirm no stale USAFCACARS process remains in Task Manager.
9. Confirm required runtimes are installed.
10. Confirm the correct simulator and aircraft are loaded.
11. Confirm the correct microphone and speaker devices are selected.
12. Preserve useful logs before reinstalling or resetting settings.
13. Reproduce the issue one more time.
14. Record the exact error message.
15. Submit a sanitized support report if the issue remains.

---

# 2. Identify the Installed Version

The application version may appear in:

- The title bar;
- Settings;
- About;
- Help & Support;
- The login screen;
- The installer entry in Windows Settings; or
- The executable file properties.

To inspect the executable:

1. Open the USAFCACARS installation folder.
2. Right-click the main executable.
3. Choose **Properties**.
4. Open the **Details** tab.
5. Review **File version** and **Product version**.

Include the exact version in every support report.

Example:

```text
USAFCACARS 1.0.4 Alpha
```

---

# 3. Locate the Installation Folder

The exact folder depends on the installer.

Possible locations include:

```text
C:\Users\<username>\AppData\Local\Programs\USAFCACARS
```

```text
C:\Program Files\USAFCACARS
```

Portable builds may be located anywhere the user extracted them.

To find the installed application:

1. Open the Start menu.
2. Search for **USAFCACARS**.
3. Right-click the result.
4. Choose **Open file location**.
5. Right-click the shortcut.
6. Choose **Open file location** again when necessary.

Do not move only the executable to another folder. USAFCACARS may require
adjacent DLLs, native libraries, resources, and configuration files.

---

# 4. Locate Logs and Settings

The exact location may vary by build.

Common locations include:

```text
%LOCALAPPDATA%\USAFCACARS
```

```text
%APPDATA%\USAFCACARS
```

```text
Documents\USAFCACARS
```

Portable builds may store settings or logs inside the application folder.

To inspect `%LOCALAPPDATA%`:

1. Press `Win + R`.
2. Enter:

```text
%LOCALAPPDATA%
```

3. Search for:

```text
USAFCACARS
```

Before sharing logs, remove:

- Passwords;
- Full authentication tokens;
- API credentials;
- Private messages;
- Private voice information;
- Internal server paths where unnecessary;
- Email addresses where not required; and
- Unrelated personal information.

---

# 5. Application Will Not Start

## Symptoms

- Nothing happens after launching;
- The splash screen disappears;
- The application closes immediately;
- A .NET error appears;
- A DLL error appears;
- A Windows error dialog appears;
- The application remains visible only in Task Manager; or
- A blank window appears.

## Steps

### Step 1: Check for a stale process

Open Task Manager and end any process named similar to:

```text
USAFCACARS
USAFCACARS.Client
USAFCACARS.Updater
USAFCACARS.Sim
```

Then launch the application again.

### Step 2: Restart Windows

A restart clears:

- Locked DLLs;
- Stale WebView2 processes;
- Audio-device locks;
- Simulator connection remnants;
- Failed update processes; and
- Pending runtime installation changes.

### Step 3: Verify the package

If the application was recently installed or updated, verify the release
checksum again.

PowerShell example:

```powershell
Get-FileHash .\USAFCACARS-Setup-1.0.4.exe -Algorithm SHA256
```

### Step 4: Confirm the .NET Desktop Runtime

Run:

```powershell
dotnet --list-runtimes
```

If the required runtime is missing, install the runtime listed in the release
notes.

### Step 5: Confirm WebView2 Runtime

Open:

```text
Windows Settings → Apps → Installed apps
```

Search for:

```text
Microsoft Edge WebView2 Runtime
```

### Step 6: Review Windows Event Viewer

Open:

```text
Event Viewer → Windows Logs → Application
```

Look for entries involving:

```text
USAFCACARS
.NET Runtime
Application Error
WebView2
```

### Step 7: Review application logs

Preserve the relevant log before reinstalling.

### Step 8: Test a clean portable build

When available, extract the portable build into a new folder and test it
without copying old settings.

---

# 6. Application Opens to a Blank or Black Window

## Possible causes

- WebView2 Runtime missing or damaged;
- Corrupt WebView2 cache;
- GPU rendering issue;
- Broken application resources;
- Interrupted installation;
- Invalid saved layout;
- Off-screen or zero-sized panel;
- Web content blocked by firewall, proxy, VPN, or DNS;
- Application startup exception.

## Steps

1. Confirm WebView2 Runtime is installed.
2. Restart Windows.
3. Reset the Workspace Manager layout.
4. Temporarily disconnect extra monitors.
5. Reopen USAFCACARS.
6. Test with Windows scaling set to a common value such as 100% or 125%.
7. Disable only the affected panel and reopen it.
8. Check the application log.
9. Check Event Viewer.
10. Repair or reinstall WebView2.
11. Test a clean portable build.

Do not permanently disable security software to test this issue.

---

# 7. Application Freezes or Becomes Unresponsive

## Common causes

- Blocking network request;
- Slow API response;
- WebView2 page load;
- Repeated map refresh;
- Flightboard animation overload;
- Large chart or weather layer;
- Audio-device lock;
- SimConnect reconnect loop;
- Excessive logging;
- Corrupt workspace layout;
- Third-party provider outage.

## Steps

1. Wait briefly to confirm whether the application recovers.
2. Record which panel was open.
3. Record whether MSFS was running.
4. Open Task Manager.
5. Record CPU and memory use.
6. Close detached windows where possible.
7. Avoid repeatedly clicking controls.
8. End the process only after preserving evidence.
9. Restart USAFCACARS.
10. Reopen one feature at a time.
11. Test whether a specific panel causes the freeze.
12. Submit a report with the affected panel and timing.

---

# 8. High CPU or Memory Usage

## Check

Open Task Manager and observe:

- USAFCACARS CPU;
- USAFCACARS memory;
- WebView2 processes;
- GPU usage;
- Network use;
- Disk use.

## Common causes

- Multiple WebView2 tabs;
- Duplicate detached windows;
- Map animation;
- Flightboard animation;
- Weather layers;
- Repeated telemetry retry;
- Audio capture remaining active;
- Duplicate timers;
- Large route or traffic datasets;
- Corrupt workspace restore;
- Logs growing rapidly.

## Steps

1. Close unused Horizon Explorer tabs.
2. Close detached panels.
3. Turn off heavy map layers.
4. Close the Flightboard.
5. Stop microphone testing.
6. Disconnect from unused voice rooms.
7. Restart the application.
8. Confirm no stale process remains.
9. Reopen features one at a time.
10. Report the feature that causes the increase.

---

# 9. Login Fails

## Invalid credentials

Symptoms:

- The application reports invalid username, email, pilot ID, or password.

Steps:

1. Confirm Caps Lock is off.
2. Confirm the correct USA Flight Club account.
3. Test login on the official website.
4. Confirm the account is active.
5. Avoid repeated failed attempts.
6. Submit account-specific details privately.

## Server unavailable

Symptoms:

- Timeout;
- Connection refused;
- DNS failure;
- TLS or certificate error;
- Server unavailable message.

Steps:

1. Open [https://usaflightclub.net](https://usaflightclub.net).
2. Confirm internet access.
3. Disable only a temporary VPN or proxy for testing when safe.
4. Confirm Windows date and time.
5. Confirm the application uses the production API.
6. Check firewall or security software.
7. Try again later if the site is under maintenance.

## Login succeeds but dashboard does not load

1. Confirm the pilot profile endpoint responds.
2. Check the application log.
3. Log out and sign in again.
4. Confirm the application version.
5. Confirm no mandatory update is required.
6. Submit a sanitized support request.

---

# 10. Application Keeps Logging Out

## Possible causes

- Expired token;
- Revoked token;
- Clock mismatch;
- Server session reset;
- API compatibility mismatch;
- Corrupt local authentication state;
- Application update;
- Account authorization change.

## Steps

1. Confirm Windows date, time, and timezone.
2. Log out manually.
3. Close USAFCACARS.
4. Restart Windows.
5. Log in again.
6. Confirm the installed version.
7. Check whether a server or mandatory update occurred.
8. Avoid manually editing token files.
9. Submit private support if the issue continues.

---

# 11. Pilot Profile Is Missing or Incorrect

## Symptoms

- Wrong pilot name;
- Missing avatar;
- Missing rank;
- Missing airline logo;
- Wrong callsign;
- Old statistics;
- Broken image icon;
- Profile remains empty.

## Steps

1. Refresh the profile.
2. Log out and sign in again.
3. Confirm the website profile is correct.
4. Confirm the application is using the correct account.
5. Check whether the image URL is reachable.
6. Confirm no cached profile from another account remains.
7. Submit profile corrections privately.

Missing optional images should use a fallback. Broken-image icons should be
reported as a defect.

---

# 12. Bids or Flights Do Not Load

## Steps

1. Confirm server connection.
2. Confirm the pilot has active bids.
3. Refresh the list.
4. Switch tabs and return.
5. Log out and sign in again.
6. Confirm the website shows the same bids.
7. Check the application log.
8. Confirm the installed version is compatible with the API.
9. Submit the affected flight numbers privately when necessary.

---

# 13. Flight Search Does Not Work

## Check

- Search term;
- Airline;
- Departure airport;
- Arrival airport;
- Aircraft;
- Route;
- Date or schedule filters;
- Three-character identifiers.

## Steps

1. Clear all filters.
2. Search only by flight number.
3. Search only by airport.
4. Test a four-character airport.
5. Test a valid three-character airport such as:

```text
81R
```

6. Confirm the application does not automatically change `81R` to `K81R`.
7. Confirm the website search behavior.
8. Report the exact search and expected result.

---

# 14. Briefing Does Not Update

## Symptoms

- Previous route remains;
- Wrong departure or arrival;
- Stale weather;
- Old charts;
- Wrong aircraft;
- Blank map;
- Missing route.

## Steps

1. Select another flight.
2. Wait for the briefing to finish loading.
3. Return to the intended flight.
4. Refresh the briefing.
5. Confirm departure and arrival in the flight list.
6. Close and reopen the briefing panel.
7. Check the application log.
8. Report whether only one section remains stale.

---

# 15. Briefing Map Is Blank

## Steps

1. Confirm WebView2 Runtime.
2. Confirm internet access.
3. Open the live-map URL in a normal browser.
4. Check whether the route data exists.
5. Confirm departure and arrival coordinates.
6. Reload the briefing panel.
7. Select another flight.
8. Check firewall, proxy, VPN, and DNS.
9. Review application logs.
10. Review WebView2 or browser-console errors where available.

---

# 16. Three-Character Airport Does Not Work

USAFCACARS must support valid identifiers such as:

```text
81R
```

Do not automatically convert every United States airport into a `K`-prefixed
identifier.

If a three-character airport fails:

1. Record the exact identifier.
2. Confirm it exists in the USAFC flight data.
3. Confirm the website displays it.
4. Test airport information.
5. Test charts.
6. Test weather.
7. Test route drawing.
8. Report which feature fails.

---

# 17. SimConnect Does Not Connect

## Recommended startup order

1. Start Microsoft Flight Simulator.
2. Load fully into an aircraft.
3. Wait until the cockpit is interactive.
4. Start USAFCACARS.
5. Sign in.
6. Connect to the simulator.

## Steps

1. Confirm MSFS 2020 or MSFS 2024 support for the build.
2. Confirm the simulator is fully loaded.
3. Confirm USAFCACARS and MSFS run at compatible privilege levels.
4. Restart USAFCACARS.
5. Restart MSFS.
6. Test a default aircraft.
7. Confirm SimConnect dependencies.
8. Check the application log.
9. Confirm no duplicate USAFCACARS process.
10. Confirm the build architecture is 64-bit.

Do not copy unverified SimConnect DLLs into the application folder.

---

# 18. Simulator Connects but Telemetry Does Not Update

## Check

- Position;
- Altitude;
- Speed;
- Heading;
- Vertical speed;
- On-ground state;
- Fuel;
- Gear;
- Flaps;
- Engine state.

## Steps

1. Move the aircraft slightly.
2. Confirm the simulator is not paused.
3. Confirm the aircraft is not in slew mode.
4. Test a default aircraft.
5. Compare with the add-on aircraft.
6. Confirm the active flight session.
7. Confirm simulator status says connected.
8. Confirm API status separately.
9. Review the telemetry log.
10. Report the exact variables that remain unchanged.

---

# 19. Complex Add-On Aircraft Does Not Work

Some add-on aircraft do not expose all systems through standard SimConnect
variables and events.

Possible requirements include:

- Local variables;
- HTML variables;
- WASM bridge;
- Custom events;
- Aircraft-specific adapter;
- Vendor SDK;
- Custom data definitions.

When reporting:

- Aircraft name;
- Developer;
- Aircraft version;
- Simulator version;
- Failed control or instrument;
- Expected result;
- Actual result;
- Whether a default aircraft works.

---

# 20. Flight Will Not Start

## Steps

1. Confirm a valid bid is selected.
2. Confirm the selected flight is still available.
3. Confirm the correct account.
4. Confirm server connection.
5. Confirm no other active flight session.
6. Confirm the aircraft assignment.
7. Confirm the simulator connection.
8. Press **Start Flight** once.
9. Wait for the result.
10. Record the exact error.
11. Check whether a session was created despite the error.
12. Avoid repeatedly pressing Start.

---

# 21. Duplicate Active Flight Session

## Symptoms

- App says another session is active;
- Flight appears twice;
- Start is blocked;
- Old flight remains on the live map.

## Steps

1. Confirm whether another USAFCACARS window is open.
2. Confirm whether another computer is logged in.
3. Check the live map.
4. Check the website for an active flight.
5. Use Cancel only when appropriate.
6. Do not create another session.
7. Submit private support if the stale session cannot be cleared.

---

# 22. Flight Phase Is Wrong

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

When reporting, include:

- Current altitude;
- Ground speed;
- Vertical speed;
- On-ground state;
- Gear state;
- Engine state;
- Parking brake;
- Distance from departure or arrival;
- Expected phase;
- Actual phase.

Report rapid switching, especially when phases oscillate repeatedly.

---

# 23. Landing Detected Incorrectly

## Possible causes

- Brief runway bounce;
- Incorrect on-ground variable;
- High descent rate;
- Touch-and-go;
- Add-on aircraft variable difference;
- Simulator pause;
- Phase threshold too sensitive.

## Steps

1. Record the aircraft and airport.
2. Record landing rate.
3. Record whether the aircraft bounced.
4. Record gear and on-ground state.
5. Record whether the flight entered Taxi In.
6. Preserve the relevant log section.
7. Report the exact timing.

---

# 24. Flight Will Not Finish

## Steps

1. Confirm the correct active flight.
2. Confirm the aircraft is on the ground.
3. Confirm the final phase.
4. Confirm engines are shut down where required.
5. Confirm the parking brake where required.
6. Confirm server connection.
7. Press **Finish Flight** once.
8. Wait for the response.
9. Check whether a PIREP was created.
10. Do not repeatedly submit.
11. Preserve logs before closing.

---

# 25. Duplicate PIREP or Finish Request

If a duplicate is suspected:

1. Stop pressing Finish.
2. Check the website.
3. Record all PIREP identifiers.
4. Preserve logs.
5. Record the exact time.
6. Submit private support.
7. Do not delete records yourself unless authorized.

---

# 26. Flight Will Not Cancel

## Steps

1. Confirm the active session.
2. Confirm server connection.
3. Press Cancel once.
4. Confirm the live aircraft disappears.
5. Confirm no completed PIREP was created.
6. Confirm the bid behavior matches USAFC rules.
7. Preserve the error and logs.
8. Submit support if the session remains active.

---

# 27. Live Map Does Not Load

Official live map:

[https://usaflightclub.net/usafcacars/live](https://usaflightclub.net/usafcacars/live)

## Steps

1. Open the URL in a standard browser.
2. Confirm the website is reachable.
3. Confirm WebView2 Runtime.
4. Confirm internet access.
5. Disable only temporary VPN or proxy routing for testing.
6. Check browser-console errors where available.
7. Reload the panel.
8. Restart USAFCACARS.
9. Test another browser.
10. Report whether the problem affects the public page, desktop app, or both.

---

# 28. Aircraft Does Not Appear on Live Map

## Steps

1. Confirm the flight started.
2. Confirm telemetry updates.
3. Confirm API connection.
4. Confirm live endpoint response where available.
5. Confirm the map source includes USAFC.
6. Confirm filters.
7. Confirm the aircraft is not hidden by another layer.
8. Refresh the map.
9. Check whether the flight appears on Flightboard.
10. Preserve logs.

---

# 29. Aircraft Jumps on the Map

## Possible causes

- Slow update interval;
- Missing interpolation;
- Stale timestamp;
- Network delay;
- Duplicate aircraft records;
- Position resets;
- Simulator teleport;
- Add-on data issue.

## Report

Include:

- Flight number;
- Aircraft;
- Approximate time;
- Update interval;
- Whether heading also jumps;
- Whether the trail remains correct;
- Whether the simulator position was smooth.

---

# 30. Departure or Arrival Is Missing

## Steps

1. Confirm flight data contains both airports.
2. Confirm coordinates exist.
3. Confirm the route layer is enabled.
4. Zoom out.
5. Refresh the map.
6. Select the aircraft.
7. Check whether only the airport marker is missing.
8. Report the route and identifiers.

Both departure and arrival should remain available even when the aircraft is
currently at one of them.

---

# 31. Route Does Not Draw

## Steps

1. Confirm the selected flight has a route.
2. Confirm departure and arrival coordinates.
3. Confirm the route layer is enabled.
4. Refresh the map.
5. Select another flight.
6. Check whether the route appears on the briefing map.
7. Review browser-console errors.
8. Report the route string.

---

# 32. Weather Layer Looks Like Blocks

## Possible causes

- Incorrect tile transparency;
- Wrong tile size;
- Provider seam;
- Raster overlay scaling;
- Incorrect opacity;
- Projection mismatch;
- Cached bad tiles;
- Provider outage.

## Steps

1. Record the exact layer.
2. Record map zoom.
3. Record region.
4. Disable and re-enable the layer.
5. Clear only the affected cache if supported.
6. Compare the public live map and desktop map.
7. Capture a screenshot.
8. Report the approximate time.

---

# 33. Flightboard Does Not Load

## Steps

1. Confirm live data exists.
2. Confirm the correct source.
3. Switch between Current, Departures, and Arrivals.
4. Reset zoom to 100%.
5. Refresh the panel.
6. Close and reopen Flightboard.
7. Check browser-console or application logs.
8. Confirm rows are not hidden below the viewport.

---

# 34. Flightboard Rows Flash or Blink

Expected behavior:

- Only changed characters animate;
- Unchanged values remain stable;
- Entire rows do not flash;
- Animation stops after the new value settles.

When reporting:

- Board tab;
- Traffic source;
- Number of rows;
- Whether every row flashes;
- Whether only one cell changes;
- Whether the issue begins after refresh;
- CPU usage.

---

# 35. Flightboard Data Is Incorrect

Check:

- Phase;
- Status;
- Flight number;
- Departure;
- Arrival;
- Altitude;
- Speed;
- Heading;
- Aircraft;
- Registration;
- Pilot.

Compare with:

- Simulator;
- Live map;
- Website;
- API data where available.

Report which source is correct and which is wrong.

---

# 36. Weather Data Is Missing

## Steps

1. Confirm internet access.
2. Confirm the airport identifier.
3. Confirm the weather provider is available.
4. Refresh the weather panel.
5. Test another airport.
6. Test METAR separately from graphical layers.
7. Check release notes for provider limitations.
8. Report the airport, layer, and time.

---

# 37. Chart Does Not Open

## Steps

1. Confirm the airport identifier.
2. Confirm charts exist for the airport.
3. Confirm the chart library path.
4. Refresh chart thumbnails.
5. Close and reopen the chart panel.
6. Test another chart.
7. Test another airport.
8. Confirm WebView2 or image viewer support.
9. Report the chart name.

Do not upload restricted chart files publicly.

---

# 38. Wrong Chart Remains After Airport Change

## Steps

1. Select the new airport.
2. Wait for thumbnails to refresh.
3. Close the old chart.
4. Reopen the chart viewer.
5. Confirm the airport label.
6. Report whether only the full viewer or thumbnails remain stale.

---

# 39. Voice Communications Does Not Connect

## Steps

1. Confirm internet access.
2. Confirm the pilot is authenticated.
3. Confirm room authorization.
4. Confirm the correct room or frequency.
5. Confirm audio devices.
6. Confirm firewall access.
7. Disconnect and reconnect.
8. Restart USAFCACARS.
9. Check application logs.
10. Submit private support for protected-room problems.

---

# 40. Microphone Is Not Detected

## Steps

1. Open Windows Sound settings.
2. Confirm the microphone appears.
3. Test the microphone in Windows.
4. Confirm microphone privacy permission.
5. Close other applications using exclusive mode.
6. Reconnect the device.
7. Restart USAFCACARS.
8. Reopen Voice & Radio Settings.
9. Select the microphone again.
10. Check the input level.

---

# 41. Microphone Test Shows Input but Has No Playback

## Steps

1. Confirm the selected output device.
2. Confirm speaker volume.
3. Confirm application communications volume.
4. Stop active voice transmission.
5. Run the microphone test again.
6. Confirm the test is local.
7. Confirm the test buffer starts and stops.
8. Test another output device.
9. Restart the application.
10. Report whether the level meter moved.

---

# 42. Speaker Test Is Silent

## Steps

1. Confirm the selected speaker.
2. Confirm Windows output.
3. Confirm application volume.
4. Test Windows audio.
5. Test another output device.
6. Close applications that may lock the device.
7. Reopen Voice & Radio Settings.
8. Run the speaker test.
9. Restart USAFCACARS.
10. Report the device name and audio format where available.

---

# 43. Push-to-Talk Does Not Work

## Check

- PTT key assignment;
- Global PTT registration;
- Mute state;
- Active room;
- Microphone selection;
- Windows permissions;
- Key conflict;
- Administrator privilege mismatch; and
- Discord mute-shortcut configuration when enabled.

## Steps

1. Confirm the PTT assignment in Communications Settings.
2. Confirm the live microphone spectrum and MIC meter move.
3. Confirm mute is off and an active room is joined.
4. Hold the key rather than tapping it; TX should illuminate for the full hold.
5. Put another application in focus and confirm global PTT still activates TX.
6. Test a different key if another application reserves the current assignment.
7. Run USAFCACARS and the simulator at compatible privilege levels. A lower-privilege application cannot always capture keys over an elevated application.
8. If Discord coordination is enabled, keep Discord's mute shortcut set to `Ctrl+Shift+M` and confirm the setting is enabled in USAFCACARS.
9. Restart USAFCACARS to reinstall the global keyboard hook.
10. Record whether the on-screen PTT button works while only the global shortcut fails.

---

# 44. Mute or Deafen Does Not Work

## Steps

1. Confirm the displayed state.
2. Toggle once.
3. Wait for the server state.
4. Confirm room membership.
5. Test with an authorized participant.
6. Disconnect and reconnect.
7. Preserve logs.
8. Report immediately if audio transmits while muted.

Transmission while muted is a security-sensitive defect and should be
reported privately when it exposes communications.

---

# 45. Communications Page Will Not Scroll

## Steps

1. Confirm the pointer is over the page.
2. Test mouse wheel.
3. Test scrollbar.
4. Test Page Up and Page Down.
5. Resize the window.
6. Test Windows scaling.
7. Reset the workspace.
8. Report the display size and scaling.

---

# 46. Horizon Explorer Is Blank

## Steps

1. Confirm WebView2 Runtime.
2. Confirm internet access.
3. Test the page in a normal browser.
4. Open a new Horizon tab.
5. Close the failed tab.
6. Restart Horizon Explorer.
7. Restart USAFCACARS.
8. Check firewall, proxy, VPN, and DNS.
9. Review WebView2 logs where available.

---

# 47. Horizon Explorer Tabs Duplicate or Do Not Close

## Steps

1. Close the affected tab once.
2. Wait for cleanup.
3. Confirm whether a detached window remains.
4. Check Task Manager for excessive WebView2 processes.
5. Restart USAFCACARS.
6. Reproduce with one page.
7. Report the tab count and page.

---

# 48. Workspace Layout Does Not Save

## Steps

1. Confirm the application can write settings.
2. Save the layout.
3. Close USAFCACARS normally.
4. Reopen it.
5. Confirm the layout name.
6. Check settings-file permissions.
7. Test a new simple layout.
8. Report whether only window positions or panel types fail.

---

# 49. Window Opens Off-Screen

## Steps

1. Use Workspace Manager Reset.
2. Press `Win + Shift + Arrow`.
3. Reconnect the previous monitor.
4. Temporarily set all monitors to the same scaling.
5. Remove the saved layout only if instructed.
6. Restart USAFCACARS.

The application should recover windows to an available monitor.

---

# 50. Fullscreen Window Will Not Restore

## Steps

1. Use the app's fullscreen toggle.
2. Press `Alt + Space`.
3. Choose **Restore**.
4. Press `Win + Down Arrow`.
5. Reset the workspace.
6. Restart USAFCACARS.
7. Report the panel and monitor.

---

# 51. Aircraft Control Does Not Operate a System

Aircraft Control depends on the simulator and aircraft.

## Steps

1. Confirm the correct aircraft is loaded.
2. Confirm SimConnect is connected.
3. Confirm the control is enabled.
4. Confirm the control is not read-only.
5. Test a default aircraft.
6. Test one system at a time.
7. Confirm the simulator visually changes.
8. Confirm the app state updates afterward.
9. Record the aircraft and add-on version.

Potential systems include:

- Lights;
- Gear;
- Flaps;
- Spoilers;
- Trim;
- Brakes;
- Doors;
- Seatbelt sign;
- No-smoking sign;
- Electrical systems;
- APU;
- Radios;
- Transponder.

---

# 52. Aircraft Control Changes the Wrong System

Stop testing immediately when a command affects an unexpected control.

Record:

- Aircraft;
- Add-on version;
- Simulator;
- Control pressed;
- Expected result;
- Actual result;
- Whether the state changed in the app;
- Whether the issue repeats.

Do not continue issuing commands until the behavior is understood.

---

# 53. Passenger Operations Does Not Match the Aircraft

Passenger Operations may be incomplete or unsupported in the current build.

## Check

- Aircraft cabin profile;
- Seating configuration;
- Class layout;
- Door mapping;
- Seat count;
- Payload;
- Service options.

## Steps

1. Confirm the correct aircraft profile.
2. Reload the aircraft.
3. Reset the cabin profile.
4. Compare with a default supported profile.
5. Report the aircraft and seat layout.

Do not enter real passenger personal information.

---

# 54. Music or Radio Does Not Play

## Steps

1. Confirm output device.
2. Confirm volume.
3. Confirm the correct tab.
4. Confirm the file or stream is available.
5. Test a local file.
6. Test a different stream.
7. Confirm internet access.
8. Check whether voice communications are using the device.
9. Restart playback.
10. Restart USAFCACARS.

---

# 55. Music Interferes with Voice Communications

## Steps

1. Lower music volume.
2. Confirm separate audio controls.
3. Confirm the communications output device.
4. Confirm ducking behavior where enabled.
5. Pause music.
6. Test voice again.
7. Report whether the problem affects microphone, speaker, or both.

---

# 56. Community Hub Does Not Load

## Steps

1. Confirm login.
2. Confirm internet access.
3. Confirm the feature is enabled.
4. Refresh the panel.
5. Check the website.
6. Confirm any Discord or external connection.
7. Avoid posting private data publicly.
8. Submit private support for account-specific problems.

---

# 57. Help and Support Panel Does Not Load

## Steps

1. Confirm internet access.
2. Confirm WebView2 Runtime.
3. Open the official website in a browser.
4. Reload the panel.
5. Restart USAFCACARS.
6. Use the website directly when the panel is unavailable.

---

# 58. Update Check Fails

## Steps

1. Confirm internet access.
2. Confirm the official website.
3. Confirm the application version.
4. Confirm the release channel.
5. Check firewall or proxy.
6. Open the official downloads page.
7. Download manually when necessary.
8. Verify the checksum.
9. Do not use an unofficial updater.

---

# 59. Update Installs but Version Does Not Change

## Steps

1. Close all USAFCACARS processes.
2. Confirm the shortcut points to the correct folder.
3. Open the executable properties.
4. Confirm the file version.
5. Check for multiple installations.
6. Remove obsolete shortcuts.
7. Reinstall the intended version.
8. Preserve logs and settings.

---

# 60. Antivirus Flags USAFCACARS

Do not ignore the warning automatically.

## Steps

1. Confirm the source.
2. Verify the checksum.
3. Record the exact detection name.
4. Scan the package again.
5. Check whether the file is newly released and unsigned.
6. Submit the file to the antivirus vendor where appropriate.
7. Contact USA Flight Club support.
8. Wait for confirmation before adding an exclusion.

Do not disable antivirus globally.

---

# 61. Firewall Blocks USAFCACARS

USAFCACARS may require outbound access for:

- Authentication;
- API;
- Live map;
- Weather;
- Charts;
- Voice communications;
- Community;
- Support;
- Downloads;
- Updates.

Allow only the official executable.

Do not open inbound ports unless explicitly required and documented.

---

# 62. TLS or Certificate Error

## Steps

1. Confirm Windows date and time.
2. Confirm the official URL.
3. Confirm no captive portal.
4. Test in a browser.
5. Disable only a temporary proxy or VPN for testing.
6. Check corporate or antivirus TLS inspection.
7. Update Windows certificates.
8. Do not disable certificate validation.
9. Submit support if the official site certificate fails.

---

# 63. DNS or Connection Timeout

## Steps

1. Confirm other websites load.
2. Test the official USAFC website.
3. Restart the router.
4. Flush DNS:

```cmd
ipconfig /flushdns
```

5. Restart Windows.
6. Test without a VPN.
7. Check firewall.
8. Try again later if the server is under maintenance.

---

# 64. Application Does Not Close Completely

## Symptoms

- Process remains in Task Manager;
- Audio continues;
- WebView2 remains active;
- SimConnect remains connected;
- Update cannot replace files;
- Build reports a locked DLL.

## Steps

1. Close all detached windows.
2. Stop microphone test.
3. Stop music and radio.
4. Leave voice rooms.
5. Close Horizon Explorer tabs.
6. Close USAFCACARS.
7. Wait briefly.
8. End stale processes in Task Manager.
9. Restart Windows if files remain locked.
10. Report which feature was active.

---

# 65. DLL or File Is Locked During Update or Build

A previously observed locked assembly may include:

```text
USAFCACARS.Sim.dll
```

## Steps

1. Close USAFCACARS.
2. Close all detached windows.
3. End all USAFCACARS processes.
4. Close Visual Studio or Codex build sessions using the files.
5. Restart Windows if necessary.
6. Rebuild or reinstall.
7. Do not delete random DLLs manually.

---

# 66. Settings Are Corrupt

## Symptoms

- App crashes on startup;
- Window is invisible;
- Layout will not load;
- Device selection fails;
- Settings page is blank;
- Reinstall does not help.

## Steps

1. Back up the settings folder.
2. Close USAFCACARS.
3. Rename the settings folder, for example:

```text
USAFCACARS-backup
```

4. Launch the application.
5. Confirm a clean settings set is created.
6. Reconfigure manually.
7. Do not copy all old files back at once.
8. Report which file caused the issue where known.

---

# 67. Reinstallation Did Not Fix the Problem

Reinstallation may preserve:

- Settings;
- Cache;
- WebView data;
- Workspace layouts;
- Logs;
- Authentication state.

## Steps

1. Uninstall USAFCACARS.
2. Preserve logs.
3. Rename the local settings folder.
4. Restart Windows.
5. Reinstall from the official package.
6. Verify the checksum.
7. Test before restoring settings.

---

# 68. How to Perform a Clean Test

A clean test is useful when a problem may be caused by settings.

1. Close USAFCACARS.
2. Back up logs and settings.
3. Use a new portable-build folder.
4. Do not copy old settings.
5. Launch the clean build.
6. Sign in.
7. Configure only required items.
8. Reproduce the issue.
9. Compare with the installed build.

---

# 69. How to Capture a Useful Screenshot

Include:

- Entire affected panel;
- Version;
- Error message;
- Flight or airport identifier where relevant;
- Connection status;
- Relevant control state.

Exclude or redact:

- Password;
- Token;
- Email where unnecessary;
- Private chat;
- Private voice information;
- Administrator data.

---

# 70. How to Capture a Useful Screen Recording

Keep the recording short.

Show:

1. Starting state;
2. Exact steps;
3. Failure;
4. Result after failure.

Do not record:

- Login password;
- Token;
- Private voice communications;
- Private pilot records;
- Security vulnerabilities.

---

# 71. How to Collect Windows Event Viewer Information

1. Open Event Viewer.
2. Go to:

```text
Windows Logs → Application
```

3. Reproduce the issue.
4. Refresh the log.
5. Find the relevant error.
6. Copy only the useful details.
7. Redact sensitive paths or data where necessary.

Useful fields:

- Faulting application;
- Faulting module;
- Exception code;
- Timestamp;
- .NET Runtime message.

---

# 72. How to Report a Bug

Use:

[SUPPORT.md](../SUPPORT.md)

Include:

- Version;
- Environment;
- Steps;
- Expected result;
- Actual result;
- Frequency;
- Error text;
- Sanitized evidence.

---

# 73. How to Report a Security Issue

Do not use a public GitHub issue.

Follow:

[SECURITY.md](../SECURITY.md)

Use the private request title:

```text
USAFCACARS Security Report
```

---

# 74. How to Submit a Privacy Request

Follow:

[PRIVACY.md](../PRIVACY.md)

Use the private request title:

```text
USAFCACARS Privacy Request
```

---

# 75. Troubleshooting Report Template

```markdown
## Summary

Describe the problem clearly.

## USAFCACARS Version

Example: 1.0.4 Alpha

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

## Feature

Dashboard / Login / Flights / Briefing / SimConnect / Tracking /
Live Map / Flightboard / Weather / Charts / Voice Communications /
ATC / TRACON / Flight Strips / Taxi Management / Horizon Explorer /
Workspace Manager / Aircraft Control / Passenger Operations /
Music & Radio / Community / Support / Update / Other

## Steps to Reproduce

1.
2.
3.
4.

## Expected Result

## Actual Result

## Frequency

Every time / Often / Occasionally / Once

## Exact Error Message

## Logs

Sanitized excerpt only.

## Screenshots or Video

Attach if useful.

## Workarounds Tried

## Privacy Confirmation

- [ ] I removed passwords, authentication tokens, API credentials, private
      communications, and sensitive personal data.
```

---

# 76. Related Documents

- [README](../README.md)
- [License](../LICENSE)
- [Changelog](../CHANGELOG.md)
- [Privacy Notice](../PRIVACY.md)
- [Security Policy](../SECURITY.md)
- [Support Guide](../SUPPORT.md)
- [Third-Party Notices](../THIRD_PARTY_NOTICES.md)
- [Installation Guide](INSTALLATION.md)
- [Alpha Testing Guide](ALPHA-TESTING.md)

---

# 77. Official Links

- **USA Flight Club:** [https://usaflightclub.net](https://usaflightclub.net)
- **Official Downloads:** [https://usaflightclub.net/downloads](https://usaflightclub.net/downloads)
- **USAFCACARS Live Map:** [https://usaflightclub.net/usafcacars/live](https://usaflightclub.net/usafcacars/live)
- **Latest GitHub Release:** [View latest release](../../../releases/latest)
- **GitHub Issues:** [View issues](../../../issues)
- **Installation Guide:** [INSTALLATION.md](INSTALLATION.md)
- **Alpha Testing Guide:** [ALPHA-TESTING.md](ALPHA-TESTING.md)

---

# 78. Final Reminder

USAFCACARS version 1.0.4 remains an alpha development release.

Preserve logs before resetting or reinstalling, avoid repeated operational
button presses, protect all credentials and private information, and always
confirm whether a feature is implemented in the current release before
treating its absence as a defect.

```text
Copyright © 2026 USA Flight Club.
All rights reserved.

USAFCACARS is proprietary software.
```
