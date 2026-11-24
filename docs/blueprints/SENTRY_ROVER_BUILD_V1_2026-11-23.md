# SENTRY Rover Build Blueprint v1.0 — 2026-11-23

Status: plan established; NOT manufacturing-ready CAD or tested new chassis.

## Verified starting point
- LAFVIN LA018-class R3/V5 + L298N and 2WD + caster assembled.
- Arduino sketch upload functional, two motor spin test succeeded, Serial Monitor F/B/L/R/S commands confirmed.
- Pi 4 Python over USB commands W and forward wheels movement confirmed.
- Orange enclosure v0.6 printed but failed wheel arch alignment/size, bumper length and battery barrel plug clearance.
- Pi keyboard GUI, Arduino motor watchdog, untethered Pi power, camera video, browser controls, ultrasonic auto-stop: NOT yet confirmed.

## Finish line (v1)
Printed modular frame, secure motor/wheel/caster mounts, battery and electronics mounts, upper Raspberry Pi 4 tray (four M2.5 fasteners), mount for actual camera model, regulated independent mobile Pi supply, Arduino motor timeout on loss of commands, accessible battery stop, phone/browser control over trusted LAN (jvmbot.local where mDNS available, LAN IP fallback), ultrasonic obstacle stop, modular panels and service hatch, complete tests and evidence. Command City/JVMGuard integration later v1.1.

## Architecture
Phone/web UI -> Pi4 Python web service + camera + telemetry -> USB serial -> Arduino R3/V5 watchdog and HC-SR04/servo -> L298N -> 2 drive motors. Pi via separate regulated USB-C source rated 5V/3A; do not power from L298N, Uno 5V or raw 2x18650 battery.

## Stage-gated build order
| Stage | Action | Pass condition |
|---|---|---|
| P0 | Backup exact working sketches, map wire colors/pin connections, photograph current robot | Recoverable baseline |
| P1 | Parametric virtual assembly with Pi/Uno/TT motors/caster/L298N/battery and plugged-in connectors | No virtual interference; clearance/access checked |
| P2 | Print ONLY TT motor mount, Pi hole gauge, fastening coupon | Real hardware fits without forcing |
| P3 | Print lower tub, other motor mount, caster attachment | Level chassis; tires and caster roll freely |
| P4 | Add battery, R3/V5 and L298N printed mounts; preserve wiring | Wheel-off-ground tests pass |
| P5 | Install printed Pi tray/upper deck, actual camera-specific mast; USB serial link | Pi boots, W command and video preview work |
| P6 | Arduino motor command expiry + Pi hold-to-drive dead-man control | Automatic STOP on idle, USB removal, app loss |
| P7 | Add safe portable USB-C Pi power bank with 5V/3A continuous output | Supervised mobile run without Pi brownout |
| P8 | Build local jvmbot.local browser drive + video + status + STOP | Same-Wi-Fi phone drives and stops safely |
| P9 | HC-SR04 reading and servo scan; conservative obstacle stop | Verified slow-speed obstacle test |
| P10 | Print side armor, compact bumper, roof hatch, cable guides | No wheel/sensor/cable contact; serviceable |
| P11 | Full acceptance run, videos, GitHub docs and later Command City integration | Reproducible v1 demo; v1.1 integration bounded |

## Printable part families
Main lower tub; left/right TT motor clamps; optional caster adapter; battery tray/retainer; R3/V5 adapter; L298N mount; Pi tray and upper posts; front sonar/servo mount; left/right armor; short bumper; hatch; camera-specific mast; cable guides. Roughly 12-16 physical pieces, not printer jobs; final count follows CAD optimization and slicing. Use metal M2.5 Pi screws and M3 structural hardware.

## Golden rules
Never print a whole shell before tiny fit coupons pass. Never change wiring and firmware in one test. Preserve baseline. Don't drive with loose cover. Don't power Pi from raw motor pack. Physical fit remains unverified until tested; manufacturer reference sizes do not mean LAFVIN clone connector locations are exact.

## Next action
Power off, archive known-good firmware and Python, photos and wire map; build virtual assembly; then print first TT motor clip coupon. PDF companion: JVMBOT_SENTRY_Rover_Complete_Build_Blueprint_v1.pdf (generated in chat).