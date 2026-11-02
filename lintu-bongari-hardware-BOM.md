# lintu-bongari – Hardware Bill of Materials (BOM)

**Source:** `docs/hardware.md` (Sections 9 & 12)  
**Status:** Prototype / pre-made modules version (walto decision 2026-11-02)  
**Notes:**
- Prices are approximate and change frequently. Always check current stock and pricing.
- Prefer European distributors (Mouser, DigiKey, Farnell, local Finnish/European suppliers) for lower shipping risk and CE-related paperwork.
- Many components have long lead times (especially Quectel modules and some MEMS). Order early.
- This is a working document for prototypes. Exact part numbers and alternatives should be verified before ordering.

---

## 1. Microphones & Audio Front-End

| Item | Recommended Part | Qty per station | Notes | Where to buy |
|------|------------------|-----------------|-------|--------------|
| Analog MEMS mic (preferred long-term) | Infineon IM73A135V01 | 4–6 | SNR ~73 dB, -40 °C rated, analog | [Mouser](https://eu.mouser.com/ProductDetail/Infineon-Technologies/IM73A135V01XTSA1) · [DigiKey](https://www.digikey.com/en/products/detail/infineon-technologies/IM73A135V01XTSA1/15776498) |
| Digital PDM MEMS (pre-made path) | Infineon IM69D130 | 4–6 | SNR ~69 dB | Search DigiKey / Mouser for IM69D130 |
| PDM mic evaluation board | Infineon S2GO-MEMSMIC-IM69D | 2–3 | 2× IM69D130 on Shield2Go | [Farnell](https://uk.farnell.com/infineon/s2gomemsmicim69dtobo1/eval-board-mems-microphone/dp/3014284) · DigiKey (check stock) |
| Audio ADC | TI TLV320ADC6140 | 2 | 4-ch high-performance ADC | [TI EVM](https://www.ti.com/tool/ADC6140EVM-PDK) · DigiKey / Mouser for the IC |
| TCXO 24.576 MHz | Various, ±1–2 ppm, -40 °C | 1 | Shared clock for ADCs | DigiKey / Mouser (search 24.576 MHz TCXO) |

---

## 2. Compute & Control

| Item | Recommended Part | Qty | Notes | Where to buy |
|------|------------------|-----|-------|--------------|
| Recorder MCU board | WeAct STM32H723 / H735 core board | 1 | High-performance Cortex-M7 | Search “WeAct STM32H723” on AliExpress / Robu / specialist shops |
| Supervisor + BLE | Seeed XIAO nRF52840 or Adafruit Feather nRF52840 | 1 | Always-on, BLE for phone setup | [Seeed](https://www.seeedstudio.com/) · [Adafruit](https://www.adafruit.com/) · DigiKey / Mouser |
| Linux module (pre-made) | Raspberry Pi Zero 2 W | 1 | On-demand only | Official Raspberry Pi resellers, DigiKey, local Finnish shops |
| Linux module (higher performance option) | Raspberry Pi CM4 (2 GB / 8 GB eMMC, wireless) | 1 | Original design | Raspberry Pi Approved Resellers |
| Secure element | Microchip ATECC608B | 1 | Hash / signing | DigiKey / Mouser |
| RTC | Micro Crystal RV-3028 or similar | 1 | Low-power, -40 °C | DigiKey / Mouser |

---

## 3. Connectivity & Positioning

| Item | Recommended Part | Qty | Notes | Where to buy |
|------|------------------|-----|-------|--------------|
| 4G modem (global) | Quectel EG25-G Mini PCIe | 1 | Global bands | DigiKey / Mouser (search EG25) – often long lead time |
| 4G modem (Europe) | Quectel EC25-E / EC25-EU Mini PCIe | 1 | Preferred for pre-made path | DigiKey / Mouser |
| GNSS module | u-blox MAX-M10S | 1 | Low power, PPS | [SparkFun Breakout](https://www.sparkfun.com/sparkfun-gnss-receiver-breakout-max-m10s-qwiic.html) · DigiKey / Mouser for the module |
| Active GNSS antenna | u-blox or generic active patch | 1 | | DigiKey / Mouser / local RF suppliers |
| LTE antennas | Outdoor omni + surge protection | 2 | | DigiKey / Mouser / specialist antenna suppliers |

---

## 4. Sensors & Health

| Item | Recommended Part | Qty | Notes | Where to buy |
|------|------------------|-----|-------|--------------|
| Temperature + humidity | Sensirion SHT45 | 1 | High accuracy | DigiKey / Mouser |
| Pressure | Bosch BMP390 | 1 | | DigiKey / Mouser |
| 9-axis IMU + magnetometer | ST or Bosch | 1 | Heading / tilt / tamper | DigiKey / Mouser |
| Power monitor | TI INA228 | 1 | Current / voltage / energy | DigiKey / Mouser |
| Self-test / self-survey emitter | Small horn tweeter + class-D amp board | 1 | | Electronics suppliers / AliExpress for prototypes |

---

## 5. Storage

| Item | Recommended Part | Qty | Notes | Where to buy |
|------|------------------|-----|-------|--------------|
| High-endurance microSD | Industrial / high-endurance 512 GB – 1 TB | 2 | Archive of record | DigiKey, Mouser, industrial SD specialists (e.g. Swissbit, ATP) |

---

## 6. Power System

| Item | Recommended Part | Qty | Notes | Where to buy |
|------|------------------|-----|-------|--------------|
| LTO cells | Yinlong 66160 2.3 V 40 Ah | 12 (6S2P) or 6 (6S1P × 2) | Excellent cold performance | [MT Audio (EU packs)](https://mtaudio.eu/) · AliExpress / specialist LTO sellers · Search “Yinlong 66160” |
| Ready-made LTO pack | 12–14.4 V LTO packs with BMS | 1–2 | Faster for prototypes | MT Audio, specialist battery shops |
| MPPT solar charger | Victron SmartSolar MPPT 75/10 | 1 | Bluetooth, reliable | Official Victron dealers, marine/solar shops, Amazon |
| Solar panel | 50–100 Wp mono, near-vertical mount | 1 | | Local solar suppliers / AliExpress for prototypes |
| Buck converters & load switches | Pololu or similar -40 °C rated | several | | DigiKey / Mouser / Pololu |

---

## 7. Mechanical & Enclosure

| Item | Recommended Part | Qty | Notes | Where to buy |
|------|------------------|-----|-------|--------------|
| IP67 enclosure | Fibox / Spelsberg or equivalent polycarbonate | 1 | Station head | Local industrial suppliers / RS Components / Farnell |
| IP65/67 pack box | Insulated battery enclosure | 1–2 | Power pack | Industrial suppliers |
| Connectors | IP67 M8 / M12 bulkhead | several | | DigiKey / Mouser / Binder / Phoenix Contact |
| 3D-printed parts | ASA filament (UV stable) | – | Pods, hub, mounting plate | Own 3D printer (walto has one) or local service |

---

## 8. Shared Kit Items (per 4-station kit)

| Item | Notes | Where to buy |
|------|-------|--------------|
| Acoustic calibrator | 94 dB / 1 kHz, Class 1 or 2 + ½-inch adapter | Brüel & Kjær, NTi, Larson Davis, or equivalent |
| Survey GNSS | Dual-band RTK (u-blox ZED-F9P class) + survey antenna | SparkFun / ArduSimple / local survey equipment suppliers |
| Transport cases + spares | – | Pelican / local case suppliers |

---

## Important Notes for Ordering

1. **Pre-made path (current plan)** prioritises speed: digital PDM mics, WeAct/Seeed boards, Pi Zero 2 W, ready-made LTO packs, Victron charger.
2. **Series path** will move to custom carrier board + analog MEMS + optimised power to hit the €700–900/station target.
3. Always verify temperature ratings (-30 °C or better for winter operation).
4. For CE/RED later: prefer modules that already have radio certifications.
5. Keep a living spreadsheet (Google Sheets / Excel) with exact order numbers, prices, and lead times once the first prototype order is placed.

---

*Generated from the lintu-bongari design documents – November 2026*  
*This file is a starting point. Update links and prices as you order.*
