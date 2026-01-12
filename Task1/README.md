# Task 1: A/B Test Simulation & Revenue Projection

## Overview
This module simulates a 30-day A/B test for "Project X" to evaluate two monetization strategies. Instead of relying on simple linear extrapolations, this project utilizes **Power Law curve fitting** and **cohort-based simulation** to model user retention and revenue with high precision.


## Methodology
The simulation is built on a custom Python engine designed to handle complex cohort behaviors:
1.  **Retention Modeling:** Uses `scipy.optimize` to fit a Power Law distribution ($R(t) = a \cdot t^b$) to the sparse retention data points (D1, D3, D7, D14).
2.  **Cohort Simulation:** Calculates Daily Active Users (DAU) by summing active users from every install cohort individually, ensuring accurate "Day n" accounting.
3.  **Mixed-Regime Modeling:** Handles dynamic scenario changes, such as the introduction of a new user source on Day 20, by tracking install dates and applying different retention curves to different cohorts.

## Key Assumptions
To conduct the revenue analysis, the following assumption was made based on standard mobile game metrics:
* **Average Revenue Per Paying User (ARPPU):** Assumed to be **$1.00**.
    * *Reasoning:* The provided dataset included the "Daily Purchase Ratio" (Conversion Rate) but did not specify the IAP price. A constant value was used to allow for relative comparison between variants.

---

## Key Findings & Results

### a) DAU Projection (Day 15)
**Winner:** **Variant B**
* **Variant A:** ~74,685 DAU
* **Variant B:** ~76,474 DAU
* *Insight:* Variant B starts with lower Day 1 retention but decays slower (higher D14 retention), allowing it to accumulate more active users over time.

![DAU Projection Trend](Task1\Outputs\DAUprojection.png)

### b) Revenue Projection (Day 15)
**Winner:** **Variant A**
* **Variant A:** ~$42,678
* **Variant B:** ~$41,208
* *Insight:* Despite having fewer users, Variant A generates more revenue in the first two weeks due to a significantly higher **Ad Impressions per DAU** (2.3 vs 1.6), which offsets the lower retention.

![Cumulative Revenue Race, 15 Days](Task1\utputs\CumRevenueRace15.png)

### c) Revenue Projection (Day 30)
**Winner:** **Variant A**
* **Variant A:** ~$117,144
* **Variant B:** ~$109,307
* *Insight:* The trend holds. Variant A's aggressive ad strategy generates more total value over 30 days, even though Variant B has a healthier retention curve.

![Cumulative Revenue Race, 30 Days](Task1\Outputs\CumRevenueRace30.png)

### d) Impact of 10-Day Sale
*Scenario: A 1% boost to Purchase Rate from Day 15–24.*
* **Result:** Revenue increases to **~$122,767** (Variant A).
* **Impact:** A significant short-term lift that makes this the highest *total revenue* option within the specific 30-day window.

![Impact of 10 Day Sale](Task1\Outputs\Sale.png)

### e) Impact of New User Source
*Scenario: Adding a high-retention user source (12k Old / 8k New) starting Day 20.*
* **Result:** Revenue is **~$117,923** (Variant A).
* **Impact:** Lower than the "Sale" scenario within the first 30 days because the new source only enters the simulation for the final 10 days.

![New User Source Revenue](Task1\Outputs\NewUserSource.png)

---

## Strategic Recommendation (Question f)

**Decision:** Prioritize the **New User Source**.

While the **10-Day Sale** generates higher revenue within the strict 30-day simulation window ($122k vs $117k), it is a temporary event. Once the sale ends, revenue reverts to baseline.

The **New User Source** represents a permanent structural improvement to the game's economy. The superior retention of the new users improves **Lifetime Value (LTV)**, meaning the value of this option will compound and surpass the temporary sale in Month 2 and Month 3. For long-term growth, retention is the priority.

![Strategic Comparison](Task1\Outputs\Comparison.png)

---

## How to Run
1.  Open `Task1.ipynb`.
2.  Ensure `scipy`, `numpy`, `pandas`, and `matplotlib` are installed.
3.  Run all cells to generate the simulation data and visualizations.