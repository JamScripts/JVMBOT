# Validation plan

No tests were rerun on physical hardware during this documentation baseline.

| Test | Procedure and expected result | Initial state |
| --- | --- | --- |
| T01 Upload | Compile/upload exact saved sketch; IDE succeeds | Builder-confirmed, raw output pending |
| T02 Motor channels | Wheels raised; test each channel; record wheel and polarity | Both wheels reported spinning; per-channel record pending |
| T03 Serial controls | Verify protocol; exercise forward/back/left/right/stop; record observations | Builder-confirmed, exact sketch pending |
| T04 Power/boot/reset | Start/reset with wheels raised; no unintended movement | Not tested in retrieved record |
| T05 Command expiry | Stop sender during a bounded command; motor-side timeout stops outputs within documented limit | Planned; prerequisite for expanded control |
| T06 Link/process loss | Disconnect USB / end Pi process; verify independent stop and no auto-resume | Planned |
| T07 Pi discovery | Record actual USB serial identity and permissions | Planned |
| T08 Pi command bridge | Exact protocol, bounded motion and explicit stop; correlate serial events | Planned |
| T09 Telemetry | Compare real Pi values, reject invalid identity, mark stale/disconnected | Planned |
| T10 Phone access | Reject unauthenticated/invalid/expired commands and competing writers | Planned |
| T11 Sensor faults | Stale/invalid/timeout sensor data blocks unsafe motion | Planned |
| T12 Policy | Unknown tool/proposal blocks; model cannot self-approve; denied commands never reach actuator | Planned |

Perform motion exercises supervised, with wheels raised first, on a stable support, away from edges and children, and with motor-power disconnect reachable. A commanded stop is not measured stopping distance. Record the actual limit observed; do not invent timing results.

Use [TEST_RECORD.md](templates/TEST_RECORD.md). A failed test is useful portfolio evidence when diagnosis and recovery are documented honestly.
