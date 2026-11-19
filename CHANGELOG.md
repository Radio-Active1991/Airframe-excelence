# Release notes

## 0.11.13 — Radar inputs, Blinker and flare outputs

- Added read-only **RWR radar detection**, **RWR lock warning**, **missile approach warning**, **own radar mode** and **STT target lock** inputs to both controllers. Individual mode inputs let sequences trigger on one exact mode.
- Added the **Blinker** gate with a frequency of **0.01–100 Hz** and **0–100% duty cycle**. Each activation starts a cycle and disabling the input resets it.
- Added **Flares / All dispensers** and per-launcher outputs to both controllers. Each rising edge or sequence step sends one pulse through Flyout's release functions. Use Blinker or separate timed sequence steps for repetition.
- Added the manual single-pulse and timed-series wiring example to the English wiki.

Download the runtime ZIP for installation. The separate Source ZIP contains the corresponding GPL-3.0 source and build tools. Use the SHA-256 file to verify either download.

## 0.11.12 — Missiles, magazines, weapon controls and performance

- Added **AE Missile RCS**, a round missile module with 12 flush steering ports and short gas-jet effects. Pitch/yaw/roll force couples work at the nose or tail. Choose internal fuel, missile fuel, or missile fuel first with internal fallback.
- Integrated liquid rockets with native **Missile Cores**, launch stages, guidance, local missile fuel and the native force/mass phase. Added the read-only **Next missile core ID** Logic input; `-1` means none is available in the selected weapon group.
- Corrected excessive rocket drag caused by replacing an assembled missile's native aerodynamic exposure. Applied the requested additional drag factors: **0.80 for liquid rockets** and **0.35 for the new Missile RCS ring**. The older single RCS thruster retains its own drag.
- Liquid-rocket effective Isp and fuel consumption now account for high-energy stock fuels, including Nuclear Propulsion. The energy factor is based on the square root of specific energy relative to 43 MJ/kg. This is a simplified game-fuel model with unlimited oxidizer, not a reactor or full propellant-chemistry simulation. The Missile RCS ring uses its explicitly configured Isp instead.
- Fixed custom bleed nozzles and the bleed motor/compressor to **air system 0** and removed that selector. Old saved air-system choices are ignored; axis mixes and other saved settings remain intact.
- Extended stock **Gun and Drum Mag caliber to 5–160 mm**, **Gun maximum fire rate to 15,000 RPM**, and **maximum barrel length to 10 m**. The stock minimum fire rate is retained.
- Added **AE Box Magazine**: capacity is rows × columns × layers, with up to **200 rows, 1,000 columns and 10 layers**. Dimensions and approximate mass follow caliber and layout. It exposes a real native magazine module for stock weapons and compatible ammo readers, including the tested Cockpit path.
- Twin guns alternate their actual muzzles. Guns with three or more barrels use the upper Gatling firing position relative to the whole gun mount; barrel-bundle rotation does not move that position. Whole-model rotation and mounting still apply.
- Added decimal **Fire start delay s**, **0–10 seconds**. Releasing the trigger cancels the pending start. Simulation pause does not consume the delay; native firing cadence and Gatling spool-up remain active.
- Moved custom stock-editor settings after position/rotation/optional size and before paint controls. Added curved Logic wires and clearer unselected/selected node contrast.
- Reduced idle work in all three custom editors, bypassed native weapon/magazine checks for unrelated devices, reused CVT energy-frame storage, and retained the tested rocket-fuel/nozzle caches. Native physics frequency, aircraft control laws and energy correction are unchanged.

The author confirmed the preceding test-series features in-game. The final performance changes passed automated boundary, numerical-equivalence and native-binding checks; **no new in-game FPS claim is made**. In an isolated 10,000-step CVT collection benchmark, the old path allocated **24,240,000 managed bytes**, while the reused production frame allocated **0 after warm-up**, with identical energy totals. This excludes native wrappers, game physics and graphics.

Use **Airframe-Excelence-0.11.12.zip** for installation; install both its Parts and Mods contents in their respective locations. The separate matching **Source ZIP** includes GPL-3.0 source, build scripts, tests and authored asset tools. Keep only one combined mod DLL installed.

Created by **Radio-Active1991**, with development, debugging and documentation assistance from **OpenAI ChatGPT / Codex**.

## 0.11.11 — Smoothing, formulas, suspension and performance

