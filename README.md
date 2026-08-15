<div align="center">

<img src=".github/banner.png" alt="CarbonCopy — Real-time folder backup for Windows" width="100%">

# CarbonCopy

### Real-time folder backup for Windows

<a href="https://github.com/KVRNL/carbon-copy/releases/latest"><img alt="Latest version" src="https://img.shields.io/github/v/release/KVRNL/carbon-copy?display_name=tag&label=version&color=F5A623&labelColor=0d0d0f&style=for-the-badge"></a>
<a href="https://github.com/KVRNL/carbon-copy/releases"><img alt="Downloads" src="https://img.shields.io/github/downloads/KVRNL/carbon-copy/total?label=downloads&color=F5A623&labelColor=0d0d0f&style=for-the-badge"></a>
<img alt="Platform" src="https://img.shields.io/badge/platform-Windows%2010%20%7C%2011-0d0d0f?style=for-the-badge&labelColor=0d0d0f">
<img alt="Price" src="https://img.shields.io/badge/price-FREE-F5A623?style=for-the-badge&labelColor=0d0d0f">
<a href="./LICENSE"><img alt="License" src="https://img.shields.io/badge/license-Proprietary%20Freeware-0d0d0f?style=for-the-badge&labelColor=0d0d0f"></a>

<br>

Mirrors the folders you choose to up to three backup drives the moment anything changes. Deleted files stay recoverable, and it runs quietly in your system tray.

### **[⬇&nbsp; Download CarbonCopy — free at kvrnl.io](https://kvrnl.io/products/carbon-copy/)**

</div>

<br>

---

## What it does

CarbonCopy watches the folders you care about and instantly mirrors any change to up to three backup destinations — an external drive, a network drive, or another folder. A background safety-net sweep catches anything missed while you were offline.

Deleted files are kept in a dated recycle bin so accidents are recoverable, and your source folders are only ever read, never modified. Free to use — claim your license key and download it here.

## Features

- **Real-time mirroring, ~1-second sync**
- **Up to three backup destinations**
- **Recoverable deletes with a Recycle Bin**
- **Source folders are never modified**

## Download &amp; install

CarbonCopy is **completely free**. Downloads run through a free KVRNL account so every
install gets its own license key.

