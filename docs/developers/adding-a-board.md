---
title: Adding a board
description: The data a new handheld needs to boot RetroForge.
---

# Adding a board

A new board takes three pieces of data, all discovered automatically by the build:

1. **A device tree** under `kernel/dts/qcom/`.
2. **A device profile** under `rootfs/overlay/usr/lib/retroforge/devices/`, plus its `model` case in `device-env`.
3. **An InputPlumber config**, if the gamepad is not already covered by an existing one.

An unmatched board falls through to `defaults.conf` and still boots, so you can bring a device up step by step.

Come and say hello on [Discord](https://discord.gg/ZfgXY3W2F9) before you start: someone may already be working on your device.
