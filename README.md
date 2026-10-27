# Midnight for SCP: Secret Laboratory — Standalone Edition

[![Platform](https://img.shields.io/badge/Platform-Windows%20x64-blue.svg)](#)
[![Target](https://img.shields.io/badge/Target-SCP%3A%20Secret%20Laboratory-orange.svg)](#)
[![Build](https://img.shields.io/badge/Build-Autonomous%20Standalone-green.svg)](#)
[![License](https://img.shields.io/badge/License-Educational%20Research-red.svg)](#)

A fully autonomous, self-contained standalone loader for Midnight on **SCP: Secret Laboratory** (`AppID: 700330`, 64-bit Unity IL2CPP). 

Engineered with zero cloud dependencies, zero external subscriptions, dynamic runtime relocation resolution, and an isolated internal heap allocator designed to eliminate match-transition and scene-load instability.

---

## ⚡ Key Highlights

- **100% Autonomous & Offline**: Completely stripped of remote authentication, heartbeats, and telemetry callbacks. Runs entirely self-contained.
- **Native Execution**: Packed as a single, zero-dependency native 64-bit binary. No Python installation, compilers, or third-party interpreters required.
- **In-Memory Decryption**: Payload is decrypted on-the-fly directly into target process memory, bypassing on-disk residue.
- **Isolated Heap Architecture**: Utilizes an independent private process heap (`HeapCreate`), preventing LFH / metadata collisions with Unity's internal networking (`libcaress.dll` / `crypt32.dll`) during map loads.
- **Re-Anchored Item Vector Tables**: Custom-staged vector tables prevent memory invalidation and access violations across all dropdown menus (Hitboxes, Visuals, Shadows).

---

## 🎮 Features

- **Aimbot**: Silent / Vector aimbot, fully configurable FOV circle display, customizable target priority.
- **Visuals / ESP**: Player ESP (Class-D, Scientists, Facility Guards, MTF, Chaos Insurgency, SCPs), Bones / 2D Boxes, Health indicators, Distance tracking.
- **Item & World ESP**: Keycards, Weapons, Medical items, Generators, Decontamination timers.
- **Chams & Lighting**: Custom entity materials and configurable scene lighting adjustments.
- **Misc Utilities**: Big step, Bunnyhop, Speed modifications, Custom hitboxes.

---

## 📋 System Requirements

| Component | Requirement |
| :--- | :--- |
| **Operating System** | Windows 10 / 11 (64-bit) |
| **Game** | SCP: Secret Laboratory (Steam x64) |
| **Dependencies** | [Visual C++ Redistributable 2015–2022 (x64)](https://aka.ms/vs/17/release/vc_redist.x64.exe) |
| **Privileges** | Administrator rights (required for process memory attachment) |

---

## 🚀 Quick Start Guide

1. Head to the **[Releases](../../releases/latest)** section and download the latest `Midnight SCP:SL by Van1sh.exe`.
2. Launch **SCP: Secret Laboratory** through Steam. Wait until you reach the **Main Menu**.
3. Right-click `Midnight SCP:SL by Van1sh.exe` and select **Run as Administrator**.
4. The launcher will automatically detect `SCPSL.exe`, stage memory sections, resolve dynamic imports, and initialize the module.
5. Return to the game window and press **`INSERT`** to open/close the cheat configuration menu.

---

## ⌨️ Controls & Keybinds

| Key | Action |
| :--- | :--- |
| **`INSERT`** | Toggle GUI Menu (Show / Hide) |
| **`MOUSE 1`** | Navigate and toggle options inside the GUI |

---

## ⚠️ Antivirus False Positives

Because the loader performs dynamic process memory allocation (`VirtualAllocEx` / `WriteProcessMemory`) and contains encrypted in-memory payloads (AES-256), generic antivirus engines and Windows Defender will flag the binary as a generic heuristic threat (`Trojan:Win32/Wacatac`, `Heur.BZC`, etc.).

- This is a standard false positive caused by the executable packer and memory injection techniques.
- If Windows Defender blocks the download or execution, add the executable or its containing folder to your **Antivirus Exclusion List**.

---

## 📜 Disclaimer

This project is published strictly for **educational, reverse engineering, and security research purposes**. It is intended to demonstrate runtime memory relocation, dynamic IAT reconstruction, and low-level process instrumentation in modern Unity IL2CPP applications. 

The authors assume no responsibility or liability for any misuse, account suspensions, or game bans resulting from the use of this software.
