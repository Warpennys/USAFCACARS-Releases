# USAFCACARS Third-Party Notices

**Last updated:** August 6, 2026  
**Current documented release:** 1.0.4 Alpha  
**Software status:** Proprietary software in active alpha development

USAFCACARS is proprietary software developed for USA Flight Club.

This document identifies third-party software, platforms, services, data
sources, libraries, runtimes, and other materials that may be included with,
required by, linked from, or used by USAFCACARS.

> [!IMPORTANT]
> The proprietary USAFCACARS license applies only to USAFC-owned software,
> documentation, graphics, branding, and other original materials.
>
> Third-party components remain subject to their own licenses, notices,
> attribution requirements, terms of service, acceptable-use policies, and
> privacy practices.

> [!NOTE]
> USAFCACARS is in active alpha development. Dependencies may change between
> releases. The package manifests and release artifacts for a specific build
> are the authoritative technical inventory for that build.

---

## 1. Purpose of This Document

This file is intended to:

- Identify third-party components used by USAFCACARS;
- Preserve required copyright and attribution notices;
- Distinguish USAFC proprietary materials from third-party materials;
- Direct users to applicable third-party licenses and terms;
- Document external services used by the application;
- Help maintainers review release-license obligations; and
- Prevent a third-party license from being incorrectly applied to the entire
  USAFCACARS project.

This file does not replace the full license text supplied by a third-party
component.

Where a dependency requires its license text to be distributed, that text
should be included in the release package under a directory such as:

```text
licenses/
```

or:

```text
THIRD-PARTY-LICENSES/
```

---

## 2. USAFCACARS Proprietary Status

USAFCACARS, including the desktop application, USAFCACARS API module,
USAFC-owned source code, user-interface design, documentation, graphics,
concept artwork, and branding, is proprietary software.

The presence of open-source or separately licensed components does not make
USAFCACARS itself open source.

The USAFCACARS module Composer metadata should use:

```json
"license": "proprietary"
```

See the repository [LICENSE](LICENSE) file for the proprietary USAFCACARS
license.

---

## 3. Required Release Review

Before publishing a release, maintainers must generate the actual dependency
inventory from the release source.

### .NET and NuGet

Run from the USAFCACARS solution directory:

```powershell
dotnet list package
dotnet list package --include-transitive
```

Where supported, also review vulnerable and outdated packages:

```powershell
dotnet list package --vulnerable
dotnet list package --outdated
```

Review all:

```text
*.csproj
packages.lock.json
Directory.Packages.props
Directory.Build.props
```

### PHP and Composer

Run from the phpVMS project directory:

```powershell
composer show
composer show --direct
composer licenses
composer audit
```

Review:

```text
composer.json
composer.lock
Modules/USAFCACARS/composer.json
```

### JavaScript and Web Assets

Review any applicable:

```text
package.json
package-lock.json
yarn.lock
pnpm-lock.yaml
composer.json
public vendor directories
module asset manifests
```

### Release Package

Inspect the final installer and portable archive for:

- Bundled DLLs;
- Native libraries;
- Runtime files;
- JavaScript libraries;
- Fonts;
- Icons;
- Audio files;
- Map assets;
- Chart assets;
- Documentation;
- License files; and
- Provider attribution.

Do not rely only on source manifests. The final distributed package must also
be inspected.

---

# Known Platforms and Frameworks

The following platforms and frameworks are known or expected to support
USAFCACARS. Exact versions may vary by release.

## 4. Microsoft .NET

USAFCACARS is a Windows desktop application built with Microsoft .NET.

Possible components include:

- .NET runtime;
- .NET Desktop Runtime;
- Windows Presentation Foundation;
- Base Class Library;
- Windows interoperability APIs; and
- Other Microsoft runtime components.

Microsoft .NET is provided under Microsoft's applicable license terms.

Official information:

