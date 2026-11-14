# JVMBOT SENTRY — Manufacturer-first hardware dimensions (2026-11-14)

**Source of truth:** LAFVIN LA018 **2WD Smart Robot Car Kit V1**, L298N, Uno-compatible CH340 R3 with V5 shield, two yellow TT-type motors/wheels, HC-SR04 on SG90-style servo, 2×18650 holder, rear caster; added Raspberry Pi 4 Model B. **Do not confuse this with the LA039 or ESP8266/L9110S variants.**

## Direct official/manufacturer-derived data

| Part | Confirmed reference | Source and caveat |
| --- | --- | --- |
| LAFVIN kit identity | LA018/V1; R3 + V5 + L298N, HC-SR04, motor pair, 2 × 3.7V 18650 cells | LAFVIN product https://lafvintech.com/products/lafvin-smart-robot-car-2wd-chassis-kit-with-ultrasonic-module-l298n-driver-board-remote-ir-control-for-arduino-uno-diy-kit and official tutorial directory https://lafvintech.com/pages/tutorials3 |
| Raspberry Pi 4 Model B | PCB 85 × 56 mm, mounting pitch 58 × 49 mm | Official mechanical drawing https://pip-assets.raspberrypi.com/categories/559-mechanical/documents/RP-001185-MD-1-Mechanical%20Drawing.pdf |
| Arduino Uno Rev3 reference | 68.6 × 53.4 mm outline, irregular four-hole pattern, Ø3.20 mm holes | Arduino official https://store.arduino.cc/products/arduino-uno-rev3 and https://docs.arduino.cc/resources/datasheets/A000066-datasheet.pdf; *LAFVIN clone/V5 shield may differ in connector protrusions* |
| SG90 reference | 23 × 12.2 × 29 mm servo body | Original TowerPro https://towerpro.com.tw/product/sg90-analog/; supplied generic may vary |
| HC-SR04 reference | ~45 × 20 × 15 mm class | Reference module vendor datasheets; actual clone may vary e.g. https://www.elecrow.com/download/DS_IM120628012_HC_SR04.pdf |

## Compatible supplier references, not verified as exact LAFVIN parts

| Part | Preliminary reference | Source / limitation |
| --- | --- | --- |
| L298N breakout board | 43 × 43 mm-class PCB; 37 × 37 mm mounting pattern seen for a specific module | https://surplustronics.co.nz/product/MOT0375/info-603.pdf?1417135682= ; L298N IC manufacturer does **not** standardize third-party PCB outline |
| Yellow TT geared motor | 70 × 22 × 18 mm body | Adafruit example https://www.adafruit.com/product/3777 ; not exact LAFVIN motor |
| Yellow TT wheel | ~65 mm diameter × 28 mm width | Example supplier https://geeksvalley.com/en/product/tt_motor_with_wheel/ ; not exact LAFVIN wheel |
| LAFVIN chassis/battery pack/caster motor bracket | No verified **kit-specific mechanical drawing** found in accessible public product/manual pages | Do not infer precision hole locations from product package dimensions or photos |

**Important caution:** Some reseller listings show 11.02 × 7.09 × 1.97 in (~280 × 180 × 50 mm) as 'product dimensions'. This is not a verified dimensioned outline of the assembled chassis and must NOT be used as an STL chassis cut line. Manuals indexed online for 'LA018' sometimes conflict on battery formats; authoritative LAFVIN V1 product page says **2×18650**.

## No-measurements CAD strategy

1. Create motor/carrier *test couplers* with rounded and adjustable slots and loose tolerances using the known TT-motor class envelopes.
2. Split lower chassis into modular replaceable sections; allow motor bracket location to vary without drilling or whole-chassis reprints.
3. Put Raspberry Pi 4 on manufacturer-known mounting grid with generous cable-connection free space (USB/Ethernet power etc.).
4. Use mounting slots and/or universal trays for uncertain L298N, battery holder, caster, and clone R3 holes.
5. Print tiny fit coupons using manufacturer-derived defaults; accept that final physical fit cannot be guaranteed without a trial print or a full original vendor STEP/DXF.
6. Rework/replace only the coupon or modular mount if a part doesn't fit; do **not** reprint an entire cosmetic body.
7. Once structural pieces fit, make cosmetic orange/black panels from final chassis dimensions.

### Acceptance criteria

- No interference with wheels during 360° rotation (unpowered).
- No shell contact against electronics, battery barrel plug, cable bend radius, or motor wiring.
- Sensor full sweep unobstructed; servo bracket fastening stable.
- Power switch, reset, USB, and battery tray remain accessible.
- Structural Pi platform ventilation and separate 5V/3A Pi power provision.
- No powered test with unfastened body.

This is a researched starting spec, **not a dimensioned LA018 factory CAD file** and not a guarantee of press-fit dimensions.
