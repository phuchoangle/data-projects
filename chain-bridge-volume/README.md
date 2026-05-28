# Cross-Chain Bridge Volume Analysis

**A comprehensive data analysis of cross-chain bridge volumes across 92 blockchain networks and 76 bridge/messaging protocols, covering H1 2025.**

This project was built during my work as a Research Lead at [Concero](https://concero.io), a cross-chain interoperability protocol. The analysis supports C-level strategic decision-making by answering three core questions: where is bridge volume concentrated, how is the market structure shifting, and what is the fee revenue opportunity.

---

## Key Findings

The cross-chain bridge market processed **$128.3B** in H1 2025 across 76 protocols. The market is highly concentrated, with the top 3 chains (Ethereum, Arbitrum, Avalanche) capturing 77-83% of all volume. Messaging protocols (LayerZero, Circle CCTP, Wormhole, Hyperlane) now handle 43.5% of total volume, signaling a structural shift from purpose-built bridges to generalized messaging infrastructure.

At a competitive 3 bps fee rate, the total addressable fee revenue is approximately $77M annualized. Arbitrum is the fastest-growing major chain (+36.9% Q2 vs Q1), while Sui and Blast are declining sharply.

---

## Project Structure

```
chain-bridge-volume/
├── README.md
├── .gitignore
├── data/
│   ├── raw/                          # Original source datasets
│   │   ├── bridge-chains.csv         # Daily net bridge volume for 92 chains
│   │   └── bridge-and-messaging-volumes.csv  # Daily volume for 76 protocols
│   └── processed/                    # Cleaned outputs and Power BI dataset
│       ├── bridge_volumes_2025_processed.csv
│       ├── messaging_volumes_2025.csv
│       ├── monthly_messaging_volumes_2024_2025.csv
│       ├── bridge_volume_distribution.csv
│       └── powerbi_dataset.xlsx      # Multi-sheet Excel workbook for Power BI
├── notebooks/
│   └── chain-bridge-volume-analysis.ipynb    # Main analysis notebook
├── charts/                           # All visualizations (PNG, 300 DPI)
│   ├── 01_chain_volume_distribution.png
│   ├── 02_net_capital_flows.png
│   ├── 03_monthly_chain_trends.png
│   ├── 04_protocol_rankings.png
│   ├── 05_messaging_vs_bridge.png
│   ├── 06_messaging_deep_dive.png
│   ├── 07_market_concentration.png
│   ├── 08_chain_growth.png
│   ├── 09_volume_volatility.png
│   ├── 10_fee_revenue_modeling.png
│   └── 11_monthly_fee_trends.png
└── reports/
    ├── dashboard.html                # Interactive HTML dashboard (open in browser)
    ├── dashboard_data.json           # Data backing the dashboard
    └── bridge-volume-analysis-h1-2025.pptx  # Executive presentation (15 slides)
```

---

## Deliverables

### Interactive Dashboard
Open `reports/dashboard.html` in any browser. No server or dependencies required. The dashboard includes executive KPIs, chain volume analysis, protocol rankings, market concentration metrics, growth analysis, and fee revenue modeling. Built with Chart.js on a green/gray/white professional palette.

### Executive Presentation
`reports/bridge-volume-analysis-h1-2025.pptx` contains 15 slides covering the executive summary, methodology, chain and protocol analysis, market concentration, growth rates, fee modeling, strategic recommendations, risk factors, and a methodology appendix.

### Power BI Dataset
`data/processed/powerbi_dataset.xlsx` is a multi-sheet Excel workbook ready for Power BI import. It includes daily chain volumes, daily protocol volumes, monthly summaries, market concentration (HHI), growth analysis, messaging vs bridge split, fee revenue modeling scenarios, net capital flows, and a setup instructions sheet.

---

## Analysis Sections

**1. Data Collection and Methodology** -- Sources (DefiLlama, Dune Analytics, CoinGecko), data coverage, calculation methods, and HHI concentration measurement.

**2. Chain-Level Volume Analysis** -- Top 10 chains by total volume, net capital flow direction (which chains are gaining or losing capital), and monthly trends.

**3. Bridge and Messaging Protocol Analysis** -- Protocol rankings with messaging vs bridge distinction, volume split analysis, and messaging protocol deep dive showing LayerZero, Circle CCTP, Wormhole, and Hyperlane trends.

**4. Market Concentration** -- HHI index tracking, top 3 chain market share over time, confirming the market remains highly concentrated throughout H1 2025.

**5. Growth and Trend Analysis** -- Q2 vs Q1 chain growth rates, emerging and declining chains, daily volume volatility with moving averages.

**6. Fee Revenue Modeling** -- Scenario analysis at 1-10 bps fee rates, bridge vs messaging fee split, monthly fee trends, and annualized projections.

**7. Strategic Recommendations** -- Actionable insights covering market positioning, messaging protocol opportunity, growth targets, revenue sizing, and risk factors.

---

## Data Sources

| Source | Description | Usage |
|--------|-------------|-------|
| DefiLlama | Aggregated cross-chain bridge volumes | Primary data (chain volumes, protocol volumes) |
| Dune Analytics | On-chain transaction data | Validation and cross-referencing |
| CoinGecko / CoinMarketCap | Market data | Stablecoin context |

---

## How to Run

**Prerequisites:** Python 3.8+, pandas, numpy, matplotlib, seaborn

```bash
pip install pandas numpy matplotlib seaborn
```

**Run the notebook:**
```bash
cd notebooks/
jupyter notebook chain-bridge-volume-analysis.ipynb
```

**View the dashboard:**
Open `reports/dashboard.html` in any web browser.

**Power BI:**
Open `data/processed/powerbi_dataset.xlsx` in Power BI Desktop. See the "PowerBI Instructions" sheet for setup guide.

---

## Tools and Technologies

Python (pandas, numpy, matplotlib, seaborn), Jupyter Notebook, Chart.js, HTML/CSS, PptxGenJS

---

## Author

**Dr. Phuc Le** | lh.phucc@gmail.com

Ex-Research Lead at Concero — cross-chain interoperability protocol.

This analysis was completed as part of strategic research for Concero's cross-chain interoperability protocol. The work demonstrates skills in data collection, exploratory analysis, market research, visualization design, and translating data into strategic recommendations for executive stakeholders.
