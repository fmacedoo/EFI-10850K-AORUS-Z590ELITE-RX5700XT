# EFI Intel Core i9 10850K, Aorus Elite Z590, RX 5700XT

Note|Description
:----|:----
Initial macOS Support|macOS 10.15, Catalina.

- Opencore version: 0.7.8
- Release date: 07/02/2022

No Debug files!

# Basic Steps

1. [Download](https://github.com/fmacedoo/EFI-10850K-AORUS-Z590ELITE-RX5700XT/releases) the latest release;
2. Generate and complete your SMBIOS infos - **ALWAYS**;
3. Adjust your BIOS;
4. Install macOS and enjoy :)

# Attention

Update **config.plist** in PlatformInfo > Generic with YOUR informations.
<br><br>
*1. MLB (Board Serial)
<br>
2. ROM (Mac Address)
<br>
3. SystemSerialNumber (Serial)
<br>
4. SystemUUID (SmUUID)*

Please use [*genSMBIOS*](https://github.com/corpnewt/GenSMBIOS/archive/refs/heads/master.zip) for generate values for above itens.
<br>
Please use [*ProperTree*](https://github.com/corpnewt/ProperTree/archive/refs/heads/master.zip) for configure/edit your config.plist.

# Compatible SMBIOS

SMBIOS|Description
:----|:----
iMac20,1|i7-10700K and lower(ie. 8 core and lower).
iMac20,2|i9-10850K and higher(ie. 10 core).

# BIOS Settings

### Disable
- Fast Boot
- Secure Boot
- Serial/COM Port
- Parallel Port
- VT-d (can be enabled if you set `DisableIoMapper` to YES)
- Compatibility Support Module (CSM).
- Thunderbolt(For initial install, as Thunderbolt can cause issues if not setup correctly)
- Intel SGX
- Intel Platform Trust
- CFG Lock (MSR 0xE2 write protection)
	- This must be off, if you can't find the option then **`ENABLE`** `AppleXcpmCfgLock`. 
	- Your hack will not boot with `CFG-Lock` enabled.

### Enable
- VT-x
- Above 4G decoding. 
	- This must be on, if you can't find the option then add `npci=0x2000` to `boot-args`. 
	- Do not have both this option and `npci` on `boot-args` enabled at the same time.
	- 2020+ BIOS Notes: When enabling Above4G, Resizable BAR Support may become an available on some Z490 and newer motherboards. Please ensure this is **`DISABLED`** instead of set to Auto.
- Hyper-Threading
- Execute Disable Bit
- EHCI/XHCI Hand-off
- OS type: Windows 8.1/10 UEFI Mode
- DVMT Pre-Allocated(iGPU Memory): 64MB
- SATA Mode: AHCI

# References
https://dortania.github.io/OpenCore-Install-Guide/config.plist/comet-lake.html
<br>
https://dortania.github.io/Getting-Started-With-ACPI/

## Fork from 
- [Gabriel Luchina](https://github.com/luchina-gabriel/BASE-EFI-INTEL-DESKTOP-10THGEN-COMET-LAKE)
