# 2026-11-04 — Physical Pi-to-Arduino drive milestone

**Evidence tier: builder-confirmed.** The builder reported that running the Raspberry Pi Python console controller and entering `W` caused JVMBOT's two wheels to move forward.

## Confirmed current control path
Pi 4 (Linux, Python, pyserial) → Pi USB-A → LAFVIN R3 CH340 USB-B → Arduino serial firmware (9600 baud) → V5 + L298N → motors.

The Pi console mapped `W` to Arduino byte `F`. The reported Linux device was `/dev/ttyUSB0`. Earlier, the builder independently confirmed the Arduino Serial Monitor commands F/B/L/R/S worked, motor test spun both wheels, and normal firmware upload succeeded after troubleshooting.

## Evidence limitation
No terminal transcript, measured stopping latency, input video, exact original running firmware export, or controlled link-loss test was uploaded with this commit. **Only Pi forward movement was individually reported**; the other Pi direction keys are not separately verified here. Do not mark an MCU watchdog, a physical power disconnect, battery runtime, ultrasonic obstacle avoidance, phone control, camera, or Command City link as completed.

## Next bounded test
1. Archive a copy of the current Arduino IDE sketch and Pi Python script.
2. Upload candidate Arduino serial firmware with an explicit 400ms movement timeout.
3. With wheels raised, confirm a single `F` command automatically stops after timeout.
4. Test a local Pi desktop GUI that sends movement commands while W/A/S/D are held and sends stop on release, focus loss, or exit.
5. Only then evaluate untethered Pi power and physical mounting.

## Power and CAD design intent
Use independent properly regulated USB-C power for Pi 4 (5V/3A continuous), separate from robot drive battery as the first mobile prototype. Protect the upper Pi with a modular canopy, preserve sensor swivel and port clearance. Chassis hole spacing / cable clearance are not measured, so enclosure CAD remains an **unverified fit prototype**.

## Historical failure and repair
Windows initially detected CH340 on COM4/COM5 and compiled sketches, but `avrdude` repeatedly reported `not in sync: resp=0x00` and intermittent port denial. Driver and port tests did not independently prove a root cause. Following Arduino board-package/software reset and reinstall, Blink upload and V5-mounted upload were builder-confirmed successful; don't claim driver rollback alone fixed it.

**Portfolio competency:** Linux/embedded integration, serial protocol, PWM drivetrain, incident troubleshooting, hardware/software separation, evidence discipline.
