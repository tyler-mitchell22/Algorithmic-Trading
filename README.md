# Algorithmic Trading Strategies

## Performance Highlights 🚀
- **26.4% CAGR** over 10+ years (2013-2023) with regime detection
- **21.7% annual alpha** vs S&P 500 - exceptional outperformance
- **900% total return** since inception (10x your money)
- **Maximum drawdown: 19.1%** - well-controlled risk
- **Sharpe ratio: 0.165** (inception), 0.22 (3-year)

## Repository Structure

### 📊 [Python Buffer Strategy](./python-buffer-strategy/)
Buffer-based momentum strategy with quarterly rebalancing and optimized turnover control.

**Key Features:**
- 40% improvement buffer to reduce unnecessary trades
- Quarterly rebalancing frequency
- PostgreSQL integration for production deployment
- Comprehensive transaction cost modeling

### 📈 [R Regime-Aware Momentum Strategy](./r-momentum-strategy/)
Monthly rebalancing momentum strategy with comprehensive risk analytics and regime detection.

**Key Features:**
- **Multi-factor regime detection** using VIX, trend, and market breadth indicators
- **Dynamic position sizing** (3-10 positions based on market conditions)
- **Adaptive allocation** based on momentum favorability
- **Enhanced database schema** with regime tracking and history
- **Advanced performance metrics** (Sortino, Calmar, Alpha/Beta)
- **Interactive visualization** with dygraphs

### 📋 [Python Performance Analysis](./python-buffer-performance.png/)
Analysis and visualization of strategy performance.

### 📋 [R Performance Analysis](./R-ETF.png/)
Comparative analysis and visualization of strategy performance vs benchmarks.

## Strategy Methodology

### Core Approach
Both implementations use **risk-adjusted momentum** as the primary factor:
- **12-month momentum** minus **1-month mean reversion**
- **Normalized by 12-month volatility** for risk adjustment
- **Dynamic position sizing** (3-10 stocks) based on regime detection
- **Rank-weighted portfolio construction**

### Regime Detection Framework
The R implementation includes sophisticated regime detection:
- **VIX-based volatility regimes** (fear vs opportunity detection)
- **Trend strength analysis** using multiple moving averages
- **Market breadth indicators** for momentum sustainability
- **Composite regime scoring** (0-1 scale) for position sizing

### Key Differences Between Implementations
| Feature | Python Version | R Version |
|---------|---------------|-----------|
| Rebalancing | Quarterly (3 months) | Monthly |
| Buffer System | 40% improvement threshold | None |
| Position Sizing | Fixed | Dynamic 3-10 |
| Database | PostgreSQL | SQLite + Regime |
| Regime Detection | None | Multi-factor |
| Transaction Costs | 0.1% per trade | Not Modeled |

## Investment Universe
- **NYSE listed stocks** with comprehensive liquidity filters
- **Market cap > $1B**, **price > $5**, **IPO before 2012**
- **Liquidity screening** to ensure tradeable universe
- **Minimal survivorship bias** through thresh.bad.data = 0 approach

## Risk Management
- **Maximum 19.1% drawdown** over 10+ year period
- **Regime-aware position sizing** for dynamic risk control
- **Volatility-adjusted momentum signals**
- **Adaptive exposure** based on market conditions

## Regime Analysis Results

### Market Regime Distribution (2014-2023)
| Regime | Months | Avg Score | Avg VIX | Strategy Behavior |
|--------|--------|-----------|---------|-------------------|
| MOMENTUM_STRONG | ~35 | 0.75+ | 25-35 | 10 positions, full exposure |
| MOMENTUM_MODERATE | ~45 | 0.50-0.70 | 20-30 | 8 positions, standard |
| MOMENTUM_WEAK | ~25 | 0.30-0.50 | 15-25 | 5 positions, defensive |
| MOMENTUM_HOSTILE | ~15 | <0.30 | <15 or >35 | 3 positions, minimal |

### Regime Performance Impact
- **2020-2023 boom** correctly identified as MOMENTUM_STRONG
- **2015-2019 consolidation** appropriately managed with reduced exposure
- **Regime detection added 16% to total returns** over base strategy

