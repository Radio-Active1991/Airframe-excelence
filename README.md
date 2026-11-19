# Airframe Excelence

Aircraft systems, propulsion, procedural wing devices and graphical controllers for **Flyout**.

**Current release: 0.11.13** · **Flyout 0.2504** · **MelonLoader 0.7.1 Open-Beta** · **Windows x64 / .NET 6**

[Download the release](https://github.com/Radio-Active1991/Airframe-excelence/releases/latest) · [Read the Wiki](https://github.com/Radio-Active1991/Airframe-excelence/wiki) · [Report an issue](https://github.com/Radio-Active1991/Airframe-excelence/issues)

## What is included?

- **Stability Assist:** configurable hover/attitude/altitude/heading control, propulsion tuning, forward-speed modes and VTOL transition.
- **Logic Processor:** graphical logic, math, PID, Smoothing, Blinker, editable Equation formulas and device control; 15 processing gates, 64 additional inputs and 3 outputs per box.
- **Sequence Controller:** timed ON/OFF sequences for custom axes, stock commands and supported turbine functions.
- **Propulsion and drivetrain:** bleed jets, swiveling nozzles, compressed-air/hydraulic motors, CVT and a two-motor gearbox.
- **Airframe systems:** fuel transfer, editable tanks, spring joints, linear servo, wing-edge/flap/dive-brake choices.
- **Weapons:** configurable box magazine, extended stock Gun/Drum Mag ranges and firing controls.
- **Engine options:** liquid rocket/RCS parts, up to 12 piston rows, Boxer and aligned radial layouts.

The package contains **23 placeable parts**. Extra wing, turbine-nozzle and piston-layout choices are integrated into their stock editors. See the [Parts catalog](https://github.com/Radio-Active1991/Airframe-excelence/wiki/Parts).

## Installation

1. Close Flyout and download **Airframe-Excelence-0.11.13.zip** from Releases.
2. Copy the package's **Mods** contents into the game's **Mods** directory.
3. Copy the 23 folders under **Parts** into:

   `%USERPROFILE%\AppData\LocalLow\Stonext Games\Flyout\Mods\Parts`

4. Start Flyout and check for **Airframe Excelence 0.11.13** in the log.

MelonLoader is installed separately. The game and user-data folders are different destinations: [full installation guide](https://github.com/Radio-Active1991/Airframe-excelence/wiki/Installation).

## New in 0.11.13

The Logic Processor and Sequence Controller can read RWR warnings and the aircraft's own radar mode and lock. Both can send single pulses to all flare dispensers or to an individual launcher. The Logic Processor's **Blinker** adds adjustable frequency and duty cycle.

The wiki shows how to use the native inputs and build a manual series that stops automatically. [Radar, RWR and Flare Outputs](https://github.com/Radio-Active1991/Airframe-excelence/wiki/Radar-RWR-and-Flare-Outputs)

## Documentation

Start with [Stability Assist](https://github.com/Radio-Active1991/Airframe-excelence/wiki/Stability-Assist), [VTOL Transition](https://github.com/Radio-Active1991/Airframe-excelence/wiki/VTOL-Transition), [Logic Processor](https://github.com/Radio-Active1991/Airframe-excelence/wiki/Logic-Processor) or [Troubleshooting](https://github.com/Radio-Active1991/Airframe-excelence/wiki/Troubleshooting). All public guides are in English.

Aircraft still require correct control directions, adequate propulsion/supply and suitable tuning. Compatibility is stated for the tested game version; there is no universal FPS or aircraft-stability guarantee.

## License and source

**GPL-3.0** — see [LICENSE](LICENSE). The main repository contains finished runtime files and documentation. Each release also includes a separately downloadable **matching Source ZIP** with the mod source, build scripts, tests and asset tools. It is available beside the runtime ZIP at no additional charge.

Do not install the Source ZIP into the game. Use the named runtime ZIP for installation. Flyout, MelonLoader and native game assets are not redistributed.

Created by **Radio-Active1991**, with development, debugging and documentation assistance from **OpenAI ChatGPT / Codex**. Previously named **Flyout Systems**.
