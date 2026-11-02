# Architecture and decisions

## Responsibilities

| Component | Present baseline | Target responsibility |
| --- | --- | --- |
| Laptop | Arduino upload and serial test interface | Development and recovery console |
| R3 CH340 | Runs motor-control sketch | Single physical actuator owner; boot-stopped outputs and independent command-expiry handling |
| V5 board / L298N | Expansion and motor-drive hardware | Documented as-built connections and power constraints |
| Raspberry Pi 4 | Owned; earlier environment progress documented | Linux services, command validation, logs and telemetry; serial client |
| Command City | Separate project | Initially read-only JVMBOT health and stale-state alerts |
| JVMGuard | Separate project | Future bounded policy evidence; no installed enforcement claim |

## ADR-001 — USB serial before GPIO integration

Decision: plan Pi USB-A to R3 USB-B for the first communication exercise. Keep the successful Arduino baseline and avoid guessing GPIO voltage compatibility. Discovery comes before commands. Actual port names must be discovered rather than assumed.

## ADR-002 — Stop must survive a dead sender

Decision: a Python `finally` block or network Stop button cannot be the only protection. Plan a motor-side watchdog / command deadline and a reachable physical motor-power disconnect. Demonstrate boot, expiry, process crash, USB loss and reconnect behavior before unrestricted control. Do not infer these protections exist in the old sketch.

## ADR-003 — One command path

Decision: operator and future agent requests enter one validated controller. One process owns the serial port. Requests carry bounded parameters, identity and expiry; unknown/expired requests stop or reject. No direct AI shell, GPIO or serial write access.

## ADR-004 — Telemetry integration is separate from movement

Decision: first City integration sends real Pi health and heartbeat only. Missing values stay unknown; stale data is visibly stale. Motor control does not enter City as part of the telemetry milestone.

## ADR-005 — Preserve evidence before replacing software

Decision: recover the exact working sketches before creating new firmware. Capture hardware revisions and configuration alongside code. Simulation results and generated code are not physical test evidence.

## State model to implement later

Lifecycle: BOOTING, IDLE, READY, ACTIVE, FAULT, EMERGENCY_STOP, RECOVERING, SHUTTING_DOWN. Keep manual/assisted/autonomous mode separate. Unknown transitions stop; a restart never resumes movement automatically; releasing an emergency stop requires deliberate reset and a fresh authorized request.
