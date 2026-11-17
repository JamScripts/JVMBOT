# JVMBOT — evidence-driven completion roadmap

**Audit date:** 2026-11-17  
**Basis:** default branch `main`, project documentation, milestone log, and open GitHub issues. No live robot, laptop, Raspberry Pi, Arduino, or electrical system was accessed or tested in this audit.  
**Execution rule:** one active hardware checkpoint, one observable acceptance test, and no unverified claims.

## 1. Current state: reported behavior versus reproducible evidence

| Capability | What is supported today | What is missing |
| --- | --- | --- |
| LAFVIN 2WD assembly and R3/L298N wiring | Builder-confirmed | As-built pin/power map and sanitized photos |
| Arduino upload, two-wheel motion, laptop serial control | Builder-confirmed | Original working `.ino` sketches, environment record, repeat tests |
| Raspberry Pi USB serial forward drive | Builder-confirmed on 2026-11-04: Pi console `W` led to forward wheel motion | Original Pi Python script, exact firmware revision, raw transcript, independent re-test |
| Stop on timeout, boot/reset, sender crash or USB loss | Design requirement | Firmware implementation and actual fault-test evidence |
| Camera, portable Pi power, fitted protective case | Hardware/design goals | Detected camera details, regulated mobile power, physical dimensions, CAD, printed fit evidence |
| Phone control, City telemetry, obstacles and secure AI missions | Planned | Implementations and real-device validation |

The current repository contains documentation, templates, and issues but **does not contain the exact running Arduino or Pi controller source**. That is the principal reproducibility blocker. A prior physical movement report must not be downgraded to “never happened,” but is not the same as a repeatable release.

See [evidence register](docs/EVIDENCE.md), [progress](docs/PROGRESS.md), and [2026-11-04 milestone](docs/milestones/2026-11-04-pi-forward-confirmed.md).

## 2. Definition of JVMBOT v1 complete

A v1 portfolio demonstration is complete when all these can be repeated by following documented setup instructions:

1. Arduino and Raspberry Pi source is versioned, identifiable, and tied to real wiring/power and tool versions.
2. With the wheels raised, R3 boots stopped, accepts bounded commands, independently expires movement on lost refresh, and does not auto-resume after restart, serial disconnect, or sender failure.
3. The Pi identifies the board through a documented USB serial device path, starts one local controller, exercises directional motion and stop reliably, and records meaningful diagnostics.
4. The mounted Raspberry Pi uses a safe, suitable power source, the purchased camera can capture a tested local image/stream, and any networking is authenticated/local first.
5. A removable, measured, printed body and camera/Pi mount fit the actual robot without blocking wheel travel, ventilation, wiring, USB access, or a reachable motor-power disconnect.
6. A repeatable supervised demo, at least one real failure-and-recovery exercise, setup guide, and sanitized evidence are committed. Link evidence to a specific revision; only then consider tagging a release.

AI autonomy, ROS 2, public internet control, commercial safety claims and full Command City integration are **not prerequisites for v1**. They remain optional expansion work.

## 3. Dependency-first milestones

