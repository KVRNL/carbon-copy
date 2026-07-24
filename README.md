# CarbonCopy

**Real-time folder backup for Windows.** CarbonCopy quietly mirrors the folders you care about to up to three destinations — an external drive, a network drive, another folder — and keeps them in sync the moment files change. It runs in the system tray and stays out of your way.

> Made by [KVRNL](https://kvrnl.io)

---

## What it does

- **Live mirroring** — the instant you save, rename, or delete a file in a watched folder, the change is copied to your backups (usually within about a second).
- **Up to three destinations** — keep a copy on, say, an external SSD *and* a network drive, so you always have a spare. Each folder you protect can go to any combination of them.
- **Mirror or Archive, per folder** — Mirror keeps the backup matching the folder. Archive means the backup only ever grows, so nothing you've ever had can disappear.
- **Knows your drives by hardware ID** — if a drive comes back on a different letter, CarbonCopy recognises it and carries on. If a *different* drive takes that letter, it refuses to write to it and asks you.
- **Follows folders that move** — rename or move a folder you're protecting and CarbonCopy notices, tells you where it went, and offers to keep going. Your existing backup stays exactly where it is.
- **A ceiling on removals** — if a background check ever wants to remove far more than usual, it stops, touches nothing, shows you the list, and asks first.
- **Recoverable deletes** — anything removed from a backup goes to a dated Recycle Bin folder inside the destination, kept for a retention period you choose, and browsable and restorable from inside the app.
- **Verify backup** — check every file against the backup and get a straight answer.
- **Tells you when something's wrong** — including the catch-all: if a folder hasn't backed up in a week, for any reason at all, you hear about it.
- **Automatic updates** — checks for new versions hourly and installs them silently in the background.
- **Tray app** — lives by the clock, starts with Windows (optional), and never nags you.

CarbonCopy is a **one-way mirror**: your source folders are the source of truth and are only ever **read** — never modified, renamed, or deleted, and nothing is ever written inside them. All writing and deleting happens inside the destination folders.

---

## Download & install

1. Grab the latest **`CarbonCopy-x.y.z-Setup.exe`** from the [**Releases**](../../releases/latest) page.
2. Run it. Windows may show a blue *"Windows protected your PC"* screen because the app isn't code-signed — click **More info → Run anyway**.
3. Follow the installer. It installs per-user (no admin needed) and can create a desktop shortcut and start with Windows.

That's it — CarbonCopy opens and drops into your system tray.

---

## Quick start

CarbonCopy walks you through this the first time you open it.

1. On the **Destinations** tab, click **Set up…** and choose where backups should go. CarbonCopy checks it can actually write there, tells you how much room is left, and warns you if the folder isn't empty.
2. On the **Protection** tab, click **+ Add folder**. Choose the folder, choose which destinations it goes to, then review exactly what's about to happen — file count, size, what's excluded, and anything already at the destination that would be moved to the Recycle Bin.
3. Click **Start backing up**. Nothing is copied or removed until you do.

Your files are mirrored into a subfolder named after each source folder (e.g. source `C:\Work` lands at `D:\Backup\Work\…`), so multiple sources never collide.

---

## How it works

**Real time plus a safety net.** A file watcher copies changes the instant they happen. On top of that, a periodic *sweep* re-checks every file (size and modified time) and fixes anything that drifted — edits made while CarbonCopy was closed, or while a destination was unplugged.

**The Protection screen** shows each folder you're protecting and its status at every destination, so the question "am I actually backed up?" has an answer you can see at a glance.

**Source folders.** Only ever read. Use **Pause** to stop watching a folder temporarily, or **Remove** to stop backing it up — you're asked whether to keep the copies (the default) or remove them.

**Destinations.** Up to three. The coloured dot shows status — green = connected and syncing, orange = paused or needs checking, red = not connected, grey = turned off. If a drive drops out, the destination pauses and nothing is removed from the backup; it catches up when the drive is back.

**Deleting files and the Recycle Bin.** When a file is removed from a source, its backup copy isn't erased — it's moved into a `Recycle Bin` folder inside the destination, organised by date, and kept for the **retention period** (set in Settings). Browse and restore them from **Destinations → Recycle Bin**.

**When a lot is about to be removed.** A single sweep won't remove more than 500 files, or 10% of a destination, without stopping to ask (both adjustable in Settings). It shows you the exact list first. This catches the cases that matter — a folder that moved, a drive that mounted differently, or something going wrong — before they cost you anything.

---

## Settings

- **Sweep interval** — how often the background safety scan runs.
- **Recycle Bin retention** — how long removed files are kept before being cleared.
- **Exclude patterns** — folder/file names to skip (e.g. `node_modules`, `.git`, `Thumbs.db`).
- **Removal ceiling** — how much a single sweep may remove before asking you.
- **Stale backup warning** — how long a folder can go without a successful backup before you're told.
- **Debounce and concurrent copies** — fine-tune responsiveness and speed.
- **Start with Windows**, notifications, and **Export / Import** to move your setup to another PC.

---

## Automatic updates

CarbonCopy checks this repository's Releases about every hour. When a newer version is published, it downloads the installer and updates itself silently in the background — closing, upgrading, and relaunching to the tray with no interruption. If an update changes how something works, you're told once, on the first launch afterwards. You can also trigger a check anytime via **Check for Updates** on the Settings tab.

---

## Running in the background

Closing the window doesn't quit CarbonCopy — it tucks into the system tray and keeps backing up. **Right-click the tray icon** for *Open Dashboard*, *Pause All*, or *Exit*.

Anything that goes wrong is listed in plain English on the **Issues** tab, with buttons that fix it. The underlying logs live at:

```
%AppData%\CarbonCopy\errors.log     failures
%AppData%\CarbonCopy\sweep.log      every removal, recorded before it happens
```

Your settings live at `%AppData%\CarbonCopy\config.json`.

---

## Notes

- **Windows / .NET.** Self-contained build — no separate .NET install required.
- **One-way mirror.** Destinations are made to match the source. Under Mirror, a file that exists in a destination's mirror folder but no longer in the source is moved to the Recycle Bin; a destination file that differs from the source is replaced by the source version. Under Archive, nothing is ever removed.
- **Not code-signed (yet).** SmartScreen will warn on first run — *More info → Run anyway*.

---

© KVRNL
