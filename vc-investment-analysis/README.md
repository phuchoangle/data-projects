# Crypto VC Investment Intelligence Report

A data-driven analysis of venture capital activity in the blockchain and cryptocurrency sector, covering November 2024 through April 2025.

## Overview

This project analyzes 338 unique funding rounds across 326 crypto projects, involving 1,298 unique investors and $6.9B in total capital deployed. The analysis identifies investment patterns, co-investment relationships, and provides strategic insights for infrastructure startups seeking venture funding.

## Key Findings

- **Blockchain Service, DeFi, and Infrastructure** are the top 3 categories by deal count
- **Seed rounds dominate** by count (40%), while Series A and strategic rounds capture more capital per deal
- The VC landscape is **highly fragmented**: 1,298 investors, but the top 256 account for 50% of all activity
- **Infrastructure** received $416M across 50 deals (14.8% of total), with most deals at Seed stage
- **Co-investment syndicates** are common: top VC pairs frequently invest together, creating predictable fundraising dynamics
- Median deal size is **$5M**, with significant variation by stage and category

---

## Project Structure

```
vc-investment-analysis/
├── README.md
├── .gitignore
├── data/
│   ├── raw/
│   │   └── vcs_investments_raw.csv       # Original dataset (2,379 records)
│   └── processed/
│       ├── vcs_investments_clean.csv     # Cleaned dataset (2,364 records, 32 categories)
│       ├── analysis_summary.json         # Key metrics summary
│       ├── dashboard_data.json           # Pre-computed data for dashboard
│       └── vc_investment_powerbi.xlsx    # Structured dataset for PowerBI (6 sheets)
├── notebooks/
│   └── vc_investment_analysis.ipynb      # Full analysis notebook
├── charts/
│   ├── 01_top_30_active_vcs.png
│   ├── 02_investment_by_category.png
│   ├── 03_monthly_trend.png
│   ├── 04_deal_size_distribution.png
│   ├── 05_stage_analysis.png
│   ├── 06_infrastructure_deep_dive.png
│   ├── 07_coinvestment_heatmap.png
│   ├── 08_vc_specialization.png
│   ├── 09_valuation_analysis.png
│   ├── 10_category_trends.png
│   ├── 11_vc_concentration.png
│   ├── 12_infra_coinvestment_pairs.png
│   └── 13_syndicate_analysis.png
└── reports/
    ├── dashboard.html                    # Interactive HTML dashboard (open in browser)
    ├── vc_investment_report.pptx         # 20-slide executive presentation
    └── powerbi_guide.md                  # Step-by-step PowerBI setup guide
```

---

## Data Collection & Methodology

**Data Source:** Investment data aggregated from Messari and CryptoRank, covering publicly disclosed funding rounds.

**Dataset:** Each row represents an investor-deal pair. A single funding round with 5 investors produces 5 rows, all sharing the same Project, Fundraise, Date, and Category values. This structure enables co-investment analysis.

**Cleaning steps:**
1. Standardized 60+ raw category labels into 32 consistent categories
2. Converted fundraise and pre-valuation from string to numeric (removed comma separators)
3. Dropped 15 rows with missing investor data
4. Assigned categories to 9 uncategorized records based on project research

**Limitations:** Covers publicly disclosed rounds only. Undisclosed or stealth investments are not represented. Some rounds may have additional undisclosed participants.

---

## Analysis Components

### 1. Market Overview
Monthly investment trends, capital allocation by category, deal size distribution, and funding stage analysis.

### 2. VC Intelligence
Top 30 most active VCs, co-investment heatmap, VC concentration curve, and investor specialization by category.

### 3. Infrastructure Deep Dive
Targeted analysis for infrastructure startups: top VCs in the category, co-investment pairs, syndicate patterns, and stage distribution.

### 4. Strategic Recommendations
Actionable insights for C-level decision-making: which VCs to target, how to leverage syndicate dynamics, and how to position for fundraising.

---

## How to Use

### Run the Analysis
```bash
pip install pandas matplotlib seaborn numpy networkx
jupyter notebook notebooks/vc_investment_analysis.ipynb
```

### Interactive Dashboard
Open `reports/dashboard.html` in any modern browser. The dashboard is self-contained (no server required) and includes all charts and data tables.

### PowerBI Dashboard
Open `data/processed/vc_investment_powerbi.xlsx` in PowerBI Desktop. See `reports/powerbi_guide.md` for detailed setup instructions, recommended visuals, DAX measures, and color theme.

### Presentation
Open `reports/vc_investment_report.pptx` in PowerPoint or Google Slides.

---

## Tools & Technologies

- Python (pandas, matplotlib, seaborn, numpy, networkx)
- Chart.js (interactive HTML dashboard)
- PowerBI (via Excel dataset)

---

## Author

**Dr. Phuc Le** | lh.phucc@gmail.com

Ex-Research Lead at Concero — cross-chain interoperability protocol.
