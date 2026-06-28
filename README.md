# Air Quality Intelligence Report
### AI-Powered Data Analysis using Amazon PartyRock (AWS Bedrock)

---

##  Problem Statement

Urban air quality deterioration is a critical public health challenge worldwide. Cities like **Lahore and Karachi** in Pakistan face severe smog crises , yet data-driven analysis of pollution patterns remains inaccessible to most people without technical expertise.

This project analyzes a real-world air quality dataset (UCI Machine Learning Repository) containing **hourly sensor readings** from a significantly polluted urban area in Italy. Using **Amazon PartyRock's AI-powered Analyze Data feature**, this project demonstrates how natural language questions , without any coding can generate accurate, actionable insights from complex environmental data.

**Core Questions This Project Answers:**
1. When is pollution at its worst — and why?
2. Which pollutants pose the greatest health risk?
3. How do weather conditions affect air quality?
4. What interventions would have the most impact?

---

##  Dataset Overview

| Property | Details |
|---|---|
| **Source** | UCI Machine Learning Repository (OpenAQ) |
| **Sample Used** | 246 hourly readings (March 10–20, 2004) |
| **Location** | Road-level urban monitoring station, Italian city |
| **Tool Used** | Amazon PartyRock — Analyze Data Feature |

### Key Features (Columns):

| Column | Pollutant | Why It Matters |
|---|---|---|
| **CO_GT** | Carbon Monoxide (mg/m³) | Vehicle exhaust gas — causes headaches, dizziness |
| **NOx_GT** | Nitrogen Oxides (µg/m³) | Traffic emissions — causes smog and lung damage |
| **NO2_GT** | Nitrogen Dioxide (µg/m³) | Respiratory irritant — triggers asthma |
| **C6H6_GT** | Benzene (µg/m³) | Known carcinogen — no safe exposure level |
| **Temperature** | Temperature (°C) | Affects atmospheric dispersion of pollutants |
| **Humidity** | Relative Humidity (%) | Influences pollution concentration |

---

##  Analysis .. 10 Questions Asked to AI

### Q1: What is the average CO concentration across the dataset?
**Result:** `2.36 mg/m³`

 Below WHO safe limit of 10 mg/m³ on average — however, 26% of individual readings exceed 3 mg/m³, indicating regular dangerous spikes.

---

### Q2: Which hour of the day has the highest NOx levels?
**Result:** `8:00 AM — 336.5 µg/m³`

 Morning rush hour is clearly the primary driver of NOx pollution. Vehicle emissions during peak commute hours create a dramatic and predictable daily spike.

---

### Q3: What is the correlation between temperature and CO levels?
**Result:** `Correlation = 0.54 (Moderate Positive)`

 As temperature rises, CO levels tend to increase. Warmer conditions lead to more traffic activity and reduced atmospheric dispersion — a pattern directly relevant to summer smog in Pakistani cities.

---

### Q4: Summary Table — Average Pollutant Levels vs WHO Thresholds

| Pollutant | Average Concentration | WHO Safe Limit | Status |
|---|---|---|---|
| CO | 2.36 mg/m³ | 10 mg/m³ |  Safe |
| NO2 | 107.51 µg/m³ | 40 µg/m³ |  2.7x ABOVE LIMIT |
| Benzene | 9.59 µg/m³ | 5 µg/m³ (EU) |  ABOVE LIMIT |

**Key Insight:** CO is not the primary concern — NO2 and Benzene are the real health threats at this location.

---

### Q5: What are 3 recommendations to improve air quality?
1. **Target 8 AM Rush Hour** — Promote carpooling, public transport, staggered work hours
2. **Temperature-Based Restrictions** — Implement temporary traffic limits on high-temperature days
3. **Reduce Benzene Sources** — Stricter vehicle emission standards + low-emission zones

---

### Q6: What time of day has the lowest pollution levels?
**Result:** `4:00 AM — All pollutants 48–76% below average`

