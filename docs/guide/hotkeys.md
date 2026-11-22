---
title: Hotkeys
description: Hold Guide for save states, fast-forward and quitting, in every emulator.
---

# Hotkeys

Every emulator uses the same hotkey layer: **hold Guide** and the shoulder buttons and Start do emulator things while the game has focus. Let go of Guide and the pad is a plain pad again, so no game ever sees a hotkey by accident.

## The same in every emulator

| Press | Does | |
|---|---|---|
| ++"Guide"++ tap | Opens the OpenGamepadUI menu | Only if you pressed nothing else while Guide was held |
| ++"Guide"+"A"++ | Opens the quick bar | A is the bottom face button |
| ++"Guide"+"X"++ | Opens the on-screen keyboard | X is the left face button on an Xbox layout |

## The usual layout

Most emulators follow one pattern, so once you know it you know nearly all of them:

<div class="grid cards" markdown>

-   ++"Guide"+"L1"++

    ---

    **Load state**

-   ++"Guide"+"R1"++

    ---

    **Save state**

-   ++"Guide"+"R2"++

    ---

    **Fast-forward**

-   ++"Guide"+"Start"++

    ---

    **Quit** back to the library

</div>

## Per emulator

Where an emulator differs from the usual layout, the table says how.

| Emulator | ++"Guide"+"L1"++ | ++"Guide"+"R1"++ | ++"Guide"+"R2"++ | ++"Guide"+"Start"++ |
|---|---|---|---|---|
| **RetroArch**<br><small>GB · GBC · GBA · SNES · MD · Mega CD · N64</small> | Load state<br><small>current slot</small> | Save state<br><small>current slot</small> | Fast-forward<br><small>while held</small> | Quit<br><small>press twice</small> |
| **DSperate**<br><small>Nintendo DS</small> | Load state | Save state | Fast-forward<br><small>while held</small> | Quit<br><small>battery save written</small> |
| **Azahar**<br><small>Nintendo 3DS</small> | Quick load | Quick save | Turbo<br><small>toggle</small> | Exit |
| **DuckStation**<br><small>PlayStation</small> | Quick load<br><small>slot 1</small> | Quick save<br><small>slot 1</small> | Fast-forward<br><small>while held</small> | Power off<br><small>resume state and memory cards written</small> |
| **ARMSX2**<br><small>PlayStation 2</small> | Load state<br><small>slot 1</small> | Save state<br><small>slot 1</small> | Fast-forward<br><small>while held</small> | Shut down<br><small>resume state and memory cards written</small> |
| **RPCS3**<br><small>PlayStation 3</small> | Reboot from newest savestate | Create savestate | Frame limit<br><small>off / on</small> | Stop game |
| **PPSSPP**<br><small>PSP</small> | Load state<br><small>current slot</small> | Save state<br><small>current slot</small> | Fast-forward<br><small>while held</small> | Exit<br><small>no dialog</small> |
| **Dolphin**<br><small>GameCube · Wii</small> | Load state<br><small>slot 1</small> | Save state<br><small>slot 1</small> | No speed limit<br><small>while held</small> | Stop |
| **Flycast**<br><small>Dreamcast</small> | Load state<br><small>current slot</small> | Save state<br><small>current slot</small> | Fast-forward<br><small>on / off</small> | Quit<br><small>resume state and VMU written</small> |
| **Cemu**<br><small>Wii U</small> | — | — | Fast-forward<br><small>toggle, on release</small> | Exit<br><small>on release</small> |
| **hakuX**<br><small>Xbox</small> | Load quick state | Save quick state | —<br><small>no fast-forward</small> | Quit<br><small>hard disk synced</small> |
| **PortMaster**<br><small>Ports</small> | — | — | — | — |

PortMaster has no hotkey layer: each port uses the plain pad and its own controls.

### Extras for the dual-screen emulators

| Emulator | Press | Does |
|---|---|---|
| DSperate | ++"Guide"+"L2"++ | Swap screens |
| | ++"Guide"+"Y"++ | Next layout |
| | ++"Guide"+"Select"++ | Pause menu |
| | ++"Guide"+"R3"++ | Microphone, while held |
| Azahar | ++"Guide"+"L2"++ | Swap screens |
| | ++"Guide"+"Y"++ | Cycle layouts |

## Good to know

**The emulator's own menu.** In RetroArch, DuckStation, ARMSX2, PPSSPP and Flycast, ++"Select"+"Start"++ still opens the emulator's own menu, with no Guide involved. DSperate's pause menu is on ++"Guide"+"Select"++ instead.

**Cemu acts on release.** Cemu runs its hotkeys when you let go of the button, so fast-forward and exit happen as you release R2 or Start.

??? info "How it works"

    InputPlumber's Guide layer sends keyboard keys, and each emulator's preset configuration maps those keys to the actions above: mostly F1 load, F2 save, F3 fast-forward and F4 quit, plus F5, F6, F9, F10, P and M for the extras. hakuX's keys are fixed in the emulator, so it gets F5, Shift+F5 and Ctrl+Q directly.

    The handhelds have no physical keyboard and no game binds the F-keys, so they never collide with anything.

    Each R2 shortcut is mapped twice, once as an analog trigger and once as a button, because boards disagree on which one their right trigger is.
