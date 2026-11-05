# 2026-11-05 — JVMBOT enclosure photo review and CAD prototype

**State: DESIGN / NOT FIT VERIFIED**

The builder supplied ruler/tape photos of the LAFVIN LA018 2WD robot to support an enclosure design. Visual inspection shows: mounted Arduino R3 with V5 shield, L298N, ultrasonic module on rotating servo, rear battery holder, two wheels, tall jumper harness and multiple chassis holes.

## Tape-photo estimates, not final measurements

| Dimension | Estimate from photographs | Confidence / limit |
|---|---|---|
| Acrylic body front-to-back | ~200–230 mm | Perspective and tape zero uncertain |
| Wheel diameter | ~65 mm | Approximate |
| Rear battery box long side | ~95–100 mm | Approximate |
| HC-SR04 module width | ~45–50 mm | Approximate |
| Usable width between wheel inner faces | unknown | Must measure |
| Four chassis mounting-hole centers | unknown | Must measure |
| Highest organized wire above acrylic | unknown | Must measure |

## v0.5 CAD fit prototype (locally delivered)

Editable parametric OpenSCAD source and several closed printable STL meshes were generated locally for the builder. They are **not** yet committed as binary artifacts to GitHub or test-fitted to the real robot.

- Raised canopy 144 × 104 mm default, front servo U-relief, open battery access.
- Four slotted-foot posts, default 80mm high; dimensions adjustable.
- Official Raspberry Pi 4 nominal board size 85 × 56mm, 58 × 49mm mounting pitch, standoff holes.
- Small print-first coupons to validate Pi mounting pattern and foot slot fit.
- Side vents / USB access. Optional Pi bumper is NOT fastened and must not be used loose.

**Design limits:** No guarantee the first STL fits chassis holes or wheel sweep; no claim of structural protection against crashes, no power-bank mount yet. The builder is instructed to print only small fit coupons until critical dimensions are taken.

## Next evidence required

1. Measured inner-wheel clearance and selected chassis hole center coordinates.
2. Height of highest re-routed cable above acrylic.
3. Servo full sweep, mounting hardware, Pi connector clearance.
4. Fit photos of coupons and later canopy on physical hardware.
5. Verify secure attachment and stability before driving on floor.

Prior physical proof remains [2026-11-04 Pi command driving forward](2026-11-04-pi-forward-confirmed.md). Never equate generated CAD with a successful enclosure fit.
