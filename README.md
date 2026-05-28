# Data Analysis Portfolio

A collection of data analysis projects focused on the blockchain and cryptocurrency ecosystem. Each project follows a consistent structure: raw data → cleaning → analysis → visualizations → interactive dashboard and executive presentation.

---

## Projects

### 1. [Cross-Chain Bridge Volume Analysis](./chain-bridge-volume/)
Analysis of $128.3B in cross-chain bridge volume across 92 chains and 76 protocols in H1 2025. Covers market concentration, messaging vs bridge protocol split, chain growth rates, and fee revenue modeling.

**Tools:** Python (pandas, matplotlib, seaborn), Chart.js, Power BI

---

### 2. [Blockchain Interoperability Market Analysis](./interop-market/)
Market sizing study of the blockchain interoperability landscape. Quantifies the coverage gap between 498 blockchain platforms and the 5 major interoperability providers (LayerZero, Wormhole, Hyperlane, Axelar, Chainlink CCIP), with growth projections to 2027.

**Tools:** Python (pandas, matplotlib, seaborn), Chart.js, Power BI

---

### 3. [Crypto VC Investment Intelligence](./vc-investment-analysis/)
Analysis of 338 funding rounds and $6.9B in capital deployed across the crypto sector (Nov 2024 – Apr 2025). Maps VC co-investment networks, category trends, and stage dynamics to inform fundraising strategy.

**Tools:** Python (pandas, matplotlib, seaborn, networkx), Chart.js, Power BI

---

## Project Structure Convention

All projects follow the same folder layout:

```
project-name/
├── README.md           # Project overview, findings, instructions
├── .gitignore
├── data/
│   ├── raw/            # Original, unmodified source data
│   └── processed/      # Cleaned CSVs, summary JSONs, Power BI Excel
├── notebooks/          # Jupyter notebooks (main analysis)
├── charts/             # All chart exports (PNG, 300 DPI)
└── reports/
    ├── dashboard.html  # Self-contained interactive dashboard
    └── *.pptx          # Executive presentation
```

---

## Author

**Dr. Phuc Le** | lh.phucc@gmail.com

Ex-Research Lead at [Concero](https://concero.io) — cross-chain interoperability protocol.