| Gate | Work and linked issues | Proof to close gate | Priority |
| --- | --- | --- | --- |
| M0 — Physical baseline | [#1](https://github.com/JamScripts/JVMBOT/issues/1), [#2](https://github.com/JamScripts/JVMBOT/issues/2), [#3](https://github.com/JamScripts/JVMBOT/issues/3) | Preserve existing builder-confirmed history without relabeling as reproduced | Recorded; archive pending |
| M1 — Recover known-good code and wiring | [#4](https://github.com/JamScripts/JVMBOT/issues/4), [#5](https://github.com/JamScripts/JVMBOT/issues/5), [#17](https://github.com/JamScripts/JVMBOT/issues/17) | Commit unchanged original `.ino` and Pi `.py`, document protocol, versions, pin/power map; supervised raised-wheel replay with test record | **FIRST** |
| M2a — Identify Pi serial device | [#7](https://github.com/JamScripts/JVMBOT/issues/7) | Stable USB identity/permissions and unplug/replug evidence with motor power off; do not assume `/dev/ttyUSB0` is stable | After source capture |
| M2b — Independent motor-side fail-safe | [#8](https://github.com/JamScripts/JVMBOT/issues/8) | Boot/reset stopped; finite command expiry; test no refresh, sender death and USB loss with wheels raised, record measured observations | Safety gate before broader driving |
| M2c — Reproducible Pi control | [#9](https://github.com/JamScripts/JVMBOT/issues/9) | One serial writer, validated F/B/L/R/S contract or actual recovered protocol, bounded motion, explicit stop, logs and fault recovery | After M2b |
| M3 — Portable physical assembly | [#10](https://github.com/JamScripts/JVMBOT/issues/10), [#11](https://github.com/JamScripts/JVMBOT/issues/11) | Verify Pi power and camera type; measure real assembly; print small fit coupons; then build removable case/Pi/camera bracket and inspect clearances | After control reliability |
| M4 — Local operations and camera | [#12](https://github.com/JamScripts/JVMBOT/issues/12) plus a dedicated camera acceptance record/issue | Pi service starts stopped, logs health and faults; camera produces tested local still/frame or stream; reboot/stop recovery captured | Core v1 |
| M5 — Optional integrations | [#13](https://github.com/JamScripts/JVMBOT/issues/13), [#14](https://github.com/JamScripts/JVMBOT/issues/14) | Telemetry remains read-only at first; phone controls are authenticated, expiry-bounded, and have no independent motor writer | Post-v1 |
| M6 — Future autonomous/security research | [#15](https://github.com/JamScripts/JVMBOT/issues/15), [#16](https://github.com/JamScripts/JVMBOT/issues/16) | Real sensing, freshness, fail-closed proposals, model never authorizes itself; no simulation-to-hardware claim | Deferred |

Do not bypass M1 simply because movement worked once: without the exact source, a new sketch can silently change pin mapping or erase a working baseline. Do not use `chmod 777`, put motor power through Pi GPIO, or expose a motor-control service directly on the public internet.

## 4. First seven-day sprint (November 17–23)

**One active hardware task at a time.** Total suggested effort: three focused sessions of 30–60 minutes, adjusted for work and family.

1. **Archive what already worked — #4.** On the Windows programming laptop, locate and save the original successful motor-test and serial-control Arduino sketches unchanged, and the Python script used for Pi console `W`. Record Arduino IDE/board settings, exact serial baud/command mapping, and any locally observed commit or file versions. Inspect attribution and secrets before pushing. **Pass:** repository contains the actual files, not AI recreations labeled “original.” **If missing:** record the loss and build a separately named replacement, not a fake recovered original.
2. **Capture hardware truth and basic replay — #5.** With motor power disconnected before inspecting, photograph wire routes and list actual driver/R3 pins, jumper locations, battery chemistry/cell count, motor polarity and Pi power method. Arrange a stable raised-wheel test, away from children and edges, with a reachable power cutoff. Repeat basic directions and stop under supervision; record exact observed results rather than assuming all Pi keys worked. **Pass:** sanitized wiring/power record, media references and test result linked to code revision.
3. **Establish stable Pi USB access — #7.** With motor power off, run the existing [Pi USB runbook](docs/runbooks/PI_USB_CHECKPOINT.md); capture `/dev/serial/by-id` when available, `id`, device permissions and reconnect behavior. **Pass:** a repeatable real device identity plus permission record, without motion.

**Next after sprint:** implement and physically validate the motor-side watchdog (#8) using a separate reviewed revision, then revise/retest the bounded Pi client (#9). The previously discussed 400 ms timeout is only an initial design candidate, not an observed safe stop guarantee; record the actual behavior and account for software/driver latencies.

## 5. Test and publication discipline

Each tested checkpoint records: UTC date/time, exact commit, board and Pi environment, physical setup, expected behavior, actual behavior, failure observations, operator, and sanitized photos/logs. Use [test template](docs/templates/TEST_RECORD.md). Distinguish **Planned → Builder-confirmed → Artifact attached → Reproduced** without automatically promoting evidence levels.

A safe test begins with the robot supported so wheels cannot propel it. Unplugging USB may alter board power: verify electrical topology before any link-loss exercise. Keep the motor-power disconnect reachable. No automatic test, simulator, or AI-generated writeup proves that a motor stopped physically.

## 6. How this supports the second goal (AZ-104)

Keep AZ-104 as a separate, active certification track, not a reason to inflate JVMBOT scope. Reuse only genuinely transferable concepts: Linux device/service diagnostics, least privilege, logs/health and command validation. For cloud-specific AZ-104 outcomes, complete Azure Portal/CLI labs directly and assess them without assistance. Avoid deploying Command City, robot telemetry or camera video to billable Azure resources merely to make the two goals appear connected.

## 7. Release criteria

- **Baseline evidence checkpoint:** #4 + #5 + #7 completed with exact source, verified device identity and meaningful real evidence.
- **Safe control checkpoint:** #8 + #9 reproducible, including an independent stop after sender/link failure.
- **Physical v1 checkpoint:** verified Pi power, camera, removable enclosure/camera mount, local service and repeatable demo.
- **Portfolio release:** [#17](https://github.com/JamScripts/JVMBOT/issues/17) evidence complete; only tag after real hardware validation.

This plan is based on repository evidence, not a live hardware inspection. Update statuses when the tests are performed, not when code is generated.
