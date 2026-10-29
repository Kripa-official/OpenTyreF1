# 🏎️ OpenTyreF1
### A Data-Driven Mobile Platform for Formula 1 Telemetry Analysis and Race-Strategy Simulation[cite: 12]

[![Python 3.11](https://img.shields.io/badge/Python-3.11-blue.svg)](https://www.python.org/)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.100%2B-green.svg)](https://fastapi.tiangolo.com/)
[![React Native](https://img.shields.io/badge/React%20Native-0.86-purple.svg)](https://reactnative.dev/)
[![Expo SDK](https://img.shields.io/badge/Expo-SDK%2057-black.svg)](https://expo.dev/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

*Turning open Formula 1 telemetry into pit-wall decision support on your mobile device.*[cite: 12, 13]

</div>

---

## 📌 About **OpenTyreF1**
Most public Formula 1 tools are purely descriptive—they show you what happened and stop there[cite: 12, 13]. **OpenTyreF1** goes a step further by offering counterfactual strategy simulation. Built as a full-stack cross-platform system, it reconciles multiple public F1 data feeds into a unified relational corpus to power lap-time predictions, Monte Carlo race outcome estimations, and a grounded AI assistant[cite: 12].

---

## 🏗️ System Architecture
The platform operates across three integrated layers:
1. **Presentation Layer (Mobile App):** Cross-platform Expo / React Native app featuring a dark, pit-wall-inspired UI, live countdowns, career stats, and interactive telemetry charts[cite: 33, 35].
2. **Application Layer (Backend):** FastAPI backend hosting 36 REST endpoints[cite: 34], the shared clean-lap filter, XGBoost inference engine[cite: 34], strategy simulators, and pit-wall modules.
3. **Data Layer:** Portable relational database reconciled from **Jolpica-F1/Ergast**, **OpenF1**, and **FastF1** covering 492 races from 2002 to 2026 across 237,308 records[cite: 12, 34].

---

## ✨ Key Features

- **🎯 Leakage-Free Lap-Time Model:** XGBoost trained on a race-relative target (offset from race median) evaluated on whole-race holdout splits, achieving an MAE of `0.893 s` ($R^2 = 0.978$)[cite: 12].
- **🔄 Counterfactual Stint Simulator:** Test alternative tyre strategies against real historical race pacing and field data[cite: 12, 13].
- **🎲 Monte Carlo Outcome Estimator:** Runs 1,500 bootstrap simulations per strategy to project probabilistic finishing positions and manage risk[cite: 12, 28].
- **🛡️ Shared Clean-Lap Filter:** A unified filtering cascade that accurately handles out-laps, pit-stops, and neutralised periods (SC/VSC/Red Flags)[cite: 24, 25].
- **💬 Grounded AI Assistant:** A retrieval-and-template assistant that answers strategy questions strictly backed by database rows and simulation facts without hallucinating[cite: 30].

---

## 🚀 Tech Stack

| Component | Technology / Framework |
| :--- | :--- |
| **Mobile App** | React Native[cite: 34], Expo SDK[cite: 34], TypeScript, TanStack Query[cite: 34], React Native SVG[cite: 34] |
| **Backend API** | Python 3.11[cite: 34], FastAPI[cite: 34], Uvicorn, Pydantic, SQLAlchemy[cite: 34] |
| **Machine Learning** | XGBoost[cite: 34], scikit-learn[cite: 34], pandas[cite: 34], NumPy[cite: 34] |
| **Data Sources** | Jolpica-F1[cite: 34], OpenF1[cite: 34], FastF1[cite: 34] |
| **Deployment** | Docker[cite: 34], Render[cite: 31, 34], Supabase PostgreSQL[cite: 34], Expo EAS[cite: 34] |

---

## 📊 Model Performance Highlights

Evaluated rigorously on 12 completely unseen races:
* **Mean Absolute Error (MAE):** `0.893 s`[cite: 12]
* **Root Mean Square Error (RMSE):** `1.205 s`[cite: 12]
* **Coefficient of Determination ($R^2$):** `0.978` (beating naive baselines by 0.270 s MAE)[cite: 12]

---

## 👥 Authors & Credits
Developed as part of the B.Tech Computer Science & Engineering dissertation at G H Raisoni University, Amravati (2026–27)[cite: 1]:
* **Kripa Patil**[cite: 2]
* *Under the guidance of:* **Mrs. Prachi Jain**[cite: 1]

---

## 📄 License
This project is open-source and available under the [MIT License](LICENSE).
