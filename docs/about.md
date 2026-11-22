---
title: About
description: Acknowledgements and licensing for RetroForge.
---

# About

RetroForge is an immutable, A/B-updatable aarch64 Linux distribution for Qualcomm Snapdragon handhelds, built on SteamOS 3 "Holo" packages and focused entirely on retro emulation.

## Acknowledgements

RetroForge stands on the work of others.

**[OpenGamepadUI](https://opengamepadui.readthedocs.io/en/latest/)**
:   The gamepad-first shell you see from the moment RetroForge boots. OpenGamepadUI gives RetroForge its library, menus, quick bar and on-screen keyboard, and its plugin system is how RetroForge adds emulators, ROMs and handheld settings on top. Without it there would be no console-like experience to build.

**[ROCKNIX](https://rocknix.org/)**
:   The majority of RetroForge's hardware bring-up comes from ROCKNIX. Its kernel patches, device trees and device-by-device enablement are what make these handhelds work at all: display panels, controllers, audio, power and suspend, board by board across every supported Snapdragon chip. ROCKNIX also showed that a console-style handheld experience on this hardware was a real target.

**[Nova-Deck](https://github.com/Nova-Deck/os-build)**
:   RetroForge's build system, A/B update path, installer, hardware layer and most of its tooling started as a copy of Nova-Deck's os-build, adapted for retro emulation.

**[OpenABL](https://github.com/OpenHandheldCollective/OpenABL/)**
:   OpenABL is the foundation everything here stands on. These handhelds ship an Android bootloader that will not load an ordinary Linux boot flow, and solving that gates every other problem.

**And more**
:   Batocera and Armada. Valve and Collabora, whose aarch64 Arch port RetroForge builds on, and the Mesa, gamescope, InputPlumber and RAUC projects.

## Licence

RetroForge's own code is **GPL-2.0-or-later**. Third-party material keeps its own licence: kernel patches are GPL-2.0-only and GRUB patches GPL-3.0-or-later.

Proprietary Qualcomm firmware is never committed to RetroForge's source. It is fetched from pinned, checksummed sources at build time.
