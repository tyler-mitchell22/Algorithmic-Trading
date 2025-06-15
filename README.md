# Algorithmic Trading Strategies

## Performance Highlights 🚀
- **24.3% CAGR** over 10+ years (2013-2023)
- **20.2% annual alpha** vs S&P 500
- **749% total return** since inception
- **Maximum drawdown: 19%** - well-controlled risk
- **Sharpe ratio: 0.16** (inception), 0.21 (3-year)

## Repository Structure

### 📊 [Python Buffer Strategy](./python-buffer-strategy/)
Buffer-based momentum strategy with quarterly rebalancing and optimized turnover control.

**Key Features:**
- 40% improvement buffer to reduce unnecessary trades
- Quarterly rebalancing frequency
- PostgreSQL integration for production deployment
- Comprehensive transaction cost modeling

### 📈 [R Momentum Risk Adjusted Strategy](./r-risk-adjusted/)
Monthly rebalancing momentum strategy with comprehensive risk analytics.

**Key Features:**
- Monthly portfolio updates
- SQLite database integration
- Advanced performance metrics (Sortino, Calmar, Alpha/Beta)
- Interactive visualization with dygraphs

### 📋 [Performance Analysis](./performance-analysis/)
Comparative analysis and visualization of strategy performance vs benchmarks.

## Strategy Methodology

### Core Approach
Both implementations use **risk-adjusted momentum** as the primary factor:
- **12-month momentum** minus **1-month mean reversion**
- **Normalized by 12-month volatility** for risk adjustment
- **Top 10 stock selection** from S&P 500 universe
- **Rank-weighted portfolio construction**

### Key Differences Between Implementations
| Feature | Python Version | R Version |
|---------|---------------|-----------|
| Rebalancing | Quarterly (3 months) | Monthly |
| Buffer System | 40% improvement threshold | None |
| Database | PostgreSQL | SQLite |
| Weighting | Rank-based with buffer logic | Equal-weighted top 10 |
| Transaction Costs | 0.1% per trade | Modeled |

## Investment Universe
- **S&P 500 constituents** with complete data from 2010+
- **Market cap > $1B** and **price > $5** filters applied
- **503 total stocks** in current universe
- Survivorship bias acknowledged but mitigated through robust backtesting

## Risk Management
- **Maximum 19% drawdown** over 10+ year period
- **Diversified momentum exposure** across sectors
- **Transaction cost optimization** through buffer mechanisms
- **Volatility-adjusted position sizing**

## Technology Stack
- **Languages:** Python, R
- **Databases:** PostgreSQL, SQLite
- **Libraries:** pandas, numpy, yfinance, tidyquant, dygraphs
- **Visualization:** matplotlib, ggplot2, interactive dashboards

## Key Performance Metrics

### Long-term Performance (2013-2023)
- **CAGR:** 24.3%
- **Total Return:** 749%
- **Alpha:** 20.2% annually
- **Beta:** 0.69 (inception)
- **Maximum Drawdown:** -19.1%
- **Volatility:** 54.9% (annualized)

### Recent Performance (3-year)
- **CAGR:** 60.0%
- **Alpha:** 67.0% annually  
- **Beta:** -0.10 (market neutral behavior)
- **Maximum Drawdown:** -15.0%
- **Sharpe Ratio:** 0.21

## Implementation Notes

### Data Requirements
- Historical monthly price data for S&P 500 stocks
- Minimum 12 months of data for momentum calculations
- Clean, survivorship-bias-aware dataset

### Key Innovations
1. **Dual-timeframe momentum** (12M trend - 1M mean reversion)
2. **Volatility normalization** for risk-adjusted signals
3. **Buffer mechanism** to optimize turnover vs performance
4. **Production-ready database integration**
5. **Comprehensive performance attribution**

## Getting Started

### Python Implementation
```bash
cd python-momentum-strategy
pip install pandas numpy matplotlib yfinance psycopg2 sqlalchemy
python momentum_etf.py
```

### R Implementation
```r
setwd("r-momentum-strategy")
install.packages(c("tidyquant", "BatchGetSymbols", "dygraphs", "RSQLite"))
source("momentum_etf.R")
```

## Future Research Areas
- **Multi-asset momentum** (bonds, commodities, international)
- **Regime detection** for adaptive parameters
- **Machine learning** factor selection
- **ESG-constrained** momentum strategies
- **Options overlay** for downside protection

## Academic Foundation
This work builds on established academic research in momentum investing:
- Jegadeesh & Titman (1993) - Cross-sectional momentum
- Asness, Moskowitz & Pedersen (2013) - Value and momentum everywhere
- Novy-Marx (2012) - Intermediate-term momentum

## Risk Disclaimers
- **Past performance does not guarantee future results**
- **High volatility strategy** - suitable for risk-tolerant investors
- **Survivorship bias** present in historical backtests
- **Transaction costs** may vary significantly in practice
- **Market conditions** can change, affecting momentum efficacy

## Contact & Collaboration
Interested in discussing systematic momentum strategies or quantitative finance applications? Feel free to reach out!

**Challenge:** Can you optimize the parameters further and beat these returns? Fork the repo and let's see! 🎯
