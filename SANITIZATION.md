# Sanitization report — hlyl-wfq9

Publication copy prepared from the local EFI snapshot. Original config backups,
logs, dumps and hidden metadata are excluded; operational binaries are byte-identical.

Source snapshot: 198 files (manifest verified before and after).
Published under `EFI/`: 188 files.

## Privacy changes (field paths only)

| Config path | Action |
| --- | --- |
| `PlatformInfo/Generic/SystemSerialNumber` | set to empty string |
| `PlatformInfo/Generic/MLB` | set to empty string |
| `PlatformInfo/Generic/SystemUUID` | set to all-zero UUID |
| `PlatformInfo/Generic/ROM` | set to six zero bytes |
| `NVRAM/Add/7C436110-AB2A-4BBB-A880-FE41995C9F82/bluetoothInternalControllerInfo` | removed (local controller state) |
| `NVRAM/Add/7C436110-AB2A-4BBB-A880-FE41995C9F82/bluetoothExternalDongleFailed` | removed (local controller state) |

No other config field changed. SMBIOS model, AMD patches and core count, device
properties, security settings, kext order, boot arguments and enabled flags are intact.

## Omitted from the public copy

- Every old `OC/config*` backup (9 files).
- `OC/Kexts/VoodooHDA_BL.kext/Contents/Info.plist.bak` (backup plist).
- `OC/Tools/` (`Misc/Tools` has no configured entries).
- Hidden metadata such as `.DS_Store`/AppleDouble files (none were present).

No logs, dumps, debug symbols or unrelated files were present or copied.

## Verification

- `plistlib` parses `EFI/OC/config.plist`: pass.
- Matching OpenCore 1.0.8 `ocvalidate`: no issues found.
- Configured ACPI/driver/kext/executable/plist/resource paths checked: 122, missing: 0.
- All nested kext `Info.plist` files parse: pass.
- Non-config copied files compared byte-for-byte with source: 187, mismatches: 0.
- Source snapshot re-hashed after packaging: unchanged.
- Semantic config diff equals exactly the 6 privacy changes above.
- Identifier scan (serial, MLB, UUID, ROM; ASCII, UTF-16LE, UTF-16BE and raw
  bytes) over all 191 public files: 0 matches.
- No config backups, `.bak` files, logs or dumps in the public tree.
- No current owner's user-directory or snapshot paths in the public tree. Other
  upstream compiler build paths may remain in unmodified vendor binaries.

## Required before use

**The public config REQUIRES new unique SMBIOS identifiers** (serial, MLB, UUID)
**and a real ROM value before it is used.** The zeroed values are placeholders for
publication only. This copy was never boot tested; validation was file-level only.
