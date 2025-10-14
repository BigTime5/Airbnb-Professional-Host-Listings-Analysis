# 🏠 Airbnb Professional Host Market Analysis

<div align="center">

![Python](https://img.shields.io/badge/python-3.8+-blue.svg)
![Pandas](https://img.shields.io/badge/pandas-latest-green.svg)
![Plotly](https://img.shields.io/badge/plotly-interactive-red.svg)
![Status](https://img.shields.io/badge/status-complete-success.svg)

**A comprehensive data-driven analysis of professional host trends across 6 major global cities**

[Overview](#-overview) • [Key Findings](#-key-findings) • [Methodology](#-methodology) • [Visualizations](#-visualizations) • [Technologies](#-technologies)

---

</div>

## 🎯 Overview

This project delivers a **strategic market analysis** for an international real estate firm, examining the growing presence of professional Airbnb hosts (defined as hosts with 5+ listings) across six diverse global markets. Through rigorous data analysis of **103,817 listings**, we uncover critical insights into pricing strategies, market share dynamics, and operational patterns that distinguish professional operators from individual hosts.

### 🌍 Cities Analyzed
- **Austin** (11,269 listings)
- **Bangkok** (17,431 listings)
- **Buenos Aires** (17,671 listings)
- **Cape Town** (16,891 listings)
- **Istanbul** (22,539 listings)
- **Melbourne** (18,016 listings)

---

## 🔥 Key Findings

### 💼 Professional Host Market Dominance

| Metric | Finding |
|--------|---------|
| **Overall Market Share** | 30.8% of all listings (31,691 properties) |
| **Highest Penetration** | Bangkok (45.8%) - Nearly half of market |
| **Lowest Penetration** | Austin (23.9%) - Most individual-host friendly |
| **Price Premium** | Professional hosts charge 22.3% more on average |

### 💰 Pricing Intelligence
```
Most Expensive City:    Buenos Aires ($2,981 median)
Most Affordable City:   Melbourne ($110 median)
Price Range:            $1 - $15,432
Professional Premium:   +37% in Austin to +35.8% in Istanbul
```

### 🏨 Operational Patterns

- **Room Type Preference**: 70.4% of professional listings are entire homes vs. 65.1% for individuals
- **Hotel Rooms**: 4.7% of professional portfolio vs. only 0.8% for individuals (6x concentration)
- **Short-term Dominance**: 83.5% of all listings target 1-6 night stays
- **Long-term Market**: Only 6.1% focus on 30+ night stays (highest in Austin & Bangkok at 12.9%)

---

## 🔬 Methodology

### Data Pipeline
```
📥 Data Collection → 🧹 Cleaning → 🔍 Analysis → 📊 Visualization → 📋 Reporting
```

#### 1️⃣ **Data Collection**
- **Source**: InsideAirbnb datasets (6 CSV files)
- **Volume**: 103,817 initial listings
- **Attributes**: 19 features including price, location, reviews, host information

#### 2️⃣ **Data Cleaning & Preprocessing**
- ✅ Handled missing values (33.6% in review columns, 100% in neighborhood_group)
- ✅ Removed extreme price outliers (top 1% and $0 listings)
- ✅ Created binary indicators (`has_reviews`, `has_license`)
- ✅ Converted date columns to datetime objects
- ✅ Retained **99.0%** of original data (102,767 listings)

#### 3️⃣ **Feature Engineering**
- **Professional Host Flag**: `calculated_host_listings_count >= 5`
- **Price Categories**: Budget, Moderate, Premium, Luxury, Ultra-luxury
- **Stay Types**: Short-term (1-6), Medium-term (7-29), Long-term (30+)
- **Host Categories**: 7 tiers from "1 listing" to "50+ listings"

#### 4️⃣ **Analysis Framework**
- Comparative statistics (professional vs. individual hosts)
- Geographic price distribution analysis
- Room type preference patterns
- Minimum stay requirement trends
- Neighborhood-level pricing insights

---

## 📊 Visualizations

### Interactive Elements Created

| Visualization Type | Description | Files Generated |
|-------------------|-------------|-----------------|
| **Geographic Maps** | Interactive Folium maps with price-coded markers | 6 HTML files (one per city) |
| **Price Distributions** | Box plots, bar charts comparing cities & room types | Matplotlib figures |
| **Professional Analysis** | Market share, pricing comparisons, portfolio composition | Multi-panel dashboards |
| **Neighborhood Insights** | Top 10 expensive neighborhoods per city | Statistical tables |

### Sample Outputs

#### Professional Host Market Share by City
```
Bangkok       ████████████████████████████████████████████ 45.8%
Istanbul      ███████████████████████████████████ 35.6%
Cape Town     ███████████████████████████ 27.4%
Melbourne     ████████████████████████ 24.6%
Buenos Aires  ████████████████████████ 24.1%
Austin        ███████████████████████ 23.9%
```

#### Price Comparison: Professional vs. Individual Hosts
```
Austin:        Professional $370  |  Individual $270  |  +37.0% 📈
Istanbul:      Professional $811  |  Individual $597  |  +35.8% 📈
Melbourne:     Professional $205  |  Individual $163  |  +25.6% 📈
Cape Town:     Professional $2168 |  Individual $1793 |  +21.0% 📈
Buenos Aires:  Professional $4353 |  Individual $3559 |  +22.3% 📈
Bangkok:       Professional $1580 |  Individual $1709 |  -7.5% 📉 (unique!)
```

---

## 🛠 Technologies

### Core Libraries
```python
# Data Manipulation & Analysis
pandas==1.5.3          # Data processing powerhouse
numpy==1.24.3          # Numerical computing

# Visualization
matplotlib==3.7.1      # Static plotting
seaborn==0.12.2        # Statistical visualizations
plotly==5.14.1         # Interactive charts
folium==0.14.0         # Geographic mapping

# Utilities
warnings               # Error handling
datetime               # Date/time processing
os                     # File system operations
```

### Development Environment
- **Language**: Python 3.8+
- **Platform**: Jupyter Notebook
- **Data Format**: CSV (6 files, ~100MB total)

---

## 📁 Project Structure
```
airbnb-professional-host-analysis/
│
├── data/
│   ├── listings_austin.csv
│   ├── listings_bangkok.csv
│   ├── listings_buenos_aires.csv
│   ├── listings_cape_town.csv
│   ├── listings_istanbul.csv
│   └── listings_melbourne.csv
│
├── output/
│   ├── map_austin.html
│   ├── map_bangkok.html
│   ├── map_buenos_aires.html
│   ├── map_cape_town.html
│   ├── map_istanbul.html
│   └── map_melbourne.html
│
├── analysis_notebook.ipynb          # Main analysis notebook
└── README.md                         # This file
```

---

## 🎓 Key Insights for Stakeholders

### For Real Estate Investors
1. **Bangkok presents the highest professional host opportunity** with 45.8% market share
2. **Professional hosts command significant price premiums** across all markets except Bangkok
3. **Entire home properties are the dominant asset class** (66.7% of market)

### For Market Analysts
1. **Short-term rentals dominate** (83.5%) - regulatory risks to consider
2. **Long-term rental markets are underdeveloped** (6.1%) - potential opportunity
3. **Geographic price variation is extreme** - Buenos Aires is 27x more expensive than Melbourne

### For Policy Makers
1. **Professional hosts control nearly 1/3 of listings** - potential housing market impact
2. **Hotel room listings concentrated with professionals** - blurring of STR/hotel boundaries
3. **Market maturity varies significantly** - one-size-fits-all regulation may not work

---

## 📈 Statistical Highlights

| Metric | Value |
|--------|-------|
| **Total Unique Hosts** | 58,930 |
| **Average Listings per Host** | 9.09 |
| **Hosts with 50+ Listings** | 4,128 (4.0% of listings) |
| **Listings with Reviews** | 67,884 (66.1%) |
| **Average Reviews per Listing** | 18.39 |
| **Date Range** | June 2010 - November 2021 |
| **Data Completeness** | 99.0% after cleaning |

---

## 🔄 Reproducibility

### Prerequisites
```bash
pip install pandas numpy matplotlib seaborn plotly folium
```

### Running the Analysis
```python
# 1. Clone the repository
# 2. Place CSV files in /home/ directory
# 3. Run all cells in analysis_notebook.ipynb
# 4. View outputs in /output/ directory
```

### Expected Runtime
- Data loading: ~30 seconds
- Cleaning & preprocessing: ~1 minute
- Analysis & visualization: ~3 minutes
- **Total: ~5 minutes** on standard hardware

---

## 💡 Future Enhancements

- [ ] Time-series analysis of professional host growth
- [ ] Predictive modeling for price optimization
- [ ] Sentiment analysis of review text
- [ ] Regulatory compliance impact assessment
- [ ] Competitive analysis vs. traditional hotels
- [ ] Seasonal trend decomposition

---

## 📝 License & Attribution

**Data Source**: [Inside Airbnb](http://insideairbnb.com/) - Community-driven data compilation  
**Analysis**: Proprietary analysis for international real estate firm  
**License**: Data usage complies with Inside Airbnb's Creative Commons CC0 1.0 Universal License

---

## 👤 Author

**Phinidy George | Business Intelligence Specialist**  
Specializing in real estate market analytics and strategic insights

---

<div align="center">

### 🌟 Analysis Complete | Insights Delivered | Value Created 🌟

**Built with precision. Analyzed with rigor. Presented with clarity.**

</div>
