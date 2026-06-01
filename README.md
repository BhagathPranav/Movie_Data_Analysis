# 🎬 Movie Market Dynamics & Audience Sentiment Analysis

[![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Pandas-2.1.0-orange.svg)](https://pandas.pydata.org/)
[![NumPy](https://img.shields.io/badge/NumPy-1.25.2-blueviolet.svg)](https://numpy.org/)
[![Framework](https://img.shields.io/badge/Data_Science-Exploratory_Data_Analysis-success.svg)]()

## 📌 Project Overview & Impact
An end-to-end data engineering and exploratory data analysis (EDA) pipeline built on **10,000+ commercial movie records** sourced from TMDB. The project simulates a production-grade data cleaning and analytics workflow—transforming raw, inconsistent unstructured endpoints into structured metrics to evaluate what drives consumer entertainment engagement.

### 🚀 Key Technical Metrics Achieved:
* **10,000 Product Records** successfully ingested, standardized, and validated.
* **100% Data Integrity** achieved by engineering automated pipelines to resolve structural anomalies, corrupt date strings, and string discrepancies.
* **Skewness Reduction:** Applied logarithmic scaling transformations to highly right-skewed metric fields (`popularity`), preparing variables smoothly for downstream predictive statistical modeling.
* **Dynamic Visualization:** Built **4 comprehensive statistical plots** capturing performance vectors across historical timelines (1950–2025+).

---

## 🛠️ Tech Stack & Architecture
* **Data Core Engine:** Python 3, Pandas (Vectorized DataFrames, Datetime conversion profiles)
* **Numerical Layer:** NumPy (Mathematical transformations, array slice masking, statistical boundary logic)
* **Visualization Engine:** Matplotlib, Seaborn (Statistical distributions, trend charting, heatmaps)

---

## 🏗️ Data Engineering Pipeline & Implementation Details

### 1. Robust Data Cleaning & Standardization
* **Missing Data Imputation:** Programmed logical check-stops mapping missing string records (`overview`) to standardized safe-fallbacks (`"No overview available"`) to maintain zero null values across critical descriptive layers.
* **Datetime Refactoring:** Converted erratic numeric/Unix nanosecond timestamps (e.g., `780278400000000000`) into clean, production-standard ISO `YYYY-MM-DD` data types (`dt.strftime`).
* **Outlier Capping Engine:** Isolated anomalous records within user interaction metrics (`vote_count`) utilizing the Interquartile Range (IQR) method. Implemented an upper-bound clipping system ($Q3 + 1.5 \times IQR$) to retain essential operational data while removing statistical noise.

### 2. NumPy Math & Aggregation Operations
* **Logarithmic Scaling:** Implemented a vectorized $log_{1p}$ transformation via `np.log1p()` on highly skewed audience distribution curves.
* **Matrix Reshaping & Slice Vectorization:** Profiled underlying dataset sub-matrices using multi-dimensional array reshaping (`.reshape(10, 10)`), demonstrating optimal low-level memory layout utilization.
* **Conditional Array Masking:** Segmented audience impact metrics seamlessly using `np.where()` arrays to flag high-performance profiles.

---

## 📊 Exploratory Data Analysis & Strategic Insights

The completed execution layer automatically isolates the following business trends and materializes them into the `/outputs` folder:

1. **Audience Distribution Analysis (`rating_distribution.png`):** A kernel density and histogram plot illustrating user sentiment curves across the platform.
2. **Multi-Variable Correlation Matrix (`correlation_heatmap.png`):** A relational matrix calculating coefficients across release years, velocity scores, and user counts. 
3. **Engagement vs. Sentiment (`popularity_vs_rating.png`):** A scatter plot evaluating if high-volume viewer velocity mathematically shifts median user ratings.
4. **Historical Release Velocity (`movies_over_time.png`):** A historical trend line measuring industry scaling velocities across operational decades.

---

## 📂 Repository Structure
```text
movie-data-analysis/
│
├── data/
│   └── movies.csv                 # Raw source records (10,000 rows x 8 features)
│
├── outputs/                       # Generated production assets
│   ├── cleaned_movies.csv         # Standardized, outlier-capped production dataset
│   ├── rating_distribution.png    # Sentiment distribution visualization
│   ├── correlation_heatmap.png    # Multivariable feature correlation matrix
│   ├── popularity_vs_rating.png   # Engagement distribution vs rating scatter plot
│   └── movies_over_time.png       # Industry output velocity historical trend line
│
├── README.md                      # Technical portfolio documentation
├── requirements.txt               # Locked project dependencies
└── movie_analysis.py              # Main analytics execution pipeline
