<div align="center">

# ✈️ CabinMind AI

### The aircraft cabin that notices how you feel — *before* you have to ask.

**Edge AI for Connected, Secure & Software-Defined Aerospace Systems**
Tata Technologies **InnoVent-27** · Track: *AI at the Edge — Aerospace* · Team **Hustle Squad**

🔴 **[Try the live app → cabinmindaiapp.vercel.app](https://cabinmindaiapp.vercel.app/#/engine)**

</div>

---

## 💡 The idea in 30 seconds

Aircraft track engines, fuel and avionics down to the last sensor. But **nobody is tracking how the people inside are doing.**

CabinMind AI turns every seat into a quiet wellbeing monitor. It senses stress, fatigue and prolonged stillness, then **calms the cabin and silently alerts the crew** — no wearables, no call button, no public announcement.

| 😰 25M+ | 🚑 1 in 15–50K | 🦵 4+ hrs | 🌀 ~30 sec |
|---|---|---|---|
| people in the US alone fear flying | passengers face an in-flight medical emergency | sitting still sharply raises DVT risk | typical warning before turbulence |

**Today the cabin reacts. CabinMind AI makes it anticipate.**

---

## 🔁 How it works — one closed loop

```
SENSE  →  ANALYZE  →  PREDICT  →  ADAPT  →  ALERT
seat       edge         Random      light +    silent crew
sensors    fusion       Forest      calming    alert with seat,
                        risk class  tone       risk, action
```

**Four capabilities**
- 🧘 **Stress-aware cabin adaptation** – light and calming tone respond to each passenger
- 🌀 **Predictive turbulence pre-calming** – calm prompts *ahead* of turbulence, not a last-second PA
- 🩺 **Silent medical escalation** – discreet crew alert with seat, risk level and suggested action
- 📋 **Post-flight wellness report** – automatic fatigue-recovery summary

---

## 🔌 The sensor rig (one seat, ~Rs 1,850)

| Sensor | What it tells us | Why it matters |
|---|---|---|
| ❤️ **MAX30102** | Heart rate | Earliest stress signal |
| 💧 **GSR module** | Skin conductance | Anxiety shows here before it shows on the face |
| 🪑 **FSR-402 pressure pad** | Seat occupancy + stillness | Skips empty seats; powers DVT "move around" prompts |
| 🏃 **MPU-6050** | Movement | Restlessness = distress, long stillness = clot risk |
| 💡 **LED + 🔔 buzzer** | Outputs | Teal → lime → amber → red light, gentle calming tone |

Brain: **ESP32** running sensor fusion and risk scoring **on the seat itself**.

---

## 🤖 The AI

- **Random Forest** (scikit-learn, 200 trees) classifies risk as `normal / watch / warning / critical`
- Inputs: heart rate, GSR, movement, cabin temperature, ambient noise
- **90.3% accuracy · 86.4% macro F1** on a held-out test set of **6,000 synthetic readings**
- Feature importance exposed, so every alert is **explainable**, not a black box
- Extra intent model powers the crew **Copilot**

> ⚠️ **Honest note:** these numbers are from synthetic data. Real accuracy will differ — collecting real sensor logs is our #1 Stage 3 task.

---

## 🔒 Privacy is built in, not bolted on

- Raw heart-rate / skin / motion data **never leaves the seat**
- Cloud receives only: *state, risk score, stillness, occupancy*
- AWS ingest function strips any `raw_*` field; data auto-deletes after 24 h
- Passenger companion is **opt-in** — decline and that seat stays unmonitored
- No cameras, no audio, no wearables, no identity link

---

## ✅ What is built today (Stage 2) — and what isn't

| Part | Status |
|---|---|
| Crew dashboard (24 seats), passenger companion, Copilot, 3D cabin twin | ✅ Working software prototype *(simulated data)* |
| Virtual ESP32 rig + 3D hardware assembly | ✅ Working simulation |
| Risk + intent ML models | ✅ Trained *(synthetic data)* |
| ESP32 firmware | 📝 Written, not yet flashed |
| AWS pipeline (IoT Core → Lambda → DynamoDB → API Gateway) | 📝 Code unit-tested, deployment next |
| Physical rig, aircraft testing, passenger studies | 🎯 Future work |

*No certification, airline partnership or passenger trial is claimed.*

---

## 📦 What's in this repository

This repo contains our two round submissions as zip files.

| File | What's inside |
|---|---|
| 📁 **`Stage1.zip`** | Stage 1 submission: our concept and proposal for CabinMind AI |
| 📁 **`Stage2.zip`** | Stage 2 submission: the full working prototype *(details below)* |

### Inside `Stage2.zip`

| Folder / file | Contents |
|---|---|
| `CabinMind_AI_Vercel_App/` | React + TypeScript + Vite app (the deployed live app) |
| `CabinMind_AI_Premium_App.html` | Standalone crew app. **Just double-click to open** |
| `passenger interaction.html` | Passenger companion screen |
| `Cabinmind ai software simulator/` | Dashboard + 3D cabin simulations |
| `Cabinmind ai Hardware prototype/` | 3D hardware assembly, virtual ESP32 simulator, wiring and breadboard diagrams |
| `Cabinmind AI Model Training-Risk classification/` | Notebook, 6,000-row dataset, confusion matrix, feature importance, results report |
| `Cabinmind AI AWS FULL/` | ESP32 firmware, AWS Lambda code + tests, architecture diagram, pitch deck |
| `CabinMind_AI_Stage2_Demo_Video.mp4` | 2 min 39 s demo walkthrough |
| `*.pdf` | Budget & Cost · InnoVent-27 Fit · Societal Impact |

### ▶️ How to try it (no setup)
1. Easiest: open the **[live app](https://cabinmindaiapp.vercel.app/#/engine)**
2. Or download `Stage2.zip`, unzip, and double-click `CabinMind_AI_Premium_App.html`

---

## 🗺️ Roadmap to the physical prototype

| When | Milestone |
|---|---|
| Oct–Nov 2026 | Order parts, assemble breadboard rig, flash firmware, bench-test |
| Nov 2026 | Deploy AWS pipeline, Seat 1A live on the dashboard |
| Dec 2026 | Collect real sensor logs, retrain the model |
| Jan 2027 | Stage 3 demo: physical seat rig → cloud → crew dashboard |

---

## 🛠️ Tech stack

`ESP32` `MAX30102` `GSR` `FSR-402` `MPU-6050` · `Python` `scikit-learn` · `React` `TypeScript` `Vite` `Three.js` · `Vercel` · `AWS IoT Core` `Lambda` `DynamoDB` `API Gateway`

---

## 👩‍💻 Team Hustle Squad

| Name | Branch |
|---|---|
| **Ananya Hebbar** *(Team Lead)* | CSE |
| Nisha Manoj Gunagi | EC |
| Afra Rafeek K | EC |
| Anjali P | CSE |
| Afsheen Banu | EC |

🎓 Mangalore Institute of Technology & Engineering (MITE), Moodabidri · Batch 2027

---

<div align="center">

**CabinMind AI — because flying should care about the person in seat 14C.**

*Built for Tata Technologies InnoVent-27*

</div>
