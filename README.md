# 🛡️ SuRaksha — AI-Powered Women & Child Safety System

> **Instant protection. Intelligent detection. Trusted evidence.**

SuRaksha is an **AI-powered safety platform designed for women and children**, combining a mobile guardian application, wearable BLE technology, real-time location sharing, geofencing, on-device machine learning, and tamper-resistant evidence logging.

The system is designed to reduce the gap between **detecting a dangerous situation and getting immediate help**.

---

## 🚨 Problem Statement

Women and children can face safety threats in both **physical and digital environments**. Existing safety solutions often have limitations such as delayed SOS activation, poor connectivity in indoor environments, lack of real-time child safety alerts, and insufficient evidence preservation.

SuRaksha addresses these challenges through:

* ⚡ Instant and discreet SOS activation
* 📍 Real-time GPS location sharing
* 👨‍👩‍👧 Guardian and family safety monitoring
* 🏫 Real-time child geofencing alerts
* 🤖 On-device AI/ML distress detection
* 🎙️ Live audio and video evidence capture
* 🔐 Tamper-resistant evidence records
* 📡 BLE wearable-based emergency triggering
* 📞 Emergency response integration

---

## 💡 Solution

SuRaksha provides a **guardian-centric safety ecosystem** where one discreet trigger can initiate the complete emergency response workflow.

### Emergency Flow

```text
        🚨 DISTRESS DETECTED
                 │
                 ▼
        ┌─────────────────┐
        │ SOS / Wearable  │
        │     Trigger     │
        └────────┬────────┘
                 │
                 ▼
        🤖 AI/ML Distress
           Verification
                 │
                 ▼
       📍 Live GPS Sharing
          + Audio Capture
                 │
        ┌────────┴────────┐
        ▼                 ▼
   👨‍👩‍👧 Guardians     🚓 Patrol
      Alerted           Alerted
        │                 │
        └────────┬────────┘
                 ▼
        🔐 Evidence Hashing
                 │
                 ▼
        📋 Tamper-Proof Log
```

The proposed methodology follows:

**Trigger → ML confirms distress → Guardians alerted with live GPS & audio → Evidence automatically hashed.**

---

# ✨ Key Features

## 🆘 1. Instant SOS

Users can activate an emergency alert by **pressing and holding the SOS button**.

The prototype uses a 1.5-second hold mechanism to reduce accidental activation.

The system also proposes an alternative hardware trigger:

```text
Triple Press Power Button
          ↓
      SOS Trigger
```

---

## 👥 2. Guardian Circle

When an SOS is activated, trusted guardians can receive the user's:

* Live location
* Emergency status
* Audio information
* Safety notification

The prototype demonstrates a Guardian Circle containing family members, roommates, and verified campus responders.

Example:

```text
                YOU
                 📍
              /      \
             /        \
        👨 Ravi      👩 Priya
       Brother       Roommate
             \        /
              \      /
            🚓 Campus
             Security
```

---

## 👨‍👩‍👧 3. Child Safety & Geofencing

Parents can create predefined **safe zones** such as:

* 🏠 Home
* 🏫 School
* 📚 Tuition Center

The application continuously monitors whether the child remains inside the configured safe zone.

The prototype demonstrates live status and activity tracking for a child named Ira.

### Example

```text
             🏫 SCHOOL
          ┌─────────────┐
          │             │
          │     👧      │
          │     IRA     │
          │             │
          └─────────────┘
                 │
           Safe Zone Active
                 │
          Child leaves zone
                 ↓
           🚨 Parent Alert
```

---

# 🤖 4. AI-Powered Distress Detection

SuRaksha proposes **on-device Machine Learning** to detect potential distress situations.

The advantage of on-device processing is that detection can happen locally without depending entirely on a continuous cloud connection.

The project presentation identifies **TensorFlow Lite** for on-device ML.

Possible future detection signals include:

* Voice distress patterns
* Abnormal movement
* Sudden activity changes
* Emergency keywords
* Wearable sensor signals

> **Note:** These detection capabilities are part of the proposed system architecture; the current uploaded prototype primarily demonstrates the SOS and guardian workflow.

---

# 📡 5. BLE Wearable Safety Tag

SuRaksha proposes a discreet **Bluetooth Low Energy (BLE) wearable tag**.

The wearable can provide an additional emergency trigger without requiring the user to unlock their phone.

