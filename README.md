# Chicago Taxi Data Analysis

**Exploratory & Statistical Analysis of Urban Mobility**  
Gustavo Mandujano Rojas

---

## Overview

This project presents an exploratory and statistical analysis of taxi trip data from the city of Chicago (November 2017), enriched with external weather data. The analysis addresses two central questions:

- **Which zones and companies generate the most taxi demand?**
- **Does weather affect trip duration on the Loop → O'Hare route?**

The project is divided into two stages: exploratory data analysis (EDA) and formal hypothesis testing.

---

## Key Findings

### 🏙️ Market Structure
The Chicago taxi market exhibits an oligopolistic structure. Flash Cab leads with a dominant share of trips, followed by Taxi Affiliation Services and Medallion Leasing. The top 3 companies concentrate the majority of the market, while a long tail of small operators perform fewer than 100 trips over the observed period.

### 📍 Demand Geography
Taxi demand is heavily concentrated in downtown Chicago. The top destination neighborhoods are:

| Rank | Neighborhood | Description |
|------|-------------|-------------|
| 1 | **Loop** | Central financial district |
| 2 | **River North** | Restaurants, galleries, nightlife |
| 3 | **Streeterville** | Tourist zone near Lake Michigan |
| 4 | **West Loop** | Business and fashion district |
| 5 | **O'Hare** | International airport |

The top 10 neighborhoods account for the vast majority of all completed trips, while peripheral residential areas show significantly lower demand.

### 🌧️ Hypothesis Test — Weather Impact on Trip Duration

**Hypothesis:**
- **H₀:** Average trip duration does NOT change on rainy Saturdays (μ_good = μ_bad)
- **H₁:** Average trip duration DOES change on rainy Saturdays (μ_good ≠ μ_bad)
- **Test:** Two-tailed Student's t-test | Significance level: α = 0.05

**Assumptions verified:**
- Sample sizes n ≥ 30 → Central Limit Theorem applies
- Homogeneous variances confirmed via Levene's test

**Result:** The test yielded a statistically significant result (p-value < 0.05), leading to **rejection of H₀**. There is sufficient statistical evidence that weather conditions significantly affect trip duration on the Loop → O'Hare route on Saturdays.

---
<!--
## Project Structure

```
.
├── notebooks/
│   └── notebook_Proyecto.ipynb     # Full analysis: EDA + hypothesis testing
├── data/
│   └── README.md                   # Data sources and download instructions
├── figures/                        # Exported visualizations
└── requirements.txt
```

---
-->
## Methodology

### Data Sources
- **Chicago Taxi Trips** — Trip records including pickup/dropoff zones, duration, and company (November 15–16, 2017)
- **Weather Data** — Historical weather conditions integrated by timestamp to study climate effects on trip duration

### Techniques Applied
- Exploratory Data Analysis (EDA) with `pandas` and `numpy`
- Market concentration analysis (oligopoly structure, Pareto distribution)
- Geospatial demand aggregation by Chicago community areas
- Statistical assumption testing: Shapiro-Wilk (normality), Levene (variance homogeneity)
- Two-tailed Student's t-test for independent samples
- Effect size calculation (Cohen's d) and 95% confidence intervals
- Data visualization with `matplotlib` and `seaborn`

---

## Visualizations

Charts generated in this project include:
- Horizontal bar chart: Top 15 taxi companies by trip volume
- Horizontal bar chart: Top 10 neighborhoods by average completed trips
- Histogram: Trip duration distribution by weather condition (Loop → O'Hare)
- Box plot & Violin plot: Duration comparison across weather groups

*(Run the notebook to reproduce all visualizations)*

---

## Installation & Usage

```bash
# Clone the repository
git clone https://github.com/GusRojas/chicago-taxi-analysis.git
cd chicago-taxi-analysis


# Launch Jupyter
jupyter notebook
```

> ⚠️ Note: Raw data files are not included due to size. See `data/README.md` for download instructions.

---

## Technologies

`Python` `pandas` `numpy` `scipy` `matplotlib` `seaborn` `Jupyter Notebook`

---

## Author

**Gustavo Mandujano Rojas**  
📧 [gusm.rojas@gmail.com](mailto:gusm.rojas@gmail.com)  
💼 [linkedin.com/in/gustavo-mandujano-rojas](https://www.linkedin.com/in/gustavo-mandujano-rojas/)
