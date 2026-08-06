# USAFCACARS Support Guide

**Last updated:** August 6, 2026  
**Current documented release:** 1.0.4 Alpha  
**Software status:** Proprietary software in active alpha development

This document explains how to obtain help with USAFCACARS, where to report
different types of problems, what information to include, and what users
should expect from support during alpha development.

Official USA Flight Club website:

[https://usaflightclub.net](https://usaflightclub.net)

Official USAFCACARS live map:

[https://usaflightclub.net/usafcacars/live](https://usaflightclub.net/usafcacars/live)

Official downloads:

[https://usaflightclub.net/downloads](https://usaflightclub.net/downloads)

> [!IMPORTANT]
> USAFCACARS is currently in active alpha development.
>
> Alpha builds may contain incomplete features, disabled controls, temporary
> layouts, compatibility limitations, crashes, configuration changes, or
> data-loss defects. Support is provided on a best-effort basis while the
> application continues to be developed.

> [!NOTE]
> Concept graphics, mockups, roadmap descriptions, and interface previews show
> the intended direction of the project. They do not guarantee that every
> depicted feature is available in the current build.

---

## 1. Where to Get Help

Use the support channel that matches the issue.

### Public GitHub Issue

Use a public GitHub issue for:

- Reproducible software defects;
- Application crashes without sensitive information;
- User-interface defects;
- Flightboard defects;
- Live-map defects;
- SimConnect compatibility problems;
- Aircraft-specific behavior;
- Weather, chart, or airport display problems;
- Voice-device problems that do not expose private communications;
- Documentation errors; and
- Feature requests.

Open an issue through the repository issue tracker when enabled:

[Open a USAFCACARS issue](../../issues/new/choose)

Do not use a public issue for account, privacy, security, or confidential
support matters.

### Private USA Flight Club Support

Use the official USA Flight Club support system for:

- Pilot-account access;
- Login problems involving private account information;
- Pilot ID or callsign corrections;
- Rank or profile corrections;
- Bid or PIREP disputes;
- Administrative requests;
- Private logs;
- Private communications;
- Membership issues;
- Voice-room authorization;
- Sensitive screenshots;
- Privacy requests;
- Security concerns; and
- Any matter involving another user's information.

Submit private support requests through:

[https://usaflightclub.net](https://usaflightclub.net)

Suggested request title:

```text
USAFCACARS Support Request
```

### Security Reports

Do not report vulnerabilities publicly.

Follow:

[SECURITY.md](SECURITY.md)

Suggested private request title:

```text
USAFCACARS Security Report
```

### Privacy Requests

Do not submit privacy requests through a public issue.

Follow:

[PRIVACY.md](PRIVACY.md)

Suggested private request title:

```text
USAFCACARS Privacy Request
```

---

## 2. Before Requesting Support

Complete these checks first:

1. Confirm the installed USAFCACARS version.
2. Read the release notes for that version.
3. Review the current known limitations.
4. Confirm whether the feature is implemented in the current alpha.
5. Restart USAFCACARS.
6. Restart Microsoft Flight Simulator if simulator-related.
7. Confirm internet access.
8. Confirm the official USA Flight Club website is reachable.
9. Confirm the correct simulator is selected.
10. Confirm the correct aircraft is loaded.
11. Confirm required runtimes are installed.
12. Confirm Microsoft Edge WebView2 Runtime is installed where required.
13. Confirm the selected microphone and speaker devices.
14. Confirm no stale USAFCACARS process remains in Task Manager.
15. Confirm the issue still occurs.
16. Gather sanitized diagnostic information.

Do not reinstall immediately unless the release notes or support guidance
recommend it. Reinstallation can remove useful evidence or settings.

---

## 3. Information to Include

A useful support request should contain the following.

### Basic Information

- USAFCACARS version;
- Release channel;
- Windows version;
- Microsoft Flight Simulator 2020 or 2024;
- Simulator build;
- Aircraft;
- Aircraft add-on developer;
- Aircraft add-on version;
- Number of monitors;
- Display resolution;
- Windows scaling;
- Audio device, where relevant;
- Network type, where relevant; and
- Whether the issue occurs in Debug, Release, installer, or portable build.

### Problem Description

Include:

- A clear summary;
- What you expected;
- What happened;
- Exact steps to reproduce;
- Whether it occurs every time;
- Whether it began after an update;
- Whether another aircraft behaves differently;
- Whether the website or live map shows the same problem;
- Whether restarting changes the result; and
- The approximate time of the failure.

### Evidence

Useful evidence may include:

- Screenshot;
- Short screen recording;
- Exact error text;
- Sanitized log excerpt;
- Windows Event Viewer entry;
- Application version screen;
- Simulator and aircraft version;
- Relevant route or airport identifiers; and
- A list of active panels or workspaces.

Do not include more data than necessary.

---

## 4. Information That Must Not Be Posted Publicly

Never publish:

- Passwords;
- Full authentication tokens;
- API keys;
- Session cookies;
- Private keys;
- Database credentials;
- `.env` contents;
- Private pilot records;
- Private email addresses without permission;
- Private chat;
- Private voice communications;
- Unredacted support tickets;
- Administrator-only information;
- Internal server paths where unnecessary;
- Database exports;
- Production logs containing secrets; or
- Security-vulnerability details.

Replace sensitive values with:

```text
[REDACTED]
```

If unsure, submit the information privately.

---

## 5. Support Request Template

```markdown
## Summary

Describe the problem in one or two sentences.

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

## Steps to Reproduce

1.
2.
3.
4.

## Expected Result

Describe what should have happened.

## Actual Result

Describe what happened instead.

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

- [ ] I removed passwords, authentication tokens, API credentials, private
      communications, and sensitive personal data.
```

---

## 6. Feature Request Template

```markdown
## Feature Summary

Describe the requested feature.

## Problem It Solves

Explain why the feature is useful.

## Suggested Workflow

Describe how the feature should work.

## Related Area

Dashboard / Flight Tracking / Pilot Briefing / Live Map / Flightboard /
Weather / Charts / Voice Communications / ATC / TRACON / Flight Strips /
Taxi Management / Aircraft Control / Passenger Operations /
Horizon Explorer / Workspace Manager / Music & Radio /
Pilot Profile / Community / Help & Support / Other

## Simulator or Aircraft Dependency

State whether the request depends on a simulator, aircraft, add-on, API,
provider, or external service.

## Concept Reference

Link to an existing concept image or roadmap section if relevant.

## Additional Notes

Add examples, limitations, or compatibility concerns.
```

---

## 7. Support Categories

### Installation and Updates

Use this category for:

- Installer failure;
- Portable package failure;
- Missing runtime;
- WebView2 requirement;
- Update detection;
- Incorrect installed version;
- Checksum mismatch;
- Old files remaining after update; and
- Application not launching after installation.

Include:

- Package filename;
- Download source;
- Checksum result;
- Installer error;
- Windows version; and
- Whether the previous build was removed.

### Login and Account

Use this category for:

- Invalid-credentials messages;
- Server-unavailable messages;
- Account not recognized;
- Pilot profile not loading;
- Incorrect callsign;
- Incorrect pilot ID;
- Rank or avatar problems; and
- Logout or session problems.

Account-specific matters should normally be submitted privately.

### Flights and Bids

Use this category for:

- Missing bids;
- Duplicate bids;
- Flight search problems;
- Incorrect route;
- Incorrect aircraft;
- Missing departure or arrival;
- Three-character airport problems;
- Flight cannot start;
- Flight cannot cancel;
- Flight cannot finish; and
- PIREP not created.

Include the flight number and route, but avoid exposing private account data.

### SimConnect

Use this category for:

- Simulator not detected;
- Connection drops;
- Aircraft not identified;
- Telemetry not changing;
- Incorrect altitude, speed, heading, or position;
- Gear or flap state wrong;
- Landing rate wrong;
- Aircraft control not working; and
- Simulator close or reconnect problems.

Include the exact aircraft and add-on version.

### Flight Phases

Use this category for:

- Wrong phase;
- Rapid phase switching;
- Cruise detected too early;
- Landing detected incorrectly;
- Shutdown detected too early;
- Completed state never reached; and
- Taxi or gate state incorrect.

Include relevant simulator state when possible.

### Live Map

Use this category for:

- Aircraft missing;
- Aircraft in the wrong place;
- Route missing;
- Departure or arrival missing;
- Stale aircraft;
- Jumping movement;
- Layer problem;
- Pop-out problem;
- Pilot selection problem; and
- Browser-console errors.

Official live map:

[https://usaflightclub.net/usafcacars/live](https://usaflightclub.net/usafcacars/live)

### Flightboard

Use this category for:

- Wrong flight status;
- Missing row;
- Duplicate row;
- Broken alignment;
- Character animation problem;
- Entire row flashing;
- Wrong altitude, speed, or heading;
- Source filter problem; and
- Departures or Arrivals tab problem.

### Weather and Charts

Use this category for:

- METAR or TAF failure;
- Weather layer blank;
- Radar misalignment;
- Block-shaped cloud tiles;
- Incorrect transparency;
- Chart missing;
- Wrong airport chart;
- Zoom problem; and
- Three-character airport chart failure.

Do not publicly attach restricted third-party chart files.

### Voice Communications

Use this category for:

- Microphone not detected;
- Speaker not detected;
- Microphone test silent;
- Speaker test silent;
- Push-to-talk failure;
- Mute failure;
- Deafen failure;
- Room authorization;
- Incorrect room or frequency;
- Audio-device lock;
- Page not scrollable; and
- App not releasing audio on shutdown.

Do not post private voice recordings publicly.

### ATC, TRACON, Flight Strips, and Taxi Management

Use this category for:

- Aircraft selection mismatch;
- Strip selection mismatch;
- Missing data block;
- Wrong controller assignment;
- Handoff failure;
- Airport selection failure;
- Taxi-route problem;
- Runway assignment problem;
- Pushback queue problem;
- Runway-incursion alert problem; and
- Scope or layer problem.

Many advanced ATC systems may remain experimental during alpha development.

### Horizon Explorer

Use this category for:

- Blank page;
- Tab failure;
- Pinned resource failure;
- WebView crash;
- Download problem;
- Pop-out problem;
- Page not closing;
- Duplicate WebView processes; and
- External navigation problem.

### Workspace Manager

Use this category for:

- Layout not saving;
- Layout not restoring;
- Window off-screen;
- Fullscreen not restoring;
- Disconnected monitor problem;
- Duplicate window;
- Reset failure; and
- Corrupt layout preventing startup.

### Aircraft Control

Use this category for:

- Instrument state wrong;
- Light control failure;
- Gear control failure;
- Flap or spoiler control failure;
- Door control failure;
- Electrical system failure;
- Radio or transponder failure;
- APU or engine-control failure; and
- Aircraft-specific compatibility.

Aircraft Control depends on what the simulator and aircraft expose through
SimConnect or aircraft-specific adapters.

### Passenger Operations

Use this category for:

- Cabin configuration;
- Seat map;
- Passenger roster;
- Boarding;
- Meal or beverage service;
- Movie or entertainment service;
- Seatbelt or no-smoking sign;
- Door status;
- Satisfaction score; and
- Deboarding.

Passenger Operations may be unavailable or incomplete in early alpha builds.

### Music and Radio

Use this category for:

- Playback failure;
- Radio stream failure;
- Music Player tab;
- Radio Scanner tab;
- Music Radio Player tab;
- Volume;
- Playlist;
- Equalizer;
- Audio-device selection; and
- Music interfering with voice communications.

### Community and Support

Use this category for:

- Community feed;
- Groups;
- Events;
- Chat;
- Discord links;
- Online members;
- Leaderboards;
- Help search;
- Knowledge base;
- Ticket links;
- Diagnostics; and
- System-status display.

Private community matters should be handled through private support.

---

## 8. Common Troubleshooting

### Application Does Not Start

1. Confirm Windows is supported.
2. Confirm the required .NET Desktop Runtime is installed.
3. Confirm Microsoft Edge WebView2 Runtime is installed where required.
4. Close stale USAFCACARS processes.
5. Restart Windows.
6. Run the application from the official installation folder.
7. Review the application log.
8. Check Windows Event Viewer.
9. Reinstall only after preserving useful logs and settings.

### Login Fails

1. Confirm the website is reachable.
2. Confirm the correct pilot credentials.
3. Confirm the API environment.
4. Check whether the message says invalid credentials or server unavailable.
5. Confirm the application version.
6. Try signing in to the official website.
7. Submit account-specific details privately.

### Simulator Does Not Connect

1. Start Microsoft Flight Simulator.
2. Load fully into an aircraft.
3. Wait until the cockpit is interactive.
4. Confirm the correct simulator adapter.
5. Restart USAFCACARS.
6. Confirm SimConnect dependencies.
7. Test with a default aircraft.
8. Compare behavior with the add-on aircraft.

### Flight Does Not Start

1. Confirm a valid bid is selected.
2. Confirm the correct pilot account.
3. Confirm the server connection.
4. Confirm no other active session exists.
5. Confirm the aircraft assignment.
6. Check the exact API error.
7. Refresh bids and try again.

### Flight Does Not Finish

1. Confirm the correct active session.
2. Confirm the aircraft is on the ground.
3. Confirm the final phase.
4. Confirm engines and parking state where required.
5. Confirm server connection.
6. Avoid repeatedly clicking Finish.
7. Preserve logs before closing.
8. Check whether a PIREP was created before retrying.

### Live Map Is Blank

1. Open the live-map URL directly.
2. Confirm internet access.
3. Confirm WebView2 Runtime.
4. Check browser-console errors.
5. Disable and re-enable the relevant layer.
6. Confirm the flight appears in the API.
7. Reload the panel.

### Voice Audio Does Not Work

1. Confirm Windows microphone permission.
2. Confirm selected microphone and speaker.
3. Run microphone and speaker tests.
4. Confirm the device is not exclusively locked.
5. Reconnect the headset.
6. Reopen Voice & Radio Settings.
7. Restart the application if the device remains locked.

### Window Is Missing

1. Use Workspace Manager Reset.
2. Disconnect or reconnect external monitors.
3. Use Windows keyboard window-move commands.
4. Reset the saved layout.
5. Remove only the layout configuration if instructed.

---

## 9. Logs and Diagnostics

USAFCACARS logs may help identify:

- Startup failures;
- Authentication failures;
- API failures;
- SimConnect failures;
- Flight phase changes;
- Telemetry failures;
- Flight completion failures;
- Voice-device failures;
- WebView failures;
- Workspace restore failures;
- Update failures; and
- Unhandled exceptions.

Before sharing a log:

1. Open it in a text editor.
2. Search for your email address.
3. Search for your pilot ID.
4. Search for `password`.
5. Search for `token`.
6. Search for `authorization`.
7. Search for `cookie`.
8. Search for private chat.
9. Search for internal server paths.
10. Remove unrelated personal information.

Share the smallest useful excerpt.

---

## 10. Expected Support Response

USA Flight Club aims to review useful reports, but alpha support does not
guarantee:

- Immediate response;
- A specific resolution date;
- A fix in the next release;
- Compatibility with every aircraft;
- Compatibility with every hardware device;
- Restoration of lost flight data;
- Recovery of local configuration;
- Individual training;
- Custom feature development;
- Continued operation of every third-party service; or
- Support for unofficial or modified builds.

Priority is generally given to:

1. Security problems;
2. Account or authorization problems;
3. Data-integrity problems;
4. Flight-start or flight-finish failures;
5. Crashes;
6. Simulator and API connectivity;
7. Voice and communications failures;
8. Live-map and flightboard failures;
9. Major user-interface defects; and
10. Feature requests and cosmetic improvements.

---

## 11. Unsupported Situations

Support may be limited or refused for:

- Unofficial builds;
- Repackaged releases;
- Modified executables;
- Modified proprietary source code;
- Unsupported Windows versions;
- Unsupported simulator versions;
- Unlicensed third-party software;
- Malware-infected systems;
- Deliberate service abuse;
- Unauthorized redistribution;
- Credential sharing;
- Testing against another user's account;
- Security probing outside the Security Policy;
- Deleted or altered logs;
- Problems caused by unsupported plug-ins; and
- Use of USAFCACARS for real-world aviation operations.

USAFCACARS is intended only for virtual aviation and flight simulation.

---

## 12. Account and PIREP Disputes

Account, bid, rank, and PIREP disputes must be submitted privately.

Include:

- Pilot ID;
- Flight number;
- PIREP identifier, if available;
- Date and approximate time;
- Route;
- Aircraft;
- Summary of the issue;
- Sanitized evidence; and
- Requested correction.

Do not publicly accuse another pilot, controller, or administrator.

---

## 13. Third-Party Services

USAFCACARS may depend on:

- Microsoft Flight Simulator;
- SimConnect;
- Microsoft Edge WebView2;
- GitHub;
- Mapping providers;
- Weather providers;
- Chart providers;
- Audio providers;
- Discord;
- VATSIM;
- IVAO;
- ADS-B providers; and
- Aircraft add-ons.

A third-party outage or policy change may be outside USA Flight Club's
control.

Check the third party's own status page and support documentation where
appropriate.

---

## 14. Release and Update Support

Each release should document:

- Version;
- Release channel;
- Release date;
- Supported simulator;
- Required runtime;
- Implemented features;
- Known limitations;
- Upgrade instructions;
- Mandatory-update status;
- Download package;
- SHA-256 checksum; and
- Support links.

Install updates only from official USA Flight Club or official GitHub release
locations.

Do not install a package when its checksum does not match.

PowerShell example:

```powershell
Get-FileHash .\USAFCACARS-Setup.exe -Algorithm SHA256
```

---

## 15. Alpha Tester Responsibilities

Alpha testers are expected to:

- Read release notes;
- Test carefully;
- Use authorized accounts;
- Avoid important flights when testing unstable features;
- Preserve useful logs;
- Report reproducible problems;
- Protect credentials;
- Avoid public disclosure of private data;
- Avoid redistributing private builds;
- Avoid disrupting services;
- Follow the proprietary license;
- Follow the Security Policy; and
- Clearly distinguish concept features from implemented features.

---

## 16. Documentation

Related documents:

- [README](README.md)
- [License](LICENSE)
- [Changelog](CHANGELOG.md)
- [Privacy Notice](PRIVACY.md)
- [Security Policy](SECURITY.md)
- [Alpha Testing Guide](docs/ALPHA-TESTING.md)
- [Third-Party Notices](THIRD_PARTY_NOTICES.md)

---

## 17. Official Links

- **USA Flight Club:** [https://usaflightclub.net](https://usaflightclub.net)
- **Official Downloads:** [https://usaflightclub.net/downloads](https://usaflightclub.net/downloads)
- **USAFCACARS Live Map:** [https://usaflightclub.net/usafcacars/live](https://usaflightclub.net/usafcacars/live)
- **Latest GitHub Release:** [View latest release](../../releases/latest)
- **GitHub Issues:** [View issues](../../issues)
- **Alpha Testing Guide:** [docs/ALPHA-TESTING.md](docs/ALPHA-TESTING.md)

---

## 18. Final Reminder

USAFCACARS is proprietary alpha software.

The best support request is specific, reproducible, sanitized, and submitted
through the correct channel.

Use public issues for reproducible non-sensitive defects. Use private USA
Flight Club support for account, privacy, security, administrative, and
confidential matters.

```text
Copyright © 2026 USA Flight Club.
All rights reserved.

USAFCACARS is proprietary software.
```