| Pollutant | 4 AM Level | vs. Average |
|---|---|---|
| CO | 0.88 mg/m³ | 63% lower |
| NOx | 41 µg/m³ | 71% lower |
| NO2 | 56 µg/m³ | 48% lower |
| Benzene | 2.27 µg/m³ | 76% lower |

 Zero traffic + cooler temperatures = dramatically cleaner air. The difference between 4 AM and 8 AM represents the entire impact of human activity on air quality.

---

### Q7: Compare CO levels — Morning vs Evening
**Result:**

| Time Period | Avg CO | Readings |
|---|---|---|
| Morning (6AM–12PM) | 3.22 mg/m³ | 60 |
| Evening (6PM–12AM) | 2.57 mg/m³ | 66 |

Morning CO is **25% higher** than evening despite similar traffic volumes. Reason: Morning atmospheric temperature inversion traps pollutants at ground level. Evening air circulates more freely.

---

### Q8: What percentage of readings exceed CO danger threshold?
**Result:** `26% of readings (64 out of 246) exceed 3 mg/m³`

 Roughly 1 in 4 hourly readings shows elevated CO — confirming that dangerous exposure is a regular occurrence, not an exception.

---

### Q9: Which pollutant shows highest variation?
**Result:**

| Pollutant | Standard Deviation | Coefficient of Variation |
|---|---|---|
| Benzene | 5.72 | **59.58%** ← Most Variable |
| CO | 0.98 | 41.66% |
| NO2 | 31.22 | 29.04% |

 Benzene's extreme variability (60%) is the most alarming finding. It means benzene occasionally spikes to very high levels unpredictably — and since it's a carcinogen with no safe exposure level, even brief spikes pose serious health risks.

---

### Q10: Overall Air Quality Assessment
**AI Verdict: Moderate to Poor**

> "This location has a traffic-dominated pollution profile with unhealthy morning air quality. Residents face regular exposure to elevated pollutants, particularly carcinogenic benzene and respiratory irritants NOx and NO2. Immediate interventions targeting rush hour emissions and benzene sources are needed."

---

##  Key Findings Summary

```
 Worst Time:    8:00 AM  (Rush hour NOx spike: 336.5 µg/m³)
 Best Time:     4:00 AM  (All pollutants 48–76% below average)
 Weather Link:  0.54 correlation between temperature and CO
 Biggest Risk:  NO2 (2.7x WHO limit) + Benzene (carcinogen)
 Root Cause:    Traffic emissions dominate the pollution profile
 Overall Grade: Moderate to Poor
```

---


##  Real-World Relevance — Pakistan Context

These findings are directly applicable to Pakistani cities:
- **Lahore** regularly records AQI above 300 in winter — same traffic-dominated pattern
- **Karachi** faces benzene pollution from old vehicles and industrial zones
- **Rush hour interventions** (odd-even traffic, metro promotion) could reduce NOx by estimated 30–40%
- **Temperature correlation** explains why smog worsens in October–November as temperatures drop and atmospheric inversions intensify

---

##  Tools Used

| Tool | Purpose |
|---|---|
| **Amazon PartyRock** | AI-powered natural language data analysis |
| **AWS Bedrock** | Foundation model powering the analysis |
| **DuckDB (embedded)** | SQL query engine for accurate calculations |
| **UCI ML Repository** | Original dataset source |
| **Kaggle** | Dataset download platform |

---

##  Methodology Note

> A representative sample of 246 hourly readings was analyzed (March 10–20, 2004) covering a complete 10-day continuous recording period capturing weekday/weekend patterns, morning rush hours, afternoon peaks, and nighttime baselines. This sample was used due to platform upload constraints. The full dataset contains 9,358 readings from March 2004 – February 2005.

---

##  Author

**Anam Jafar** — Udacity AI/ML Scholarship Program  
Project: Analyze Data Using AI with PartyRock  
Platform: Amazon PartyRock (AWS Bedrock)

---

*This project was completed as part of the Udacity AI/ML Scholarship Challenge using Amazon PartyRock — demonstrating how AI-powered tools can make complex data analysis accessible without requiring programming expertise.*
