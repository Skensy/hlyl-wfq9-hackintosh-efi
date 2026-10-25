# Public EFI inventory — hlyl-wfq9

Sanitized publication copy of the current Hackintosh EFI. No boot test was performed.

## Contents

| Area | Files |
| --- | --- |
| BOOT | 1 |
| OC root | 4 |
| ACPI | 8 |
| Drivers | 5 |
| Kexts | 112 |
| Resources | 58 |
| **Total under EFI/** | **188** |

Layout: `EFI/BOOT/BOOTX64.EFI`, `EFI/OC/OpenCore.efi`, `EFI/OC/config.plist`,
with `ACPI/`, `Drivers/`, `Kexts/`, `Resources/` and the `.contentFlavour`/
`.contentVisibility` metadata files. `Misc/Tools` has no entries; `OC/Tools` is omitted.

## ACPI

| File | State | Comment |
| --- | --- | --- |
| `SSDT-ALS0.aml` | enabled | SSDT-ALS0.aml |
| `SSDT-EC.aml` | enabled | SSDT-EC.aml |
| `SSDT-PLUG-ALT.aml` | enabled | SSDT-PLUG-ALT.aml |
| `SSDT-PNLF.aml` | enabled | SSDT-PNLF.aml |
| `SSDT-USB-Reset.aml` | enabled | SSDT-USB-Reset.aml |
| `SSDT-USBX.aml` | enabled | SSDT-USBX.aml |
| `SSDT-XOSI.aml` | enabled | SSDT-XOSI.aml |
| `SSDT-GPIO.aml` | enabled | SSDT-GPIO.aml - Huawei MateBook D AMD GPIO Interrupts |

## Drivers

| Driver | State |
| --- | --- |
| `apfs_aligned.efi` | enabled |
| `HfsPlus.efi` | enabled |
| `OpenRuntime.efi` | enabled |
| `ResetNvramEntry.efi` | enabled |
| `OpenCanopy.efi` | enabled |

## Kexts

| Bundle | Version | State | Min – Max kernel |
| --- | --- | --- | --- |
| `AppleMCEReporterDisabler.kext` | 1.2 | enabled | - – - |
| `Lilu.kext` | 1.7.3 | enabled | - – - |
| `AzurewaveUVCFix.kext` | 1.0.2 | enabled | 25.6.0 – 25.6.99 |
| `NootedRed.kext` | 0.9.0 | enabled | - – - |
| `NVMeFix.kext` | 1.1.4 | enabled | - – - |
| `RealtekBluetoothFirmware.kext` | 1.0.2 | disabled | - – - |
| `RestrictEvents.kext` | 1.1.7 | enabled | - – - |
| `USBToolBox.kext` | 1.2.0 | enabled | - – - |
| `UTBMap.kext` | 1.1 | enabled | - – - |
| `VirtualSMC.kext` | 1.3.9 | enabled | - – - |
| `AMDRyzenCPUPowerManagement.kext` | 3.34.0 | enabled | 25.0.0 – 25.99.99 |
| `SMCAMDProcessor.kext` | 3.34.0 | enabled | 25.0.0 – 25.99.99 |
| `VoodooPS2Controller.kext` | 2.3.8 | enabled | - – - |
| `VoodooI2C.kext/Contents/PlugIns/VoodooGPIO.kext` | 1.1 | enabled | - – - |
| `VoodooI2C.kext/Contents/PlugIns/VoodooI2CServices.kext` | 1.0 | enabled | - – - |
| `VoodooI2C.kext/Contents/PlugIns/VoodooInput.kext` | 1.1.7 | enabled | - – - |
| `VoodooPS2Controller.kext/Contents/PlugIns/VoodooInput.kext` | 1.1.7 | disabled | - – - |
| `VoodooPS2Controller.kext/Contents/PlugIns/VoodooPS2Keyboard.kext` | 2.3.8 | enabled | - – - |
| `VoodooPS2Controller.kext/Contents/PlugIns/VoodooPS2Mouse.kext` | 2.3.8 | disabled | - – - |
| `VoodooPS2Controller.kext/Contents/PlugIns/VoodooPS2Trackpad.kext` | 2.3.8 | disabled | - – - |
| `BrcmFirmwareData.kext` | 2.7.2 | enabled | 25.0.0 – 25.99.99 |
| `BrcmPatchRAM3.kext` | 2.7.2 | enabled | 25.0.0 – 25.99.99 |
| `BlueToolFixup.kext` | 2.7.3 | enabled | 21.0.0 – - |
| `BrightnessKeys.kext` | 1.0.4 | enabled | - – - |
| `ForgedInvariant.kext` | 1.5.0 | enabled | - – - |
| `SMCBatteryManager.kext` | 1.3.9 | enabled | - – - |
| `SMCLightSensor.kext` | 1.3.9 | enabled | - – - |
| `VoodooI2C.kext` | 2.9.1 | enabled | - – - |
| `VoodooI2CHID.kext` | 1.0 | enabled | - – - |
| `AMFIPass.kext` | 1.4.1 | enabled | 25.0.0 – 25.99.99 |
| `AirportBrcmFixup.kext` | 2.2.1 | enabled | 25.0.0 – 25.99.99 |
| `IOSkywalkFamily.kext` | 1.0 | enabled | 25.0.0 – 25.99.99 |
| `IO80211FamilyLegacy.kext` | 12.0 | enabled | 25.0.0 – 25.99.99 |
| `IO80211FamilyLegacy.kext/Contents/PlugIns/AirPortBrcmNIC.kext` | 14.0 | enabled | 25.0.0 – 25.99.99 |
| `AirportBrcmFixup.kext/Contents/PlugIns/AirPortBrcmNIC_Injector.kext` | 1.0 | enabled | 25.0.0 – 25.99.99 |
| `AirPort_RTW88.kext` | 2.0.1 | disabled | 25.0.0 – 25.99.99 |
| `VoodooHDA_BL.kext` | 3.7.0 | enabled | 25.0.0 – 25.99.99 |

Kext order and enabled flags are unchanged from the source config. Disabled kext
files are published alongside disabled entries so the tree matches the config.

### Present but not configured

- `GenericUSBXHCI.kext`
- `RealtekRTL8822C-Debug.kext`
- `RealtekRTL8822C.kext`

## Kernel patches

| Comment | Min – Max kernel | State | Count |
| --- | --- | --- | --- |
| algrey  /  Force cpuid_cores_per_package to constant (user-specified)  /  10.13-10.14 | 17.0.0 – 18.99.99 | enabled | 1 |
| algrey  /  Force cpuid_cores_per_package to constant (user-specified)  /  10.15-11.0 | 19.0.0 – 20.99.99 | enabled | 1 |
| algrey  /  Force cpuid_cores_per_package to constant (user-specified)  /  12.0-13.2 | 21.0.0 – 22.3.99 | enabled | 1 |
| algrey  /  Force cpuid_cores_per_package to constant (user-specified)  /  13.3+ | 22.4.0 – 25.99.99 | enabled | 1 |
| algrey  /  _commpage_populate  /  Remove rdmsr  /  10.13+ | 17.0.0 – 25.99.99 | enabled | 1 |
| algrey  /  _cpuid_set_cache_info  /  Set CPUID proper instead of 4  /  10.13+ | 17.0.0 – 25.99.99 | enabled | 1 |
| algrey  /  _cpuid_set_generic_info  /  Remove wrmsr(0x8B)  /  10.13+ | 17.0.0 – 25.99.99 | enabled | 1 |
| algrey  /  _cpuid_set_generic_info  /  Replace rdmsr(0x8B) with constant 186  /  10.13+ | 17.0.0 – 25.99.99 | enabled | 1 |
| algrey  /  _cpuid_set_generic_info  /  Set flag=1  /  10.13+ | 17.0.0 – 25.99.99 | enabled | 1 |
| algrey  /  _cpuid_set_generic_info  /  Disable check to allow leaf7  /  10.13+ | 17.0.0 – 23.99.99 | enabled | 1 |
| algrey  /  _cpuid_set_generic_info  /  Disable check to allow leaf7  /  15.0+ | 24.0.0 – 25.99.99 | enabled | 1 |
| algrey  /  _cpuid_set_info  /  GenuineIntel to AuthenticAMD  /  10.13-11.0 | 17.0.0 – 20.99.99 | enabled | 1 |
| Goldfish64, algrey  /  Bypass GenuineIntel check panic  /  12.0+ | 21.0.0 – 25.99.99 | enabled | 1 |
| algrey  /  _cpuid_set_cpufamily  /  Force CPUFAMILY_INTEL_PENRYN  /  10.13-11.2 | 17.0.0 – 20.3.0 | enabled | 1 |
| algrey  /  _cpuid_set_cpufamily  /  Force CPUFAMILY_INTEL_PENRYN  /  11.3+ | 20.4.0 – 25.99.99 | enabled | 1 |
| algrey  /  _i386_init  /  Remove 3 rdmsr calls  /  10.13+ | 17.0.0 – 25.99.99 | enabled | 0 |
| algrey, XLNC  /  Remove version check and panic  /  10.13+ | 17.0.0 – 25.99.99 | enabled | 1 |
| CaseySJ  /  probeBusGated  /  Disable 10 bit tags  /  12.0-15.x | 21.0.0 – 24.99.99 | enabled | 1 |
| CaseySJ  /  probeBusGated  /  Disable 10 bit tags  /  26.0+ | 25.0.0 – 25.99.99 | enabled | 1 |
| CaseySJ  /  IOPCIIsHotplugPort  /  Fix PCI bus enumeration on AM5  /  13.0+ | 22.0.0 – 25.99.99 | disabled | 1 |
| Visual  /  thread_quantum_expire, thread_unblock, thread_invoke  /  Remove non-monotonic time panic  /  12.0+ | 21.0.0 – 25.99.99 | enabled | 3 |
| Visual  /  thread_invoke, thread_dispatch  /  Remove non-monotonic time panic  /  12.0-26.3 | 21.0.0 – 25.3.99 | enabled | 2 |
| laobamac  /  thread_invoke, thread_dispatch  /  Remove non-monotonic time panic  /  26.4+ | 25.4.0 – 25.99.99 | enabled | 2 |
| algrey  /  _mtrr_update_action  /  fix PAT  /  10.13+ | 17.0.0 – 23.99.99 | disabled | 0 |
| Shaneee  /  _mtrr_update_action  /  Fix PAT  /  10.13+ | 17.0.0 – 23.99.99 | enabled | 0 |
| Algrey / Zormeister  /  _mtrr_update_action  /  Fix PAT  /  15.0+ | 24.0.0 – 25.99.99 | disabled | 0 |
| Shaneee / Zormeister  /  _mtrr_update_action  /  Fix PAT  /  15.0+ | 24.0.0 – 25.99.99 | enabled | 0 |

## ACPI patch

| Comment | Count | State |
| --- | --- | --- |
| _OSI to XOSI rename - requires SSDT-XOSI.aml | 0 | enabled |

## Boot and security

- `boot-args`: `debug=0x100 keepsyms=1 -amfipassbeta -NRedDisplayFix -NRedVideoFix revcpu=0`
- `csr-active-config`: `03080000`
- `AllowSetDefault`: `True`
- `ApECID`: `0`
- `AuthRestart`: `False`
- `BlacklistAppleUpdate`: `True`
- `DmgLoading`: `Signed`
- `EnablePassword`: `False`
- `ExposeSensitiveData`: `6`
- `HaltLevel`: `2147483648`
- `PasswordHash`: `b''`
- `PasswordSalt`: `b''`
- `ScanPolicy`: `0`
- `SecureBootModel`: `Disabled`
- `Vault`: `Optional`
- `Misc/Boot/PickerVariant`: `Acidanthera\GoldenGate`
- `Misc/Boot/Timeout`: `10`
- `Misc/Boot/LauncherOption`: `Full`

## Notes

The SMBIOS model and hardware-specific device properties are unchanged; only the
unique Apple identifiers were reset. See `SANITIZATION.md`.
