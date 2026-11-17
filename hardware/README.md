# Hardware Documentation

This directory contains the hardware design documentation, component specifications, PCB designs, and supporting resources for the OSIRIS Integrated Performance Console.

OSIRIS consists of three major hardware subsystems:

1. **Digital DJ Mixer** – Handles audio playback, mixing, and tone adjustment.
2. **Digital Octapad** – Detects physical pad strikes and generates digital percussion sounds.
3. **Music-Reactive LED Backdrop** – Analyzes audio input and generates synchronized lighting effects.

Each subsystem uses dedicated embedded processing and supporting electronic components.

---

## Hardware Architecture

The hardware implementation combines microcontroller-based processing, analog audio circuits, sensor inputs, and addressable LED outputs.

The following sections document the individual hardware designs and their associated components.

## PCB Designs

PCB designs were developed for two of the three hardware subsystems.

| Hardware Module | PCB Design |
| :--- | :--- |
| Digital DJ Mixer | [View PCB Design](https://u.easyeda.com/join?type=project&key=5c5e7610b214060292de60c37f0c5b76&inviter=b9b5f0d0071f4287a9b8bf906969b0bd) |
| Digital Octapad | [View PCB Design](https://u.easyeda.com/join?type=project&key=cca712bce40a11b25514944aa4cb97ba&inviter=dd74b28929074b3bae9ff57879d18bc3) |
| LED Backdrop | [View PCB Design](pcb-designs/led-backdrop/PCB_LED_Backdrop-.pdf) |

The LED Backdrop subsystem was implemented using a manually assembled circuit rather than a dedicated PCB.

## Circuit Schematics

Circuit schematics and related design documents are organized in the `schematics/` directory.

| Hardware Module | Documentation |
| :--- | :--- |
| Digital DJ Mixer | [View Schematics](schematics/audio-mixer/) |
| Digital Octapad | [View Schematics](schematics/digital-octapad/) |
| LED Backdrop | [View Schematics](schematics/led-backdrop/) |

## Bill of Materials (BOM)

The following tables summarize the main electronic components used in each subsystem. Specifications and quantities are based on the final project report and budget.

### 1. Digital DJ Mixer

| Component | Specification | Quantity |
| :--- | :--- | :---: |
| ESP32 Development Board | ESP-WROOM-32 / ESP32 DevKit V1 | Shared |
| MicroSD Card Module | MicroSD Adapter | 2 (overall) |
| DAC Module | PCM5102 I²S | 2 (overall) |
| Audio Amplifier | PAM8403 | 1 (overall) |
| Rotary Encoder | HW-040 | 2 |
| Linear Slide Potentiometer | Channel Fader / Crossfader | - |
| Audio Potentiometers | WH148 | 6 |
| Passive Equalizer Circuit | Bass and Treble RC Network | Integrated |
| Speaker | 4Ω, 30W, 4-inch | 1 |
| Push Button Switches | 12 × 12mm Tactile | Shared |
| Resistors and Capacitors | Passive Components | As required |

### 2. Digital Octapad

| Component | Specification | Quantity |
| :--- | :--- | :---: |
| ESP32 Development Board | ESP-WROOM-32 / ESP32 DevKit V1 | Shared |
| DAC Module | PCM5102 I²S | 2 (overall) |
| Analog Multiplexer | CD74HC4067, 16-channel | 1 |
| Piezoelectric Sensors | 35mm | 8 |
| OLED Display | 0.96-inch, 128 × 64 | 1 |
| Push Button Switches | 12 × 12mm Tactile | Shared |
| Speaker | 4Ω, 30W, 4-inch | 1 (shared) |

### 3. Music-Reactive LED Backdrop

| Component | Specification | Quantity |
| :--- | :--- | :---: |
| ESP32 Development Board | ESP-WROOM-32 / ESP32 DevKit V1 | Shared |
| Microphone Module | MAX9814 with AGC | 1 |
| Addressable LED Strip | WS2812B RGB | as required |

### 4. Shared Power and Supporting Components

| Component | Specification | Quantity |
| :--- | :--- | :---: |
| Power Supply | 12V/5V SMPS | 2 |
| Buck Converter | LM2596 | - |
| DC Step-Down Converter | MP1584 | - |
| Logic Level Shifter | 4-channel | 1 |
| Screw Terminal | 2-pin | - |
| Wiring | Various | As required |
| Connectors | Various | As required |

*Note: Components marked as shared or overall are listed in the project-wide budget. Their exact allocation between individual subsystems should be verified against the final assembled hardware and circuit schematics.*

---

## Enclosure Design

The enclosure documentation contains the design resources and supporting materials used for the physical construction of the OSIRIS performance console.

The project used a laser-cut enclosure.

Relevant design files, dimensions, and photographs will be maintained in the `enclosure/` directory.

---

## Directory Structure

```text
hardware/
│
├── README.md
│
├── schematics/
│   ├── audio-mixer/
│   ├── digital-octapad/
│   └── led-backdrop/
│
├── pcb-designs/
│   ├── audio-mixer/
│   └── digital-octapad/
│
├── enclosure/
    └── images/

```

---

## Documentation Notes

- Component specifications are based on the final project report.
- Quantities are referenced from the project budget where available.
- Some components are shared across multiple subsystems.
- The LED Backdrop uses a manually assembled circuit without a dedicated PCB design.
- Final wiring configurations, GPIO assignments, and power requirements should be referenced from the corresponding circuit documentation.
- Any future corrections or additional hardware details should reflect the final assembled prototype.
