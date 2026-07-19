# Custom Linux Single Board Computer

Open-source hardware design for a minimal **Allwinner V3s**-based Single Board Computer, designed with **KiCad 9.0**.

## Features

- **Allwinner V3s** — ARM Cortex-A7 @ 1.2 GHz with **64 MB integrated DDR2 RAM** (SiP)
- **EA3036CQB** PMIC — 3-channel regulator (1.2V / 1.8V / 3.3V) from 5V input
- **10/100 Ethernet** — integrated PHY in V3s + RJ45 with magnetics (Hanrun HR911105A)
- **USB Type-C** — power input (5V) and USB OTG
- **USB Type-A** — host port
- **microSD** card slot (Molex 104031-0811, push-push) — boot and storage
- **Debug UART** — 3-pin 2.54mm header for serial console
- **GPIO header** — 2x20 pin, Raspberry Pi-like pinout
- **CR1220** coin cell holder — RTC backup
- **Boot/reset button**

## Pinout (J6 — 40-pin GPIO Header)

```
         +3.3V  (1)  (2)  +5V
     UART2_TX  (3)  (4)  +5V
     UART2_RX  (5)  (6)  GND
     I2C0_SCL  (7)  (8)  PWM0
     I2C0_SDA  (9) (10)  PWM1
    SPI0_MISO (11) (12)  GPIO_PE2
     SPI0_CLK (13) (14)  GND
      SPI0_CS (15) (16)  GPIO_PE4
    SPI0_MOSI (17) (18)  GPIO_PE6
    GPIO_PE0  (19) (20)  GND
         +3.3V (21) (22) GPIO_PE8
    GPIO_PE1  (23) (24)  GPIO_PE10
          GND (25) (26)  GPIO_PE12
    GPIO_PE3  (27) (28)  GPIO_PE14
    GPIO_PE5  (29) (30)  GND
    GPIO_PE7  (31) (32)  GPIO_PE15
    GPIO_PE9  (33) (34)  GND
    GPIO_PE11 (35) (36)  GPIO_PE16
    GPIO_PE13 (37) (38)  GPIO_PE17
          GND (39) (40)  +1V8
```

## Gallery

### PCB Layout
![PCB](PCB.png)

### 3D View
![Diseño](Diseño.png)

### Schematic
![Esquematico](Esquematico.png)

## Board Specifications

| Parameter | Value |
|-----------|-------|
| Layers | 4 |
| Dimensions | 115.6 × 61.2 mm |
| PCB thickness | 1.6 mm |
| Copper finish | ENIG (gold) |
| Min track width | 0.15 mm |
| Min clearance | 0.15 mm |
| Via size | 0.6 mm / 0.3 mm drill |

## Repository Contents

| File / Folder | Description |
|---------------|-------------|
| `Allwinner V3s.kicad_sch` | Schematic |
| `Allwinner V3s.kicad_pcb` | PCB layout |
| `Allwinner V3s.kicad_pro` | KiCad project file |
| `production/` | Gerbers, BOM, pick-and-place, netlist |
| `Allwinner V3s-backups/` | Design backups |

## Production Files

The `production/` folder contains everything needed for PCB fabrication and assembly:

- `Allwinner_V3s.zip` — Gerber files + NC drill
- `bom.csv` — Bill of Materials with LCSC part numbers
- `positions.csv` — Pick-and-place centroid data
- `netlist.ipc` — IPC-356 electrical test netlist

## Datasheets

| Component | Datasheet |
|-----------|-----------|
| Allwinner V3s | [V3s Datasheet V1.0](https://linux-sunxi.org/images/2/23/Allwinner_V3s_Datasheet_V1.0.pdf) |
| EA3036C (PMIC) | [EA3036C datasheet](https://www.lcsc.com/datasheet/C570857.pdf) |
| HR911105A (RJ45) | [HR911105A specification](https://www.shotech.de/Datasheet/HanRun/1811141815_HANRUN-Zhongshan-HanRun-Elec-HR911105A_C12074.pdf) |

## Status

- **DRC**: 1 warning (local footprint override, non-critical)

## License

Open hardware — use, modify, and manufacture at your own risk.
