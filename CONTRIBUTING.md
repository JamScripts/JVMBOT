# Development and update workflow

1. Select one Next Up issue with an observable completion gate.
2. Move it to In Progress and preserve the current working baseline.
3. Work on a descriptive branch; keep hardware and configuration changes traceable.
4. Record expected/actual behavior, environment, exact code revision and relevant failure exercise.
5. Attach sanitized evidence and update `docs/PROGRESS.md`. Use explicit evidence levels.
6. Commit the source and documentation together; review before merging.
7. Move to Completed only when the gate is met. Keep missing artifacts as separate open tasks.

## Board

Use **Backlog**, **Next Up**, **In Progress**, **Completed**. Maintain one active physical lab task. GitHub issues are the live work records once imported; `tracking/` is the initial seed snapshot and must not be mistaken for automatically synchronized state.

Future chat sessions do not automatically upload laptop files or know every change. Provide the repository link and the session result; update the associated issue and documentation with each meaningful checkpoint.

## Publishing rules

No credentials, `.env` contents, private network topology, employer information, household details or unreviewed personal media. Firmware/CAD must be your work or carry appropriate attribution and redistribution permission. Do not copy vendor example code or private related repositories wholesale.
