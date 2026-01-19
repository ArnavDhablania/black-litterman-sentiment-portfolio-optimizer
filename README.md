# black-litterman-sentiment-portfolio-optimizer

This project implements a quantitative investment strategy that enhances the Black-Litterman model by integrating Natural Language Processing (NLP). By using FinBERT to analyze financial news, the model generates objective "views" that are mathematically blended with market equilibrium returns to produce optimized asset weights.

**Core Logic**
Traditional portfolio optimization is often hypersensitive to return estimates. This tool solves that by:
1. Anchoring the portfolio to market-cap equilibrium (the "prior").
2. Updating the portfolio with sentiment-driven views (the "posterior") using a Bayesian framework.

**Technical Workflow**
- Sentiment Analysis: Scrapes live headlines from Finviz and uses a FinBERT Transformer to score sentiment for a 15-stock universe.
- Bayesian Blending: Constructs a Relative Picking Matrix ($P$) and View Vector ($Q$) to calculate the specific excess returns implied by current news cycles.
- Risk Framework: Calculates a $15 \times 15$ covariance matrix using 3 years of historical data via yfinance.
- Weight Optimization: Quantifies the "Weight Shift" required to move from a passive market-cap index to a sentiment-optimized active strategy.

**Key Results**
- Successfully automated the pipeline from raw HTML scraping to final allocation.
- Generated significant active tilts based on high-conviction positive sentiment trends.

**Tech Stack**
- Python: NumPy, Pandas, Matplotlib.
- ML/NLP: PyTorch, HuggingFace (FinBERT).
- Data: BeautifulSoup4 (Web Scraping), yfinance (Market Data).
