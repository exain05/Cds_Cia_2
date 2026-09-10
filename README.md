## Global Food Price & Commodity Market Analysis (2019–2026)

## Overview

This project analyzes global food-price data from the **World Food Programme (WFP)** to track how commodity prices shifted before, during, and after the COVID-19 pandemic.

By building a pipeline to clean, aggregate, and visualize the data, the analysis aims to answer one central question: **Did global food prices return to their pre-COVID baseline, or did pandemic-era shocks result in a persistently higher price level?**

## Project Objectives

* **Establish a Baseline:** Use 2019 pricing as a pre-COVID standard.
* **Track the Shock:** Measure price changes during the COVID period and the major post-COVID price increase.
* **Analyze Granular Trends:** Compare price fluctuations across different countries, specific commodities, and food categories.
* **Evaluate Market Types:** Contrast price behavior between retail and wholesale markets.
* **Identify Volatility:** Identify commodities with the highest price levels and the most extreme price volatility.
* **Uncover Seasonality:** Analyze monthly and seasonal price patterns across the calendar year.

## The Dataset

* **Source:** World Food Programme (WFP) – Global Food Prices
* **Coverage:** 2019–2026 (2026 contains partial-year data)
* **Scope:** Country-level observations across 94 countries and 760 distinct commodities.
* **Volume:** Approximately 2.94 million observations with valid USD prices used for the primary analysis.

## Methodology & Preprocessing

To ensure reliable analysis, eight separate yearly WFP datasets were merged and cleaned through a dedicated preprocessing pipeline.

* **Filtering:** Removed non-food observations to maintain focus on food commodities.
* **Standardization:** Parsed raw dates into proper datetime objects and extracted year and month variables for analysis.
* **Price Validation:** Removed records with negative or zero local-currency values.
* **Handling Missing Data:** Missing USD prices were not artificially estimated, avoiding potentially inaccurate exchange-rate assumptions. Only records with valid `usdprice > 0` were retained for the primary USD-based analysis.
* **Metric Selection:** The analysis primarily uses the **median** rather than the mean price because the median is less affected by extreme price observations and outliers.

## Key Findings

* **The Post-COVID Surge:** The global median food price increased from **$0.92 in 2019** to **$1.25 in 2022**, representing a **35.9% increase** from the 2019 baseline.
* **A Higher Price Level:** Although prices moderated slightly in recent years, remaining around **$1.22–$1.23 between 2024 and 2026**, they have not returned to the 2019 level. This suggests that food prices remained at a higher level following the major post-COVID shock.
* **Mean vs. Median:** The mean price remains higher than the median across several years, indicating the presence of high-value observations and supporting the use of the median as a more robust measure of typical observed prices.

## Visualizations

The analysis notebook presents the findings as a progressive data story using interactive **Plotly** visualizations, including:

* Global median food-price trends.
* Global food-price changes indexed to **2019 = 100**.
* Year-over-year percentage changes.
* Country-level comparisons of price increases and decreases.
* Country-year heatmaps showing price intensity.
* Category-level treemaps and price comparisons.
* Retail versus wholesale price trends.
* Commodity-level price increases and volatility.
* Monthly trends and seasonal price patterns.

## Technologies Used

* **Python** – Main programming language.
* **Pandas** – Data cleaning, transformation, aggregation, and analysis.
* **NumPy** – Numerical operations.
* **Plotly** – Interactive data visualization.
* **Jupyter Notebook** – Data analysis and presentation environment.

## Repository Structure

```text
Global-Food-Price-Analysis/
│
├── README.md
├── requirements.txt
├── .gitignore
│
├── notebooks/
│   ├── 01_Data_Preprocessing_2019_2026.ipynb
│   └── 02_Global_Food_Price_Analysis.ipynb
│
├── data/
│   ├── raw/         # Raw WFP CSV files, ignored by git
│   └── processed/   # Generated processed dataset, ignored by git
│
└── outputs/         # Generated analysis outputs
