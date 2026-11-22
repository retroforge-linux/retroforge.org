---
title: Installation
description: Write RetroForge to an SD card and boot it on your handheld.
---

# Installation

Before you start, make sure you have everything on [What you need](requirements.md), including OpenABL already installed.

## 1. Download the image

Download the latest `retroforge-<version>.img.gz` from the releases page. There is one image for every supported device, so there is nothing to choose.

## 2. Write it to an SD card

Use any image writer that accepts `.img.gz` files, such as [balenaEtcher](https://etcher.balena.io/) or Raspberry Pi Imager's *Use custom* option.

=== "balenaEtcher"

    1. Open balenaEtcher and choose **Flash from file**.
    2. Select the `.img.gz` you downloaded.
    3. Select your SD card as the target and choose **Flash!**

=== "Linux command line"

    Find your SD card's device name with `lsblk`, then write the image to it. Double-check the device name: everything on it is overwritten.

    ```bash
    gunzip -c retroforge-<version>.img.gz | sudo dd of=/dev/sdX bs=4M conv=fsync status=progress
    ```

## 3. Boot it

1. Power the device off and insert the SD card.
2. Power it on. OpenABL finds RetroForge on the SD card and offers it alongside Android.
3. Choose RetroForge. The first boot takes a little longer while the system sets itself up for your device.

To go back to Android, power off, remove the SD card, and power on. Android is untouched.

## Installing to internal storage

You can install RetroForge from an SD card to internal storage, alongside Android, from **Settings › General › Internal storage**. This keeps Android bootable but **erases Android's user data** (apps, saves and photos), it is entirely optional and you choose how much space Android keeps before anything is written.
