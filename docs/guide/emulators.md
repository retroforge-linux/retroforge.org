---
title: Emulators, ROMs and BIOS
description: Which emulator runs each system, where its games go, and which BIOS files it needs.
---

# Emulators, ROMs and BIOS

Which emulator runs each system, where to put its games, and which BIOS or firmware files it needs.

<div class="grid cards" markdown>

-   :lucide-folder-open:{ .lg .middle } __`~/roms/<system>/`__

    ---

    **One folder per system.** Each game file becomes a card in the library. An `.m3u` playlist wins over the discs it lists, so a multi-disc game shows up once.

-   :lucide-hard-drive:{ .lg .middle } __`~/bios/`__

    ---

    **One flat folder for every BIOS.** No per-system subfolders: every file has its own name, so they never collide.

</div>

In the tables below, a BIOS is:

- **Required** if games do not start without it.
- **Optional** if games run on a built-in replacement without it.
- **None** if the emulator needs nothing.

## RetroArch

Libretro cores, installed with RetroArch.

| System | ROM folder | File types | BIOS in `~/bios` |
|---|---|---|---|
| Game Boy<br><small>armGBA core</small> | `~/roms/gb`{ style="white-space: nowrap" } | `gb` `zip` `7z` | Optional<br>`gb_bios.bin` |
| Game Boy Color<br><small>armGBA core</small> | `~/roms/gbc`{ style="white-space: nowrap" } | `gbc` `gb` `zip` `7z` | Optional<br>`gbc_bios.bin` |
| Game Boy Advance<br><small>armGBA core</small> | `~/roms/gba`{ style="white-space: nowrap" } | `gba` `zip` `7z` | Optional<br>`gba_bios.bin` |
| Super Nintendo<br><small>Snes9x core</small> | `~/roms/snes`{ style="white-space: nowrap" } | `sfc` `smc` `zip` | None |
| Nintendo 64<br><small>armN64 core (HLE)</small> | `~/roms/n64`{ style="white-space: nowrap" } | `z64` `n64` `v64` `zip` `7z` | None[^n64] |
| Mega Drive<br><small>Genesis Plus GX core</small> | `~/roms/md`{ style="white-space: nowrap" } | `md` `gen` `bin` `zip` | None |
| Mega CD<br><small>Genesis Plus GX core</small> | `~/roms/segacd`{ style="white-space: nowrap" } | `chd` `cue` | **Required**<br>`bios_CD_U.bin`, `bios_CD_E.bin` or `bios_CD_J.bin` |

[^n64]: armN64 writes its own `armN64/` cache folder into `~/bios`. Leave it there.

For Mega CD, any one region is enough. The launcher refuses the game when none is present.

## Microsoft

| System | Emulator | ROM folder | File types | BIOS in `~/bios` |
|---|---|---|---|---|
| Xbox | hakuX | `~/roms/xbox`{ style="white-space: nowrap" } | `iso` `xiso` `chd` | None (HLE) |

**Xbox.** hakuX needs no BIOS, MCPX ROM or hard-disk image. It takes XISO, full `.iso` (XGD1 to XGD3) and DVD `.chd` only.

## Nintendo

| System | Emulator | ROM folder | File types | BIOS in `~/bios` |
|---|---|---|---|---|
| Nintendo DS | DSperate | `~/roms/nds`{ style="white-space: nowrap" } | `nds` `zip` `7z` | Optional<br>`bios9.bin` `bios7.bin` `firmware.bin` |
| Nintendo 3DS | Azahar | `~/roms/3ds`{ style="white-space: nowrap" } | `3ds` `cci` `cxi` `3dsx` `zcci` `zcxi` `z3dsx` | None |
| GameCube | Dolphin | `~/roms/gc`{ style="white-space: nowrap" } | `iso` `gcm` `gcz` `rvz` `ciso` `wia` | None |
| Wii | Dolphin | `~/roms/wii`{ style="white-space: nowrap" } | `iso` `wbfs` `rvz` `gcz` `ciso` `wia` | None |
| Wii U | Cemu | `~/roms/wiiu`{ style="white-space: nowrap" } | `wua` `wud` `wux` `rpx` | For `.wud` / `.wux` only<br>`keys.txt` |

**Nintendo DS.** Games run on the built-in FreeBIOS without the BIOS files. You need real dumps only to boot the DS menu from Open.

**Nintendo 3DS.** Only decrypted games work. A `.cia` has to be installed in Azahar first.

**Wii U.** `keys.txt` holds disc keys and is needed only for `.wud` and `.wux` dumps. A `.wua`, which holds the game, its update and DLC in one file, needs nothing.

## Sega

| System | Emulator | ROM folder | File types | BIOS in `~/bios` |
|---|---|---|---|---|
| Dreamcast | Flycast | `~/roms/dc`{ style="white-space: nowrap" } | `chd` `gdi` `cdi` `cue` | Optional<br>`dc_boot.bin` |

**Dreamcast.** Most games boot on Flycast's built-in BIOS. Naomi BIOS zips go in `~/bios` too.

## Sony

| System | Emulator | ROM folder | File types | BIOS in `~/bios` |
|---|---|---|---|---|
| PlayStation | DuckStation | `~/roms/psx`{ style="white-space: nowrap" } | `chd` `cue` `pbp` `m3u` `iso` | **Required**<br>a PS1 BIOS image, such as `scph5501.bin` |
| PlayStation 2 | ARMSX2 | `~/roms/ps2`{ style="white-space: nowrap" } | `chd` `iso` `cso` `zso` `gz` `cue` | **Required**<br>a PS2 BIOS image |
| PSP | PPSSPP | `~/roms/psp`{ style="white-space: nowrap" } | `iso` `cso` `chd` `pbp` | None (HLE) |
| PlayStation 3 | RPCS3 | `~/roms/ps3`{ style="white-space: nowrap" } | `iso` `psn`, and disc folders | **Required**<br>`PS3UPDAT.PUP` |

**PlayStation and PlayStation 2.** Any file name works. DuckStation and ARMSX2 search `~/bios` and pick a matching image themselves.

**PlayStation 3.**

- The firmware, `PS3UPDAT.PUP`, is installed once on the first launch. Without it no game starts.
- A disc folder is any folder containing `PS3_GAME/USRDIR/EBOOT.BIN`.
- A redump `.iso` also needs its `.dkey` file beside it.
- PSN `.pkg` files go in `~/roms/ps3/psn`, to be installed from **Settings › Library**.

## Ports

| System | Emulator | ROM folder | File types | BIOS in `~/bios` |
|---|---|---|---|---|
| Ports | PortMaster | `~/roms/ports`{ style="white-space: nowrap" } | `sh` | None |

PortMaster installs each port as a launch script in `~/roms/ports`. Its own app lives in `~/roms/ports/PortMaster`.

## Good to know

**Copying files over the network.** `roms`, `bios`, `saves` and `states` are shared over Samba, so you can copy games and BIOS files from another computer. A soft factory reset keeps all four.