- Added a **Smoothing** processing gate with configurable maximum change in units/second and an initial output. It limits changes in both directions using elapsed simulation time.
- Added an **Equation** processing gate with four inputs, editable formulas, arithmetic, functions and simulation-time variables. Syntax errors appear in the editor; invalid arithmetic releases the affected output. Formulas compile on load/apply rather than being parsed during physics ticks.
- Kept the existing limits of 15 processing gates, 64 additional inputs and 3 outputs. Existing graphs retain their gate IDs and settings; graphs using the new gates require 0.11.11 or newer.
- Added **Mass multiplier** (0.1–100, default 1) to Spring Bearing, Spring Damper and Linear Servo. It changes real part/vehicle mass, with native inertia recalculated on launch.
- Corrected Spring Bearing's asymmetric angular-stop mapping, including mirrored parts. Displayed angles, rest targets and physical limits now use consistent signs. Existing asymmetric setups may need their travel checked again.
- Expanded editor damping to **1,000 kN·m·s/deg** for Spring Bearing and **1,000 kN·s/m** for Spring Damper; retained saved values and defaults. Expanded flight information for suspension tuning.
- Reduced repeated graph dependency work, duplicate compilation during Apply, per-frame mechanical/nozzle snapshot allocations and editor node/palette lookups. Mechanical, bleed-nozzle, rocket and motor/CVT information text refreshes at 10 Hz; physics and actuator timing remain active.
- Updated the English Wiki with formulas, examples, reset/error behavior, suspension setup and troubleshooting.

The author confirmed the tested features in-game before publication. Offline logic/extension/native-axis/device suites passed **10,784 assertions**. A mixed maximum-size graph completed 100,000 evaluations in about 48 ms with zero managed bytes allocated in its evaluation loop; cached snapshot reads also allocated zero bytes after warm-up. These are isolated offline checks, **not a new game FPS measurement**. Compatibility audits passed 85 native hooks and 6,155 reachable Unity wrapper calls with no unavailable paths.

Download the runtime ZIP for installation. The separate **Source ZIP** contains the matching GPL-3.0 source, build scripts, tests and authored asset tools. Development, debugging and documentation assistance: **OpenAI ChatGPT / Codex**.

## 0.11.10 — Controller options, engine fixes and performance

- Added independent native Collective/Throttle lift input and output selection, plus separate custom lift axes. Corrected Collective input so climb/descent requests reach the assistant.
- Added optional activation delay after measured hover-nozzle arrival, and separate pitch/roll/yaw angular-acceleration profiles in deg/s² (0 disables each limit).
- Added a one-time custom-axis write on transition completion, including manual handover.
- Added independent ON/OFF sequence options to hold or release outputs after the final step and wait. Zero-wait final commands still execute once.
- Added Logic Processor outputs for Pitch, Roll, Yaw, all three trims and Throttle.
- Fixed piston-case mesh loss after a test drive and return to the editor, including newly loaded/created engines. Rockets and liquid-fuel RCS now honor Unlimited Fuel.
- Reduced repeated allocation calculations, duplicate propulsion/body reads, empty-controller queries and stable-wing preparation/registry allocations. Painting and native lifecycle repair remain active.
- Expanded the English Wiki and added the development acknowledgement.

The author reported a **1% low improvement from 17 FPS to 41 FPS** in the Test Vtol setup with the performance update. This is one reported setup, not a general FPS guarantee. Offline allocation comparisons produced identical outputs; native/boundary regressions were also checked. Aircraft and other installed mods can change the result.

## 0.11.9 — Airframe Excelence

- Renamed the combined mod and DLL to **Airframe Excelence / AirframeExcelence.dll**.
- Retained existing part folders, save metadata, settings and internal texture paths.
- Added English installation, system guides and troubleshooting documentation.
- Published the finished runtime files separately from the matching GPL source archive.

## Included fixes from 0.11.8

- Boxer case closure accepts the valid stock mesh without UV0 instead of aborting.
- Custom piston flywheels follow the actual compact rear case plane, including direct flywheel-setting updates.
- Preserved normal stock arrangements, selected flywheel radius/visibility and native engine solving.

## Other included features

- Up to 12 procedural piston rows, Boxer and aligned radial layouts.
- Compact custom-engine spacing and fitted cases.
- Catalog images, tank/joint categorization and updated rocket visuals.
- Stability Assist, hover force control, forward modes and VTOL transition.
- Graphical Logic Processor and Sequence Controller with device commands.
- Bleed/hydraulic motors, CVT control, two-motor coupling and fuel transfer.
- Editable tanks, joints/servo, rockets/RCS and procedural wing devices.

The 0.11.8 engine correction was confirmed in-game by the author before this branding release. Automated checks cover native bindings and selected production-code boundaries; aircraft-specific flight behavior and interactions with other mods remain dependent on the installation and aircraft.
