---
date_published: 2026-05-10
date_modified: 2026-05-10
canonical_url: https://ike.network/dashboard.html
---

# IKE Dashboard

The IKE Dashboard is one window for working with Komet. It keeps Komet versions installed side by side and current, keeps the knowledge bases in `~/Solor` current, and opens any knowledge base in any Komet version as an independent application. Its first screen, **Notices**, lists what needs attention, each with one action: a newer build of a knowledge base, work not yet committed, a newer Komet.

## [#download](#download)Download

- [Download the IKE Dashboard for Mac](https://github.com/IKE-Network/ike-dashboard/releases/latest/download/IKE-Dashboard-osx-aarch64.pkg)[1] (Apple silicon)
- [Download the IKE Dashboard for Windows](https://github.com/IKE-Network/ike-dashboard/releases/latest/download/IKE-Dashboard-windows-x86_64.msi)[2] (64-bit)

Each link always fetches the newest version. Both are installers, as Komet’s are.

## [#install](#install)Install

### [#mac](#mac)Mac

1. Open the downloaded `IKE-Dashboard-osx-aarch64.pkg`.
2. Follow the installer. It puts **IKE Dashboard** in your Applications folder.
3. Open it from there.

The installer is signed with IKE’s Developer ID and notarized by Apple, so macOS opens it without warnings.

### [#windows](#windows)Windows

1. Open the downloaded `IKE-Dashboard-windows-x86_64.msi`.
2. Follow the installer. It installs the dashboard for you alone, with no administrator password, and adds **IKE Dashboard** to the Start menu.
3. Open it from the Start menu.

The Windows installer is not signed yet, so Windows SmartScreen may say *Windows protected your PC*. Choose **More info**, then **Run anyway**.

## [#updates](#updates)Updates

From then on the dashboard updates itself. When a newer version is published, the Notices screen offers it; **Update and restart** downloads it, checks it, and restarts the dashboard on it. Komets that are running are not affected.

## [#more](#more)More

- [Every release](https://github.com/IKE-Network/ike-dashboard/releases)[3], with its notes and checksums
- [Source and documentation](https://github.com/IKE-Network/ike-dashboard)[4]
- [Report a problem](https://github.com/IKE-Network/ike-issues/issues)[5]