1. Go to **[kvrnl.io/products/carbon-copy/](https://kvrnl.io/products/carbon-copy/)**
2. Create a free account — email verification, nothing else
3. Claim your license key — instant, no waiting
4. Download and install

> [!NOTE]
> CarbonCopy isn't code-signed yet, so Windows SmartScreen may warn you on first run.
> Click **More info → Run anyway**. Code signing is on the roadmap.

## Your license key

- **Free, one per product**, issued from your KVRNL account.
- **A key activates on one machine.** The first device to activate it claims it.
- **Switching computers?** Hit **Release device** on your
  [account page](https://kvrnl.io/account/) and the key is free to use again.
- Keys are checked over HTTPS at launch. See [Privacy](#privacy).

## Requirements

- **Windows 10 or 11** (64-bit)
- A free [KVRNL account](https://kvrnl.io/signup/) for your license key

## Privacy

CarbonCopy sends KVRNL only what's needed to validate your license: **the key, the
product name, and a hardware ID**. No telemetry, no analytics, no tracking, and
none of your files. Full policy: **[kvrnl.io/privacy](https://kvrnl.io/privacy/)**

## What's new

**v2.0.13** — 2026-08-14
  - Fixed tooltips running off the side of the screen. The explanation text wasn't wrapping at all, so longer ones stretched into a single endless line and got cut off before you could finish reading them. They now wrap to a readable width and break into short paragraphs.
  - Fixed the destination dropdown in the Recycle Bin being white text on white — unreadable. Windows draws drop-downs in its own light colours unless an app replaces them outright, which CarbonCopy hadn't. The same fix covers the file list's column headers and row highlighting.

**v2.0.12** — 2026-08-14
  - Fixed the "hasn't backed up in X days" warning that wouldn't go away. A single file that couldn't be copied — a mail file, a browser database, anything another program had open — was enough to stop CarbonCopy ever recording a successful backup again. The warning then counted up forever on a folder that was, in fact, being backed up perfectly every half hour, and nothing you did would clear it. It now clears itself the moment a backup succeeds.
  - Fixed the same warning coming straight back after restarting. The time of each successful backup was never actually being saved to disk, so every restart loaded the old date and put the warning back up.
  - Files that can't be copied are now reported on their own, as a plain warning that names how many and points you at the log — instead of being invisible and quietly poisoning the health of the whole folder.
  - Warnings can now be dismissed. Advisory items have an X, and dismissing one keeps it away for a week rather than for the two minutes it took the next health check to put it back. Anything that means a folder genuinely isn't protected — a disconnected drive, a missing folder — deliberately can't be hidden.
  - Completely rebuilt the Settings screen. It was one long scroll where the two settings anyone actually changes sat in the same pile as the deletion ceiling and the debounce timer. It's now organised into pages down the side — General, Backups, Deleted files, Safety limits, Speed, Your setup — grouped by what you're trying to do rather than by which part of the code they belong to.
  - Every setting now explains itself. Hover anything and a tooltip appears immediately, in plain English, telling you what it does and how to choose — including what the sensible default is and when you'd want something different.
  - New How to use page inside Settings, replacing the separate help window, so the instructions no longer lock the rest of the app while you read them.
  - New Report a bug page. Describe the problem in your own words and it goes straight to KVRNL, with your version, drive status, settings and recent log entries attached automatically — so a report doesn't turn into twenty questions. The technical details are optional and you can see exactly what's included.
  - New About page with your version, the machine your licence is tied to, and links to your account.

**v2.0.11** — 2026-07-24
  - Fixed the app freezing after adding a folder. The first backup was running on the same thread that draws the window, so CarbonCopy locked up with a spinning cursor until it finished — which on a large folder could be several minutes. It now runs in the background as it always should have, and the window stays responsive throughout.
  - Fixed the same freeze in every other place it could happen: turning a destination on, changing where a folder backs up to, switching between Mirror and Archive, removing a folder and its copies, and browsing the Recycle Bin.
  - Setting up a destination and opening the add-folder window no longer stall while they check drives. Anything that reads from a disk now happens in the background, so a slow or disconnected network drive can't hold the window hostage.

**v2.0.10** — 2026-07-24
  - Mirror and Archive are now properly explained before you pick one. Clicking the setting used to flip it the instant you touched it — it now opens a window laying out both options, what each one does to your files, and which one this folder currently uses, with a Save and a Cancel.
  - Switching a folder from Archive back to Mirror now tells you what it would cost first — it counts the files the archive has been holding on to that your folder no longer has, and shows you the number before you commit.
  - The Protection screen now spells the setting out ('Mirror — remove it from the backup too') instead of showing a single word you'd have to guess at.
  - Added a note making clear that CarbonCopy's Mirror is not the same thing as Google Drive's 'Mirror files' setting. They share a word and mean completely different things — Google's decides whether your cloud files are stored on your PC, ours decides what happens to a backup copy when you delete the original.
  - CarbonCopy now warns you if you pick a cloud folder (Google Drive, OneDrive, Dropbox) to back up. Those files often live online rather than on your PC, so copying them means downloading your entire cloud account — worth knowing before it starts, not after. It also warns if you try to use one as a destination, where everything you back up would get uploaded again.
  - Rewrote the in-app help. It was still describing two destinations and buttons that no longer exist.

**v2.0.9** — 2026-07-24
  - New Protection screen. Instead of a settings page, the app now opens on a plain answer to 'am I actually backed up?' — every folder you protect, its status at every destination, and when it was last verified.
  - Adding a folder now shows you what's about to happen first. You pick the folder, pick where it goes (nothing is ticked for you any more), and then see the file count, the size, what's being skipped, and — importantly — a warning listing anything already in that destination folder that would be moved to the Recycle Bin. Nothing is copied or removed until you press Start.
  - CarbonCopy now recognises your backup drives by their hardware ID rather than their drive letter. If a drive comes back as E: instead of D:, it spots it and carries on. If a different drive takes that letter, it refuses to write to it and asks you first — previously it could have started backing up onto the wrong disk.
  - If you rename or move a folder you're backing up, CarbonCopy now finds it and asks whether to follow it. Before, it went quiet and simply stopped backing that folder up, while the dashboard still looked perfectly healthy.
  - New safety ceiling on removals. If a background check ever wants to remove far more than usual — because a folder moved, a drive mounted oddly, or something went wrong — it stops, touches nothing, shows you the exact list of files, and asks. Adjustable in Settings.
  - New weekly heartbeat: if a folder hasn't backed up successfully in seven days, for any reason at all, you're told.
  - New Issues tab. Everything that's wrong, in plain English, with buttons that fix it — instead of an error log nobody opens.
  - New per-folder choice between Mirror and Archive. Mirror keeps the backup matching your folder (what it has always done). Archive means the backup only ever grows, so nothing you've ever had can disappear, even if you delete the original.
  - New Recycle Bin browser. Removed files have always been recoverable, but until now the only way to reach them was through File Explorer. You can now browse and restore them inside the app.
  - New 'Verify backup' button — checks every file against the backup and gives you a straight count rather than a status light.
  - Removing a folder now asks whether to keep the backed-up copies (the default) or remove them, instead of a bare Yes/No.
  - Destinations are now tested properly when you set one up — CarbonCopy writes a real file to prove it can, checks free space, and warns you if the folder isn't empty. A read-only network drive used to pass the old check and then fail every single copy quietly.
  - After an update, CarbonCopy now waits a couple of minutes before its first background check, and tells you once if anything works differently. Your folders, destinations and settings are carried over exactly as they were.

Full history → **[kvrnl.io/changelog/carbon-copy](https://kvrnl.io/changelog/carbon-copy/)**

## Documentation

Setup guides and how-tos → **[kvrnl.io/docs/carbon-copy](https://kvrnl.io/docs/carbon-copy/)**

## Support

- 🐛 **Found a bug?** [Open an issue](https://github.com/KVRNL/carbon-copy/issues/new/choose)
- 💬 **Question?** [kvrnl.io/contact](https://kvrnl.io/contact/)
- ❓ **FAQ** → [kvrnl.io/faq](https://kvrnl.io/faq/)

## License

**Proprietary freeware — free to use, not open source.**

This repository hosts the installer releases, documentation, and license for
CarbonCopy. **The application source code is not published.** See
**[LICENSE](./LICENSE)** for the full terms.

---

<div align="center">
<br>

**[kvrnl.io](https://kvrnl.io)** &nbsp;·&nbsp; **[All products](https://kvrnl.io/products/)** &nbsp;·&nbsp; **[Changelog](https://kvrnl.io/changelog/)** &nbsp;·&nbsp; **[Contact](https://kvrnl.io/contact/)**

<sub>© 2026 <b>KVRNL</b> — an AI-powered software studio shipping free desktop tools.</sub>

</div>
