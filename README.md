# Gallagheri Race Engineer for F1 26

Gallagheri Race Engineer for F1 26 is a Windows app that listens to F1 25 (with the 2026 Season Pack) over UDP telemetry and gives you race engineer radio calls in a pre-recorded cloned voice: race strategy and box calls, gaps and rivals, tyres, fuel and damage, flags and safety cars, corner coaching, and practice and qualifying programmes.

Every line is pre-recorded, so there is no live speech generation and the app is light on the GPU. The radio is one-way: the engineer talks, you drive.

This repository holds the voice packs and the release notes; the installer is on Patreon and Ko-fi. The source code is private.

## Downloads

| Download | Link |
|---|---|
| Installer (Windows, version 1.0.0) | On Patreon: https://www.patreon.com/gallagheri/posts/f1-26-f1tv-for-175615083, or Ko-fi: https://ko-fi.com/s/3444a1561d |
| Voice packs | [voices release](https://github.com/gallagheri/RaceEngineer/releases/tag/voices) |
| Release notes | [Release notes 1.0](https://github.com/gallagheri/RaceEngineer/releases/tag/v1.0.0) |
| User guide | [User guide](USER_GUIDE.md) |

The installer includes one voice (Gianluca). The second voice (James) is installed from inside the app, in Settings > Voice; you do not need to download the voice pack files by hand.

The installer is not code-signed. Windows SmartScreen shows "Windows protected your PC": click More info, then Run anyway. It installs for your Windows user only and needs no admin rights.

## Requirements

- Windows 10 (1809 or later) or Windows 11, 64-bit.
- F1 25 with the 2026 Season Pack DLC. The base game's 2025 grid is not supported in 1.0.
- Offline sessions: races, practice and qualifying.
- F1 25 telemetry: UDP Telemetry On, UDP Format 2026, IP 127.0.0.1, port 20778. With SimHub, keep the game on 20777 and forward to 127.0.0.1:20778.

## Support and news

News, feedback and support are on Patreon: https://www.patreon.com/cw/gallagheri

## Licence

Copyright Gallagheri. All rights reserved. The app is for Gallagheri's patrons (https://www.patreon.com/cw/gallagheri); the source code is private and the files here may not be redistributed or modified.

Race Engineer is an independent fan project, not affiliated with or endorsed by Electronic Arts, Codemasters or Formula 1.
