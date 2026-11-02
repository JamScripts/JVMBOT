# Next lab: discover the R3 from the Pi

**Goal:** prove Linux can identify the board. This checkpoint does not command motion or change firmware.

1. Preserve the working Arduino sketch and photograph wiring first.
2. Turn motor power off. Confirm the kit's power routing before connecting USB alongside any other supply. Keep wheels raised for any later motor test.
3. Boot the Pi with its suitable power supply. Open its terminal locally or through an already working SSH connection.
4. With the R3 USB disconnected, run:

   ```bash
   ls -l /dev/serial/by-id/
   ```

   If the directory is absent, record that; it may simply mean no matching USB serial device is attached.
5. Connect a data-capable USB cable from a Pi USB-A port to the R3 USB-B port. Repeat the listing. Record the new stable device link if present; CH340 devices often appear under a ttyUSB name, but use the observed result.
6. Inspect identity and permissions without granting broader access:

   ```bash
   id
   ls -l /dev/ttyUSB* /dev/ttyACM*
   ```

   A “no such file” result for one pattern is not by itself failure. Use the device that actually appeared. Do not use `chmod 777` or run an eventual controller as root to hide a permission problem.
7. Record the Pi OS, USB identity, link, permission group and disconnect/reconnect result in a test record. Redact private network information before publishing.

**Pass:** a real connected board appears and disappears predictably, with its device identity recorded. **Not yet proven:** commands reaching motors, a watchdog, phone control or City telemetry.

Next design gate: validate the firmware contract and motor-side stop behavior before enabling bounded Pi commands. Only one application may hold the serial port.
