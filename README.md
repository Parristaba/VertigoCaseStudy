# Vertigo Games — Data Analyst Case Study

This repository contains the complete solution for the **Data Analyst Case Study**, divided into two distinct modules: an **A/B Test Simulation (Task 1)** and a **Deep-Dive User Segmentation Analysis (Task 2)**.

---

## 📂 Project Structure

```text
├── Task1/                     # A/B Test Simulation & Revenue Projection
│   ├── Task1.ipynb            # Simulation Engine (Power Law Modeling & Cohort Analysis)
│   ├── README.md              # Detailed methodology and strategic recommendations
│   └── Outputs/               # Generated visualizations (Revenue race, Retention curves)
│
├── Task2/                     # Exploratory Data Analysis (EDA)
│   ├── Task2.ipynb            # Hypothesis-driven analysis (Rage Quit, Aha Moment, Whales)
│   ├── README.md              # Key behavioral insights and product actions
│   ├── Data/                  # (Gitignored) Raw CSV files
│   └── Outputs/               # Key charts (Heatmaps, Lift charts, Archetypes)
│
├── READMEmd                     
├── .gitignore                 # Datasets are ignored, for size concerns
└── Case Study PDF
```

---

## 🚀 Overview of Modules

### Task 1: Simulation & Revenue Projection

* **Goal:** Evaluate two game variants (**A vs. B**) and model the impact of a **10-Day Sale** vs. a **New User Source**.
* **Approach:** Built a custom Python simulation engine using **SciPy** for **Power Law retention fitting** and **mixed-cohort modeling**.
* **Key Output:** A strategic recommendation balancing **Long-Term Value (LTV)** vs. **Short-Term Revenue**.

### Task 2: User Segmentation & EDA

* **Goal:** Analyze user behavior to identify drivers of **Churn** and **Monetization**.
* **Approach:** Used **Pandas** and **Scikit-Learn (Decision Trees)** to identify **Rage Quitters**, **Whale Thresholds**, and **Matchmaking Pain Points**.
* **Key Output:** Actionable product insights on **game balance**, **technical stability**, and **hybrid monetization**.

---

## 🛠️ Requirements

To run the notebooks, ensure the following Python libraries are installed:

```bash
pip install pandas numpy matplotlib scipy scikit-learn
```

For detailed findings, methodology, and visualizations, please refer to the specific `README.md` files inside the `Task1/` and `Task2/` directories.
