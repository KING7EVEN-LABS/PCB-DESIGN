# ⚡ ESP32-S3 USB-C Hardware Board Design

## 📌 Project Overview

This project features a custom **4-layer PCB design** for the **ESP32-S3 Mini** microcontroller with a native **USB-C** interface, developed in **Altium Designer**. 

All schematic symbols, PCB footprints, stackup configurations, and 3D component models were built from scratch and assembled following design practices from **Robert Feranec's** hardware design tutorials.

---

## 🛠️ Key Specifications

| Parameter | Specification Details |
| :--- | :--- |
| **CAD Tool** | Altium Designer |
| **Microcontroller** | ESP32-S3 Mini |
| **Board Layers** | 4-Layer Stackup (`Signal` - `GND` - `PWR` - `Signal`) |
| **Target PCB Stackup** | JLCPCB **JLC04161H-3313** Standard Stackup |
| **Connector Type** | USB Type-C (USB 2.0 High-Speed) |
| **Circuit Protection** | TVS Diode Array (`AQ3045-01ETG`) for ESD protection on $V_{BUS}$ & Data Lines |
| **Impedance Control** | $90\,\Omega$ Differential Pair Routing for USB Data Lines ($D+/D-$) |
| **Library Assets** | Custom Schematic Symbols, PCB Footprints & 3D STEP Models |

---

## 📁 Repository Structure

```text
ESP32_S3_USBC/
│
├── 📁 3D/                                    # Component STEP models
├── 📁 Docs/                                  # Datasheets & Pinout reference files
├── 📁 Image/                                 # 3D Renders, Schematics & Layer screenshots
├── 📁 Libs/                                  # Library files
├── 📁 Project Logs for esp32-s3-mini/        # Altium ECO compilation logs
├── 📁 Project Outputs for esp32-s3-mini/     # Gerber, BOM & DRC Reports
│
├── 📄 ESP32 with USBC.PcbDoc                 # 4-Layer PCB Board Layout
├── 📄 ESP32 with USBC.SchDoc                 # Circuit Schematic Document
├── 📄 Job.OutJob                             # Altium Output Job Configuration
├── 📄 PcbLib.PcbLib                          # Custom PCB Footprint Library
├── 📄 Schlib.SchLib                          # Custom Schematic Symbol Library
├── 📄 esp32-s3-mini.PrjPcb                   # Main Altium Project File
├── 📄 esp32-s3-mini.PrjPcbStructure          # Altium Project Metadata
└── 📄 README.md                              # Project Documentation
```

## 📐 Design Files & Visual Previews

### 📄 1. Circuit Schematic (`ESP32 with USBC.SchDoc`)
Complete circuit schematic including ESP32-S3 microcontroller circuitry, USB-C interface, power regulation, and ESD protection:

![ESP32 S3 Schematic](Image/Schematic.png)

---

### 🗂️ 2. 4-Layer PCB Board Stackup, Renders & Full Board View (`ESP32 with USBC.PcbDoc`)
Complete 4-layer routing layout, JLCPCB stackup configuration (JLC04161H-3313), impedance-matched differential traces ($90\,\Omega$), and 3D renderings.

#### PCB Layer Stackup (JLC04161H-3313)
* **Stackup Model:** JLCPCB 4-Layer Standard (JLC04161H-3313)
* **Controlled Impedance:** $90\,\Omega$ Differential Traces for USB 2.0 ($D+/D-$)

![Layer Stack Manager](Image/Layer%20Stack%20Manager.png)

#### Full Board Layout (All Layers Combined)
Preview of all signal layers and internal planes overlaid:
![All Layers View](Image/All%20Layers.png)

#### 3D Board Views
| Top View (3D Render) | Bottom View (3D Render) |
| :---: | :---: |
| ![3D Model TopView](Image/3D%20Model%20TopView.png) | ![3D Model BottomView](Image/3D%20Model%20BottomView.png) |

