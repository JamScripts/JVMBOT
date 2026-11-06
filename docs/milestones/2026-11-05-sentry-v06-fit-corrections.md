# JVMBOT SENTRY v0.6 physical fit test — builder feedback, 2026-11-05

**Status: printed main outer shell, not fit for use.**

The builder's physical orange shell trial identified three problems:
1. Wheel cutout is in the wrong longitudinal position relative to the real wheels.
2. Wheel arch is too wide.
3. Front bumper portion needs to be shorter.
An earlier observation also identified the protruding battery barrel-power connector/cable as an interference point.

Observed from builder-supplied photographs; the shell has not been fastened. Wheel travel, servo sweep, top hatch, structural mounts, and safe powered driving with shell remain **not verified**.

## Root cause in v0.6 assumptions
The v0.6 model used a wheel arch center x=-5 mm relative to a nominal 210 mm hull midpoint and a radius of 41 mm (82 mm wide). Actual wheel position and inside clearance had not been measured; the CAD was an estimated fit prototype.

## v0.7 provisional changes created (not user-verified)
- Wheel center position x=-38 mm (forward 33 mm)
- Wheel arch radius 36 mm (72 mm diameter; 10 mm narrower)
- Shell length 198 mm (12 mm shorter overall; front and rear 6 mm each)
- Separate cosmetic bumper from 15 to 10 mm longitudinal depth, 98 to 88 mm total width
- Added provisional battery cable cutout on both side walls, pending measurement of actual side and connector position
- Created *thin side alignment gauge* to test wheel arch / plug position before a new full hull print
- Created separate shortened bumper prototype
- Full v0.7 hull exported for inspection only; **do not print until gauge fits**

The revision uses real photo feedback but **still lacks precise measurements**. These are trial geometry adjustments, not confirmed fits. Source/output package was delivered in ChatGPT conversation.

## Next acceptance criteria
- Mark front-of-shell datum.
- Measure from hull front reference to wheel axle center.
- Measure wheel diameter, required radial clearance and shell-to-tire gap.
- Measure required shortened bumper overhang along robot axis, and separately confirm bumper width.
- Locate power plug and needed bend radius relative to shell front and chassis top face.
- Print arch alignment gauge and photograph it against stationary robot; no power.
- Do not print the other full parts until clearance and mounting are verified.
