# USAFCACARS-Releases
Public installer and automatic update packages for USA Flight Club ACARS. Source code is maintained privately.
<p align="center">
  <img
    src="assets/readme/usafcacars-hero.png"
    alt="USAFCACARS Desktop Flight Operations System"
    width="100%"
  >
</p>

<p align="center">
  <img
    src="assets/readme/usafc_acars.png"
    alt="Completed USAFCACARS Operations Center Concept"
    width="100%"
  >
</p>

<p align="center">
  <em>Concept preview of the completed USAFCACARS desktop flight operations platform.</em>
</p>

<h1 align="center">USAFCACARS</h1>

<p align="center">
  <strong>The official desktop flight operations and ACARS client for USA Flight Club.</strong>
</p>

<p align="center">
  Flight planning · Live tracking · SimConnect telemetry · Weather · Charts · Communications · ATC tools
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Windows%2010%20%7C%2011-1f6feb?style=for-the-badge&logo=windows" alt="Windows 10 and Windows 11">
  <img src="https://img.shields.io/badge/Simulator-MSFS%202020%20%7C%202024-263b5e?style=for-the-badge" alt="Microsoft Flight Simulator 2020 and 2024">
  <img src="https://img.shields.io/badge/Application-USAFCACARS-a00000?style=for-the-badge" alt="USAFCACARS">
  <img src="https://img.shields.io/badge/License-Proprietary-555555?style=for-the-badge" alt="Proprietary software">
</p>

<p align="center">
  <a href="../../releases/latest">
    <img src="https://img.shields.io/badge/DOWNLOAD-LATEST%20RELEASE-a00000?style=for-the-badge&logo=github" alt="Download the latest USAFCACARS release">
  </a>
  &nbsp;
  <a href="https://usaflightclub.net">
    <img src="https://img.shields.io/badge/VISIT-USA%20FLIGHT%20CLUB-263b5e?style=for-the-badge" alt="Visit USA Flight Club">
  </a>
</p>

---

## Welcome to USAFCACARS

**USAFCACARS** is the official desktop operations client for **USA Flight Club**.

It connects USA Flight Club pilots, Microsoft Flight Simulator, and the USAFC phpVMS platform through one integrated flight operations environment. Pilots can select assigned flights, review briefing information, connect to the simulator, transmit live aircraft data, follow flight progress, communicate with other members, and submit completed flight reports.

USAFCACARS is designed as more than a basic flight tracker. It brings together the tools a virtual airline pilot needs before, during, and after a flight while maintaining the distinctive USA Flight Club operations-center appearance.

> Feature availability may vary by release channel and application version. Review the release notes before installing or updating.

---

## Application Preview

<p align="center">
  <img
    src="assets/readme/dashboard.png"
    alt="USAFCACARS pilot dashboard"
    width="92%"
  >
</p>

<p align="center">
  <em>The USAFCACARS pilot dashboard brings flight selection, pilot information, weather, communications, and operational tools into one desktop application.</em>
</p>

<table>
  <tr>
    <td width="50%" align="center">
      <img src="assets/readme/live-map.png" alt="USAFCACARS live flight map" width="100%">
      <br>
      <strong>Live Flight Map</strong>
    </td>
    <td width="50%" align="center">
      <img src="assets/readme/flightboard.png" alt="USAFCACARS flightboard" width="100%">
      <br>
      <strong>Operations Flightboard</strong>
    </td>
  </tr>
  <tr>
    <td width="50%" align="center">
      <img src="assets/readme/comms.png" alt="USAFCACARS communications system" width="100%">
      <br>
      <strong>Voice Communications</strong>
    </td>
    <td width="50%" align="center">
      <img src="assets/readme/workspace-manager.png" alt="USAFCACARS workspace manager" width="100%">
      <br>
      <strong>Workspace Manager</strong>
    </td>
  </tr>
</table>

---

## Core Features

### Flight Operations

USAFCACARS connects directly to the USA Flight Club flight operations system.

Pilots can:

* Sign in using their USA Flight Club pilot account
* View available flights and current bids
* Review completed flights
* Search the USAFC flight schedule
* Select an assigned aircraft
* Review departure and arrival information
* Display the planned route
* Begin, track, cancel, and complete flights
* Submit flight data to the USAFC phpVMS system
* Review current flight status throughout the operation

### Live ACARS Tracking

USAFCACARS communicates with Microsoft Flight Simulator through SimConnect and sends active flight information to the USA Flight Club servers.

