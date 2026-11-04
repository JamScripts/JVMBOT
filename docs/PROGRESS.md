# Progress ledger

Baseline recorded 2026-11-01. Earlier lab dates are approximate unless an artifact establishes them. This is a retrospective record, not a claim these tests were rerun during repository setup.

| ID | Work | State | Evidence / limitation |
| --- | --- | --- | --- |
| C01 | Assemble LAFVIN chassis, motors, wheels and caster | Builder-confirmed completed | Conversation confirmation; photos to archive |
| C02 | Wire R3 / V5 / L298N robot | Builder-confirmed completed | Exact as-built wiring and power details not yet archived |
| C03 | Resolve repeated Arduino upload failure | Builder-confirmed completed | “Done Uploading” reported after troubleshooting; definitive root cause not captured |
| C04 | Run motor exercise; observe both wheels spinning | Builder-confirmed completed | Builder statement; exact test sketch and video pending |
| C05 | Use serial keyboard commands to control movement | Builder-confirmed completed | Builder said exercise worked; exact running firmware pending |
| H01 | Pi boot, desktop, SSH and Python environment | Historical documented progress | 2026-10-04 blueprint; current recheck and source evidence pending |
| H02 | Simulated movement, obstacle checks and reusable controller | Historical documented progress | Blueprint reports prototypes; not physical autonomy and source not recovered |
| H03 | Modular package, JSON logging and tests | Historical delivery claim | Blueprint reports files delivered; no fresh execution or source import in this baseline |

## 2026-11-04 builder-confirmed Raspberry Pi milestone

| ID | Work | State | Evidence / limitation |
| --- | --- | --- | --- |
| C06 | Raspberry Pi Python via USB serial to R3 commands JVMBOT forward | Builder-confirmed | Pi console `W` moved both wheels; precise software revision and repeatable raw output not yet archived. See [milestone log](milestones/2026-11-04-pi-forward-confirmed.md). |

## Not yet demonstrated here

Pi-side A/S/D/X individual exercises, motor-side timeout, GUI hold-to-drive and link-loss safety, phone driving, an installed motor watchdog, measured motor speed, enclosure fit, live Command City telemetry, enforced JVMGuard robot policy, camera perception, autonomous navigation, and battery state estimation.

## Session log

| Recorded date | Outcome | Next checkpoint |
| --- | --- | --- |
| 2026-11-01 | Consolidated reported robot progress, evidence gaps, technical plan and portfolio structure | Recover exact firmware and demo evidence |
| 2026-11-04 | Raspberry Pi Python console `W` physically moved both wheels forward (builder-confirmed) | Archive exact firmware; watchdog and hold-to-drive test |

Use [the session template](templates/SESSION.md) for each new lab. Completed issues preserve the evidence level rather than retroactively upgrading a recollection to a verified test.