- [https://dotnet.microsoft.com](https://dotnet.microsoft.com)
- [https://github.com/dotnet](https://github.com/dotnet)

The installed runtime version required by a particular build should be listed
in that release's notes.

---

## 5. Windows Presentation Foundation

USAFCACARS uses Windows Presentation Foundation for its Windows desktop user
interface.

WPF is part of the Microsoft .NET ecosystem and remains governed by
Microsoft's applicable license terms.

Official information:

[https://github.com/dotnet/wpf](https://github.com/dotnet/wpf)

---

## 6. Microsoft Edge WebView2

USAFCACARS may use Microsoft Edge WebView2 for:

- Embedded maps;
- Horizon Explorer;
- Charts;
- Weather pages;
- Airport information;
- Web-based panels; and
- Other embedded browser content.

WebView2 is provided under Microsoft's applicable license and distribution
terms.

Official information:

[https://developer.microsoft.com/microsoft-edge/webview2/](https://developer.microsoft.com/microsoft-edge/webview2/)

Users may be required to install the Microsoft Edge WebView2 Runtime.

Third-party websites opened inside WebView2 remain subject to their own
terms, licenses, security practices, and privacy notices.

---

## 7. Microsoft Flight Simulator and SimConnect

USAFCACARS may connect to Microsoft Flight Simulator through SimConnect.

Potential supported simulator products include:

- Microsoft Flight Simulator 2020; and
- Microsoft Flight Simulator 2024.

Microsoft Flight Simulator, SimConnect, simulator SDK materials, trademarks,
and related components are owned by Microsoft and their respective
licensors.

USAFCACARS is not affiliated with, endorsed by, or sponsored by Microsoft
unless expressly stated in writing.

Official information:

- [https://www.flightsimulator.com](https://www.flightsimulator.com)
- Microsoft Flight Simulator SDK documentation supplied through Microsoft's
  authorized channels

Any SimConnect managed wrapper or native interoperability package included
with a release must be listed separately in the generated package inventory.

---

## 8. phpVMS

The USAFCACARS server-side module integrates with phpVMS.

phpVMS is a separate project and remains governed by its own license and
project terms.

Official information:

- [https://www.phpvms.net](https://www.phpvms.net)
- [https://github.com/phpvms](https://github.com/phpvms)

USAFCACARS does not claim ownership of phpVMS.

The USAFCACARS module remains proprietary even though it operates within a
separately licensed phpVMS installation.

---

## 9. Laravel

The USAFCACARS phpVMS module operates within the Laravel framework used by
phpVMS.

Laravel is a separate open-source project and remains governed by its
applicable license.

Official information:

- [https://laravel.com](https://laravel.com)
- [https://github.com/laravel/framework](https://github.com/laravel/framework)

Laravel's license does not apply to proprietary USAFCACARS source code merely
because USAFCACARS uses Laravel APIs.

---

## 10. PHP

The USAFCACARS API module runs on PHP through the USA Flight Club phpVMS
environment.

PHP is distributed under the PHP License.

Official information:

- [https://www.php.net](https://www.php.net)
- [https://www.php.net/license/](https://www.php.net/license/)

---

## 11. Composer

Composer may be used to install and manage PHP dependencies.

Composer is a separate project and remains governed by its applicable
license.

Official information:

- [https://getcomposer.org](https://getcomposer.org)
- [https://github.com/composer/composer](https://github.com/composer/composer)

Composer package licenses must be reviewed from the actual `composer.lock`
used for each release.

---

## 12. NuGet

NuGet may be used to obtain and manage .NET dependencies.

NuGet itself and each NuGet package are governed by their applicable terms
and licenses.

Official information:

- [https://www.nuget.org](https://www.nuget.org)
- [https://github.com/NuGet](https://github.com/NuGet)

A package appearing on NuGet does not automatically mean it may be
redistributed without conditions. Review each package license.

---

# Mapping, Airport, Weather, and Aviation Data

## 13. OpenStreetMap

USAFCACARS may use map data derived from OpenStreetMap.

OpenStreetMap data is made available under the Open Data Commons Open
Database License, subject to its applicable attribution requirements.

Required attribution generally includes:

```text
© OpenStreetMap contributors
```

Official information:

- [https://www.openstreetmap.org/copyright](https://www.openstreetmap.org/copyright)
- [https://www.openstreetmap.org](https://www.openstreetmap.org)

Attribution must remain visible where required by the map implementation.

---

## 14. CARTO Basemap Tiles

USAFCACARS currently uses or may use CARTO basemap styling or tile services,
including dark basemap presentation.

CARTO services and assets remain subject to CARTO's applicable terms,
licenses, and attribution requirements.

Official information:

- [https://carto.com](https://carto.com)
- [https://carto.com/legal/](https://carto.com/legal/)

Where required, the map should display attribution for both CARTO and
OpenStreetMap contributors.

Do not copy or redistribute tile archives outside the provider's allowed use.

---

## 15. Leaflet, MapLibre, or Other Mapping Libraries

USAFCACARS may use a browser mapping library such as:

- Leaflet;
- MapLibre GL JS;
- A compatible movement or animation library; or
- Another map-rendering component.

Only libraries actually present in the release should be listed in the final
release package.

Potential official sources:

- Leaflet: [https://leafletjs.com](https://leafletjs.com)
- MapLibre GL JS: [https://maplibre.org](https://maplibre.org)

The current source and lock files must be reviewed before attributing a
specific mapping library to a build.

---

## 16. OurAirports

USAFCACARS may use airport information derived from OurAirports.

OurAirports data remains subject to the terms and licensing information
published by OurAirports.

Official information:

- [https://ourairports.com](https://ourairports.com)
- [https://ourairports.com/data/](https://ourairports.com/data/)

The actual data files and their stated license must be reviewed before
redistribution.

---

## 17. OpenStreetMap Overpass API

USAFCACARS may query OpenStreetMap data through the Overpass API or compatible
services.

Overpass services remain subject to provider usage limits and policies.

Official information:

- [https://wiki.openstreetmap.org/wiki/Overpass_API](https://wiki.openstreetmap.org/wiki/Overpass_API)

Applications must avoid excessive automated requests and should use caching
where appropriate.

---

## 18. Aviation Charts

USAFCACARS may display or link to aviation charts.

Chart providers may include government, public, licensed, or separately
authorized sources.

Charts must not be copied, bundled, modified, or redistributed unless the
provider permits it.

The chart viewer should preserve all required:

- Copyright notices;
- Effective dates;
- Source notices;
- Disclaimers; and
- Attribution.

USAFCACARS charts are for flight simulation only and must not be relied upon
for real-world navigation.

---

## 19. Weather Data

USAFCACARS may display weather information from one or more weather providers.

Weather data may include:

- METAR;
- TAF;
- Radar;
- Satellite;
- Clouds;
- Wind;
- Temperature;
- Pressure;
- Precipitation;
- Visibility;
- Lightning;
- SIGMET; and
- AIRMET information.

Each provider remains subject to its own:

- Terms of service;
- Attribution rules;
- API limits;
- Redistribution restrictions;
- Caching rules; and
- Privacy policy.

Only actual providers used by the release should be named in the final
provider list.

Do not copy proprietary Windy tiles, artwork, scripts, or service data unless
USAFC holds the necessary authorization.

A visual design inspired by a provider does not grant the right to copy that
provider's assets.

---

# Aviation Networks and External Traffic

## 20. VATSIM

USAFCACARS may display or interact with publicly available VATSIM network
information where permitted.

VATSIM names, services, data, and trademarks remain owned by their respective
owners and are subject to VATSIM's terms and policies.

Official information:

[https://vatsim.net](https://vatsim.net)

USAFCACARS is not affiliated with or endorsed by VATSIM unless expressly
stated.

---

## 21. IVAO

USAFCACARS may display or interact with IVAO network information where
permitted.

IVAO names, services, data, and trademarks remain owned by their respective
owners and are subject to IVAO's terms and policies.

Official information:

[https://www.ivao.aero](https://www.ivao.aero)

USAFCACARS is not affiliated with or endorsed by IVAO unless expressly
stated.

---

## 22. ADS-B and Live Aviation Data

USAFCACARS may display live aviation traffic from an authorized ADS-B or
aviation-data provider.

Such data may be subject to:

- API restrictions;
- Display-only requirements;
- Attribution;
- Rate limits;
- Geographic restrictions;
- Delayed-data requirements;
- Noncommercial-use limitations; and
- Redistribution restrictions.

The exact provider and required notices must be added before enabling the
feature in a public release.

Do not assume that publicly visible ADS-B data may be copied, archived, or
redistributed without limitation.

---

# Communications, Community, and Media

## 23. Voice and Audio Libraries

USAFCACARS may use third-party audio libraries for:

- Microphone capture;
- Audio playback;
- Device enumeration;
- Voice communications;
- Audio testing;
- Music playback;
- Radio streams; and
- Audio visualization.

Each included audio package must be listed from the actual NuGet or native
dependency inventory.

Required license files must be included in the release package.

---

## 24. Discord

USAFCACARS may link to or integrate with Discord for community features.

Discord is a separate service governed by Discord's terms and privacy policy.

Official information:

- [https://discord.com](https://discord.com)
- [https://discord.com/terms](https://discord.com/terms)
- [https://discord.com/privacy](https://discord.com/privacy)

USAFCACARS is not affiliated with or endorsed by Discord unless expressly
stated.

---

## 25. GitHub

GitHub may be used to:

- Host public release documentation;
- Distribute release packages;
- Publish checksums;
- Receive issue reports;
- Publish changelogs; and
- Manage release metadata.

GitHub is a separate service governed by GitHub's applicable terms and
privacy practices.

Official information:

- [https://github.com](https://github.com)
- [https://docs.github.com/en/site-policy](https://docs.github.com/en/site-policy)

Release packages downloaded from GitHub may generate logs or other data under
GitHub's policies.

---

## 26. Music and Radio Content

USAFCACARS may provide controls for user-selected local media or authorized
radio streams.

USAFC does not grant rights to copyrighted music, broadcasts, station logos,
album artwork, or other third-party media.

Users and maintainers are responsible for complying with:

- Copyright law;
- Streaming-provider terms;
- Station requirements;
- Public-performance restrictions;
- Recording restrictions; and
- Redistribution restrictions.

Do not bundle commercial music or copyrighted artwork in a USAFCACARS
release without authorization.

---

# Fonts, Icons, Images, and Visual Assets

## 27. Fonts

USAFCACARS may include or reference third-party fonts.

Before distribution, maintainers must verify:

- Desktop embedding rights;
- Web embedding rights;
- Redistribution rights;
- Modification rights;
- Attribution requirements; and
- Whether the font license file must be included.

Do not copy commercial font files into a public repository or installer
without permission.

System fonts supplied by Windows remain governed by Microsoft's terms.

---

## 28. Icons and Graphics

Third-party icons, photos, screenshots, maps, airport diagrams, chart
thumbnails, or other graphics must be documented with:

- Creator or provider;
- Source;
- License;
- Required attribution;
- Modification status; and
- Distribution permission.

USAFC-owned concept images and custom application graphics remain proprietary
USA Flight Club materials unless explicitly identified otherwise.

---

## 29. Aircraft Names, Logos, and Trademarks

Aircraft manufacturer names, aircraft model names, simulator names, airline
names, network names, logos, and other trademarks belong to their respective
owners.

Their appearance in USAFCACARS is for identification or simulation purposes
and does not imply endorsement.

Do not bundle protected logos, liveries, manuals, or aircraft assets without
authorization.

---

# Dependency Inventory

## 30. Release-Specific Package Table

Before publishing a release, replace or supplement this section with the
actual dependency inventory generated from the source and release package.

| Component | Version | Source | License | Bundled | Required notice |
|---|---:|---|---|---|---|
| Microsoft .NET Desktop Runtime | Release-specific | Microsoft | Microsoft terms | Maybe | Review runtime distribution terms |
| Microsoft Edge WebView2 Runtime | Release-specific | Microsoft | Microsoft terms | Maybe | Review distribution terms |
| SimConnect component/wrapper | Release-specific | Microsoft/NuGet | Package-specific | Maybe | Include package license |
| phpVMS | Site-specific | phpVMS | Project-specific | Server-side | Preserve project license |
| Laravel Framework | Site-specific | Laravel | MIT | Server-side | Preserve copyright/license |
| Composer packages | Lock-file-specific | Packagist | Package-specific | Server-side | Generate with `composer licenses` |
| NuGet packages | Project-specific | NuGet | Package-specific | Maybe | Generate from project manifests |
| Map library | Build-specific | Project-specific | Project-specific | Maybe | Preserve attribution/license |
| Basemap/data provider | Service-specific | Provider | Provider terms | No/Maybe | Visible attribution |
| Weather provider | Service-specific | Provider | Provider terms | No | Required attribution |
| Audio library | Build-specific | NuGet/native | Package-specific | Maybe | Include license |
| Other native DLLs | Build-specific | Provider | Provider-specific | Maybe | Include license |

Do not leave inaccurate package names or versions in a production release.

---

## 31. Example License Directory

A release package may use:

```text
USAFCACARS/
├── USAFCACARS.exe
├── LICENSE
├── PRIVACY.md
├── SECURITY.md
├── SUPPORT.md
├── THIRD_PARTY_NOTICES.md
└── THIRD-PARTY-LICENSES/
    ├── dotnet-notice.txt
    ├── laravel-license.txt
    ├── map-library-license.txt
    ├── audio-library-license.txt
    └── other-package-license.txt
```

The actual filenames should identify the corresponding dependency.

---

## 32. Attribution Display

Attribution may need to appear:

- In the application About page;
- In Settings;
- In the Help and Support Center;
- In a Third-Party Notices dialog;
- On the live map;
- Under weather layers;
- In chart viewers;
- In the README;
- In the installer;
- In the installed application directory; and
- In release documentation.

Attribution must be readable and must not be hidden merely because the
application uses a dark interface.

---

## 33. Third-Party Service Availability

USAFC does not control third-party services.

A provider may:

- Change its API;
- Change its license;
- Change its terms;
- Change its prices;
- Limit requests;
- Require new credentials;
- Require new attribution;
- Remove data;
- Experience outages; or
- Discontinue service.

A feature depending on that provider may be changed, suspended, or removed.

---

## 34. Third-Party Privacy and Security

Third-party providers may receive technical request information such as:

- IP address;
- User agent;
- Requested airport;
- Requested map tile;
- Requested weather layer;
- Requested chart;
- Requested audio stream;
- Request timestamp; and
- Provider account or API credential information.

Review [PRIVACY.md](PRIVACY.md) for USAFCACARS privacy information.

Review [SECURITY.md](SECURITY.md) for reporting security concerns.

---

## 35. No Endorsement

References to a third-party product, service, network, aircraft, provider, or
organization do not imply:

- Sponsorship;
- Partnership;
- Certification;
- Approval;
- Endorsement; or
- Affiliation

unless USAFC expressly states otherwise in writing.

---

## 36. No Real-World Aviation Use

Third-party aviation data displayed through USAFCACARS is intended only for
virtual aviation and flight simulation.

It must not be relied upon for:

- Real-world navigation;
- Real-world flight planning;
- Real-world dispatch;
- Real-world air traffic control;
- Real-world weather decisions;
- Aircraft maintenance;
- Emergency response; or
- Any safety-critical purpose.

---

## 37. Maintainer Checklist

Before every release:

- [ ] Run `dotnet list package --include-transitive`.
- [ ] Run `composer licenses`.
- [ ] Review `composer.lock`.
- [ ] Review all `.csproj` files.
- [ ] Review JavaScript lock files.
- [ ] Inspect bundled native DLLs.
- [ ] Inspect installer contents.
- [ ] Identify all fonts.
- [ ] Identify all icons and images.
- [ ] Identify map providers.
- [ ] Identify weather providers.
- [ ] Identify chart providers.
- [ ] Identify audio libraries and streams.
- [ ] Include required license texts.
- [ ] Include required copyright notices.
- [ ] Display map attribution.
- [ ] Display weather attribution.
- [ ] Confirm chart redistribution permission.
- [ ] Confirm installer redistribution rights.
- [ ] Confirm WebView2 distribution method.
- [ ] Confirm SimConnect distribution rights.
- [ ] Remove unused dependencies.
- [ ] Review dependency security advisories.
- [ ] Update this file.
- [ ] Update the release notes.
- [ ] Confirm the proprietary USAFCACARS license remains unchanged.

---

## 38. Reporting a Missing Notice

If a required third-party attribution or license notice appears to be
missing, submit a private or public documentation report as appropriate.

For a normal documentation correction:

[Open a GitHub issue](../../issues/new/choose)

For a legal, licensing, or confidential concern, use the official USA Flight
Club website:

[https://usaflightclub.net](https://usaflightclub.net)

Suggested request title:

```text
USAFCACARS Third-Party License Notice
```

---

## 39. Related Documents

- [README](README.md)
- [License](LICENSE)
- [Changelog](CHANGELOG.md)
- [Privacy Notice](PRIVACY.md)
- [Security Policy](SECURITY.md)
- [Support Guide](SUPPORT.md)
- [Alpha Testing Guide](docs/ALPHA-TESTING.md)

---

## 40. Copyright Notice

```text
USAFCACARS and original USA Flight Club materials:
Copyright © 2026 USA Flight Club.
All rights reserved.

Third-party software and materials:
Copyright belongs to the respective owners and is governed by the applicable
third-party licenses and terms.
```

USAFCACARS is proprietary software. Third-party licenses apply only to their
respective components.
