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

  * **Sensors**: Five Tekscan FlexiForce pressure sensors (0–25 lb range) plus Adafruit flex sensors for finger bend.

  * **Multiplexing**: 16-channel CD74HC4067 MUX to read all 10 analog signals into the Arduino Uno WiFi Rev2.

  * **Power**: Nightshade energyShield battery pack (~6 hr runtime at 10 ms update).

  * **Enclosure**: 3D-printed housing on forearm, neoprene-sewn glove sleeve for comfort and stability .

### Bluetooth Communication

  * **Module**: HC-06 paired to the Uno’s serial pins (via a voltage-divider on RX) to stream sensor data at up to 100 Hz.

  * **Auto-Reconnect**: On app startup, a BluetoothManager in the Unity VR app searches for and reconnects to the glove, then polls its serial feed every frame or at a set interval.

Poster PDF: [Infographic_DENOVUS.pdf](https://github.com/jameshuang101/Denovus-Physical-Therapy/files/11194727/Infographic_DENOVUS.pdf)

Demonstration Video Link: https://www.youtube.com/watch?v=5rdVQwTPSA4

Project Report: [Denovus_FinalProjectReport.pdf](https://github.com/jameshuang101/Denovus-Physical-Therapy/files/11194708/Denovus_FinalProjectReport.pdf)
