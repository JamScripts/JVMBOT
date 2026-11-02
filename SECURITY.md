# Security design and reporting

JVMBOT is an educational system. Security controls listed in the roadmap are goals until implemented and tested.

Never commit keys, tokens, passwords, private IP/network inventories or sensitive logs. Use placeholders in examples. Keep remote control local until an explicit authenticated design and negative tests exist. Do not expose a motor endpoint directly to the public internet.

Future controls: least-privilege node identity; authenticated command requests; schema and range validation; command expiry; single actuator owner; motor-side watchdog; stale-sensor rejection; audit events; no model self-approval or direct shell/GPIO access.

For a security issue, avoid placing credentials or exploitable private details in a public issue. Use GitHub private vulnerability reporting if enabled; otherwise contact the maintainer through an already established private channel. No private reporting address is configured by this initial baseline.
