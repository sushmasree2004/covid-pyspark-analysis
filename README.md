#  OVID-19 Global Analytics Pipeline — PySpark

A complete end-to-end **Big Data analytics pipeline** built with **PySpark** to analyze global COVID-19 trends using real-world datasets. This project covers data ingestion, cleaning, transformation, aggregation, time-series analysis, and visualization.

---

##  Project Overview

During the COVID-19 pandemic, governments and healthcare organizations needed quick access to reliable insights. This project simulates how a real-world analytics team processes pandemic data for reporting and decision-making using a scalable PySpark pipeline.

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| **PySpark** | Large-scale data processing |
| **Python** | Additional scripting |
| **Spark SQL** | Analytical queries |
| **Matplotlib** | Data visualization |
| **Plotly** | Interactive geo visualizations |
| **Parquet / CSV** | Output storage formats |
| **Jupyter Notebook** | Development environment |
| **VS Code** | Code editor |

---

## 📂 Project Structure

```
CovidAnalysis/
├── covid.ipynb              # Main analysis notebook
├── data/                    # Input datasets
│   ├── full_grouped.csv
│   ├── covid_19_clean_complete.csv
│   ├── country_wise_latest.csv
│   ├── day_wise.csv
│   ├── usa_county_wise.csv
│   └── worldometer_data.csv
└── output/                  # Generated outputs
    ├── top_countries.csv
    ├── region_summary.csv
    ├── daily_trends.csv
    ├── mortality_report.csv
    ├── recovery_report.csv
    ├── top_countries.parquet
    ├── region_summary.parquet
    └── covid_dashboard.png
```

---

## 📊 Datasets Used

All datasets sourced from [Kaggle - Corona Virus Report](https://www.kaggle.com/datasets/imdevskp/corona-virus-report)

| Dataset | Description |
|---|---|
| `full_grouped.csv` | Daily country-level COVID trends |
| `covid_19_clean_complete.csv` | Location-level historical data |
| `country_wise_latest.csv` | Latest country statistics |
| `day_wise.csv` | Global day-wise trends |
| `usa_county_wise.csv` | US county-level data |
| `worldometer_data.csv` | Population and global COVID stats |

---

## 🔧 Modules & Tasks

### Module 1: Data Loading & Schema Handling
- ✅ Loaded all 6 CSV files into PySpark DataFrames
- ✅ Inferred schema and printed column types
- ✅ Counted rows in each dataset

### Module 2: Data Cleaning
- ✅ Handled missing `Province/State` values → replaced with "Unknown"
- ✅ Standardized country names (US → United States, Korea, South → South Korea)
- ✅ Removed duplicate Country + Date records

### Module 3: Aggregation
- ✅ Top 10 countries by total confirmed cases
- ✅ Top 10 countries by death rate
- ✅ WHO Region-wise total cases, deaths, recoveries

### Module 4: Time-Series Analysis
- ✅ Daily global new cases trend
- ✅ Daily death growth percentage using window functions
- ✅ Monthly COVID case growth

### Module 5: Window Functions
- ✅ Top 5 most affected countries per WHO Region using `dense_rank()`
- ✅ Country-wise daily case increase using `lag()`

### Module 6: Join Operations
- ✅ Joined `country_wise` + `worldometer` datasets
- ✅ Found countries with large data mismatches between sources
- ✅ Population vs total cases — infection rate analysis

### Module 7: Geographic Analysis
- ✅ USA state-wise case distribution
- ✅ Latitude-Longitude based case cluster visualization

### Module 8: Advanced Analytics
- ✅ Recovery rate analysis — best and worst countries
- ✅ Active case burden analysis — high risk countries
- ✅ Pandemic peak identification — dates with max cases and deaths

### Module 9: Feature Engineering
- ✅ Severity category classification:
  - 🟢 Low → < 10K cases
  - 🟡 Medium → 10K–100K cases
  - 🟠 High → 100K–1M cases
  - 🔴 Critical → > 1M cases

### Module 10: Final Pipeline
- ✅ End-to-end pipeline: Extract → Clean → Standardize → Join → Analyze → Export
- ✅ Outputs saved as CSV and Parquet
- ✅ Final dashboard visualization generated

---

## 💡 Key Insights

- 🌍 **Most Affected Country** → United States (4.3M+ confirmed cases)
- 💀 **Highest Death Rate** → Yemen (29%+ death rate)
- 💚 **Best Recovery Rate** → Countries in Eastern Mediterranean region
- 🌐 **Most Affected WHO Region** → Americas
- 📈 **Pandemic Peak** → Cases peaked in late July–August 2020
- ⚠️ **25 countries** showed significant data discrepancies between sources

---

## ⚙️ Setup & Installation

### Prerequisites
- Python 3.13+
- Java JDK 11+

### Installation

```bash
# Install required packages
python -m pip install pyspark matplotlib plotly pandas notebook ipykernel
```

### Running the Project

1. Clone the repository:
```bash
git clone https://github.com/sushmasree2004/covid-pyspark-analysis.git
cd covid-pyspark-analysis
```

2. Download datasets from [Kaggle](https://www.kaggle.com/datasets/imdevskp/corona-virus-report) and place in `data/` folder

3. Open the notebook:
```bash
jupyter notebook covid.ipynb
```

4. Run all cells in order

---

## 📈 Visualizations Generated

- Bar chart → Top 10 countries by confirmed cases
- Horizontal bar chart → Top 10 countries by death rate
- Pie chart → WHO Region-wise case distribution
- Line chart → Daily global new cases trend
- Line chart → Daily death growth percentage
- Line chart → Monthly COVID case growth
- Grouped bar charts → Top 5 countries per WHO region
- Comparison bar chart → Country Wise vs Worldometer data
- Scatter plot → Population vs total cases
- Bar charts → USA state-wise distribution
- Geo scatter plot → Global case clusters by lat/long
- Best vs Worst recovery rate charts
- Active vs Recovered case comparison
- Peak markers on case/death trend charts
- Pie chart → Severity category distribution
- Final dashboard → 6-chart combined view

---

## 🔑 Key PySpark Concepts Used

- `SparkSession` — Entry point for PySpark
- `inferSchema` — Automatic data type detection
- `fillna()` / `dropna()` — Null handling
- `dropDuplicates()` — Duplicate removal
- `groupBy()` + `agg()` — Aggregations
- `Window.partitionBy()` — Window functions
- `dense_rank()` — Ranking within groups
- `lag()` — Accessing previous row values
- `join()` — Multi-dataset joins
- `when().otherwise()` — Conditional logic
- `to_date()`, `year()`, `month()` — Date operations

---

## 👩‍💻 Author

**Sushma Sree**
- GitHub: [@sushmasree2004](https://github.com/sushmasree2004)

---

## 📄 License

This project is for educational purposes as part of an internship data analytics training program.
