
<h1 align="center">Luma3DS Custom Firmware</h1>

<p align="center">
  <strong>System Patching. Firmware Control. Homebrew Integration.</strong>
</p>

<p align="center">
  Nintendo 3DS / 2DS · Custom Firmware · System Software Development
</p>

<p align="center">
  <img src="https://img.shields.io/badge/platform-Nintendo%203DS%20%2F%202DS-A63A55?style=flat-square">
  <img src="https://img.shields.io/badge/category-Custom%20Firmware-A63A55?style=flat-square">
  <img src="https://img.shields.io/badge/license-GPL--3.0-555555?style=flat-square">
  <img src="https://img.shields.io/badge/version-13.5-333333?style=flat-square">
</p>

## Overview

Luma3DS is a custom firmware project for the Nintendo 3DS family of consoles. It patches and reimplements significant parts of the system software, providing an extended software environment for system customization, homebrew applications, debugging, and firmware-level modifications.

The project is built around a combination of low-level firmware components, ARM9 and ARM11 code, kernel extensions, and reimplemented system modules.

One of its defining components is Rosalina, an integrated overlay and system management interface that provides access to multiple firmware features.

Luma3DS requires boot9strap as its underlying boot environment.

## Technical Architecture

Luma3DS uses a layered architecture consisting of several independently developed components.

### ARM9 and ARM11

The core firmware loader and settings interface operate at the bare-metal level.

Their responsibilities include:

- Firmware loading and initialization.
- Official firmware patching.
- Process9 code modification.
- Injection of custom system components.
- Payload chainloading.
- Firmware configuration management.

### Kernel Extension

The `k11_extension` component extends the ARM11 NATIVE_FIRM kernel.

Its functionality includes:

- System call (SVC) hooking.
- Additional SVC implementation.
- Inter-process communication hooking.
- Kernel-level process interaction.
- Support for selected debugging and overlay operations.

### System Modules

Luma3DS includes reimplementations of selected Nintendo 3DS system modules.

These components integrate with the operating system and provide additional control over process management, loading, and system services.

## Core Components

| Component | Description | Technical Role |
|---|---|---|
| ARM9 | Bare-metal firmware component | Firmware loading and initialization |
| ARM11 | System-level firmware component | Firmware configuration and patching |
| k11_extension | ARM11 kernel extension | Kernel hooks and additional SVCs |
| Rosalina | Integrated overlay and system interface | Runtime system management |
| Loader | System module | Application and homebrew loading |
| PXI | Reimplemented system module | ARM9–ARM11 communication |
| SM | Service Manager module | Service access management |
| PM | Process Manager module | Process lifecycle management |
| Plugin Loader | Game plugin loading component | 3GX plugin integration |

## Key Features

### Firmware Modification

- System software patching across the Nintendo 3DS family.
- Reimplementation of selected system software components.
- Custom firmware configuration through `config.ini`.
- Support for user-provided patches and system module replacements.

### Rosalina System Interface

- Integrated system overlay activated by `L + Down + Select` by default.
- Runtime configuration and system management.
- Screenshot capture and screen filter controls.
- Input redirection and network time synchronization.
- Access to selected debugging functions.

### Homebrew and Payload Management

- Native homebrew application support.
- 3DSX homebrew loading.
- Chainloading of additional firmware payloads.
- Support for user-provided system modifications.
- 3GX game plugin loading.

### Developer and Debugging Tools

- Integrated GDB debugging stub.
- Process inspection capabilities.
- Break-on-start debugging functionality.
- Kernel-level debugging interfaces.
- Tools for reverse engineering and homebrew development.

## Rosalina

Rosalina is one of the central components of Luma3DS.

It provides an overlay interface for interacting with the running system without requiring a separate application for each supported function.

| Function | Description |
|---|---|
| System Menu | Access to firmware management options |
| Screen Filters | Display color and visual adjustments |
| Screenshot Capture | Capture console screen output |
| Input Redirection | External input device support |
| Network Time | NTP-based date and time synchronization |
| GDB Server | Remote debugging functionality |
| Process Management | Selected process-level operations |
| System Configuration | Runtime firmware settings |

Default activation combination:

`L + Down + Select`

The combination can be customized through the Rosalina configuration interface.

## Firmware Configuration

Luma3DS uses configuration files to control selected system behaviors.

### Configuration File

`/luma/config.ini`

The file contains configurable firmware options.

When Luma3DS is launched from CTRNAND without an SD card, the configuration location is:

`/rw/luma/config.ini`

### Payload Management

Additional firmware payloads are stored in:

`/luma/payloads/`

Payload files use the `.firm` extension.

