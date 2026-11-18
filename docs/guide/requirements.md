---
title: What you need
description: The hardware and bootloader you need before installing RetroForge.
---

# What you need

## A supported device

Check your handheld is on the [supported devices](../devices/index.md) list. RetroForge supports Qualcomm Snapdragon handhelds only: a device built on another chip will not boot it.

## An unlockable bootloader

These handhelds ship with Android, and the bootloader has to be unlocked before it will start anything else. Unlocking is done once, from Android, and the steps vary by manufacturer. Respect your device's unlock terms.

## OpenABL

Your device must already be running [OpenABL](https://github.com/OpenHandheldCollective/OpenABL), the custom bootloader that can start a Linux system on these handhelds at all. It is the community continuation of the ROCKNIX ABL, so if you already run ROCKNIX you have a compatible one.

RetroForge does not ship a bootloader. On a stock Android bootloader a RetroForge card simply does nothing.

!!! danger "Flash OpenABL carefully"

    OpenABL replaces your device's `abl` partition, and a wrong or damaged image can stop the device from starting. Follow the [OpenABL installation guide](https://github.com/OpenHandheldCollective/OpenABL/wiki/Installation) exactly, use the image for your chipset, and keep your device's stock firmware so you can restore it.

## An SD card

A spare microSD card to hold RetroForge. Everything on it is erased when the image is written, so back up anything you want to keep.
