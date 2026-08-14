<p align="center">
  <a href="https://github.com/Joverit5/Frutii/releases/latest">
    <img src="https://github.com/user-attachments/assets/4d6623b3-67a1-4141-839e-fef2490330b5" alt="Frutii" width="200">
  </a>
</p>

<h3 align="center">A social gaming platform for ROMs</h3>

<p align="center">
  <a href="https://github.com/Joverit5/Frutii/releases"><img src="https://img.shields.io/badge/version-0.3.9--alpha-7c3aed?label=latest" alt="Latest Release"/></a>
  <a href="https://github.com/Joverit5/Frutii"><img src="https://img.shields.io/badge/platform-Windows-blue" alt="Windows"/></a>
  <a href="https://github.com/Joverit5/Frutii/blob/main/LICENSE"><a href="LICENSE"><img src="https://img.shields.io/badge/license-proprietary-lightgrey" alt="Proprietary license"/></a></a>
  <a href="https://github.com/Joverit5/Frutii"><img src="https://img.shields.io/badge/built%20with-C%2B%2B%20%2B%20React-purple" alt="Built with C++ + React"/></a>
</p>

<p align="center">
  <a href="#download">Download</a> ·
  <a href="#requirements">Requirements</a> ·
  <a href="#what-frutii-does">Features</a> ·
  <a href="#reporting-a-bug">Report a bug</a> ·
  <a href="#roadmap">Roadmap</a> ·
  <a href="#faq">FAQ</a>
</p>

---

**Frutii** turns a folder of ROMs into a library worth looking at. It scans your collections, finds the artwork, launches games in its own built-in emulator, tracks RetroAchievements while you play, and keeps your save states as real screenshots you can jump back into — all in a Frutiger Aero interface built for a couch, a controller, and a big screen.

> [!IMPORTANT]
> **This repository is Frutii's download page.** It hosts releases, issues and discussions. The application's source code is developed privately and is not published here.