The chainloader menu can be accessed by pressing `Start` during boot or through the configuration menu.

When only one payload is present, the selection menu may be skipped.

## Platform Compatibility

| Platform | Hardware Family | Compatibility |
|---|---|---|
| Nintendo 3DS | Original 3DS | Supported |
| Nintendo 3DS XL | Original 3DS XL | Supported |
| New Nintendo 3DS | New 3DS | Supported |
| New Nintendo 3DS XL | New 3DS XL | Supported |
| Nintendo 2DS | Original 2DS | Supported |
| New Nintendo 2DS XL | New 2DS XL | Supported |

Luma3DS targets the Nintendo 3DS family, including its 2DS variants.

The firmware requires boot9strap. Specific installation and system firmware requirements should be verified against the official project documentation.

## Installation and Configuration

### Prerequisites

- Nintendo 3DS family console.
- Existing boot9strap installation.
- Compatible SD card.
- Official Luma3DS release archive.
- Access to the console's SD card filesystem.

### Installation Overview

1. Verify that boot9strap is installed and functioning.
2. Obtain the official Luma3DS release archive.
3. Extract the release files onto the root of the SD card.
4. Replace existing files and merge folders where required.
5. Insert the SD card and start the console.
6. Verify the firmware configuration menu.

### Firmware Verification

Press `Select` during boot to access the Luma3DS configuration menu.

Verify that the expected firmware version is displayed and that the selected configuration options are correct.

### Updating

Obtain the latest release from the official Luma3DS repository and replace the corresponding files on the SD card.

Review release notes before updating.

## Technical Specifications

| Parameter | Details |
|---|---|
| Project | Luma3DS |
| Platform | Nintendo 3DS / 2DS |
| Software Type | Custom Firmware |
| Latest Release | v13.5 |
| Core Architecture | ARM9 / ARM11 |
| Kernel Extension | k11_extension |
| System Interface | Rosalina |
| Boot Environment | boot9strap |
| Firmware Format | FIRM |
| Configuration | config.ini |
| Development Languages | C / C++ / Assembly |
| License | GPL-3.0 with documented exceptions |
| Source Repository | LumaTeam/Luma3DS |

## Development and Build Environment

Luma3DS is an open-source firmware project with a source-based development workflow.

The official build environment includes:

- Git.
- makerom.
- firmtool.
- devkitARM.
- libctru.
- devkitPro development packages.

The compiled firmware output is distributed as:

`boot.firm`

The release archive also includes associated homebrew components.

Refer to the official source repository for build instructions and dependency requirements.

## Frequently Asked Questions

### What is Luma3DS?

Luma3DS is custom firmware for the Nintendo 3DS family that patches and reimplements significant parts of the console's system software.

### Does Luma3DS support Nintendo 2DS?

Yes. The original Nintendo 2DS and New Nintendo 2DS XL belong to the supported Nintendo 3DS hardware family.

### What is Rosalina?

Rosalina is an integrated system overlay providing access to firmware configuration, screen controls, input redirection, debugging, and additional system functions.

### Does Luma3DS require boot9strap?

Yes. The official project identifies boot9strap as a required boot environment.

### Where are firmware settings and payloads stored?

The main configuration file is located at `/luma/config.ini`, while additional `.firm` payloads are stored in `/luma/payloads/`.

## SEO Keywords

Luma3DS custom firmware, Nintendo 3DS CFW, Luma3DS firmware installation, Nintendo 2DS custom firmware, Luma3DS Rosalina, 3DS system modification, boot9strap firmware, Nintendo 3DS homebrew, ARM11 kernel extension, Luma3DS configuration, 3DS firmware patching, Nintendo 3DS system modules, Luma3DS payload chainloader, 3DS homebrew environment, Rosalina system overlay, Luma3DS GDB debugging, Nintendo 3DS firmware development, 3DS system software modification, Luma3DS GitHub, Nintendo 3DS firmware architecture.

## Technical References

- [Official Luma3DS Repository](https://github.com/LumaTeam/Luma3DS)
- [Official Releases](https://github.com/LumaTeam/Luma3DS/releases)
- [Luma3DS Source Code](https://github.com/LumaTeam/Luma3DS/tree/master)
- [Luma3DS Documentation](https://github.com/LumaTeam/Luma3DS/tree/master/docs)
- [boot9strap Repository](https://github.com/SciresM/boot9strap)
- [Luma3DS License](https://github.com/LumaTeam/Luma3DS/blob/master/LICENSE)

<p align="center">
  <strong>Luma3DS Custom Firmware</strong>
  <br>
  Nintendo 3DS · Nintendo 2DS · System Software
  <br>
  Firmware Architecture and System-Level Development
</p>
