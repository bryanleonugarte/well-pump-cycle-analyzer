# Well Pump Cycle Analyzer 🌊

Automated Python pipeline for irrigation water tracking
in large-scale agricultural operations.

---

## 🔧 Problem

Managing 20+ water wells in a blueberry and grapevine farm
means tracking every pump cycle — when it turned ON, when it
turned OFF, and how many m³ were extracted.

This was done manually every two weeks. It took several hours
per cycle and was prone to human error.

---

## ✅ Solution

A Python pipeline that processes sensor data automatically:

- Reads CSV files from 20+ well sensors
- Detects valid ON/OFF pump cycles (filters noise < 15 min)
- Crosses each cycle with monthly flow meter readings
- Calculates m³ of water extracted per cycle
- Chains flow meter readings across cycles for accurate totals
- Exports a clean consolidated CSV ready for Power BI or Excel

**Result:** what used to take several hours now runs in minutes,
at a biweekly frequency across the full well network.

---

## 📁 Project structure

well-pump-cycle-analyzer/
│
├── pipeline_pozos.ipynb ← Main notebook
│
├── data/
│ ├── valores_pozos/
│ │ ├── pozo_1_2026_06.csv ← Sensor data per well (fictional)
│ │ ├── pozo_2_2026_06.csv
│ │ └── pozo_3_2026_06.csv
│ │
│ ├── valores_caudalimetro/
│ │ └── registro_caudalimetros.xlsx ← Monthly flow meter readings
│ │
│ └── registro_pozos/
│ └── registro_pozos_final.csv ← Pipeline output sample

---

## 🛠 Tech stack

- **Python** — Pandas, glob, os, datetime
- **Input:** CSV sensor files + Excel flow meter records
- **Output:** consolidated CSV with m³ per cycle

---

## ▶ How to run

```bash
pip install pandas openpyxl
jupyter notebook pipeline_pozos.ipynb
```

Open the notebook and run all cells (`Kernel → Restart & Run All`).

---

## 👤 Author

**Bryan León Ugarte** — Agricultural Engineer & AgTech Data Analyst

[LinkedIn](https://www.linkedin.com/in/bryan-aquiles-le%C3%B3n-ugarte-13a76b156/)