```text
       👤 USER
          │
          │
     ┌────▼────┐
     │  BLE    │
     │ Wearable│
     └────┬────┘
          │
       Bluetooth
          │
          ▼
    📱 SuRaksha App
          │
          ▼
       🚨 SOS
```

The proposed technology stack includes **Flutter + BLE wearable hardware**.

---

# 📍 6. Real-Time Location Sharing

During an emergency, SuRaksha is designed to share the user's location with authorized guardians and responders.

The prototype demonstrates:

* Current user position
* Guardian positions
* Patrol location
* Safety-zone visualization

The Guardian Circle screen visually represents these locations.

---

# 🎙️ 7. Live Audio & Video Evidence

During an active SOS event, the prototype displays audio and video recording indicators.

```text
              🚨 SOS ACTIVE
                    │
        ┌───────────┴───────────┐
        │                       │
        ▼                       ▼
     🎙️ AUDIO                🎥 VIDEO
        │                       │
        └───────────┬───────────┘
                    ▼
             🔐 Evidence
```

The prototype explicitly communicates that audio, video, and location information are recorded during an SOS event.

---

# 🔐 8. Tamper-Proof Evidence Logging

One of SuRaksha's key differentiators is its evidence-preservation concept.

Emergency records can be timestamped, hashed, and stored in a tamper-resistant system.

The proposed technical approach mentions **Hyperledger evidence logs**.

The prototype's Evidence Log demonstrates records containing:

* Incident type
* Timestamp
* Duration
* Hash
* Blockchain-sealed status

### Evidence Flow

```text
Audio / Video / GPS
        │
        ▼
   Timestamp
        │
        ▼
    Generate
      Hash
        │
        ▼
Tamper-Proof Storage
        │
        ▼
  Evidence Log
```

---

# 📞 9. Emergency Response

During an active SOS, the prototype provides an option to **call emergency services directly using 112**.

It also demonstrates notifications being sent to:

* Brother
* Roommate
* Campus Security
* Nearest Patrol

---

# 🏗️ System Architecture

```text
                 ┌──────────────────┐
                 │      USER        │
                 └────────┬─────────┘
                          │
             ┌────────────┴────────────┐
             │                         │
             ▼                         ▼
      📱 Mobile App             ⌚ BLE Wearable
             │                         │
             └────────────┬────────────┘
                          │
                          ▼
                 🤖 On-Device ML
                 Distress Detection
                          │
                          ▼
                    🚨 SOS Engine
                          │
            ┌─────────────┼─────────────┐
            │             │             │
            ▼             ▼             ▼
         📍 GPS        🎙️ Audio      🎥 Video
            │             │             │
            └─────────────┼─────────────┘
                          │
                          ▼
                  ☁️ Firebase Backend
                          │
            ┌─────────────┼─────────────┐
            ▼             ▼             ▼
       👨‍👩‍👧 Guardians   🚓 Patrol   🔐 Evidence
                                    Ledger
```

---

# 🛠️ Technology Stack

| Component               | Technology                 |
| ----------------------- | -------------------------- |
| Mobile Application      | Flutter                    |
| Wearable Communication  | Bluetooth Low Energy (BLE) |
| Backend                 | Firebase                   |
| Machine Learning        | TensorFlow Lite            |
| Evidence Ledger         | Hyperledger                |
| Location                | GPS                        |
| Emergency Communication | SMS / API-based fallback   |
| Emergency Response      | 112 Integration            |

The technologies and methodology are based on the project's submitted technical approach.

---

# 📱 Prototype

The repository includes a clickable **SuRaksha prototype walkthrough**.

The prototype contains four major screens:

### 🏠 Home

Displays:

* Guardian Circle status
* GPS status
* Encryption status
* SOS button
* Nearest safe zone
* Child safety status

### 🟢 Guardian Circle

Displays:

* User location
* Guardian locations
* Campus security
* Online/offline status

### 👨‍👩‍👧 Family Safety

Displays:

* Child location
* Safe zones
* Geofence radius
* Activity timeline

### 📋 Evidence Log

Displays:

* Previous safety events
* Incident duration
* Event status
* Hash values
* Blockchain-sealed records

---

# 🖱️ How to Use the Prototype

1. Open the HTML prototype in a modern web browser.
2. Start from the **Home** screen.
3. Navigate using:

   * Home
   * Circle
   * Family
   * Log
