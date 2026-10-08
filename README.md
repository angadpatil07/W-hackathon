# USB Security Gateway – Inline Hardware USB Firewall

[![AARAMBH WCE-HACKATHON 2026](https://img.shields.io/badge/AARAMBH_WCE--HACKATHON-2026-cyan.svg)](https://www.walchandsangli.ac.in)
[![Category](https://img.shields.io/badge/Category-Hardware-emerald.svg)]()
[![Track](https://img.shields.io/badge/Track-Cybersecurity_%26_Digital_Forensics-blue.svg)]()
[![Institution](https://img.shields.io/badge/Institute-Walchand_College_of_Engineering%2C_Sangli-purple.svg)]()

> **"A small hardware device connected between your USB and computer that checks, alerts, and stops harmful USB devices before they can touch your system."**  
> Developed by **Team Forensight**, Department of Electrical Engineering, Walchand College of Engineering, Sangli *(A Government-Aided Autonomous Institute)*.

---

## ⚡ What is This Project?

Computers trust USB devices blindly. When you insert an unknown USB, your operating system immediately loads drivers without asking you. Attackers take advantage of this by using fake keyboards (BadUSB) that type harmful commands in less than 3 seconds, or rogue network cards that steal internet traffic.

Our project is a **hardware inline firewall**. You plug the USB into our device, and our device plugs into the computer. It keeps the data wires disconnected, reads the USB details on an ESP32 microcontroller, checks the security rules in under 450 milliseconds, and only connects the device to your PC if it is safe.

```
[ UNTRUSTED USB DEVICE ]
           │
           ▼
[ WCE INLINE GATEWAY ]
  ├── 1. Electrical & Power Check (15 ms)
  ├── 2. Reads Device ID & Manufacturer (120 ms)
  ├── 3. Checks Device Type (HID, Storage, Network) (180 ms)
  └── 4. Hardware Decision
           │
     ┌─────┴─────────────────────┐
     ▼                           ▼
[ SAFE DEVICE ]             [ HARMFUL / UNKNOWN ]
- Connects data wires       - Wires stay disconnected
- Green LED lights up       - Loud buzzer alarm sounds
- OLED: "STATUS: TRUSTED"   - OLED: "BLOCKED SUSPICIOUS"
                            - Red LED lights up
                            - Event saved to audit log
```

---

## 📑 Separate Pages in This Website

The website is organized into separate dedicated pages:

1. **Overview / Home (`/`)**: Main hero with real prototype photo states (Allowed, Blocked, Alert), key stats, and overview cards.
2. **Problem Statement (`/problem`)**: Simple explanations of USB risks (instant trust, BadUSB keystroke injectors, dropped flash drives, rogue dongles).
3. **Proposed Solution (`/solution`)**: How our hardware sits between the USB and PC, and 4 core capabilities.
4. **How It Works (`/how-it-works`)**: 4-stage screening workflow stepper, ESP32 microcontroller role, and USB policy table.
5. **Live Demo Simulator (`/demo`)**: The interactive simulator with OLED screen, LED light, synthesized buzzer audio, 8 test devices, policy editor, and CSV/JSON log download.
6. **Hardware Architecture & Cost (`/hardware`)**: Real workbench prototype photo from WCE Cyber Lab, wiring diagram, parts list, ₹3,000 Bill of Materials, and Software vs Hardware comparison.
7. **Impact & Benchmarks (`/impact`)**: Benefits for college labs, banks, hospitals, and offices, plus benchmark charts.
8. **Project Roadmap (`/roadmap`)**: 4 development phases from student prototype to custom PCB.
9. **References & Guides (`/references`)**: Official documentation, Wikipedia articles, and video demos.
10. **Team Forensight (`/team`)**: Student members from Electrical Engineering at WCE Sangli.
11. **Pitch Script (`/pitch`)**: 3-minute hackathon presentation script with jury Q&A guide.

---

## 🚀 How to Run Locally

### 1. Install Dependencies
```bash
npm install
```

### 2. Start the Development Server
```bash
npm run dev
```
Open **[http://localhost:5173](http://localhost:5173)** in your browser.

### 3. Build for Production
```bash
npm run build
```

---

## ⏱️ 3-Minute Hackathon Presentation Script

### 00:00 – 00:45 | The Problem
> *"Respected judges, computers in our college labs, banks, and offices blindly trust any USB device plugged into them. If an attacker plugs in a BadUSB device, it pretends to be a super-fast keyboard and types harmful terminal commands in under 3 seconds. Regular antivirus software cannot stop this because it only runs after Windows boots up. We need a physical hardware barrier."*

### 00:45 – 01:30 | The Hardware Gateway
> *"To solve this, Team Forensight built the WCE Inline USB Security Gateway. It is a small hardware adapter that sits between the USB device and your computer. Powered by an ESP32-S3 microcontroller and a USB host chip, it intercepts the USB device first, checks its manufacturer, model, and class in under 450 milliseconds, and only connects the data wires if the device is safe. Our prototype costs just ₹3,000 INR."*

### 01:30 – 02:30 | Live Simulator Demonstration
> *"Let us show you a live test on our simulator:*  
> *1. When we plug in an approved SanDisk pen drive, the gateway approves it, the OLED reads 'STATUS: TRUSTED DEVICE ALLOWED', the green LED lights up, and data connects.*  
> *2. When an attacker inserts a Rubber Ducky keystroke injector, the gateway catches the fake keyboard, sounds an 85dB alarm buzzer, turns on the red LED, and keeps the computer data wires disconnected!*  
> *3. Every event is recorded in our live log, which we can download as CSV or JSON for security audits."*

### 02:30 – 03:00 | Conclusion & Q&A
> *"Our device works completely offline, needs no expensive monthly software licenses, and brings physical zero-trust security to every USB port. Thank you! We look forward to your questions."*

---

## 🏛️ Institution Details

- **Institute:** Walchand College of Engineering, Sangli *(A Government-Aided Autonomous Institute)*
- **Department:** Department of Electrical Engineering
- **Event:** AARAMBH WCE-HACKATHON 2026
- **Category:** Hardware | **Track:** Cybersecurity & Digital Forensics
- **Team:** Team Forensight
