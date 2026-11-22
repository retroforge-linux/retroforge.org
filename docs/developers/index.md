---
title: Developers
description: How RetroForge is put together.
---

# Developers

RetroForge is an immutable, A/B-updatable aarch64 Linux distribution built on SteamOS 3 "Holo" packages, for Qualcomm mobile silicon: **SM4450, SM6115, SM8250, SM8550, SM8650 and SM8750**.

- The root is **read-only**, bootstrapped from packages into a sealed Btrfs image.
- Updates are **RAUC bundles** installed to the inactive slot, behind a custom `retroforge-bootctl` bootloader backend.
- The build is **unified**: one image for every supported SoC, and one kernel carrying the union of drivers and device trees.
- There is no Steam client, no x86 emulation and no Android container.

## Boot flow

```mermaid
flowchart LR
  XBL[XBL] --> ABL[OpenABL]
  ABL --> ESP[ESP GRUB<br/>picks slot A or B]
  ESP --> S2[Slot GRUB<br/>picks the board]
  S2 --> K[Unified kernel<br/>+ board DTB]
  K --> R[Read-only root]
```

## Source layout

The build lives in the `os-build` repository. Its tree follows the order a build happens in: assemble a root, lay it onto a disk, ship it to a device.

| Path | Purpose |
|---|---|
| `rootfs/` | What is inside a root: the package closure, the bootstrap, and the seal, trim and guard steps |
| `rootfs/overlay/` | Files injected into every root, mirroring the device's filesystem |
| `image/` | Turning a root into partitions: the A/B layout, initramfs and SD card assembler |
| `ota/` | Signed RAUC bundles and their publishing |
| `installer/` | The internal-storage installer |
| `packages/` | PKGBUILDs for what RetroForge patches or version-bumps |
| `kernel/` | The unified kernel: config fragments, patches and device trees |
| `firmware/` | Fetch-and-verify recipes for vendor firmware |
| `boot/` | UEFI boot: the ESP GRUB and per-slot configs |
| `tests/` | The offline test suites |

<div class="grid cards" markdown>

-   :lucide-hammer: __[Building](building.md)__

    Build an image or a kernel yourself.

-   :lucide-circuit-board: __[Adding a board](adding-a-board.md)__

    Bring up a new handheld.

</div>
