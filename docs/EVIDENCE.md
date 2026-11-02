# Evidence and source register

## Evidence levels

| Level | Meaning |
| --- | --- |
| Planned | Design or task only; no implementation claim |
| Historical documented | Earlier project document describes work; artifacts/run not independently checked here |
| Builder-confirmed | Builder explicitly reports doing the physical test and observing the outcome |
| Artifact attached | Code, log, photo or video is present and identified; presence alone does not prove a full test |
| Reproduced | Procedure executed against an exact revision and environment with results attached |

## Inputs used for this baseline

1. JVMBOT project conversation: builder reported successful upload, both wheels turning, and working serial keyboard commands. Conversations are summarized here, not published wholesale.
2. `JVMBOT_Blueprint.md`, dated 2026-10-04: mission, architecture, earlier software prototypes and honest measurement constraints. Its reported software deliveries have not been recovered or rerun here.
3. Command City `ROADMAP.md`, dated 2026-10-05: staged simulator and real Pi telemetry milestones; initial real-node integration explicitly excludes motor control. This is a design dependency, not proof of today's deployed City state.
4. Earlier assistant instructions describe serial `F/B/L/R/S`, 9600 baud, and a candidate pin map. The exact sketch and as-built wiring must validate these before reproduction. They are not manufacturer-verified wiring instructions.

## Missing artifacts

- Exact successful motor-test sketch and currently running control sketch.
- Board package/version, IDE version, selected port and actual board settings.
- As-built wiring photos and a pin-to-pin table, including power routing and jumper positions.
- Demo media, serial transcript, test dates and hardware revision.
- Earlier Pi/simulator package and its genuine test outputs.
- Enclosure CAD/STL files and physical measurements.

No source code was reconstructed and labeled as the original. No tests were marked passing merely from an earlier generated document. Media must be inspected and cleared of private information before publication.

## Attach evidence to a commit

Record test ID, UTC timestamp, operator, commit SHA, environment, procedure, expected result, actual result, and attachment path. Note whether a measurement is observed, commanded, simulated or unknown. An unavailable sensor reports UNKNOWN / NOT_INSTALLED rather than a fabricated healthy value.
