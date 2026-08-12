# USAFCACARS Installation Guide

**Last updated:** August 11, 2026
**Current documented release:** 1.0.16 Alpha
**Software status:** Proprietary software in active alpha development

This guide explains how to download, verify, install, configure, update, repair,
and remove the USAFCACARS Windows desktop application.

Official USA Flight Club website:

[https://usaflightclub.net](https://usaflightclub.net)

Official USAFCACARS downloads:

[https://usaflightclub.net/downloads](https://usaflightclub.net/downloads)

Official USAFCACARS live map:

[https://usaflightclub.net/usafcacars/live](https://usaflightclub.net/usafcacars/live)

> [!IMPORTANT]
> USAFCACARS is currently in active alpha development.
>
> Alpha builds may contain unfinished features, disabled controls, visual
> placeholders, compatibility limitations, crashes, configuration changes, or
> data-loss defects.
>
> Read the release notes before installing or updating.

> [!CAUTION]
> Do not install an update while a USAFCACARS flight is active.
>
> Complete or safely cancel the flight, close USAFCACARS, and confirm that no
> USAFCACARS process remains open before replacing application files.

---

## 1. Installation Options

A USAFCACARS release may be distributed in one or more formats.

### Windows Installer

Typical package:

```text
USAFCACARS-Setup-1.0.4.exe
```

or:

```text
USAFCACARS-1.0.4.msi
```

Use the installer when you want:

- A normal Windows installation;
- Start menu shortcuts;
- Desktop shortcuts where enabled;
- Automatic installation into the supported application directory;
- Repair and uninstall support;
- Prerequisite checks; and
- Future update integration.

### Portable Package

Typical package:

```text
USAFCACARS-Portable-1.0.4.zip
```

Use the portable package when you want:

- A self-contained test copy;
- Side-by-side alpha testing;
- No traditional installer;
- A removable test folder; or
- A clean comparison with another build.

Portable packages must be fully extracted before running.

Do not launch USAFCACARS directly from inside the ZIP archive.

### Development Build

Development builds may be supplied to authorized testers.

They may:

- Contain diagnostic tools;
- Require additional runtimes;
- Use a development API;
- Be less stable than public alpha builds;
- Produce more detailed logs; and
- Require manual configuration.

Do not redistribute a development build unless USA Flight Club explicitly
authorizes it.

---

## 2. System Requirements

Exact requirements are listed in the release notes for each build.

General target requirements are:

| Requirement | Details |
|---|---|
| Operating system | Windows 10 or Windows 11 |
| Architecture | 64-bit Windows |
| Simulator | Microsoft Flight Simulator 2020 and/or Microsoft Flight Simulator 2024 |
| Simulator connection | Microsoft SimConnect |
| USAFC account | Active USA Flight Club pilot account for connected services |
| Internet connection | Required for login, live tracking, maps, updates, and online services |
| Browser runtime | Microsoft Edge WebView2 Runtime where required |
| Audio | Microphone and speakers or headset for communications |
| Runtime | .NET Desktop Runtime required by the release |
| Display | 1920×1080 recommended |
| Multi-monitor support | Supported by developing Workspace Manager features |

Recommended:

- Windows fully updated;
- 16 GB RAM or more;
- Modern 64-bit processor;
- Dedicated graphics hardware for advanced map and WebView panels;
- SSD storage;
- Stable broadband connection;
- Headset with microphone for Voice Communications; and
- Current Microsoft Flight Simulator updates.

---

## 3. Before Downloading

Before downloading USAFCACARS:

1. Confirm the release is official.
2. Read the release notes.
3. Confirm the release channel.
4. Confirm simulator compatibility.
5. Confirm required runtimes.
6. Review known limitations.
7. Confirm whether the build is installer or portable.
8. Confirm whether the update is mandatory.
9. Confirm whether existing settings can be retained.
10. Complete or cancel any active flight.

Official sources should be limited to:

- The USA Flight Club Downloads page;
- The official USAFCACARS GitHub Releases page; or
- Another location explicitly identified by USA Flight Club.

Do not install packages obtained from:

- Unofficial mirrors;
- File-sharing sites;
- Repacked archives;
- Unknown cloud-storage links;
- Social-media attachments;
- Unverified direct messages; or
- Another virtual airline or organization.

---

## 4. Verify the Download

Official release packages may include a SHA-256 checksum.

### PowerShell

Open PowerShell in the folder containing the download and run:

```powershell
Get-FileHash .\USAFCACARS-Setup-1.0.4.exe -Algorithm SHA256
```

For a portable package:

```powershell
Get-FileHash .\USAFCACARS-Portable-1.0.4.zip -Algorithm SHA256
```

Compare the returned hash with the value published in the release notes.

### Command Prompt

Windows can also use:

```cmd
certutil -hashfile USAFCACARS-Setup-1.0.4.exe SHA256
```

### Do not install when

Do not install the package if:

- The checksum does not match;
- The filename is unexpectedly changed;
- The package came from an unofficial source;
- Windows identifies the publisher differently than expected;
- The package contains unexpected scripts or files;
- Antivirus software reports a confirmed threat;
- The download redirects through an unknown host; or
- The release is not listed by USA Flight Club.

Submit a private support request if the official checksum does not match.

---

## 5. Required Windows Components

Depending on the release, USAFCACARS may require the following.

### .NET Desktop Runtime

USAFCACARS is a Windows desktop application built with Microsoft .NET.

The required runtime version is listed in the release notes.

To check installed .NET runtimes:

```powershell
dotnet --list-runtimes
```

If `dotnet` is not recognized, the required runtime may not be installed or
may not be available through the command path.

Install only the official Microsoft .NET Desktop Runtime required by the
release.

### Microsoft Edge WebView2 Runtime

WebView2 may be required for:

- Live map;
- Horizon Explorer;
- Weather panels;
- Chart viewers;
- Airport information;
- Embedded web content; and
- Other browser-based panels.

To verify WebView2:

1. Open Windows Settings.
2. Open **Apps**.
3. Open **Installed apps**.
4. Search for:

```text
Microsoft Edge WebView2 Runtime
```

If it is missing, install it from Microsoft's official source.

### Microsoft Flight Simulator and SimConnect

SimConnect features require a supported Microsoft Flight Simulator
installation.

The application may connect to:

- Microsoft Flight Simulator 2020;
- Microsoft Flight Simulator 2024; or
- Both, depending on the build.

Some releases may include required SimConnect components. Others may rely on
the simulator installation.

Do not copy random SimConnect DLLs from unverified websites into the
application folder.

### Audio Devices

Voice Communications requires:

- A working microphone;
- A working speaker or headset;
- Windows microphone permission;
- A selected input device;
- A selected output device; and
- A supported audio format; and
- Firewall access to the configured USAFCACARS communications service.

A headset is recommended to prevent feedback.

---

## 6. Clean Installation with the Windows Installer

Use these steps for a first installation.

### Step 1: Close Related Applications

Close:

- USAFCACARS;
- Microsoft Flight Simulator, if the installer requests it;
- Any USAFCACARS updater;
- Any detached USAFCACARS window;
- Any log viewer locking application files; and
- Any development tool currently building USAFCACARS.

Open Task Manager and confirm no process remains named similar to:

```text
USAFCACARS
USAFCACARS.Client
USAFCACARS.Updater
```

### Step 2: Start the Installer

Right-click the official installer and choose:

```text
Open
```

Use **Run as administrator** only when:

- The installer requests elevated access;
- The selected installation directory requires it; or
- Support instructions specifically require it.

Do not run the application as administrator for normal daily use unless a
known simulator-permission issue requires matched elevation.

### Step 3: Review the License

Read and accept the proprietary USAFCACARS license only if you agree to its
terms.

The application is licensed, not sold.

### Step 4: Select the Installation Folder

Use the default folder unless there is a specific reason to change it.

A typical per-user installation may use a path under:

```text
C:\Users\<username>\AppData\Local\Programs\USAFCACARS
```

A machine-wide installer may use:

```text
C:\Program Files\USAFCACARS
```

The actual path depends on the installer.

Avoid installing into:

- The Microsoft Flight Simulator package directory;
- The Windows directory;
- The phpVMS website directory;
- A Git repository;
- A temporary folder;
- A cloud-synchronized source-code directory; or
- The root of a drive.

### Step 5: Select Shortcuts

The installer may offer:

- Start menu shortcut;
- Desktop shortcut;
- Launch after installation; and
- File associations.

Select only the options you need.

### Step 6: Install

Complete the installation.

Do not interrupt the installer while files are being written.

### Step 7: Launch

Start USAFCACARS from:

- The Start menu;
- The desktop shortcut; or
- The installed executable.

Confirm the displayed version matches the downloaded release.

---

## 7. Portable Installation

Use these steps for a portable build.

### Step 1: Create a Folder

Create a dedicated folder such as:

```text
C:\USAFCACARS-Portable\1.0.4
```

or:

```text
D:\USAFCACARS-Test\1.0.4
```

Do not extract over another version unless the release notes explicitly allow
it.

### Step 2: Extract All Files

Right-click the ZIP and choose:

```text
Extract All
```

Confirm all files are extracted.

### Step 3: Unblock the Archive When Necessary

Windows may mark downloaded files as coming from the internet.

Before extraction:

1. Right-click the ZIP.
2. Choose **Properties**.
3. If an **Unblock** option appears, review the source.
4. Select **Unblock** only if the file is official and the checksum matches.
5. Apply the change.
6. Extract again.

### Step 4: Run the Application

Open the extracted folder and run the primary USAFCACARS executable.

Do not move only the executable. Keep all included DLLs, runtimes,
configuration files, and resources together.

### Step 5: Preserve Side-by-Side Builds

Portable alpha builds may be stored in separate folders:

```text
C:\USAFCACARS-Portable\
├── 1.0.3\
├── 1.0.4\
└── Development\
```

Do not share the same settings folder between builds unless the release notes
confirm compatibility.

---

## 8. First Launch

On first launch, verify:

- The application opens without crashing;
- The login screen is visible;
- USAFC branding loads;
- Text is readable;
- Controls are not clipped;
- The version is correct;
- The server status appears;
- The application remains responsive; and
- Closing the application ends all related processes.

The first launch may create:

- Settings files;
- Log folders;
- Cache folders;
- WebView2 data;
- Workspace layouts;
- Audio preferences;
- Map preferences;
- Update information; and
- Authentication storage.

---

## 9. Initial Configuration

After launching, review the following.

### API Environment

Production should use the official USA Flight Club service.

Development builds may offer a development environment.

Do not enter an unofficial API address.

A local development environment may use:

```text
http://usaflightclub.local
```

Production should use:

```text
https://usaflightclub.net
```

Normal public users should not select the local development environment.

### Pilot Login

Use your authorized USA Flight Club account.

Do not share:

- Password;
- Token;
- Session information;
- Administrator credentials; or
- Private test account credentials.

### Simulator Selection

Select the supported simulator when the application provides a choice.

Confirm whether the release supports:

- MSFS 2020;
- MSFS 2024; or
- Both.

### Audio Configuration

Open Voice & Radio Settings and choose:

- Microphone;
- Speaker or headset;
- Global push-to-talk control;
- Microphone level;
- Communications volume;
- Optional Discord microphone-mute coordination;
- Music volume; and
- Radio volume.

Run:

- Microphone test; and
- Speaker test.

Confirm the microphone test remains local and is not transmitted to an
active room.

### Workspace Configuration

Review:

- Main display;
- Additional monitors;
- Saved layout;
- Pop-out windows;
- Fullscreen behavior; and
- Workspace reset.

Use the default layout first.

---

## 10. Connecting to Microsoft Flight Simulator

Recommended sequence:

1. Start Microsoft Flight Simulator.
2. Load into the main menu.
3. Select an aircraft.
4. Load fully into the flight.
5. Wait until the cockpit is interactive.
6. Start USAFCACARS.
7. Sign in.
8. Open simulator settings.
9. Connect through SimConnect.
10. Confirm simulator status changes to connected.

Verify telemetry such as:

- Aircraft identity;
- Position;
- Altitude;
- Speed;
- Heading;
- Vertical speed;
- On-ground state;
- Gear;
- Flaps;
- Fuel; and
- Engine state.

If a complex add-on aircraft does not expose a system through standard
SimConnect, an aircraft-specific adapter may be required.

---

## 11. Starting a Test Flight

For alpha testing:

1. Sign in.
2. Load My Flights or Bids.
3. Select a valid flight.
4. Review the briefing.
5. Confirm departure and arrival.
6. Confirm the aircraft.
7. Start Microsoft Flight Simulator.
8. Load the selected aircraft.
9. Confirm SimConnect is connected.
10. Start the flight in USAFCACARS.
11. Confirm the active session begins.
12. Confirm telemetry updates.
13. Open the official live map.
14. Confirm the flight appears.
15. Continue the test.

Official live map:

[https://usaflightclub.net/usafcacars/live](https://usaflightclub.net/usafcacars/live)

Do not use an alpha test as the only record of an important flight.

---

## 12. Updating from an Earlier Version

Before updating:

1. Complete or cancel any active flight.
2. Confirm the PIREP status.
3. Close USAFCACARS.
4. Close all pop-out windows.
5. Confirm no USAFCACARS process remains.
6. Read the new release notes.
7. Review configuration changes.
8. Back up settings if instructed.
9. Download the official package.
10. Verify the checksum.

### Installer Update

Run the new installer.

The installer may:

- Replace application files;
- Preserve settings;
- Update prerequisites;
- Update shortcuts; and
- Remove obsolete files.

Do not cancel the update after file replacement has started.

### Portable Update

For a portable package:

1. Extract the new release into a new folder.
2. Launch it once.
3. Confirm it works.
4. Copy only supported settings when instructed.
5. Keep the old folder temporarily for rollback.
6. Do not copy old DLLs into the new build.

### Configuration Migration

A release may change:

- Settings format;
- Token storage;
- Workspace layout;
- API compatibility;
- Audio configuration;
- Simulator adapter;
- WebView cache; or
- Map preferences.

Follow release-specific migration instructions.

---

## 13. Downgrading

Downgrading may not be supported.

A newer version may change:

- Configuration files;
- Database records;
- API compatibility;
- Workspace layouts;
- Authentication tokens;
- Cache format; or
- Simulator adapters.

Before downgrading:

1. Read the older release notes.
2. Export or back up supported settings.
3. Close USAFCACARS.
4. Remove the newer application.
5. Install the older version into a separate folder.
6. Do not reuse incompatible settings.
7. Confirm server compatibility.

A server may reject an outdated application for security or API reasons.

---

## 14. Repairing an Installation

Use repair when:

- Files are missing;
- The application no longer starts;
- A DLL is damaged;
- A shortcut is broken;
- An update was interrupted; or
- WebView integration is damaged.

### Installer Repair

Open:

```text
Windows Settings → Apps → Installed apps
```

Find USAFCACARS.

If available, choose:

```text
Modify
```

or:

```text
Repair
```

### Reinstall

If repair is unavailable:

1. Preserve logs and settings.
2. Uninstall USAFCACARS.
3. Restart Windows.
4. Download the official package again.
5. Verify the checksum.
6. Install the same or newer version.

Do not use third-party registry cleaners.

---

## 15. Uninstalling USAFCACARS

### Windows Installer

Open:

```text
Windows Settings → Apps → Installed apps
```

Select USAFCACARS and choose:

```text
Uninstall
```

Follow the prompts.

### Portable Build

Close USAFCACARS and delete the portable folder.

### Remaining User Data

Uninstalling may leave:

- Settings;
- Logs;
- WebView cache;
- Workspace layouts;
- Downloaded charts;
- Map cache;
- Audio preferences; and
- Crash reports.

This allows settings to survive reinstallations.

Do not delete remaining data until:

- Support no longer needs the logs;
- You confirm no active flight depends on it;
- You no longer need the layout; and
- You have backed up anything important.

A future release may include an in-application reset or data-removal tool.

---

## 16. Firewall and Security Software

USAFCACARS may require outbound network access for:

- Authentication;
- API communication;
- Live tracking;
- Live map;
- Weather;
- Charts;
- Voice communications;
- Community features;
- Support;
- Downloads; and
- Updates.

Allow only the official executable.

Do not:

- Disable Windows Firewall globally;
- Disable antivirus protection permanently;
- Add broad exclusions for an entire drive;
- Expose inbound ports unless instructed;
- Run unverified scripts; or
- disable TLS certificate validation.

If security software blocks USAFCACARS:

1. Confirm the package is official.
2. Verify the checksum.
3. Review the exact alert.
4. Submit the file to the security vendor when appropriate.
5. Contact USA Flight Club support.
6. Add the smallest safe exception only when justified.

---

## 17. Windows Permissions

USAFCACARS should normally run as a standard user.

Running as administrator may cause problems when:

- Microsoft Flight Simulator runs as a different privilege level;
- Drag-and-drop is used;
- WebView2 stores per-user data;
- Audio permissions differ; or
- Settings are written to another user context.

If simulator connectivity requires elevation, the application and simulator
may need matching privilege levels.

Use elevated access only when necessary.

---

## 18. Multiple Monitors

Before saving an advanced workspace:

1. Connect all intended displays.
2. Configure Windows display arrangement.
3. Confirm scaling on each display.
4. Launch USAFCACARS.
5. Open Workspace Manager.
6. Arrange panels.
7. Save the layout.
8. Restart USAFCACARS.
9. Confirm the layout restores.

If a monitor is later removed, USAFCACARS should recover windows to an
available display.

Use Workspace Reset when a window cannot be found.

---

## 19. Logs and Settings

The exact log and settings locations may vary by build.

Possible locations include:

```text
%LOCALAPPDATA%\USAFCACARS
```

```text
%APPDATA%\USAFCACARS
```

```text
Documents\USAFCACARS
```

or an application-relative folder for portable builds.

Use Windows Run:

```text
%LOCALAPPDATA%
```

and search for:

```text
USAFCACARS
```

Before sharing logs:

- Remove passwords;
- Remove full tokens;
- Remove private chat;
- Remove private voice information;
- Remove API keys;
- Remove unrelated personal information; and
- Share only the relevant portion.

---

## 20. Common Installation Problems

### Installer Does Not Start

Check:

- Windows version;
- 64-bit architecture;
- Official download source;
- Checksum;
- Antivirus alert;
- File permissions;
- Download completion; and
- Whether Windows has blocked the file.

### Application Does Not Start

Check:

- Required .NET Desktop Runtime;
- WebView2 Runtime;
- Missing DLLs;
- Interrupted installation;
- Stale running process;
- Windows Event Viewer;
- Application logs; and
- Whether the portable package was fully extracted.

### Missing Web Content

Check:

- WebView2 Runtime;
- Internet connection;
- Firewall;
- Proxy or VPN;
- DNS;
- TLS inspection;
- System date and time; and
- WebView cache.

### SimConnect Does Not Connect

Check:

- Simulator is running;
- Aircraft is fully loaded;
- Correct simulator version;
- SimConnect dependency;
- Matching privilege level;
- Stale client process;
- Add-on aircraft compatibility; and
- Release notes.

### Login Fails

Check:

- Internet access;
- Official website;
- Correct credentials;
- Correct API environment;
- Account status;
- Application version;
- Server availability; and
- Whether a mandatory update exists.

### Audio Devices Missing

Check:

- Windows sound settings;
- Microphone permission;
- Device connection;
- Bluetooth state;
- Exclusive-mode lock;
- Selected device;
- Application restart; and
- Driver updates.

### Window Opens Off-Screen

Use:

- Workspace Manager Reset;
- Windows `Win + Shift + Arrow`;
- Display reconnect;
- Layout reset;
- Settings reset where instructed.

### Antivirus Reports the Installer

Do not bypass the warning automatically.

1. Confirm the source.
2. Verify the checksum.
3. Review the exact detection.
4. Scan with the installed security product.
5. Report a possible false positive to USAFC support.
6. Wait for confirmation before adding an exclusion.

---

## 21. Installation Support Request

Use this template:

```markdown
## USAFCACARS Version

Example: 1.0.4 Alpha

## Package

Installer / MSI / Portable ZIP

## Package Filename

Example: USAFCACARS-Setup-1.0.4.exe

## Download Source

Official USAFC website / Official GitHub release

## SHA-256 Result

Paste the hash or state whether it matched.

## Windows Version

## Error Message

Paste the exact error.

## Installation Step

State where the failure occurred.

## Previous Version

State whether another version was installed.

## Required Components

- .NET Desktop Runtime:
- WebView2 Runtime:
- Microsoft Flight Simulator:
- SimConnect:

## Logs

Attach only sanitized excerpts.

## Screenshots

Attach if useful.

## Privacy Confirmation

- [ ] I removed passwords, tokens, API credentials, private communications,
      and sensitive personal data.
```

Submit non-sensitive installation defects through GitHub Issues.

Submit account-specific, private, privacy, or security matters through the
official USA Flight Club support system.

---

## 22. Administrator and Developer Installation

This public guide is for the desktop release.

Server and development setup may require:

- phpVMS;
- Laravel;
- PHP;
- Composer;
- MySQL;
- Apache or another supported web server;
- .NET SDK;
- Visual Studio or compatible build tools;
- SimConnect SDK or runtime components;
- Module migrations;
- Environment configuration;
- Local development certificates;
- API configuration; and
- Source repository access.

Do not place:

- Production credentials;
- `.env` files;
- Database exports;
- Signing keys;
- API secrets; or
- Private source code

inside the public USAFCACARS Releases repository.

Development installation instructions should remain in the private source
repository or authorized developer documentation.

---

## 23. Release Maintainer Installation Checklist

Before publishing a release:

- [ ] Build version is correct.
- [ ] Installer version is correct.
- [ ] Release notes are complete.
- [ ] Alpha status is clearly shown.
- [ ] Supported simulators are listed.
- [ ] Required .NET runtime is listed.
- [ ] WebView2 requirement is listed.
- [ ] SimConnect requirement is listed.
- [ ] Installer was tested on a clean Windows profile.
- [ ] Portable build was tested after extraction.
- [ ] Upgrade from the previous version was tested.
- [ ] Uninstall was tested.
- [ ] Repair was tested where supported.
- [ ] No secrets are included.
- [ ] No `.env` file is included.
- [ ] No private logs are included.
- [ ] No development bypass is enabled.
- [ ] Package was scanned.
- [ ] SHA-256 checksums were generated.
- [ ] Third-party license files are included.
- [ ] Privacy, Security, and Support links are current.
- [ ] Official download links work.
- [ ] The live-map link works.
- [ ] The application displays the correct version.
- [ ] The application starts and closes cleanly.

---

## 24. Related Documents

- [README](../README.md)
- [License](../LICENSE)
- [Changelog](../CHANGELOG.md)
- [Privacy Notice](../PRIVACY.md)
- [Security Policy](../SECURITY.md)
- [Support Guide](../SUPPORT.md)
- [Third-Party Notices](../THIRD_PARTY_NOTICES.md)
- [Alpha Testing Guide](ALPHA-TESTING.md)

---

## 25. Official Links

- **USA Flight Club:** [https://usaflightclub.net](https://usaflightclub.net)
- **Official Downloads:** [https://usaflightclub.net/downloads](https://usaflightclub.net/downloads)
- **USAFCACARS Live Map:** [https://usaflightclub.net/usafcacars/live](https://usaflightclub.net/usafcacars/live)
- **Latest GitHub Release:** [View latest release](../../../releases/latest)
- **GitHub Issues:** [View issues](../../../issues)
- **Alpha Testing Guide:** [ALPHA-TESTING.md](ALPHA-TESTING.md)

---

## 26. Final Reminder

Install USAFCACARS only from an official USA Flight Club source.

Verify release checksums, read the release notes, close all active flights
before updating, and remember that version 1.0.4 remains an alpha development
release.

```text
Copyright © 2026 USA Flight Club.
All rights reserved.

USAFCACARS is proprietary software.
```
