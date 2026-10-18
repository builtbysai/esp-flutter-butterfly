# ESP-FLUTTER Bionic Butterfly — Build Guide

An ESP32-C3 powered RC bionic butterfly that actually flies. Servo-driven ornithopter, phone-controlled, LED-lit wings. This repo is the complete build companion: parts, costs, and the no-3D-printer path.

Based on [Max Imagination's ESP-FLUTTER](https://youtu.be/5Le4I-1Pf9I) — all credit for the design, firmware, and files goes to him. This repo organizes the build; it doesn't replace his tutorial.

## At a glance

| | |
|---|---|
| All-up weight | 70 g |
| Flight time | ~5 min (longest continuous 1:09) |
| Range | ~25 m (WiFi) |
| Control | Phone web app (free) or RC transmitter |
| Wings | Produce bag with LEDs |
| First-build cost | **~$98** (no 3D printer needed) |
| Second build | **~$63** (tools already owned) |

## Full bill of materials

| # | Part | Spec | Price | Where |
|---|---|---|---|---|
| 1 | XIAO ESP32-C3 | Seeed Studio, RISC-V, WiFi + BLE | $4.90 | [seeedstudio.com](https://www.seeedstudio.com) |
| 2 | Digital micro servos ×2 | 4.3 g class (EMAX ES9051 equiv.) | ~$13 | Amazon |
| 3 | 2S 220 mAh 45C LiPo | 7.4 V | ~$10 | Amazon / Horizon Hobby |
| 4 | Wing LEDs | WS2812B strip segment | ~$6 | Amazon |
| 5 | Flight controller PCB | Gerbers in Drive folder, 5 pcs | ~$2 | [JLCPCB](https://jlcpcb.com/?from=MaxImagination) |
| 6 | Frame parts | PETG + TPU, STLs in Drive folder | ~$10 | [JLC3DP](https://jlc3dp.com/3d-printing-quote) |
| 7 | Wings | Produce bag | $0 | Grocery store |
| 8 | Wire, connectors, screws | Misc | ~$5 | Amazon / AliExpress |
| 9 | 2S balance charger | E-flite 2S DC Li-Po | $14.99 | [horizonhobby.com](https://www.horizonhobby.com) |
| 10 | Soldering iron kit | Basic 60 W (one-time) | ~$20 | Amazon |

## No 3D printer? Three ways to get the frame

The frame is small PETG parts plus flexible TPU hinges (30–60 g of plastic total). Ranked cheapest-reliable first:

**1. JLC3DP online printing — recommended**
Order the PCB and the printed parts together from JLC and they ship in one parcel, one shipping fee. Instant quote at jlc3dp.com. Frame set runs ~$8–15 in the correct materials. No quality gamble.

**2. Public library / makerspace**
$0.05–0.20/g makes this potentially cheapest ($2–12). Catch: almost all libraries print PLA only. The design needs PETG for strength and TPU for the flexible hinges — PLA hinges will snap on the first flap. Ask about PETG before committing.

**3. Hand-build from carbon rod**
1 mm carbon fiber rods + heat-shrink + epoxy, ~$8–12. Skips printing entirely, but the servo linkage geometry is precise and hand-building risks sloppy flapping. Highest skill, most frustration. Not recommended for a first build.

**Do not** let any print service substitute PLA for the TPU hinge parts.

## Build steps

1. **Order boards + frame** from JLCPCB/JLC3DP (Gerbers and STLs in the [Drive folder](https://drive.google.com/drive/folders/1XTTW8Ez_hmZl5E6mPUDXgX2qnnI3Cp2e?usp=sharing)). One shipment.
2. **Order electronics**: XIAO ESP32-C3, servos, LiPo, LEDs, charger.
3. **Flash the firmware** — [github.com/maximagination1/ESP-FLUTTER](https://github.com/maximagination1/ESP-FLUTTER). No Python needed: flash in Chrome via Espressif's ESP Tool. If flashing fails, hold BOOT and tap RESET on the XIAO.
4. **Solder** the XIAO, servo leads, and battery connector to the PCB. Practice first if you're new — the castellated edges are small.
5. **Assemble** the frame, mount servos, attach linkages per the [video tutorial](https://youtu.be/5Le4I-1Pf9I).
6. **Wings**: cut from a produce bag, mount, run the LED strip along them.
7. **Fly**: power on, join the `Butterfly_RC` WiFi (password `12345678`), open `http://192.168.4.1` in your phone browser. On-screen joystick, no app install.

## Gotchas

- **The charger is mandatory.** Never USB-charge a bare 2S LiPo. The $15 balance charger is non-negotiable.
- **Weight budget is 70 g.** Every gram of glue counts. Don't substitute heavy materials.
- **Phone control is free** and fine for build #1. The ELRS transmitter route adds $50–100 in radio gear — skip it until you know you want it.
- **Firmware license** is PolyForm Noncommercial 1.0: personal/hobby/educational builds are fine, commercial use needs the author's permission.

## Project files (Max Imagination's)

| | |
|---|---|
| Firmware | [github.com/maximagination1/ESP-FLUTTER](https://github.com/maximagination1/ESP-FLUTTER) |
| Gerbers, BOM, diagrams | [Google Drive folder](https://drive.google.com/drive/folders/1XTTW8Ez_hmZl5E6mPUDXgX2qnnI3Cp2e?usp=sharing) |
| 3D files (STL + STEP) | In the Drive folder (also on Cults3D, linked from the video) |
| Build tutorial | [YouTube](https://youtu.be/5Le4I-1Pf9I) |
| PCBs | [JLCPCB](https://jlcpcb.com/?from=MaxImagination) |

## Build log

- [ ] PCBs + frame ordered
- [ ] Electronics ordered
- [ ] Firmware flashed
- [ ] PCB soldered
- [ ] Frame assembled
- [ ] Wings + LEDs mounted
- [ ] First flight
