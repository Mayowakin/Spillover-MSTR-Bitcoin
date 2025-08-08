# Bitcoin-MicroStrategy Spillover Analysis

## Overview

This repository contains the empirical analysis code and data for investigating bidirectional return spillover effects between Bitcoin (BTC) and MicroStrategy (MSTR). The research examines how MicroStrategy's corporate Bitcoin adoption strategy fundamentally altered the interconnectedness between these assets using Vector Autoregression (VAR) models and Forecast Error Variance Decomposition (FEVD).

## Research Summary

This study quantifies the bidirectional return spillover effects between Bitcoin and MicroStrategy using a comparative bivariate VAR framework supplemented with Granger causality analyses, impulse response functions, and static and rolling FEVD, the analysis examines daily log returns from January 2018 to March 2025.

## Key Findings

- **Pre-adoption period (2018-2020)**: Minimal spillovers (1.02% Bitcoin→MSTR, 0.17% MSTR→Bitcoin)
- **Post-adoption period (2020-2025)**: Substantial spillovers (24.60% Bitcoin→MSTR, 15.28% MSTR→Bitcoin)
- **Structural transformation**: 24-fold increase in Bitcoin→MSTR spillovers, 90-fold increase in reverse direction
- **Dynamic patterns**: Time-varying spillovers linked to acquisition cycles and market conditions

## Repository Structure

```
├── README.md                           # This file
├── requirements.txt                    # Python dependencies
├── .gitignore                         # Git ignore file
├── notebooks/
│   ├── EDA.ipynb                      # Exploratory Data Analysis
│   ├── Staticspillover_1.ipynb       # Pre-adoption period analysis
│   ├── Staticspillover_2.ipynb       # Post-adoption period analysis
│   ├── Spillover_rolling_windowFEVD.ipynb    # Rolling window analysis
├── data/
│   ├── MSTR-Bitcoin(2018-2025).xlsx   # Full dataset
│   ├── MSTR-Bitcoin(2018-2020).xlsx   # Pre-adoption period
│   ├── MSTR-Bitcoin(2020-2025).xlsx   # Post-adoption period
└── outputs/
    ├── spill_1.csv                    # Pre-adoption analysis output
    ├── spill_2.csv                    # Post-adoption analysis output
    ├── spill_1.xlsx                   # Pre-adoption analysis output
    ├── spill_2.xlsx                   # Post-adoption analysis output
    └── rolling_spillover.xlsx         # Full rolling analysis output
```

## Methodology

### Data
- **Source**: Daily open prices from Refinitiv Eikon
- **Period**: January 2018 - March 2025
- **Assets**: Bitcoin (BTC) and MicroStrategy (MSTR)
- **Returns**: Log returns with temporal alignment adjustments

### Analytical Framework
1. **Stationarity Testing**: Augmented Dickey-Fuller (ADF) tests
2. **VAR Model**: Bivariate VAR(1) specification
3. **Granger Causality**: Directional predictability testing
4. **Impulse Response Functions**: 10-day horizon shock transmission
5. **FEVD Analysis**: Static and rolling window (100-day) spillover quantification

### Key Periods
- **Pre-adoption**: January 2, 2018 - August 7, 2020 (654 observations)
- **Post-adoption**: August 10, 2020 - March 31, 2025 (1,166 observations)

## Getting Started

### Prerequisites
- Python 3.8+
- Jupyter Notebook or JupyterLab
- Required packages (see requirements.txt)

### Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/bitcoin-microstrategy-spillover-analysis.git
cd bitcoin-microstrategy-spillover-analysis
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Launch Jupyter:
```bash
jupyter notebook
```

### Running the Analysis

1. **Start with EDA**: Open `notebooks/EDA.ipynb` for exploratory data analysis
2. **Pre-adoption analysis**: Run `notebooks/Staticspillover_1.ipynb`
3. **Post-adoption analysis**: Run `notebooks/Staticspillover_2.ipynb`
4. **Dynamic analysis**: Execute `notebooks/Spillover_rolling_windowFEVD.ipynb`
5. **Robustness check**: Run `notebooks/Spillover_rolling_windowreordered.ipynb`

## Results Summary

### Static Analysis
| Period | Bitcoin→MSTR | MSTR→Bitcoin | Granger Causality (BTC→MSTR) |
|--------|--------------|--------------|------------------------------|
| Pre-adoption | 1.02% | 0.17% | p = 0.0156 |
| Post-adoption | 24.60% | 15.28% | p < 0.001 |

### Rolling Window Analysis
- **Window size**: 100 days
- **Forecast horizon**: 10 days
- **Key finding**: Time-varying spillovers linked to acquisition cycles and market regimes

## Data Sources

- **Price Data**: Refinitiv Eikon
- **Corporate Actions**: MicroStrategy SEC filings and investor relations

## Methodology References

- Diebold, F. X., & Yilmaz, K. (2012). Better to give than to receive: Predictive directional measurement of volatility spillovers. *International Journal of Forecasting*, 28(1), 57-66.
- Pesaran, H. H., & Shin, Y. (1998). Generalized impulse response analysis in linear multivariate models. *Economics Letters*, 58(1), 17-29.

## Usage

This code is provided for educational and research purposes. Please contact the author before using in other research projects.

## Contact

**Author**: Olumayowa Akinlude 
**Institution**: Dublin City University Business School  
**Program**: Master of Science in Financial Technology and Innovation  
**Supervisors**: Prof. Michael Dowling & Prof. Pawan Kumar

For questions about the research methodology or findings, please refer to the full thesis document.

## Acknowledgments

- Dublin City University Business School
- Supervisors: Prof. Michael Dowling and Prof. Pawan Kumar
- Refinitiv Eikon for data provision

---

**Keywords**: Bitcoin, MicroStrategy, Spillover Effects, VAR Model, FEVD, Cryptocurrency, Financial Econometrics, Corporate Treasury Strategy

