# Release notes

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
