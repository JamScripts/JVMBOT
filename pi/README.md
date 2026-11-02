# Raspberry Pi subsystem

Pi integration is planned. No controller or systemd service is supplied as tested software in this baseline.

Start with [USB discovery](../docs/runbooks/PI_USB_CHECKPOINT.md). Then recover or implement a bounded serial client only after the Arduino baseline and motor-side stop requirements are documented.

Planned deliverables: explicit serial-device configuration, single port owner, safe startup, structured command/event logs, finite timeouts, local health status, deployment/recovery instructions and telemetry-only City client. A future phone UI uses that same validated controller.
