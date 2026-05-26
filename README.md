# Industrial Automation - Distributing and Testing Stations

This repository contains the PLC code and configuration files developed for the Final Project of the Industrial Automation course. The project focuses on the integration, programming, and synchronization of two industrial automation stations: a **Distributing Station** and a **Testing Station**.

The main objective was to create a fully automated system capable of extracting, inspecting, and classifying different types of workpieces based on their material and physical characteristics.

---

## 🛠️ System Overview

The system is split into two main physical stations controlled by PLCs:

1. **Distributing Station:** Responsible for workpiece storage and extraction. It uses a pneumatic feeder to push pieces out and a pneumatic rotary arm with a vacuum suction cup to transfer them to the next stage.
2. **Testing Station:** Receives the workpiece and performs quality and material inspection. It features a capacitive sensor, an inductive sensor, and an optical sensor to identify the piece type (e.g., metallic vs. plastic) and a pneumatic slide to sort or reject them.

---

## 💻 Control Logic & Programming

The control architecture is fully modular and implemented using the following industrial automation standards:
* **Sequential Function Chart (SFC / Grafcet):** Used to program the main state machine and sequence logic (Initialization, Waiting, Piece Extraction, Pick-Up, Transfer, Detection, and Classification).
* **Inter-Station Communication:** Setup of network communications (using GET requests/blocks) to share status variables (`ACTIVE`) and keep both stations synchronized without collisions.
* **SCADA System:** Development of a supervisory interface to monitor system states, track cycle counts, and visualize real-time sensor data.

---

## ⚠️ Challenges & Technical Solutions

* **Sensor Calibration:** During testing, we faced limitations identifying shiny/silver workpieces due to sensor threshold variations. The logic was modified in the PLC program to accurately classify them by combining multiple sensor inputs simultaneously.
* **Network Synchronization:** Initially, tracking the active status across the entire system was a bottleneck. We resolved this by implementing a unified project configuration to handle data exchange efficiently between the station controllers.

---

## 🎥 Project Demonstration & Code

To see the fully integrated system in action, including the synchronization between the Distributing and Testing stations, check out our demonstration video:

https://youtu.be/iKDXJ2vswZg

Additionally, since PLC project files require specific software to be opened, we have exported the complete control logic (SFC/Grafcet and routines) as a readable document. You can review the full logic here:
* [📄 View Full Code (PDF)](./CODE.pdf)

---

## 📁 Repository Structure

* Everything related to this project is located in the [`integrated project`](./Integrated_Project.zip) folder, including the PLC code blocks and sequence configurations.

---
