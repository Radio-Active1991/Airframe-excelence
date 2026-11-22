# Airframe Excelence

Aircraft systems, propulsion, procedural wing devices and graphical controllers for **Flyout**.

**Current release: 0.11.14** · **Flyout 0.2504** · **MelonLoader 0.7.3 Open-Beta** · **Windows x64 / .NET 6**

[Download the release](https://github.com/Radio-Active1991/Airframe-excelence/releases/latest) · [Read the Wiki](https://github.com/Radio-Active1991/Airframe-excelence/wiki) · [Report an issue](https://github.com/Radio-Active1991/Airframe-excelence/issues)

## What is included?

- **Stability Assist:** configurable hover/attitude/altitude/heading control, propulsion tuning, forward-speed modes and VTOL transition.
- **Logic Processor:** graphical logic, math, PID, Smoothing, Blinker, editable Equation formulas and device control; 15 processing gates, 64 additional inputs and 3 outputs per box.
- **Sequence Controller:** timed ON/OFF sequences for custom axes, stock commands and supported turbine functions.
- **Propulsion and drivetrain:** bleed jets, swiveling nozzles, compressed-air/hydraulic motors, CVT and a two-motor gearbox.
- **Airframe systems:** fuel transfer, editable tanks, spring joints, linear servo, wing-edge/flap/dive-brake choices.
- **Surface finishes** for wings and editable fuselages in the stock Material Type menu.
- **Weapons:** configurable box magazine, extended stock Gun/Drum Mag ranges and firing controls.
- **Engine options:** liquid rocket/RCS parts, up to 12 piston rows, Boxer and aligned radial layouts.

The package contains **23 placeable parts**. Extra wing, turbine-nozzle and piston-layout choices are integrated into their stock editors. See the [Parts catalog](https://github.com/Radio-Active1991/Airframe-excelence/wiki/Parts).

## Installation

### Install with Flyout Mod Installer

1. Download [FlyoutModInstaller.exe](https://github.com/Radio-Active1991/Airframe-excelence/raw/refs/heads/main/FlyoutModInstaller.exe) and [Airframe-Excelence-0.11.14.zip](https://github.com/Radio-Active1991/Airframe-excelence/releases/download/v0.11.14/Airframe-Excelence-0.11.14.zip).
2. Close Flyout and run the installer on Windows 10 or 11 with .NET Framework 4.8.
3. Click **Open ZIP...** and select the downloaded mod ZIP. Check the game and user folders, then choose **Install / Update**.

The [package manifest](flyout-mod.json) tells the installer where to copy the game files and 23 part folders.

### Install manually

For manual installation, copy the contents of `Mods` into the game's `Mods` folder. Copy the contents of `Parts` into `%USERPROFILE%\AppData\LocalLow\Stonext Games\Flyout\Mods\Parts`. After starting Flyout, look for **Airframe Excelence 0.11.14** in the log.

MelonLoader is installed separately. The game and user-data folders are different destinations: [full installation guide](https://github.com/Radio-Active1991/Airframe-excelence/wiki/Installation).

## New in 0.11.14

The stock **Material Type** menu now includes nine Airframe Excelence finishes, from tread plate and brushed metal to leather, velour and ceramics. Perforated metal has see-through openings using Flyout's Mesh shader. [Surface Finishes guide](https://github.com/Radio-Active1991/Airframe-excelence/wiki/Surface-Finishes)

## Documentation

Start with [Stability Assist](https://github.com/Radio-Active1991/Airframe-excelence/wiki/Stability-Assist), [VTOL Transition](https://github.com/Radio-Active1991/Airframe-excelence/wiki/VTOL-Transition), [Logic Processor](https://github.com/Radio-Active1991/Airframe-excelence/wiki/Logic-Processor) or [Troubleshooting](https://github.com/Radio-Active1991/Airframe-excelence/wiki/Troubleshooting). All public guides are in English.

Aircraft still require correct control directions, adequate propulsion/supply and suitable tuning. Compatibility is stated for the tested game version; there is no universal FPS or aircraft-stability guarantee.

## License and source

**GPL-3.0** — see [LICENSE](LICENSE). The main repository contains finished runtime files and documentation. Each release also includes a separately downloadable **matching Source ZIP** with the mod source, build scripts, tests and asset tools. It is available beside the runtime ZIP at no additional charge.

Do not install the Source ZIP into the game. Use the named runtime ZIP for installation. Flyout, MelonLoader and native game assets are not redistributed.

Created by **Radio-Active1991**, with development, debugging and documentation assistance from **OpenAI ChatGPT / Codex**. Previously named **Flyout Systems**.
