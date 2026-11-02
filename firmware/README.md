# Arduino firmware archive

**Source recovery pending.** The original successful sketches are not available in this repository yet. No replacement sketch is being presented as tested historical code.

1. Open the working sketch in Arduino IDE on the laptop used for the robot.
2. Save an unchanged copy under a descriptive sketch folder; Arduino folder and `.ino` base names must match.
3. Record IDE version, board package/version, board selection, port and serial settings.
4. Confirm the exact pin map against the assembled robot before reproducing movement.
5. Add a test record and demo tied to the commit. Preserve separate motor-test and serial-control versions if both exist.

Earlier instructions used 9600 baud, No line ending, and `F`/`B`/`L`/`R`/`S`. Verify these in the recovered sketch before use. Stop-on-disconnect and watchdog behavior are unknown until tested or implemented.