Tracked information may include:

* Aircraft position
* Altitude
* Ground speed
* Heading
* Vertical speed
* Flight phase
* On-ground state
* Route progress
* Fuel information
* Aircraft status
* Flight time
* Departure and arrival information
* Landing rate
* Final flight results

The client is designed to tolerate temporary communication interruptions and restore the live connection when possible.

### Intelligent Flight Phases

USAFCACARS follows the aircraft through the complete flight cycle.

Typical phases include:

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

Phase transitions are derived from simulator data and stabilized to reduce false or rapidly changing status updates.

### Pilot Dashboard

The pilot dashboard can display:

* Pilot avatar
* Pilot name
* USAFC pilot ID
* Callsign
* Airline or division
* Rank
* Current airport
* Local weather
* Current flight status
* Communications status
* Assigned flight
* Aircraft information
* Operational tools

### Briefing Map

The integrated briefing map provides a visual overview of the selected flight.

Depending on the selected flight and available data, it can display:

* Departure airport
* Arrival airport
* Planned route
* Airport markers
* Flight path
* Weather information
* Aircraft position
* Navigation information
* Airport charts

USAFCACARS supports both standard four-character airport identifiers and shorter identifiers such as `81R`.

---

## Live Map and Operations Center

<p align="center">
  <img
    src="assets/readme/operations-center.png"
    alt="USAFCACARS live map and operations center"
    width="92%"
  >
</p>

The USA Flight Club live map provides an operations-center view of active flights, pilots, routes, airports, and participating network traffic.

Map capabilities may include:

* Active USAFC aircraft
* Departure and arrival airports
* Planned routes
* Traveled flight trails
* Aircraft information
* Pilot information
* Flight selection
* Airport details
* Chart viewing
* Weather overlays
* Airspace layers
* Navigation layers
* ATC coverage
* VATSIM traffic
* IVAO traffic
* ADS-B traffic
* FAA aviation layers
* Pop-out panels
* Multiple map workspaces
* Layer-state profiles
* Zulu time display
* Range and compass tools

The map uses the established USA Flight Club dark-glass and radar-inspired visual design.

---

## Flightboard

The USAFCACARS flightboard presents current aviation activity in a split-flap-inspired operations display.

Available board views include:

```text
CURRENT
DEPARTURES
ARRIVALS
```

Available sources may include:

```text
USAFC
ADS-B
VATSIM
IVAO
```

Flightboard information can include:

| Column            | Information                      |
| ----------------- | -------------------------------- |
| Phase             | Current operational flight phase |
| Status            | Current board status             |
| Flight            | Airline and flight number        |
| Departure         | Departure airport                |
| Arrival           | Arrival airport                  |
| Departure Time    | Scheduled or actual departure    |
| Estimated Arrival | Calculated arrival time          |
| Altitude          | Current aircraft altitude        |
| Speed             | Current ground speed             |
| Heading           | Current heading                  |
| Aircraft          | Type and registration            |
| Pilot             | Pilot or network callsign        |

Changed characters animate independently to reproduce the appearance of a mechanical airport flight-information board without continuously flashing unchanged information.

---

## Weather

USAFCACARS provides integrated aviation-weather tools for flight planning and live operations.

Weather capabilities may include:

* Current airport weather
* METAR information
* TAF information
* Weather radar
* Cloud coverage
* Wind
* Temperature
* Pressure
* Precipitation
* Visibility
* Lightning
* Weather thumbnails
* Selectable map overlays
* Saved weather-layer profiles

Weather data availability depends on the services configured for the active release.

---

## Airport Information and Charts

Airport information is available directly through the application and map system.

Available data may include:

* Airport name
* Airport identifier
* Location
* Coordinates
* Elevation
* Runways
* Radio frequencies
* Current weather
* Navigation information
* Airport charts

The chart viewer supports:

* Chart thumbnails
* In-application viewing
* Pop-out chart windows
* Zoom controls
* Zoom percentage
* Reset-to-original-size controls
* Airport-specific chart filtering

---

## Voice Communications

<p align="center">
  <img
    src="assets/readme/voice-communications.png"
    alt="USAFCACARS voice and radio communications"
    width="88%"
  >
</p>

USAFCACARS includes an integrated communications system designed for USA Flight Club operations.

Communication options may include:

* Airport frequency rooms
* UNICOM
* Private crew rooms
* Open group rooms
* Push-to-talk
* Microphone mute
* Speaker deafen
* Microphone device selection
* Speaker device selection
* Microphone level monitoring
* Microphone playback test
* Speaker test
* Active frequency display
* Room participant information
* Automatic room transitions
* On Comms pilot status

Private rooms and protected communications require valid USAFC authorization.

---

## TRACON and ATC Tools

The integrated TRACON and ATC tools provide a radar-inspired view of current operations.

Capabilities may include:

* Selectable aircraft targets
* Pilot information panels
* Aircraft information panels
* Flight strips
* Arrival and departure activity
* Scope range controls
* Scope radials
* Outer range indicators
* Standard aircraft symbols
* TRACON data blocks
* Airport symbols
* VOR and NDB symbols
* Obstacles
* SID and STAR overlays
* Airspace
* ATC coverage

Selecting an aircraft or flight strip synchronizes the selected pilot across the map, information panels, flight strips, and related operational displays.

---

## Horizon Explorer

**Horizon Explorer** is the integrated aviation browser and resource workspace included with USAFCACARS.

It may provide:

* Multiple browsing tabs
* Pinned aviation links
* USAFC start page
* Navigation controls
* Loading indicators
* Integrated WebView content
* Separate tool-window operation
* USAFC-themed browser controls

Horizon Explorer allows pilots to keep charts, airport information, weather resources, and other flight-planning material available without leaving the USAFCACARS workspace.

---

## Workspace Manager

The Workspace Manager allows pilots to arrange USAFCACARS tools across one or more displays.

Supported workspace concepts may include:

* Grid layouts
* Rows
* Columns
* Stacked panels
* BSP layouts
* Ultrawide layouts
* Floating windows
* Saved window positions
* Saved window dimensions
* Multiple-monitor layouts
* Fullscreen windows
* Reset-to-default layout
* Off-screen window recovery

Layouts are designed to remain usable when display configurations change.

---

## Music and Radio

USAFCACARS may include integrated music and radio controls for use during flight.

Depending on the active release, controls may include:

* Play
* Pause
* Stop
* Previous
* Next
* Volume
* Current track
* Radio stream selection
* Audio-device handling

Audio playback operates separately from USAFC voice communications.

---

## System Requirements

Release-specific requirements are listed with each GitHub release.

General requirements may include:

| Requirement      | Details                                                            |
| ---------------- | ------------------------------------------------------------------ |
| Operating system | Windows 10 or Windows 11                                           |
| Architecture     | 64-bit Windows                                                     |
| Flight simulator | Microsoft Flight Simulator 2020 or Microsoft Flight Simulator 2024 |
| USAFC account    | Active USA Flight Club pilot account                               |
| Internet         | Required for authentication, live tracking, and online services    |
| SimConnect       | Required for simulator telemetry                                   |
| WebView2         | Required by builds that use the Microsoft Edge WebView2 Runtime    |
| Audio devices    | Required for voice communications and audio testing                |
| Runtime          | Listed in the release notes or included with the installer         |

Some features require simulator access, an active flight assignment, or authorization from the USA Flight Club server.

---

## Installation

1. Open the [latest USAFCACARS release](../../releases/latest).
2. Review the release notes and system requirements.
3. Select the correct installer or portable package.
4. Verify the file checksum when one is provided.
5. Close any running copy of USAFCACARS.
6. Run the installer or extract the portable package.
7. Start USAFCACARS.
8. Sign in using your USA Flight Club pilot credentials.
9. Review application, simulator, audio, and communications settings.
10. Connect to Microsoft Flight Simulator and begin your assigned flight.

Do not install application files directly over a running copy of USAFCACARS.

---

## Updating

USAFCACARS may check the USA Flight Club server for available application releases.

When an update is available, the application can display:

* New version number
* Release channel
* Release notes
* Required or optional update status
* Official download location

Install updates only from the official USA Flight Club website or this GitHub repository.

Before updating:

* Complete or safely end any active flight
* Close USAFCACARS
* Preserve custom configuration when instructed
* Review breaking changes in the release notes
* Confirm simulator compatibility

---

## Release Channels

| Channel         | Purpose                                                          |
| --------------- | ---------------------------------------------------------------- |
| **Stable**      | Recommended production release for normal USAFC operations       |
| **Beta**        | Feature-complete testing release that may still contain defects  |
| **Development** | Active development build intended for controlled testing         |
| **Legacy**      | Previous release retained for compatibility or rollback purposes |

