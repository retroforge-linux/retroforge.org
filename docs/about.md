---
title: About
description: Acknowledgements and licensing for RetroForge.
---

# About

RetroForge is an immutable, A/B-updatable aarch64 Linux distribution for Qualcomm Snapdragon handhelds, built on SteamOS 3 "Holo" packages and focused entirely on retro emulation.

## Acknowledgements

RetroForge stands on the work of others.

**[ROCKNIX](https://rocknix.org/)**
:   Showed that a console-style handheld experience on this hardware was a real target.

**[Nova-Deck](https://github.com/Nova-Deck/os-build)**
:   RetroForge's build system, A/B update path, installer, hardware layer and most of its tooling started as a copy of Nova-Deck's os-build, adapted for retro emulation.

**[OpenABL](https://github.com/OpenHandheldCollective/OpenABL/)**
:   OpenABL is the foundation everything here stands on. These handhelds ship an Android bootloader that will not load an ordinary Linux boot flow, and solving that gates every other problem. Beyond that: the kernel enablement, device trees and device-by-device bring-up this class of hardware depends on.

**And more**
:   Valve and Collabora, whose aarch64 Arch port RetroForge builds on, and the Mesa, gamescope, InputPlumber, OpenGamepadUI and RAUC projects.

## Licence

RetroForge's own code is **GPL-2.0-or-later**. Third-party material keeps its own licence: kernel patches are GPL-2.0-only and GRUB patches GPL-3.0-or-later.

Proprietary Qualcomm firmware is never committed to RetroForge's source. It is fetched from pinned, checksummed sources at build time.
