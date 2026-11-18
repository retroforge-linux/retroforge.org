---
title: Updates
description: How RetroForge updates itself without risking your device.
---

# Updates

RetroForge updates itself over Wi-Fi. You never have to reflash a card to get a new version.

## How it works

RetroForge keeps two copies of the system, called slot A and slot B. You run from one while an update is written to the other:

1. The update is downloaded and its signature is checked. Anything not signed by RetroForge is refused.
2. It is installed to the slot you are **not** running from, so a failed download or a power cut cannot damage the system you are using.
3. On the next boot the device tries the new slot.
4. If the new slot does not boot properly, the device rolls back to the previous one automatically.

The system itself is read-only, so an update always replaces it with exactly what was tested. Your settings and games live separately and carry over.

## Channels

| Channel | For |
|---|---|
| Stable | Everyone. Tested releases. |
| Beta | Trying upcoming changes before they reach stable. |
| Nightly | Testers. Built every night from the latest code, and may break. |

Updates are not checked until you have finished first-boot setup.