> [!NOTE]
> Frutii is in **alpha**. It is a native Windows desktop application, not a web app. Expect bugs and missing pieces — [reporting them](#reporting-a-bug) is the fastest way to get them fixed.

---

## Download

Grab the latest build from **[Releases](https://github.com/Joverit5/Frutii/releases/latest)**.

| File | What it is |
|---|---|
| **`Frutii-Setup.exe`** | Recommended. Installs per user into `%LOCALAPPDATA%\Frutii` with **no admin prompt**, creates Start Menu and optional desktop shortcuts, and silently installs the Microsoft Edge WebView2 Runtime if your machine doesn't have it. |
| `frutii_portable.zip` | No installer. Unzip anywhere and run `frutii_host.exe`. You have to install the WebView2 Runtime yourself if it's missing. |

Installing over an existing version **upgrades in place** and keeps your library, saves, save states, screenshots and settings.

> [!WARNING]
> The installer is not code-signed yet, so Windows SmartScreen will show a blue *"Windows protected your PC"* dialog. Click **More info → Run anyway**. Signing costs money that an alpha doesn't have; that's the whole reason.

---

## Requirements

| | |
|---|---|
| **OS** | Windows 10 or later, 64-bit |
| **GPU** | OpenGL 3.3 capable |
| **RAM** | 4 GB minimum · 8 GB+ if you emulate GameCube, Wii, PS2 or 3DS |
| **Disk** | ~150 MB for the app, plus your ROMs, the libretro cores you install and the artwork cache |
| **Runtime** | Microsoft Edge WebView2 — the installer sets it up for you |

---

## What Frutii does

### Your library, scanned and watched
Point Frutii at as many ROM folders as you like and they become one library, with the console detected per file. The folders stay **watched in real time** — add, rename or delete a ROM and the library updates on its own, no rescan button.

### Artwork that shows up by itself
Icons and grid art come from SteamGridDB, with an IGDB screenshot fallback for titles that have no icon. Everything is cached on disk so it's fetched once.

### A built-in emulator
Frutii ships **its own libretro frontend** as a separate process, so a core crash can never take the launcher down.

- Cores download **on demand** the first time you launch a game on a console you haven't played yet — scanning never downloads anything
- Curated default core per console, with alternatives you can switch to
- 4 controllers with hot-plug, per-console button mapping shared with external emulators, touch/stylus support for DS
- SRAM plus 10 save state slots, screenshots, integer scaling and letterboxing
- CRT and scanline shaders, rewind, fast-forward and slow motion
- A **System Files** manager that tells you which BIOS each console needs and validates what you import by checksum

### An in-game overlay
Press **ESC** mid-game for a Wii/3DS-style menu: the frame freezes and you get Resume, Save, Load, Screenshot, Achievements and Exit — with real thumbnails of each save slot, so you pick the state you can actually see.

### RetroAchievements, live
Connect your RetroAchievements account and achievements unlock **while you play**, with a badge toast and a jingle in-game. Unlocks earned on another device — RetroArch, a console, another PC — are picked up too and show in the same feed.

### Save states you can find again
Every slot of every game in one grid, each with the real capture from the moment you saved, timestamped. Pick one and the game boots straight into it.

---

## Screenshots

<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/a172a425-70e4-4064-8dcd-9b17e0c3b16b" />

<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/33339964-b0b9-43b1-b0ef-55696d3ab79c" />

<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/b861bed2-4fef-44b1-85b4-6955411bc86d" />

<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/7ae5d4b5-68b4-4cda-9d1c-552db6dbe1a7" />

<!--
  Paste screenshots here: drag the image into a GitHub issue comment or the
  release description, copy the generated user-attachments URL, and drop it in
  as <img src="..." width="820">. Suggested set:
    1. Home screen with the console channels
    2. A collection with artwork
    3. The in-game overlay (ESC menu) over a real game
    4. Achievements page
-->

---

## Updating

Frutii checks this repository's releases when it starts and tells you when a newer build is out. Download the new `Frutii-Setup.exe` and run it over your current install — your data is untouched.

---

## Your data

Your library, artwork cache, presets, saves, save states and screenshots live in Frutii's own data directory, **not** inside the install folder. Uninstalling Frutii does not delete your games or your progress. There's a Backup & Restore panel in the app that packs all of it into a single file you can move to another machine.

---

## Reporting a bug

Open an **[issue](https://github.com/Joverit5/Frutii/issues/new/choose)**. Two files make the difference between a report that gets fixed and one that doesn't — both sit in the install folder (`%LOCALAPPDATA%\Frutii` by default):

- **`frutii_host.log`** — the launcher
- **`frutii_emu.log`** — the emulator, including the core's own output
- **`*-crash-*.dmp`** — written automatically if something crashed; the log line right before the crash gives you the exact path

Drag them into the issue. Include your Windows version, your GPU, and the game and console if it only happens with one.

---

## Roadmap

Frutii is being built offline-first: everything that lives on your machine has to be solid before anything is shared with anyone else.

**Working today** — library and collections, artwork, the built-in emulator with cores, input profiles and BIOS management, the in-game overlay, RetroAchievements with in-game unlocks and hardcore mode, save state manager, shaders, rewind, fast-forward, backup and restore, per-user installer.

**Next** — Vulkan rendering for the heavy 3D consoles, an overlay for external emulators, multi-disc support and cheats.

**After that** — the social layer, in this order: a Frutii account, profiles, friends and presence, notifications, a feed, chat, and finally netplay (delay-based first, rollback later). The account is deliberately **additive**: losing it never costs you your library, saves, states, screenshots or RetroAchievements progress.

---

## FAQ

**Does Frutii come with games?**
No. Frutii ships no ROMs, no ISOs and no BIOS files. You point it at content you already own.

**Does it bundle emulator cores?**
No. Cores are downloaded from the official libretro buildbot the first time you need one, and you can manage or remove them in the Emulation panel.

**Can I use my existing emulators instead?**
Yes. Consoles that don't have a solid native path yet — GameCube, Wii, PS2, 3DS — can launch through your own standalone emulator, and Frutii writes the controller mapping as an override instead of touching your global config.

**Is the source code available?**
Not currently. Frutii is developed in a private repository during alpha.

**Is it on Steam / Linux / macOS / Android?**
No. Windows only for now.

**Something looks broken after an update.**
Check the log files above and open an issue — include the version you upgraded *from*.

---

## License

Frutii is **free to download and use** for personal use.

The source code is private and is not distributed with the binaries. The releases published here are provided as-is, with no warranty. Redistribution, repackaging or resale of the installer is not permitted.

© 2026 Frutii. All rights reserved.

Frutii is not affiliated with Nintendo, Sony, Microsoft, SEGA, RetroAchievements, SteamGridDB, IGDB or the libretro project. All trademarks belong to their respective owners.

---

## Credits

- **Inspired by** the Nintendo Wii, the Nintendo 3DS and Miiverse
- **Design language** Frutiger Aero — Wii Shop Channel, 3DS Home Menu
- **Built on** SDL3, OpenGL, WebView2, libretro, rcheevos, NanoVG, React
- **Artwork data** SteamGridDB and IGDB · **Achievements** RetroAchievements

---

<p align="center">
  Made with ❤️ by the Frutii Team
</p>
