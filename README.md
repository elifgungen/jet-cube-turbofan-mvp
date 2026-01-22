# Jet Cube Turbofan MVP

This repository contains a **decision-support–oriented digital twin MVP** for
**predictive maintenance of commercial turbofan engines**, developed using the
NASA **C-MAPSS** degradation simulation dataset.

The focus of this project is **not only prediction**, but the **translation of
model outputs into actionable maintenance decisions**.

---

## 📌 Project Objective

Modern predictive maintenance systems often provide outputs such as:
- Remaining Useful Life (RUL)
- Anomaly scores

However, these outputs are frequently:
- hard to interpret,
- detached from operational decision-making,
- dependent on manual expert judgment.

**This project addresses that gap.**

The objective is to build an MVP that:
- combines RUL and anomaly detection outputs,
- applies a transparent, literature-backed decision logic,
- produces **clear maintenance-oriented recommendations**.

---

## 🧠 Digital Twin Perspective (MVP Level)

In this project, a digital twin is defined as:

> A data-driven representation of a physical turbofan engine that
> continuously reflects its health state and supports maintenance decisions.

At the MVP level:
- the twin is **data-driven**, not fully physics-based,
- it is designed to be **extendable** to hybrid (physics + data) twins,
- emphasis is placed on **decision-support**, not real-time deployment.

---

## 📊 Dataset

The MVP is developed using the **NASA C-MAPSS FD001** dataset, a widely accepted
benchmark for turbofan engine degradation and RUL estimation.

Key generated artifacts:
- `fd001_processed.csv` — cleaned and processed sensor + cycle data
- `fd001_rul_predictions.csv` — model-based RUL estimates
- `fd001_anomaly_scores.csv` — anomaly scores per engine cycle

---

## ⚙️ System Architecture
Sensor Data
↓
Preprocessing & Feature Engineering
↓
RUL Estimation        Anomaly Detection
↓                     ↓
Decision-Support Layer
(Threshold-based logic)
↓
Maintenance Recommendation
The **decision-support layer** is the core contribution of this MVP.

---

## 🧩 Decision-Support Logic

Rather than relying solely on model confidence, the system uses:
- RUL thresholds (e.g. critical, warning, normal),
- anomaly score thresholds,
- joint interpretation of both signals.

This enables outputs such as:
- *“Continue operation”*
- *“Increase monitoring frequency”*
- *“Schedule maintenance”*

Each recommendation is accompanied by a **clear rationale**, ensuring
interpretability and operational relevance.

---
## 📁 Repository Structure

- **AGENTS.md**  
  Project-level instructions for agent-based and automated workflows.

- **notebooks/**  
  Jupyter notebooks covering the full MVP pipeline:
  - setup
  - exploratory data analysis (EDA)
  - preprocessing
  - RUL modeling
  - anomaly detection
  - decision-support logic

- **data/**
  - **raw/**: original, untouched datasets  
  - **processed/**: cleaned and feature-engineered data  
  - **outputs/**: model predictions and intermediate results

- **docs/**
  - `motor_context.md`: high-level turbofan and sensor context  
  - `decision_logic.md`: decision-support rules and thresholds

- **demo/**  
  Demo-related materials and visualization artifacts.

- **requirements.txt**  
  Python dependencies required to run the project.

- **README.md**  
  Project overview and documentation.
## 🚀 MVP Scope and Limitations

Included in MVP:
- single-engine analysis,
- RUL estimation,
- anomaly detection,
- explainable decision-support logic.

Not included in MVP:
- real-time sensor integration,
- proprietary maintenance records,
- full physics-based simulation.

The architecture is intentionally designed to support future extension to:
- fleet-level monitoring,
- hybrid digital twin implementations,
- industrial pilot deployments.

---

## 📌 Key Contribution

The primary contribution of this project is **not model accuracy alone**, but:

> the systematic transformation of predictive model outputs into
> interpretable, defensible, and actionable maintenance decisions.

---

## 📄 License & Usage

This repository is intended for research, prototyping, and demonstration purposes.
Dataset usage follows the terms provided by NASA C-MAPSS.
