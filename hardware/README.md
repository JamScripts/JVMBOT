# Hardware and wiring record

| Item | Known state | Record still needed |
| --- | --- | --- |
| LAFVIN 2WD chassis, two DC motors, wheels, caster | Assembled; both motors reported working | Photos, dimensions and motor specification |
| R3 CH340 Uno-compatible board | Successful upload reported | Board revision, device identity and IDE settings |
| V5 expansion board | Part of assembled kit | Clear top/bottom photos and as-built connections |
| L298N motor driver | Part of motor setup | Terminal mapping, jumpers, supply and regulator routing |
| Ultrasonic sensor / SG90 servo / IR components | Included in kit | Installed state and individual tests unconfirmed |
| Battery holder and batteries | Obtained for robot | Chemistry, cell count, voltage, protection and measured supply unrecorded |
| Raspberry Pi 4 with microSD | Owned; earlier setup documented | Current OS, power supply and USB discovery results |
| Bambu Lab P1S | Available for custom components | CAD dimensions and fit evidence |

## Candidate mapping from earlier instructions — NOT an as-built verification

| L298N signal | Previously proposed R3 pin |
| --- | --- |
| ENA | D5 |
| IN1 | D2 |
| IN2 | D4 |
| ENB | D6 |
| IN3 | D7 |
| IN4 | D8 |

Do not rewire from this table alone. Compare the physical kit, current working sketch, expansion-board routing and kit documentation first. Identify which wheel each channel drives and record direction polarity during a raised-wheel test.

Before changes, turn off motor power and disconnect USB. Do not power motors from Pi GPIO or infer a suitable Pi supply from an unknown motor battery. USB may power the R3; inspect the board/shield power arrangement before combining supplies. Preserve a reachable motor-power disconnect.

Use `docs/templates/TEST_RECORD.md` and add sanitized photos to `media/`.
