# 🎸 Oscivox-Analog-Acoustic-Guitar-Tuner-EN2091-Analog-Project
The Analog Acoustic Guitar Tuner is a fully analog signal-processing system that detects the frequency of a plucked guitar string and visually indicates whether the string is tuned correctly.  Unlike digital tuners, this device performs all signal processing using analog circuits, including filtering, frequency detection, and voltage comparison.

This repository presents the **Analog Acoustic Guitar Tuner** developed by **Team Oscivox** as part of the module:

IN23-S3-EN2091 – Laboratory Practice and Projects
Department of Electronic & Telecommunication Engineering
University of Moratuwa
---

## 👩‍💻 My Key Contribution

My primary contributions to this project were focused on **hardware implementation and circuit realization**, specifically:

* 🔹 **PCB schematic and layout design** using **Altium**
* 🔹 **Circuit design of the output indication stage**, particularly the **comparator-based tuning indicator**
* 🔹 **Implementation of the PCB hardware prototype**
* 🔹 Participation in **breadboard testing, debugging, and system integration**

The comparator stage designed in this project enables **clear visual feedback (LED indication)** that informs the user whether the guitar string is **under-tuned, over-tuned, or perfectly tuned**.

---

# 📌 Project Overview

The **Analog Acoustic Guitar Tuner** is a **fully analog signal-processing system** that detects the frequency of a plucked guitar string and visually indicates whether the string is tuned correctly.

Unlike digital tuners, this device performs **all signal processing using analog circuits**, including filtering, frequency detection, and voltage comparison.

The system supports standard acoustic guitar tuning:

| String | Note | Frequency |
| ------ | ---- | --------- |
| 6      | E6   | 82.41 Hz  |
| 5      | A5   | 110 Hz    |
| 4      | D4   | 146.83 Hz |
| 3      | G3   | 196 Hz    |
| 2      | B2   | 246.94 Hz |
| 1      | E1   | 329.63 Hz |

The device operates using a **9V power supply** and provides tuning feedback using **LED indicators**.

---

# ⚙️ System Working Principle

The overall system processes the acoustic signal through several analog stages.

```
Guitar String Vibration
        ↓
Microphone Input
        ↓
Signal Amplification
        ↓
State Variable Bandpass Filter
        ↓
Schmitt Trigger
        ↓
Frequency-to-Voltage Converter
        ↓
Buffer Stage
        ↓
Comparator Circuit (Potential Dividers)
        ↓
LED Tuning Indicator
```

Each block performs a specific function in converting **sound → frequency → voltage → tuning indication**.

---

# 🔬 System Architecture

## 1️⃣ Microphone Input

🎤 **Purpose**

Convert acoustic vibrations of the guitar string into an electrical signal.

**Key components**

* Condenser microphone
* LM358 operational amplifier
* Variable resistor for gain adjustment

The microphone captures signals typically in the **60–400 Hz frequency range**.

---

## 2️⃣ Amplifier Stage

🔊 **Purpose**

Increase the microphone signal to a usable voltage level.

**Key component**

* **C1845 transistor amplifier**

The amplifier provides approximately:

* **Gain:** 35–40 dB
* **High input impedance (>1 MΩ)**

This stage ensures the signal is strong enough for further processing.

---

## 3️⃣ State Variable Filters

🎚 **Purpose**

Extract the **fundamental frequency** of the selected guitar note while suppressing harmonics and noise.

Six **second-order active band-pass filters** were designed, each corresponding to one guitar string frequency.

State variable filters were chosen because they:

* Provide **sharp frequency selectivity**
* Maintain signal amplitude better than passive filters
* Are suitable for **audio applications**

---

## 4️⃣ Schmitt Trigger

📉 **Purpose**

Convert the filtered analog waveform into a **clean digital square wave**.

**Key component**

* LM393 comparator

This stage removes noise and prepares the signal for frequency measurement.

---

## 5️⃣ Frequency-to-Voltage Converter

🔄 **Purpose**

Convert the signal frequency into a **proportional DC voltage**.

**Key component**

* **LM2917 Frequency-to-Voltage Converter**

This stage transforms frequency information into voltage that can be easily compared.

---

## 6️⃣ Buffer Stage

🧩 **Purpose**

Prevent loading between stages and stabilize the output signal.

**Key component**

* LM358 operational amplifier

---

## 7️⃣ Comparator and Output Indicator

💡 **Purpose**

Determine whether the detected frequency is:

* **Lower than the correct frequency**
* **Higher than the correct frequency**
* **Equal to the correct frequency**
  
Here, potential divider circuit is used to generate reference voltages corresponding to correct tuning frequency of the note as follows.

| Voltage (V) | Frequency (Hz) | Guitar Note |
| ----------- | -------------- | ----------- |
| 1.2 V       | 82.4 Hz        | E (Low E)   |
| 1.6 V       | 110 Hz         | A           |
| 2.1 V       | 146.6 Hz       | D           |
| 2.8 V       | 196 Hz         | G           |
| 3.5 V       | 246.9 Hz       | B           |
| 4.6 V       | 329.6 Hz       | E (High E)  |


**Key component**

* LM393 comparator

**LED Indications**

| Condition          | LED Output     |
| ------------------ | -------------- |
| Frequency too low  | 🟢 Green LED   |
| Frequency too high | 🔴 Red LED     |
| Correct tuning     | 🟢🔴 Both LEDs |

The **output indication of comparator stage were designed as part of my circuit design contribution.**

---

# 🧩 PCB Design

The system was implemented on a **custom PCB designed in Altium**.

### Design considerations

* Efficient component placement
* Reduced noise coupling
* Clear signal routing for analog stages
* Stable power distribution

📌 **My Role**

* Designed the **schematic and PCB layout**
* Organized analog stages for **minimal interference**
* Assisted with **PCB assembly and debugging**

---

# 🧱 Enclosure Design

The device enclosure was designed using **Autodesk Fusion**.

### Key design goals

* Compact handheld structure
* Easy access to the tuning dial
* Proper positioning of the **microphone near guitar strings**
* Protection of internal circuitry

---

# 🎥 Project Demonstration

A demonstration of the working tuner can be viewed below:

👉 **[Project Demo Video](ADD_VIDEO_LINK_HERE)**

---

# 👥 Team Oscivox

| Name                | Index   |
| ------------------- | ------- |
| Gunathunga U.A.     | 230218G |
| Palihena H.H.       | 230458P |
| Abeywardhana T.C.W. | 230012U |
| Perera K.W.A.O.V.   | 230481E |

---



✔ **Repository Contents**

```
/PCB
/Schematics
/Enclosure
/Simulations
/Datasheet
/Final_Report
README.md
```

