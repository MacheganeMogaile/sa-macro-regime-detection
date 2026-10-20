# Unsupervised Macroeconomic Regime Detection in South Africa (1999–2025)

## Executive Summary
This project applies unsupervised machine learning—specifically a **2-State Gaussian Hidden Markov Model (HMM)**—to 26 years of South African quarterly macroeconomic data (1999 Q1 – 2025 Q4). By simultaneously analyzing **Interest Rates (Repo Rate)**, **Inflation (CPI)**, **Output Growth (GDP)**, and the **Nominal Effective Exchange Rate (NEER)**, the model automatically identifies persistent macroeconomic regimes and structural shocks without human bias or manual date splits.

---

## Key Findings

### 1. Robust State Persistence & Transition Probabilities
Model validation confirms high state stability, eliminating short-term chatter:
* **State 0 Persistence:** 91.5% probability of remaining in Macro Stress quarter-to-quarter.
* **State 1 Persistence:** 97.5% probability of remaining in Normal Operating conditions quarter-to-quarter.

### 2. Empirical Characterization of Macro Regimes

| Macroeconomic Metric | State 0: Macro Stress Regime | State 1: Normal Operating Regime |
| :--- | :--- | :--- |
| **YoY Inflation (%)** | 5.40% | 5.42% |
| **QoQ GDP Growth (%)** | **0.39%** | **0.60%** |
| **$\Delta$ NEER (% Change)** | **-1.75%** | **-0.53%** |
| **Real Repo Rate (%)** | **-0.64%** | **2.92%** |

* **State 0 (Macro Stress):** Captures acute structural shock windows (such as the 2008 Global Financial Crisis and 2020 COVID-19 pandemic), characterized by negative real interest rates (-0.64%), depressed GDP growth (0.39%), and sharp currency depreciation (-1.75%).
* **State 1 (Normal Operating Regime):** Captures baseline economic operating conditions where the South African Reserve Bank maintains positive real rates (2.92%) to manage inflation alongside steady GDP growth (0.60%).

---

## Technical Stack
* **Language:** Python
* **Environment:** Google Colab
* **Libraries:** `hmmlearn`, `pandas`, `numpy`, `matplotlib`, `seaborn`
* **Feature Engineering:** Stationarity transformations ($\Delta \text{NEER}_t$, $\text{Inflation}_{\text{YoY}}$, $\text{Real Repo Rate}_t$, $\text{GDP}_{\text{QoQ}}$) to ensure scale-invariant clustering.
