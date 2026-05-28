# PowerBI Dashboard Setup Guide

This guide explains how to use the `vc_investment_powerbi.xlsx` file to build an interactive dashboard in PowerBI.

## Dataset Structure

The Excel workbook contains 6 sheets designed as a star schema for PowerBI:

### Fact Tables

**Deals** (primary fact table)
- Deal_ID, Project, Fundraise_M, Pre_Valuation_M, Val_Multiple, Stage, Category, Date, Month, Quarter, Year
- One row per unique funding round (338 records)

**Deal_Investor_Bridge** (many-to-many bridge)
- Project, Investor, Category, Stage, Date, Fundraise_M
- One row per investor-deal pair (2,364 records)
- Links deals to investors for co-investment analysis

### Dimension / Summary Tables

**Investors** - Investor profiles with deal counts by category and top specialization
**Monthly_Summary** - Pre-aggregated monthly metrics
**Category_Summary** - Pre-aggregated category metrics with valuation multiples
**CoInvestment_Matrix** - Top 20 VC co-investment counts

## Step-by-Step Setup

### 1. Import Data
1. Open PowerBI Desktop
2. Click "Get Data" and select "Excel Workbook"
3. Navigate to `vc_investment_powerbi.xlsx`
4. Select all 6 sheets and click "Load"

### 2. Set Up Relationships
In the Model view, create these relationships:

- **Deal_Investor_Bridge[Project]** to **Deals[Project]** (Many-to-One)
- **Deal_Investor_Bridge[Investor]** to **Investors[Investor]** (Many-to-One)

### 3. Recommended Visuals

**Page 1: Market Overview**
- KPI cards: Total Deals, Total Capital, Active Investors, Median Deal Size
- Stacked bar chart: Monthly capital by category (use Monthly_Summary)
- Horizontal bar chart: Capital by category (use Category_Summary)
- Donut chart: Stage distribution (use Deals table, Stage field)

**Page 2: VC Intelligence**
- Bar chart: Top 20 VCs by Total_Deals (use Investors table)
- Matrix visual: CoInvestment_Matrix sheet (format as heatmap with conditional formatting)
- Table: Investor details with Category breakdown columns

**Page 3: Infrastructure Focus**
- Filter all visuals by Category = "Infrastructure"
- Bar chart: Top infrastructure investors (filter Investors table)
- Stage breakdown for infrastructure deals only
- Table: Infrastructure specialist investors (filter by Infra_Deals > 0, sort by Infra_Deals)

### 4. Formatting
- Use the blue/gray/white color palette:
  - Primary: #1B3A5C
  - Secondary: #2E6B9E
  - Accent: #4A90D9
  - Light: #A8C8E8
  - Background: #F5F7FA
- Font: Segoe UI
- Set page background to #F5F7FA

### 5. Slicers (Filters)
Add these interactive filters:
- Category slicer (dropdown)
- Stage slicer (dropdown)
- Date range slicer (slider)
- Month slicer (for time-series filtering)

## DAX Measures (Optional)

```
Total Capital = SUM(Deals[Fundraise_M])
Deal Count = COUNTROWS(Deals)
Avg Deal Size = AVERAGE(Deals[Fundraise_M])
Median Val Multiple = MEDIAN(Deals[Val_Multiple])
Unique Investors = DISTINCTCOUNT(Deal_Investor_Bridge[Investor])
Infra % = DIVIDE(
    CALCULATE(COUNTROWS(Deals), Deals[Category] = "Infrastructure"),
    COUNTROWS(Deals)
)
```

## Tips

- Use the Deal_Investor_Bridge table when you need to analyze investor-level data alongside deal metrics
- The CoInvestment_Matrix sheet works best as a standalone matrix visual with conditional formatting
- For the heatmap effect, use conditional formatting (background color scale) on the matrix values
- The Investors table already has pre-computed category breakdowns, which avoids complex DAX for basic investor profiling
