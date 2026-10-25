# HONOR HLYL-WFQ9 — anonymized OpenCore EFI reference

Configuration snapshot: October 25, 2026. AMD Ryzen 5 4600H / Radeon Renoir, 16 GB RAM, WD Blue SN580 1 TB, Broadcom BCM4352 wireless replacement, macOS Tahoe 26.7.1 (`25G241`).

**Experimental reference, not a ready-to-boot universal EFI. The SMBIOS identity is deliberately incomplete.**

## Contents

Download: [EFI-HLYL-WFQ9-Tahoe.zip](EFI-HLYL-WFQ9-Tahoe.zip). The archive contains the sanitized `EFI/BOOT` and `EFI/OC` trees copied from the owner's current internal EFI. See [INVENTORY.md](INVENTORY.md) for ACPI, drivers, kexts, patch ranges and configuration values, and [SANITIZATION.md](SANITIZATION.md) for the exact privacy changes and omissions.

- OpenCore 1.0.8 RELEASE; installed OpenCore binary matched the local X64 release package.
- NootedRed from the steve12311 fork, v0.9.0-pre-release.9; its internal kext version is `0.9.0`.
- Original operational binaries, device paths, AMD patches, kext order, enabled flags and security settings retained.
- Old configuration backups, local controller state, unrelated bootloaders, metadata and diagnostic files excluded.

`ARCHIVE-SHA256SUMS` verifies the ZIP download. `SHA256SUMS` records the individual extracted EFI files. The publication notes record file checks, not a firmware boot test.

## Before using any file

1. Keep a separate bootable recovery USB and a backup of your own EFI. Do not replace a working setup merely because the CPU model matches.
2. Review the full configuration against your hardware and target OS, including AMD core-count patches, kernel bounds, USB mapping, ACPI and device properties. The original BIOS revision/settings have not been independently verified for this publication.
3. Generate your own appropriate, unique SMBIOS identity. `SystemSerialNumber` and `MLB` are empty, `SystemUUID` is all zeroes and `ROM` is six zero bytes. These are publication placeholders and must not be treated as valid identity values.
4. Validate the personalized configuration with the matching OpenCore 1.0.8 `ocvalidate`, then test from recovery media before considering an internal installation. Anonymization validation does not establish bootability.

No instruction here changes the host machine's EFI or security configuration automatically.

## System changes outside the EFI

This machine is not an unpatched macOS baseline. The current observed SIP configuration disables kext signing and filesystem protections; Authenticated Root is disabled, and `SecureBootModel` is disabled in the EFI.

The owner's incident report records OCLP-Plus 3.2.2 Modern Wireless metadata affecting `wifip2pd`, `IO80211.framework` and `WiFiPeerToPeer.framework`. The exact reinstall and rollback sequence is not reproduced here as a tested procedure. A copied EFI alone does not apply those patches.

Local Bluetooth recovery, mouse reconnection and AirDrop-mode helpers also live outside the EFI and are not included. AirDrop transfers succeeded when mouse reconnection was paused; simultaneous mouse/AirDrop/Instant Hotspot remains unresolved. Automatic hotspot activation has been intermittent.

## Known graphics/video issue

On October 24, wallpaper browsing preceded a graphical freeze on NootedRed pre-release.9, with VCN0Dec GPU-reset reports and a WindowServer watchdog timeout. See [the open issue and maintainer discussion](https://github.com/steve12311/NootedRed/issues/5). The exact cause and repeatability remain unproven; no resolution is claimed.

Earlier short Metal and H.264/HEVC VideoToolbox tests passed on a previous graphics build. These results do not guarantee current-build stability, DRM, 4K/HDR, screen sharing or compatibility with every application. Audio, webcam, external displays, all USB ports, full sleep recovery and real battery life have not received a complete physical test pass for this publication.

## Attribution and licenses

The bootloader, kexts and resources belong to their respective upstream contributors, including Acidanthera, AMD-OSX, ChefKiss, steve12311, Voodoo and the Broadcom patching projects. Existing upstream license notices are retained where present. No blanket license is asserted over third-party binaries. This snapshot also contains local/custom components; an independently reproducible source build of every bundled component has not been established.

Documentation was prepared with AI assistance from current configuration and earlier verification records. The original system EFI was not modified to prepare this publication. The sanitized public copy has not been boot tested.
