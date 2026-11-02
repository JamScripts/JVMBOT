# Roadmap

Sequence is based on evidence and dependencies, not promised delivery dates. Only one hardware checkpoint should be In Progress.

| Milestone | Scope | Completion gate | Initial state |
| --- | --- | --- | --- |
| M0 — Physical baseline | Assembly, upload, motor and serial exercises | Builder confirms each result; remaining evidence gaps stay visible | Builder-confirmed; evidence archive pending |
| M1 — Reproducible baseline | Recover exact sketches, photos, wiring, versions and test logs | Clean checkout can reproduce a supervised demonstration with traceable evidence | Next |
| M2 — Pi integration | USB discovery, serial bridge, motor-side watchdog, fault tests | Boot stopped; bounded motion; expired commands and disconnected sender stop motors; reset requires fresh command | Planned |
| M3 — Mechanical protection | Measure, design and fit removable body / Pi mount | Ports, power disconnect, ventilation and sensor travel remain accessible; no wheel/cable interference | Planned |
| M4 — Operations telemetry | Local service, logs, health, telemetry-only Command City link | Real measurements identified; invalid credentials rejected; stale/offline/restart behavior demonstrated | Planned |
| M5 — Supervised phone control | Authenticated local command UI through one controller | Access control, command validation, expiry, contention and disconnect tests pass | Planned |
| M6 — Secure missions | Sensors, bounded missions, policy and JVMGuard integration experiments | Unsafe/unknown proposals block; stale sensors stop; model cannot self-authorize; failure report produced | Future |

## Next actions

1. Record the wiring, board settings and a short forward/back/left/right/stop demonstration with the wheels raised.
2. Discover the R3 from the Pi over USB without issuing movement commands; record actual device identity and permissions.

## Later expansion gates

- Obstacle detection requires sensor mounting, timeout/freshness tests and physical calibration. A kit's advertised feature is not a proven JVMBOT feature.
- Encoders and odometry are optional later hardware. Until installed and validated, duty cycle is a command, not measured speed or distance.
- Camera processing, ROS 2 and local AI follow reliable control and diagnostics. Choosing software versions when the implementation begins.
- Remote access outside the home remains deferred until the local system is authenticated and tested. No direct public motor-control endpoint.
- Command City and JVMGuard remain separate projects; will link all together into separate repository
## Release gates

**First physical release:** exact firmware, verified wiring, environment details, repeatable demo, test record, fault exercise and incident note tied to a commit. No release tag is created merely because documentation exists.

**Pi integration release:** add deterministic stop behavior, link-loss evidence, deployment/recovery instructions and a real Pi serial demonstration.
