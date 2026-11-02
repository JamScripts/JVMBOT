# Incident: Arduino upload failures

## Recorded symptom and outcome

Programming on Windows repeatedly failed with `programmer is not responding`, `not in sync: resp=0x00`, and later `Access is denied`. COM4 was used in the earlier attempts. The builder subsequently reported `Done Uploading`, then successful motor and keyboard exercises.

**Resolved outcome, unconfirmed root cause:** the available record does not prove which change fixed it. The V5 shield was discussed during isolation; do not assert that it caused the failure or that a board replacement was necessary.

## Beginner diagnostic procedure for a recurrence

1. Stop the robot, switch off motor power, and disconnect USB before removing a shield or changing wires. Photograph the working arrangement first.
2. Connect the R3 directly using a known data-capable USB cable. Watch Windows Device Manager for the port that appears; do not assume it is still COM4.
3. In Arduino IDE, select the correct Uno-compatible board and that observed port. Close Serial Monitor, other IDE windows and other programs holding the port before upload.
4. Compile and upload a minimal known sketch with the motors isolated. Capture the exact error or success text. Distinguish compilation failure from port access and upload handshake failure.
5. If upload works on the bare R3, disconnect USB before reinstalling the shield. Inspect connections using the actual kit reference; test one change at a time.
6. After a successful upload, recheck the intended firmware and test with wheels raised and motor power reachable. Upload success alone does not prove correct motor directions.

If it still fails, record cable, port appearance, board selection, driver version, upload output and isolation results. Avoid repeated random driver changes or purchasing another board before isolating the failing layer.

## Evidence to add

Exact successful change, IDE output, environment versions, baseline sketch, repeat test result and a sanitized photo. Never claim a definitive cause until the evidence supports it.
