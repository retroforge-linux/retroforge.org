---
title: Building
description: Build a RetroForge image yourself.
---

# Building

Everything goes through the top-level `Makefile`, which wires the per-stage scripts into one incremental graph. The kernel, rootfs assembly, boot packaging and bundling all cross-compile inside the `retroforge-build` Docker image.

!!! warning

    Never invoke the stage scripts by hand. Always go through `make`.

## Common targets

```sh
make help      # every target and knob
make sdcard    # full image -> out/images/sdcard.img
make kernel    # Image + dtbs + modules
make test      # offline suites: no build, no container, no root, no device
```

## Developer builds

Dev versus release is selected by the **environment**, not by a make variable, and it must be sourced before every invocation:

```sh
set -a; . ./dev.env; set +a
```

`RETROFORGE_DEV=1` bakes in Wi-Fi credentials, an SSH key and the developer package set.

!!! tip

    A bare `make` after a dev build flips the mode and rebuilds the other one. Source `dev.env` in every shell you build from.