Most pilots should use the latest **Stable** release.

Development and beta releases should not be used for important flights unless requested by USA Flight Club administration.

---

## Checksums

Official releases may include a SHA-256 checksum.

A checksum allows you to confirm that the downloaded file matches the package published by USA Flight Club.

Example PowerShell command:

```powershell
Get-FileHash .\USAFCACARS-Setup.exe -Algorithm SHA256
```

Compare the displayed hash with the SHA-256 value included in the corresponding release notes.

Do not install a package when its checksum does not match.

---

## Troubleshooting

### Application does not start

* Confirm that Windows meets the release requirements.
* Install the required .NET Desktop Runtime when it is not bundled.
* Confirm that Microsoft Edge WebView2 Runtime is installed when required.
* Restart Windows after installing missing prerequisites.
* Review the release notes for known issues.

### Simulator does not connect

* Confirm Microsoft Flight Simulator is running.
* Confirm the aircraft is fully loaded into a flight.
* Confirm the app and simulator are running under compatible permissions.
* Verify that the correct SimConnect components are installed.
* Restart USAFCACARS after the simulator is fully loaded.

### Login fails

* Confirm the USA Flight Club website is available.
* Confirm the correct pilot credentials are being used.
* Confirm the computer has internet access.
* Check for an application update.
* Distinguish an invalid-login message from a server-connection error.

### No microphone or speaker audio

* Confirm the intended audio devices are selected.
* Check Windows microphone permissions.
* Check application volume.
* Run the microphone and speaker tests.
* Confirm another application is not exclusively locking the audio device.
* Reconnect devices and reopen the communications settings.

### Map or browser content is blank

* Confirm internet access.
* Confirm Microsoft Edge WebView2 Runtime is installed.
* Check whether a firewall or security product is blocking the application.
* Restart the affected panel or the application.

---

## Reporting an Issue

Before submitting a report:

1. Confirm you are using the latest appropriate release.
2. Review the release notes.
3. Reproduce the problem.
4. Record the steps that caused it.
5. Include the application version.
6. Include the Windows version.
7. Include the simulator version.
8. Include relevant error messages.
9. Remove passwords, tokens, private pilot information, and other sensitive content.

Submit reports through the repository’s issue system when enabled:

[Open a USAFCACARS issue](../../issues/new/choose)

A useful report should explain:

* What you expected
* What happened
* How to reproduce it
* Whether the problem occurs every time
* Whether it began after an update
* Which USAFCACARS release is installed

---

## Security

USAFCACARS communicates with USA Flight Club services and may temporarily process authentication, pilot, flight, simulator, map, and communications data.

USAFCACARS must never be distributed with:

* Hardcoded passwords
* Private API keys
* Authentication tokens
* Database credentials
* Private certificates
* Development bypasses
* Administrator credentials
* Private pilot records

Do not publish sensitive logs with an issue report.

Security concerns should be reported privately to USA Flight Club administration rather than posted publicly.

---

## Repository Purpose

This repository is the official public release location for the USAFCACARS desktop application.

It may contain:

* Installers
* Portable release packages
* Release notes
* Checksums
* Public documentation
* Application screenshots
* Public graphics
* Installation instructions
* Compatibility information

The presence of release packages in this repository does not make the USAFCACARS source code open source.

---

## Proprietary Software

USAFCACARS is proprietary software developed for USA Flight Club.

Unless expressly authorized in writing, users may not:

* Copy or redistribute the software
* Modify or reverse engineer the application
* Resell the application
* Rebrand the application
* Extract proprietary USAFC assets
* Use the software for an unrelated airline or organization
* Publish private source code
* Remove ownership or copyright notices

Third-party components remain subject to their respective licenses.

```text
Copyright © USA Flight Club.
All rights reserved.
```

---

## Official Links

* **USA Flight Club:** https://usaflightclub.net
* **Latest Release:** [USAFCACARS Releases](../../releases/latest)
* **Issues:** [USAFCACARS Issue Tracker](../../issues)
* **Downloads:** Available through the official USA Flight Club downloads page and this repository

---

<p align="center">
  <img
    src="assets/readme/usafc-logo.png"
    alt="USA Flight Club"
    width="180"
  >
</p>

<p align="center">
  <strong>USA Flight Club</strong><br>
  Virtual aviation operations, flight tracking, communications, and community.
</p>

<p align="center">
  <sub>USAFCACARS is proprietary software. All rights reserved.</sub>
</p>
