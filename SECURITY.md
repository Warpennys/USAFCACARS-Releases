# USAFCACARS Security Policy

**Last updated:** August 6, 2026  
**Current documented release:** 1.0.4 Alpha  
**Software status:** Proprietary software in active alpha development

USA Flight Club takes the security of USAFCACARS, its users, and its connected
services seriously.

This document explains:

- Which USAFCACARS versions are supported;
- How to report a suspected vulnerability;
- What information to include;
- What not to publish;
- How reports are reviewed;
- Which security areas are in scope;
- Which testing activities are not authorized; and
- The security expectations for releases, accounts, logs, telemetry, voice
  communications, and connected services.

> [!IMPORTANT]
> **Do not report a security vulnerability through a public GitHub issue,
> discussion, comment, screenshot, or social-media post.**
>
> Public disclosure may expose pilots, accounts, servers, application tokens,
> private communications, or USA Flight Club infrastructure before a fix is
> available.

> [!WARNING]
> Never include passwords, full authentication tokens, API keys, private keys,
> database credentials, production `.env` contents, private voice recordings,
> or unredacted personal information in a vulnerability report.

---

## 1. Reporting a Security Vulnerability

Report suspected vulnerabilities privately through the official USA Flight
Club website:

[https://usaflightclub.net](https://usaflightclub.net)

Use the subject or request title:

```text
USAFCACARS Security Report
```

If GitHub Private Vulnerability Reporting is enabled for this repository, it
may also be used.

Do not use a public GitHub issue for a security report.

### Include the following

Provide as much of the following information as safely possible:

- A clear summary of the issue;
- The affected USAFCACARS version;
- Whether the issue affects the desktop application, API module, website,
  live map, communications system, installer, update process, or another
  component;
- The affected operating system;
- Microsoft Flight Simulator version, if relevant;
- The aircraft or add-on involved, if relevant;
- The affected URL, API route, screen, or feature;
- Exact steps to reproduce;
- Expected behavior;
- Actual behavior;
- Security impact;
- Whether authentication is required;
- Whether administrator access is required;
- Whether the issue works against production, development, or both;
- Sanitized logs or screenshots;
- A proof of concept that does not expose secrets or harm users;
- Any suggested mitigation; and
- A safe method for follow-up contact.

### Do not include

Do not send:

- A real user's password;
- A full bearer token;
- A full session cookie;
- Private encryption or signing keys;
- Database dumps;
- Production environment files;
- Private pilot records;
- Unredacted support tickets;
- Private chat transcripts;
- Voice recordings without authorization;
- Unnecessary personal information;
- Large collections of downloaded data; or
- Exploit code designed to cause damage or persistence.

Replace sensitive values with placeholders such as:

```text
[REDACTED TOKEN]
[REDACTED EMAIL]
[REDACTED PILOT ID]
[REDACTED SERVER PATH]
```

---

## 2. Supported Versions

USAFCACARS is currently in alpha development.

Security fixes are generally applied to the newest available release.

| Version | Security support |
|---|---|
| 1.0.4 | Supported alpha baseline |
| Latest development release | Supported when distributed by USA Flight Club |
| 1.0.0–1.0.3 | Limited or unsupported unless specifically stated |
| Unofficial or modified builds | Not supported |
| Repackaged third-party distributions | Not supported |

Users should update to the newest authorized release when a security update is
published.

Older releases may remain downloadable for testing or rollback purposes, but
availability does not mean they continue to receive security fixes.

---

## 3. Scope

This policy applies to official USA Flight Club systems and components,
including:

- USAFCACARS Windows desktop application;
- USAFCACARS installer and portable packages;
- USAFCACARS update-checking system;
- USAFCACARS phpVMS/API module;
- USAFCACARS authentication;
- USAFCACARS live map;
- USAFCACARS flightboard;
- USAFCACARS ATC and TRACON systems;
- USAFCACARS voice communications;
- USAFCACARS airport, weather, and chart services;
- USAFCACARS aircraft-control integrations;
- USAFCACARS Passenger Operations;
- USAFCACARS Community and Support integrations;
- Official USAFCACARS GitHub release assets;
- Official USAFCACARS documentation; and
- Related USA Flight Club services that explicitly use the USAFCACARS system.

Official live map:

[https://usaflightclub.net/usafcacars/live](https://usaflightclub.net/usafcacars/live)

Official website:

[https://usaflightclub.net](https://usaflightclub.net)

---

## 4. High-Priority Vulnerability Categories

The following issues are especially important to report privately.

### Authentication and authorization

Examples:

- Login bypass;
- Token forgery;
- Session fixation;
- Session hijacking;
- Token leakage;
- Password exposure;
- Privilege escalation;
- Pilot-to-pilot account access;
- Pilot-to-administrator access;
- Unauthorized access to protected API routes;
- Unauthorized access to private crew rooms;
- Unauthorized access to support or administrative data; and
- Missing authorization checks on flight, PIREP, or communications actions.

### Remote code execution and unsafe file handling

Examples:

- Remote code execution;
- Arbitrary command execution;
- Unsafe deserialization;
- Malicious installer execution;
- Path traversal;
- Arbitrary file upload;
- Arbitrary file overwrite;
- Arbitrary file deletion;
- DLL hijacking;
- Untrusted plug-in loading;
- Unsafe archive extraction; and
- Update packages accepted without appropriate validation.

### API and server security

Examples:

- SQL injection;
- Command injection;
- Server-side request forgery;
- XML external entity processing;
- Insecure direct object references;
- Mass assignment;
- Missing request validation;
- Missing rate limits on sensitive routes;
- Cross-site request forgery affecting protected actions;
- Cross-site scripting;
- CORS misconfiguration;
- Sensitive error disclosure;
- Production debug mode exposure; and
- Unauthorized access to phpVMS or USAFCACARS data.

### Flight and PIREP integrity

Examples:

- Updating another pilot's flight;
- Finishing another pilot's PIREP;
- Duplicate PIREP submission;
- Forging a flight session;
- Starting a flight without an authorized bid;
- Modifying protected flight results;
- Bypassing aircraft or assignment rules;
- Tampering with flight completion;
- Altering landing-rate data without authorization; and
- Creating uncontrolled duplicate live sessions.

### Update and release security

Examples:

- Malicious or unsigned update substitution;
- Update-server impersonation;
- Insecure download redirection;
- Checksum mismatch;
- Release package tampering;
- Downgrade attacks;
- Mandatory-update bypass with security impact;
- Installer privilege escalation;
- Installation outside intended directories; and
- Exposure of signing material.

### Voice and communications security

Examples:

- Joining a private room without permission;
- Listening to private communications without authorization;
- Transmitting while muted;
- Microphone capture outside an active session;
- Local microphone-test audio sent to a room;
- Unauthorized recording;
- Voice-session impersonation;
- Participant identity spoofing;
- Room-token leakage; and
- Remote control of another user's audio state.

### Privacy and data exposure

Examples:

- Exposure of passwords or tokens;
- Public email-address disclosure;
- Private pilot-record disclosure;
- Private chat disclosure;
- Private support-ticket disclosure;
- Unintended voice recording;
- Sensitive logs accessible without permission;
- Database credentials in a release;
- `.env` files in a public package;
- Internal server paths exposed unnecessarily; and
- Public live-map fields exceeding the configured visibility policy.

### Desktop application security

Examples:

- Insecure credential storage;
- Tokens stored in plaintext without protection;
- Untrusted WebView navigation;
- JavaScript bridge abuse;
- Unsafe protocol handlers;
- Local privilege escalation;
- Sensitive data written to crash dumps;
- Insecure temporary files;
- Predictable local IPC endpoints;
- Insecure named pipes;
- Stale background processes retaining credentials; and
- Sensitive information exposed through debug logging.

### SimConnect and aircraft-control security

Examples:

- Commands sent to the wrong aircraft;
- Untrusted remote input reaching SimConnect;
- Aircraft controls activated without user action;
- Unsafe command replay;
- Cross-session aircraft control;
- Unauthorized remote control of simulator state;
- Add-on adapter loading from an untrusted location; and
- Simulator-control features operating outside the intended virtual
  environment.

USAFCACARS must never be used to operate or control a real aircraft or
real-world safety-critical system.

---

## 5. Out-of-Scope Reports

The following are generally not security vulnerabilities unless they create
a meaningful security impact:

- Visual defects;
- Spelling or grammar errors;
- Missing concept features;
- Feature requests;
- Normal alpha instability;
- Simulator incompatibility without a security impact;
- Unsupported aircraft behavior;
- Missing weather tiles;
- Public information intentionally displayed on the live map;
- Denial of service caused only by extremely unrealistic local resource use;
- Vulnerabilities in an unsupported or unofficial build;
- Reports based only on automated scanner output without verification;
- Clickjacking on pages that perform no sensitive action;
- Missing security headers without an exploitable consequence;
- Self-XSS requiring a user to paste code into a developer console;
- Username or email enumeration with no practical additional impact;
- Rate-limit suggestions on low-risk, non-sensitive functions;
- Issues requiring physical access to an already-unlocked computer;
- Social engineering without a technical vulnerability;
- Third-party service issues that do not affect USAFC systems; and
- General claims that alpha software may contain bugs.

Normal defects should be reported through the standard issue or support
process after removing sensitive information.

---

## 6. Unauthorized Testing

The following activities are not authorized:

- Accessing another user's account;
- Using stolen or guessed credentials;
- Extracting or downloading large amounts of data;
- Testing against accounts without permission;
- Disrupting production services;
- Denial-of-service testing;
- Flooding APIs, voice rooms, or map services;
- Sending malware;
- Establishing persistence;
- Modifying or deleting production data;
- Changing flight, PIREP, pilot, or administrative records;
- Recording private voice communications without permission;
- Intercepting another user's traffic;
- Social-engineering pilots, staff, or service providers;
- Attempting physical access;
- Publishing a vulnerability before coordinated remediation;
- Sharing private builds or source code without authorization;
- Testing third-party providers without their permission; and
- Using USAFC infrastructure as a platform to attack another system.

If a test could affect another user, stop and report the suspected issue
without continuing.

---

## 7. Safe Testing Guidelines

When investigating a suspected issue:

1. Use your own authorized account.
2. Use a test account when one is available.
3. Use the local development environment when practical.
4. Minimize the number of requests.
5. Avoid changing persistent records.
6. Stop after confirming the issue.
7. Do not retrieve more data than necessary.
8. Redact all secrets.
9. Preserve relevant timestamps.
10. Report privately.
11. Wait for guidance before additional testing.
12. Delete any inadvertently obtained private data after USAFC confirms it is
    no longer needed.

A proof of concept should demonstrate the issue with the least possible
impact.

---

## 8. Coordinated Disclosure

USAFC requests reasonable time to investigate and correct a valid report
before public disclosure.

Do not publicly disclose:

- The vulnerability;
- Exploit instructions;
- A proof of concept;
- A vulnerable endpoint;
- A leaked secret;
- Private correspondence;
- A patch that reveals the weakness; or
- A release package containing exploit material

until USAFC confirms that disclosure is appropriate or a reasonable
coordinated-disclosure period has passed.

USAFC may request additional time for complex issues involving:

- Multiple releases;
- Third-party providers;
- Simulator integrations;
- Installer or update replacement;
- Database migrations;
- Credential rotation;
- Voice infrastructure;
- Production deployment; or
- Member notification.

---

## 9. What to Expect After Reporting

USAFC aims to:

1. Acknowledge receipt of a clear report;
2. Confirm whether additional information is needed;
3. Reproduce and assess the issue;
4. Assign a severity;
5. Develop a mitigation or fix;
6. Test the correction;
7. Prepare an update or server-side remediation;
8. Notify affected users where appropriate;
9. Publish security information when safe; and
10. Credit the reporter when requested and appropriate.

Response times may vary because USAFCACARS is an independently developed
proprietary alpha project.

Submitting a report does not guarantee:

- Payment;
- A bounty;
- Public credit;
- A specific response deadline;
- Immediate remediation;
- Continued access to testing systems; or
- Acceptance of unauthorized testing.

---

## 10. Severity Considerations

USAFC may consider:

- Required access level;
- User interaction;
- Exploit complexity;
- Number of affected users;
- Confidentiality impact;
- Integrity impact;
- Availability impact;
- Flight or PIREP integrity;
- Administrative access;
- Credential or token exposure;
- Persistence;
- Scope across environments;
- Public exploitability;
- Third-party impact; and
- Whether a mitigation already exists.

Possible internal severity levels:

| Severity | General meaning |
|---|---|
| Critical | Broad compromise, remote code execution, administrator takeover, signing-key exposure, or severe production compromise |
| High | Account takeover, privilege escalation, protected-data exposure, or major integrity failure |
| Medium | Limited unauthorized access, meaningful data exposure, or constrained security bypass |
| Low | Limited impact, difficult exploitation, or defense-in-depth weakness |
| Informational | Hardening suggestion or report without demonstrated security impact |

---

## 11. Security Updates

Security updates may be delivered through:

- A new GitHub Release;
- The official USA Flight Club Downloads page;
- An application update notice;
- A server-side API update;
- A module update;
- A website update;
- Credential or token revocation;
- A configuration change; or
- Temporary disabling of an affected feature.

Official downloads:

[https://usaflightclub.net/downloads](https://usaflightclub.net/downloads)

Users should install security updates promptly.

A release may be marked mandatory when continued use of an older build would
create a security or compatibility risk.

---

## 12. Release Verification

Official release packages may include SHA-256 checksums.

PowerShell example:

```powershell
Get-FileHash .\USAFCACARS-Setup.exe -Algorithm SHA256
```

Compare the returned value with the checksum published in the official
release notes.

Do not install a package when:

- The checksum does not match;
- The package came from an unofficial source;
- The filename or publisher appears altered;
- The download redirects to an unexpected host;
- Windows reports an unexpected signature warning;
- The archive contains unexpected scripts or credentials; or
- The release is not listed by USA Flight Club.

---

## 13. Repository Security Rules

The public USAFCACARS Releases repository may contain:

- README documentation;
- LICENSE;
- CHANGELOG;
- Security and privacy documents;
- Alpha-testing documentation;
- Concept images;
- Public screenshots;
- Release notes;
- Checksums; and
- Official release packages attached as GitHub Release assets.

It must not contain:

- Proprietary source code unless explicitly authorized;
- Production `.env` files;
- Database dumps;
- Passwords;
- Authentication tokens;
- API keys;
- Private signing keys;
- Code-signing certificates;
- Server SSH keys;
- Private pilot data;
- Private communications;
- Unredacted diagnostic logs;
- Internal-only administrative tools;
- Production backups; or
- Third-party proprietary files without authorization.

Installers should normally be attached to GitHub Releases rather than
committed into normal Git history.

---

## 14. Secret Management

Secrets must not be hardcoded in:

- Desktop source code;
- PHP source code;
- JavaScript;
- Blade templates;
- XAML;
- Configuration committed to Git;
- Installer scripts;
- Test fixtures;
- Documentation;
- Screenshots;
- Crash reports; or
- Release packages.

Examples of secrets include:

- Database passwords;
- API keys;
- OAuth secrets;
- JWT signing secrets;
- Encryption keys;
- Webhook secrets;
- Private certificates;
- SMTP passwords;
- Storage credentials;
- Voice-service credentials; and
- Administrator bypass tokens.

Development and production secrets must remain separate.

If a secret is committed or released:

1. Treat it as compromised.
2. Revoke or rotate it immediately.
3. Remove it from active systems.
4. Review access logs.
5. Replace affected packages.
6. Do not rely only on deleting it from the latest commit.
7. Consider repository-history cleanup where appropriate.
8. Notify affected parties when necessary.

---

## 15. Authentication and Token Requirements

USAFCACARS authentication should follow these principles:

- Passwords are transmitted only over protected production connections;
- Passwords are never stored in plaintext by USAFCACARS;
- Full passwords are never logged;
- Full tokens are never logged;
- Tokens are validated on protected requests;
- Expired or revoked tokens are rejected;
- Logout clears the active session where supported;
- Pilot authorization is checked server-side;
- Administrator access is enforced server-side;
- Tokens are scoped and retained only as needed;
- Development credentials are never shipped in production packages; and
- Authentication errors do not reveal unnecessary internal details.

Client-side hiding of a button is not an authorization control.

---

## 16. API Security Requirements

The USAFCACARS API module should:

- Require authentication for protected routes;
- Verify that a pilot may access the requested object;
- Validate all input;
- Reject malformed identifiers;
- Validate numeric ranges;
- Prevent mass assignment;
- Use parameterized database access through Laravel;
- Limit sensitive error details;
- Protect against duplicate flight submissions;
- Prevent cross-pilot updates;
- Rate-limit sensitive endpoints where appropriate;
- Avoid global authentication weakening;
- Preserve phpVMS core security boundaries;
- Avoid editing vendor files;
- Log meaningful security events;
- Redact credentials and tokens; and
- Use HTTPS in production.

No phpVMS core or vendor modification should be required to bypass security
controls.

---

## 17. Desktop Application Security Requirements

The desktop application should:

- Use official API endpoints;
- Validate server responses;
- Use explicit network timeouts;
- Handle certificate failures safely;
- Avoid disabling TLS validation;
- Avoid loading executable content from untrusted locations;
- Restrict WebView navigation and bridges;
- Sanitize file and URL inputs;
- Store tokens using an appropriate protected mechanism;
- Avoid writing sensitive data to logs;
- Release audio and simulator resources on shutdown;
- Avoid untrusted DLL search paths;
- Verify update metadata;
- Avoid automatically executing downloaded files;
- Display clear errors without exposing secrets; and
- Separate development diagnostics from production behavior.

The application must not contain hidden administrative bypasses or test
credentials in public builds.

---

## 18. WebView and Horizon Explorer Security

Embedded browsing features should:

- Treat third-party pages as untrusted;
- Avoid exposing privileged application objects to arbitrary pages;
- Restrict navigation where needed;
- Validate custom URL schemes;
- Prevent arbitrary local-file access;
- Avoid injecting authentication tokens into third-party pages;
- Avoid enabling dangerous debugging features in production;
- Isolate downloads;
- Warn before opening executable files; and
- Clean up browser resources when tabs close.

A page opened in Horizon Explorer remains subject to the third party's own
security and privacy practices.

---

## 19. Voice Communications Security

Voice communications should:

- Verify room authorization server-side;
- Protect private crew rooms;
- Avoid exposing room tokens;
- Transmit only while intended;
- Respect mute and deafen controls;
- Keep microphone testing local;
- Avoid recording by default;
- Release audio devices on exit;
- Prevent participant impersonation;
- Protect signaling connections;
- Avoid logging private audio; and
- Provide clear connection status.

Any future recording or transcription feature should require separate review,
notice, authorization, and retention rules.

---

## 20. Live Map and Operational Data Security

The live map should expose only information intended by USAFC policy.

Public or member-visible fields should be reviewed for:

- Pilot name or display name;
- Pilot ID;
- Callsign;
- Aircraft type;
- Aircraft registration;
- Virtual position;
- Route;
- Departure;
- Arrival;
- Flight phase;
- Status;
- Altitude;
- Speed;
- Heading; and
- Controller information.

The live map must not expose:

- Passwords;
- Authentication tokens;
- Email addresses unless intentionally authorized;
- Private chat;
- Private voice data;
- Internal server paths;
- Database identifiers not needed publicly;
- Administrator-only notes; or
- Security-sensitive diagnostics.

---

## 21. Logging Requirements

Logs should help diagnose problems without creating a new security risk.

Logs may include:

- Application version;
- Startup status;
- API status;
- SimConnect status;
- Flight-session identifiers where necessary;
- Sanitized pilot identifiers;
- HTTP status codes;
- Error categories;
- Phase changes;
- Update results;
- Audio-device errors;
- WebView errors;
- Performance warnings; and
- Sanitized stack traces.

Logs must not include:

- Plaintext passwords;
- Full bearer tokens;
- Full session cookies;
- Database passwords;
- Private keys;
- Full private chat;
- Voice audio;
- Unnecessary personal data; or
- Sensitive environment configuration.

Repeated failures should be throttled to prevent log flooding.

---

## 22. Installer and Build Security

Release builds should:

- Be produced from an authorized source state;
- Use documented build commands;
- Exclude development secrets;
- Exclude local databases;
- Exclude temporary logs;
- Exclude debug credentials;
- Exclude unnecessary symbol or source files from public packages;
- Use controlled dependency versions;
- Generate a SHA-256 checksum;
- Record the version accurately;
- Be tested after packaging;
- Be scanned for malware;
- Be uploaded only through authorized accounts; and
- Preserve proprietary licensing notices.

Where code signing is used, signing keys must not be stored in the repository
or included in build artifacts.

---

## 23. Dependency Security

The project may depend on:

- Microsoft .NET;
- Microsoft Flight Simulator SimConnect;
- Microsoft Edge WebView2;
- Laravel;
- phpVMS;
- Composer packages;
- NuGet packages;
- Mapping libraries;
- Audio libraries;
- Weather or chart services; and
- Other third-party components.

Maintainers should:

- Track dependency versions;
- Review security advisories;
- Avoid abandoned or untrusted packages;
- Remove unused dependencies;
- Preserve third-party notices;
- Test updates;
- Avoid dependency confusion;
- Use official package sources; and
- Document material security changes.

Third-party licenses do not change the proprietary status of USAFCACARS.

---

## 24. Backup and Recovery Security

Backups may contain sensitive information.

Backups should:

- Be access-controlled;
- Be encrypted where appropriate;
- Be stored separately from public web files;
- Avoid public repository storage;
- Follow a retention schedule;
- Be tested for restoration;
- Be protected from unauthorized deletion;
- Avoid embedding secrets in filenames; and
- Be destroyed securely when no longer required.

A backup is not a substitute for version control, and version control is not
a substitute for a secure backup.

---

## 25. Security Checklist for Each Release

Before publishing a release, confirm:

- [ ] Version number is correct.
- [ ] Release channel is correct.
- [ ] Build came from the intended branch and commit.
- [ ] No passwords are present.
- [ ] No full tokens are present.
- [ ] No `.env` file is present.
- [ ] No database dump is present.
- [ ] No private key or signing certificate is present.
- [ ] No development bypass is enabled.
- [ ] Production TLS validation remains enabled.
- [ ] API endpoints use the intended production URL.
- [ ] Debug logging is appropriate for a public alpha build.
- [ ] Sensitive logs are excluded.
- [ ] WebView debugging is disabled where required.
- [ ] Update metadata is correct.
- [ ] Installer and portable package were tested.
- [ ] SHA-256 checksums were generated.
- [ ] Packages were scanned.
- [ ] Third-party notices are current.
- [ ] Privacy documentation matches actual behavior.
- [ ] Known security limitations are documented privately or publicly as
      appropriate.
- [ ] Security contact and reporting method work.
- [ ] Previous vulnerable packages are removed or clearly marked when
      necessary.
- [ ] Mandatory-update status is set when appropriate.

---

## 26. Security Checklist for Server Deployment

Before deploying the USAFCACARS module:

- [ ] Production debug mode is disabled.
- [ ] Production uses HTTPS.
- [ ] `.env` is outside the public repository.
- [ ] Database credentials are not exposed.
- [ ] API routes have correct middleware.
- [ ] Administrator routes require administrator authorization.
- [ ] Pilot routes enforce pilot ownership.
- [ ] Validation is enabled.
- [ ] Rate limits are reviewed.
- [ ] CORS settings are restricted appropriately.
- [ ] CSRF configuration is not weakened globally.
- [ ] File uploads are validated.
- [ ] Download paths do not expose physical server paths.
- [ ] Logs redact credentials.
- [ ] Migrations are non-destructive.
- [ ] Backups exist.
- [ ] Dependencies are current enough for deployment.
- [ ] Default or test credentials are removed.
- [ ] Storage permissions are correct.
- [ ] Public storage contains no private files.
- [ ] Security headers are reviewed.
- [ ] Error pages do not reveal sensitive internals.

---

## 27. Incident Response

If a security incident is suspected, maintainers should:

1. Preserve relevant evidence.
2. Restrict access to affected systems.
3. Revoke exposed tokens.
4. Rotate exposed credentials.
5. Disable affected features where necessary.
6. Identify affected versions and users.
7. Review server, application, and hosting logs.
8. Correct the vulnerability.
9. Test the fix.
10. Publish an updated release or server-side correction.
11. Notify affected users when appropriate.
12. Document the incident internally.
13. Review whether security and privacy documentation must change.
14. Remove or mark vulnerable release packages where appropriate.

Do not destroy evidence needed to understand the incident.

---

## 28. Security Advisories

When appropriate, a security advisory may include:

- Affected versions;
- Fixed version;
- Severity;
- General impact;
- Required user action;
- Workaround;
- Update link;
- Checksum;
- Credit; and
- Disclosure timeline.

An advisory should avoid publishing exploit details before users have had a
reasonable opportunity to update.

---

## 29. Researcher Recognition

USAFC may acknowledge a reporter who:

- Reports privately;
- Acts in good faith;
- Avoids user harm;
- Follows this policy;
- Provides a clear and useful report; and
- Allows reasonable remediation time.

Recognition is optional and may be withheld for privacy, safety, legal, or
operational reasons.

No bug-bounty payment is promised by this policy.

---

## 30. Good-Faith Security Research

USAFC appreciates good-faith reports that help protect users and systems.

To remain within the intended spirit of this policy:

- Test only what you are authorized to access;
- Avoid harm;
- Avoid unnecessary data access;
- Stop after confirming the issue;
- Report privately;
- Do not demand payment or threaten disclosure;
- Do not retain private data;
- Do not disrupt services; and
- Follow applicable law.

This policy does not grant permission to violate law, access controls,
third-party terms, or the proprietary USAFCACARS license.

It is not a blanket authorization to test production systems.

---

## 31. Contact

Submit security concerns privately through:

[https://usaflightclub.net](https://usaflightclub.net)

Request title:

```text
USAFCACARS Security Report
```

Include a safe contact method for follow-up.

Do not include passwords, full tokens, private keys, database credentials, or
unnecessary personal information.

---

## 32. Related Documents

- [README](README.md)
- [License](LICENSE)
- [Changelog](CHANGELOG.md)
- [Privacy Notice](PRIVACY.md)
- [Alpha Testing Guide](docs/ALPHA-TESTING.md)
- [Support Information](SUPPORT.md)
- [Third-Party Notices](THIRD_PARTY_NOTICES.md)

---

```text
Copyright © 2026 USA Flight Club.
All rights reserved.

USAFCACARS is proprietary software.
```
