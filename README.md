[![License: MSG](https://img.shields.io/badge/License-MSG%20v1.0-blue.svg)](LICENSE)
# VAC Live + Overwatch 2.0: Hybrid Anti-Cheat System (Proposal)
**Author:** (steam mishka.sit2002) 
**Version:** 3.5 (Final)  
**Steam:** [Mishka.sit2002](https://steamcommunity.com/profiles/76561198773549167/)

---

## 🚀 Overview
This repository contains a technical proposal and a Python-based proof-of-concept for a hybrid anti-cheat system designed for Counter-Strike 2. The goal is to close the "arms race" gap where cheat developers adapt faster than machine learning (VAC Live) can retrain.

## 🧠 Key Features

### 1. Glicko-2 Judge Rating
Unlike the old Overwatch, this system uses the **Glicko-2 algorithm** to rate judges based on their accuracy. 
* **Bot-Farm Protection:** High entry barriers (wins/hours) and weighted voting make bribery or botting economically impossible.
* **Vote Weight:** A Senior Judge's verdict carries more weight than a Trainee's.

### 2. Invisible Honeypot Entities (Deterministic Detection)
A method to provide mathematical proof of cheating. 
* Invisible "honeypot" entities are placed inside geometry or behind walls. 
* If a player's telemetry shows consistent snapping or tracking of these invisible targets, the system records a **100% deterministic violation**.

### 3. Shadow Monitoring (2-3 Match Verification)
To eliminate False Positives:
* If found "Guilty" by consensus, the account is shadow-flagged.
* It remains under surveillance for the next 2-3 matches.
* The ban is only finalized if cheating patterns (AIM/WH anomalies) persist.

---

## 🛠 Movement Bug Fix (Bonus)
This proposal also includes a logic fix for the "Fall Damage" bug in Source 2:
* **The Problem:** Engine calculates damage based on "air-time," leading to deaths while sliding on boxes.
* **The Fix:** Switch to a **Vertical Height Delta (Z-delta)** method. Reset the fall interval on *any* solid contact (ledge, slope, or box edge).

---

## 💻 How to use this repository
1. Read the documentation above for the logic.
2. Run `prototype.py` (to be added) to see the Python simulation of judge ratings and case processing.
