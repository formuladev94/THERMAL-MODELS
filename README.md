# THERMAL-MODELS
Thermal analysis tools and predictive models (LSTM) based on open data from NASA (Curiosity REMS and LRO Diviner) for Mars and the Moon. Developed for the NASA Space Apps Challenge 2026.


# 🌌 Thermal Analysis & LSTM Forecasting for Mars & Moon (NASA Space Apps Challenge)

This repository contains two Python notebooks designed to extract, process, visualize, and model real thermal data from celestial bodies using public NASA repositories (Planetary Data System - PDS). 

Both notebooks are optimized to run seamlessly in **Google Colab** with no accounts or complex setup required.

---

## 📂 Repository Contents

1. **`mars_rems_temperature_lstm.ipynb`**: Downloads the chronological weather history from the **Curiosity** rover's REMS station on Mars, generates hourly CSV/Excel tables, and trains an **LSTM** neural network to forecast short-term air and ground temperatures.
2. **`lunar_diviner_table.ipynb`**: Processes polar thermal maps from the **Lunar Reconnaissance Orbiter (LRO Diviner)** to extract surface temperature profiles at craters of interest (such as Shackleton) across a full lunar day (summer and winter)

---

## 🚀 1. Mars Surface & Air Temperature History + LSTM (Curiosity REMS)

This notebook works with real, continuous chronological data collected by the Curiosity rover in Gale Crater since August 2012.

### Key Features:
* **Automated Data Retrieval:** Fetches REMS Reduced Data Records (RDR) directly from the NASA PDS Atmospheres Node.
* **Temporal Processing:** Computes minimum, maximum, and mean temperatures (in Kelvin) for every hour of each sol (Martian day).
* **LSTM Forecasting Model:** Implements a recurrent neural network (LSTM using TensorFlow/Keras) that analyzes a 24-hour Martian historical window to predict the next hour's air and ground temperatures, benchmarking performance against a naive persistence baseline.
* **Data Export:** Automatically exports processed tables to `.csv` and `.xlsx` formats.

<img width="1189" height="490" alt="Gale Crater (Curiosity REMS) daily temperature range" src="https://github.com/user-attachments/assets/b990a6ba-c6ca-4531-b5b5-f751059ff66b" />

---

## 🌙 2. Lunar Polar Temperature Table (LRO Diviner)

This notebook analyzes lunar polar regions using accumulated bolometric brightness temperature maps measured by the Diviner instrument aboard LRO between 2009 and 2019.

### Key Features:
* **Region of Interest (ROI) Selection:** Allows analysis of key polar craters (*Shackleton*, *Haworth*, *Shoemaker*, *Faustini*, *Cabeus*, *Peary*) or custom latitude/longitude coordinates with an adjustable radius.
* **Full Lunar Cycle:** Generates 96-step temperature tables per lunar day (~7.4 hours per step) for both summer and winter seasons.
* **Thermal Stability Analysis:** Helps evaluate extreme thermal conditions and potential water-ice stability zones (referenced against the 110 K threshold).

<img width="1188" height="490" alt="shackleton surface temperature (Diviner 2009 - 2019)" src="https://github.com/user-attachments/assets/3f49ddba-661a-49d3-877f-0d4e847d0c20" />

---

## ⚙️ Requirements & Usage

Both notebooks are built to run out-of-the-box in **Google Colab**. Standard dependencies (`pandas`, `numpy`, `matplotlib`, `requests`, `tensorflow`) are pre-installed in the Colab environment.

### Quick Start:
1. Upload the desired `.ipynb` file to Google Colab.
2. Run all cells sequentially from top to bottom.
3. *Important Note:* In **Step 1** of each notebook, you will find a quick-test flag (`QUICK_TEST = True`). Run the notebook once with this setting enabled to verify data downloads, then switch it to `False` to run the full dataset and model training.

---

## 📊 NASA Data Sources

* **Mars:** NASA PDS Atmospheres Node – Mars Science Laboratory (MSL) Curiosity REMS Reduced Data Records (RDR).
* **Moon:** NASA PDS Geosciences Node – LRO Diviner Polar Cumulative Products (PCP) binned by subsolar longitude.

---

## 👥 Team / Authors
OVERDRIVE SPACE for the **NASA Space Apps Challenge 2026**.
