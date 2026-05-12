# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

This is a documentation-only repository. It contains an OpenWrt installation guide for the TP-Link Archer MR200 v5 router (MediaTek MT7628AN, 64MB RAM, 16MB flash).

There are no build steps, tests, or source code — the sole artifact is `README.md`.

## Device Context

- **Target**: `ramips / mt76x8`
- **OpenWrt support**: since 24.10.0
- **Flash layout**: firmware starts at `0x20000`, length `0x7B0000`
- **UART**: 115200 baud, 8N1, Raw mode; TX/RX crossed; 3V3 pin must stay unconnected
- **TFTP recovery IP**: router at `192.168.0.1` (WPS method) or `192.168.0.2` (U-Boot method); PC at `192.168.0.225`

## Editing Guidelines

- Keep all IP addresses, flash offsets, and U-Boot commands exactly as documented — these are hardware constants.
- The three installation methods (WPS/TFTP, UART/U-Boot, LuCI sysupgrade) are distinct; do not conflate their steps.
- Firmware filename for TFTP recovery must be `tp_recovery.bin` — the bootloader expects this exact name.
