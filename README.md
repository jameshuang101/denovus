# What is Denovus?
A project aimed at creating a virtual reality (VR) game-based application for upper-extremity physical therapy

![Infographic_DENOVUS](https://user-images.githubusercontent.com/130106532/231019294-e4408248-ab27-4c66-be00-d2fd1992c6c8.png)

# Overall System & Motivation

* **Goal**: Provide an inexpensive, at-home VR system to supplement clinical PT for upper-limb rehabilitation post-stroke, addressing cost and motivation barriers.

* **Core Components**:

  1. Custom Sensor Glove (10 sensors: 5 force, 5 flex)

  2. Oculus Quest Wireless VR Headset

  3. Physical Therapy “Egg” for pinch/grip exercises
 
# Sensor Glove & Bluetooth Interface

### Hardware
![image](https://github.com/user-attachments/assets/731e0c89-2091-4444-b7a9-bc90371a809e)

  * **Sensors**: Five Tekscan FlexiForce pressure sensors (0–25 lb range) plus Adafruit flex sensors for finger bend.

  * **Multiplexing**: 16-channel CD74HC4067 MUX to read all 10 analog signals into the Arduino Uno WiFi Rev2.

  * **Power**: Nightshade energyShield battery pack (~6 hr runtime at 10 ms update).

  * **Enclosure**: 3D-printed housing on forearm, neoprene-sewn glove sleeve for comfort and stability.

### Bluetooth Communication

  * **Module**: HC-06 paired to the Uno’s serial pins (via a voltage-divider on RX) to stream sensor data at up to 100 Hz.

  * **Auto-Reconnect**: On app startup, a BluetoothManager in the Unity VR app searches for and reconnects to the glove, then polls its serial feed every frame or at a set interval.

# VR Application & Mini-Games
![image](https://github.com/user-attachments/assets/e2a6f132-ef04-4ed6-b99a-a3212200ba90)
![image](https://github.com/user-attachments/assets/e72ed3a0-1d25-4962-a737-59a6a638fb41)

* **Environment**: Calming nature scene, table-calibration on startup for real-world safety.

* **Interaction**: Point-and-pinch UI; four short “mini-games” (Stone Blaster, Bone Blaster, Alien Annihilation, Fishing Frenzy) that map to key hand exercises (grip strength, pinch, reach, dexterity).

* **Adaptive Difficulty**: User-selectable slider; game logic scales number/speed of targets based on prior performance.

# Progress Tracking & Data Management
![image](https://github.com/user-attachments/assets/202b4705-2425-42c8-8ca4-010ef16faafa)

In-Game “Progress” Menu: Shows history of each mini-game with date/time, score, duration, and actual force/flex values (converted via polynomial calibration curves).

# Key Innovations

* Real-Time, High-Rate Bluetooth Glove: Achieves up to 100 Hz streaming of ten analog channels over HC-06, with automatic reconnection and minimal latency, all in a self-contained, comfortable glove design.

* Integrated Progress Tracking: Full history of force/flex data is saved directly on the headset; users and therapists can view quantitative improvement over time without external software.

# Validation & Outcomes

* **Accuracy**: Glove sensors calibrated against known weights (0–20 lb per finger) with ≤ 5% error; hand/finger tracking within ± 10 mm.

* **Session Times**: Full four-game sessions run 15–25 min (well under 2 hr limit).

* **Cost**: Prototype bill-of-materials totals $798.44, under the $800 target.

* **User Feedback**: Informal testing showed measurable fatigue/soreness and small strength gains over repeated sessions.

This combined hardware-software approach—melding a low-cost Bluetooth-enabled sensor glove with an adaptive VR mini-game suite and built-in progress tracking—represents a novel, accessible path toward engaging, quantified at-home stroke rehabilitation. This project won third place in the UTDesign Capstone Competition in 2020.

Poster PDF: [Infographic_DENOVUS.pdf](https://github.com/jameshuang101/Denovus-Physical-Therapy/files/11194727/Infographic_DENOVUS.pdf)

Demonstration Video Link: https://www.youtube.com/watch?v=5rdVQwTPSA4

Project Report: [Denovus_FinalProjectReport.pdf](https://github.com/jameshuang101/Denovus-Physical-Therapy/files/11194708/Denovus_FinalProjectReport.pdf)