4. To test SOS:

   * Press and hold the **HOLD FOR SOS** button for approximately **1.5 seconds**.
5. Observe the emergency workflow.
6. The prototype will simulate guardian notifications.
7. Use **Hold to cancel SOS** to reset the emergency state.

The prototype implements the SOS timer, guardian notification animation, navigation, and hold-to-cancel interaction using JavaScript.

---

# 🎯 Feasibility & Viability

SuRaksha is designed around commercially available technologies and hardware.

### Feasibility

* Off-the-shelf BLE hardware
* Standard mobile APIs
* Cloud backend infrastructure
* On-device ML
* Existing emergency communication infrastructure

### Major Challenges

* Network dead zones
* False emergency detection
* Privacy concerns

### Proposed Strategies

* SMS fallback
* ML-based filtering
* Encrypted opt-in tracking

These feasibility considerations and mitigation strategies are part of the submitted project proposal.

---

# 🌍 Impact

SuRaksha aims to create measurable improvements in both individual and community safety.

### For Women

* Faster emergency response
* Discreet SOS activation
* Live location sharing
* Evidence preservation

### For Children

* Real-time parent alerts
* Safe-zone monitoring
* School and tuition tracking
* Location-based safety notifications

### For Society

* Increased social trust
* Better emergency coordination
* Stronger evidence preservation
* Safer smart-city environments

The project identifies faster help for women and instant parent alerts for children as key expected benefits.

---

# 🚀 Future Scope

Potential future improvements include:

* Advanced voice-based distress detection
* Fall and impact detection
* Smartwatch integration
* More wearable form factors
* Offline-first emergency communication
* Mesh-based emergency networking
* Automated emergency escalation
* Advanced AI risk prediction
* Multi-language voice assistance
* Police and institutional dashboards
* Stronger privacy-preserving ML

---

# ⚠️ Current Prototype Limitations

This repository contains a **demonstration prototype**, not a production-ready emergency service.

The current HTML prototype simulates:

* SOS activation
* Guardian notification
* GPS visualization
* Family geofencing
* Evidence logs
* Emergency response UI

Actual deployment would require production implementations of:

* Real GPS services
* Authentication
* Secure backend APIs
* BLE hardware communication
* ML models
* Emergency service integrations
* Secure evidence storage
* Privacy and consent mechanisms

---

# 📂 Project Structure

```text
SuRaksha/
│
├── prototype.html
├── README.md
│
├── assets/
│   ├── images/
│   └── icons/
│
├── mobile/
│   └── Flutter application
│
├── ml/
│   └── TensorFlow Lite models
│
├── wearable/
│   └── BLE firmware
│
└── backend/
    └── Firebase configuration
```

> The exact production structure may change as the prototype evolves.

---

# 👨‍💻 Team

### Team — AI Sentinals

| Member                | Role                       |
| --------------------- | -------------------------- |
| **Abhishek Tiwari**   | Flutter Engineer           |
| **Aditya Raj Tiwari** | Firebase Backend Developer |
| **Priyanshu Tiwari**  | ML Engineer                |
| **Rudranshu Tiwari**  | Frontend Developer         |

The submitted presentation identifies the team and corresponding roles.

---

# 🏆 Competition

**International Innovation Challenge 3.0**

**Theme:** Women & Child Safety

**Idea:** SuRaksha — AI-powered guardian app + wearable tag for instant, discreet protection.

---

# 📚 References

The project proposal references:

* NCRB — Crime in India reports
* Ministry of Women & Child Development
* Nirbhaya Fund and One Stop Centre guidelines
* Existing safety applications including Himmat, bSafe and 112 India

---

# ⚖️ Disclaimer

SuRaksha is currently a **student innovation project and prototype** developed for the International Innovation Challenge 3.0.

The prototype is intended to demonstrate the proposed safety workflow and should **not be treated as a replacement for official emergency services**.

In a real emergency, users should contact the appropriate emergency services.

---

## ⭐ Vision

> **SuRaksha aims to turn a moment of danger into an immediate, coordinated response — protecting women, children, and their families through intelligent technology.**

---

## 📌 Status

**Project Status:** 🚧 Prototype / Proof of Concept

**Focus:** Women & Child Safety

**Platform:** Mobile + Wearable

**Core Technologies:** Flutter • BLE • Firebase • TensorFlow Lite • Hyperledger