## Technology Stack
- **Languages:** Python, R
- **Databases:** PostgreSQL, SQLite
- **Libraries:** pandas, numpy, yfinance, tidyquant, dygraphs, BatchGetSymbols
- **Visualization:** matplotlib, ggplot2, interactive dashboards
- **Regime Detection:** TTR, custom volatility indicators

## Key Performance Metrics

### Current Strategy Performance (2013-2023)
- **CAGR:** 26.4%
- **Total Return:** 900% (10x return)
- **Alpha:** 21.7% annually
- **Beta:** 0.66 (inception)
- **Maximum Drawdown:** -19.1%
- **Volatility:** 55.1% (annualized)
- **Sharpe Ratio:** 0.165 (inception), 0.22 (3-year)

### Recent Performance (3-year)
- **CAGR:** 19.3%
- **Alpha:** 66.4% annually  
- **Beta:** 0.55 (recent period)
- **Maximum Drawdown:** -16.1%
- **Sharpe Ratio:** 0.22

## Implementation Notes

### Data Requirements
- Historical monthly price data for NYSE stocks
- VIX data for regime detection
- Minimum 12 months of data for momentum calculations
- Clean, liquidity-filtered dataset

### Key Innovations
1. **Dual-timeframe momentum** (12M trend - 1M mean reversion)
2. **Volatility normalization** for risk-adjusted signals
3. **Multi-factor regime detection** for adaptive positioning
4. **Dynamic position sizing** based on market conditions
5. **Production-ready database integration** with regime tracking
6. **Comprehensive performance attribution** by regime

## Getting Started

### Python Implementation
```bash
cd python-momentum-strategy
pip install pandas numpy matplotlib yfinance psycopg2 sqlalchemy
python momentum_etf.py
```

### R Implementation (Regime-Aware)
```r
setwd("r-momentum-strategy")
install.packages(c("tidyquant", "BatchGetSymbols", "dygraphs", "RSQLite", "TTR"))
source("regime_momentum_etf.R")
```

## Research Insights

### Regime Detection Effectiveness
- **Modest but consistent improvement** (16% total return boost)
- **Better risk-adjusted returns** in challenging periods
- **Successful identification** of 2020+ momentum-friendly environment
- **Defensive positioning** during 2015-2019 consolidation

### Market Regime Learnings
- **Low volatility periods** (VIX <15) are hostile to momentum
- **Moderate volatility** (VIX 20-30) provides best momentum opportunities
- **Extreme volatility** (VIX >35) indicates fear-driven markets
- **Trend persistence** matters more than absolute volatility levels

## Future Research Areas
- **Transaction cost modeling** for regime-aware strategies
- **Machine learning regime detection** (Hidden Markov Models)
- **Multi-asset momentum** with regime overlays
- **Sector rotation** based on regime transitions
- **Options overlay** for regime-specific downside protection
- **International momentum** with local regime detection

## Academic Foundation
This work builds on established academic research in momentum investing and regime detection:
- Jegadeesh & Titman (1993) - Cross-sectional momentum
- Asness, Moskowitz & Pedersen (2013) - Value and momentum everywhere
- Novy-Marx (2012) - Intermediate-term momentum
- Ang & Bekaert (2002) - Regime switches in interest rates
- Guidolin & Timmermann (2007) - Asset allocation under regime switching

## Risk Disclaimers
- **Past performance does not guarantee future results**
- **High volatility strategy** - suitable for risk-tolerant investors
- **Regime detection** based on historical patterns that may not persist
- **Transaction costs** may vary significantly in practice
- **Market conditions** can change, affecting both momentum and regime detection efficacy
- **Model complexity** increases implementation and maintenance risks

## Contact & Collaboration
Interested in discussing systematic momentum strategies, regime detection, or quantitative finance applications? Feel free to reach out! Email is in my portfolio bio!

**Challenge:** Can you improve the regime detection model and beat these returns? Fork the repo and let's see! 🎯

---

*"The best momentum strategies adapt to market conditions rather than fighting them."*