#### 2x2 PCB Layer Breakdown
| Layer 1 (Top Signal) | Layer 2 (GND Plane) |
| :---: | :---: |
| ![L1 Top Layer](Image/L1.png) | ![L2 GND Plane](Image/L2.png) |
| **Layer 3 (Power Plane)** | **Layer 4 (Bottom Signal)** |
| ![L3 Power Plane](Image/L3.png) | ![L4 Bottom Layer](Image/L4.png) |

---

### 📦 3. Custom Libraries & Project Files
* **`esp32-s3-mini.PrjPcb`** — Main Altium Designer Project file
* **`Schlib.SchLib`** — Custom Schematic Symbol Library
* **`PcbLib.PcbLib`** — Custom Component Footprint Library
* **`Job.OutJob`** — Altium Manufacturing Output Job File

---

## 🏭 Output Files & Manufacturing Release

All fabrication and assembly outputs are generated via **`Job.OutJob`** for standard PCB manufacturing:

### 📦 Output Files
* **Gerber Files:** Complete layer traces, silkscreen, solder mask, and paste layer outputs.
* **NC Drill Files:** Plated (PTH) and non-plated (NPTH) hole coordinates and drill specifications.
* **Pick & Place File (`.csv`):** Component placement coordinates and orientations for automated SMT assembly.
* **Bill of Materials (`BOM`):** Comprehensive component list with designators, footprints, and manufacturer part numbers.

---

## 🌐 Interactive 3D & Altium 365 Web Viewer

You can inspect the complete schematic, 4-layer PCB layout, and 3D component alignment directly in your web browser without installing Altium Designer:

👉 **[Launch Altium 365 Interactive 3D Viewer](https://kousik-p.365.altium.com/designs/1118BF20-100B-4C25-B650-FC5BA60F2F93)**

### 🔍 Web Viewer Highlights
* **Interactive 3D Inspection:** Full 360° board rotation and component clearance check.
* **Cross-Probing:** Click any schematic net to highlight corresponding PCB traces.
* **Gerber & Layer Stackup:** Real-time inspection of L1–L4 stackup and manufacturing outputs.
* **BOM Manifest:** Live component list with footprint and designator tracking.

---

## 🎓 Acknowledgments & References

This hardware design was created by following the expert hardware engineering tutorials provided by **Robert Feranec**. 

* **Instructor:** Robert Feranec (Hardware Design Engineer & Educator)
* **YouTube Channel:** [FEDEVEL Educational / Robert Feranec](https://www.youtube.com/watch?v=KWIzhbQaZZk)
* **Topics Covered:** Altium Designer workflows, 4-layer PCB stackup planning, custom component footprint creation, and USB differential pair routing.

## 📚 Additional Resources

### 📄 Core Datasheets & Reference Material
* **[ESP32-S3-MINI-1 Datasheet](Docs/esp32-s3-mini-1_mini-1u_datasheet_en.pdf)** — Hardware specifications, RF layout guidelines, and pinout definitions.
* **[ESP32 Pinout Matrix](Docs/ESP32%20pinout%20sheet.xlsx)** — Detailed GPIO multiplexing and peripheral mapping reference.
* **[Design & Material Notes](Docs/material_note.xlsx)** — Component selection parameters, stackup constraints, and BOM notes.

---

### 🛠️ Design Tools & Official Documentation
* **[Altium Designer Documentation](https://www.altium.com/documentation/altium-designer)** — Official guides for schematic capture, PCB layout, and Output Job generation.

---

---

## 👤 Author & Maintainer

<p align="center">
  <b>Designed & Engineered by Kousik P</b><br>
  <i>Hardware / PCB Design Engineer</i>
</p>

<p align="center">
  <a href="https://github.com/KING7EVEN-LABS"><img src="https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white" alt="GitHub"></a>
  <a href="https://www.linkedin.com/in/kousik-p-a99b4b283"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"></a>
  <a href="mailto:kousikings.eve.n7@gmail.com"><img src="https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Gmail"></a>
</p>