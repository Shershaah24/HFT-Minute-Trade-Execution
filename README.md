HFT Forex Trade Execution System - Project Overview
Project Overview
This project aims to build a real-time high-frequency trading (HFT) system that executes forex trades every minute with
a 96% win-rate target. Leveraging cutting-edge AI models deployed on AWS SageMaker, the system integrates multiple
data sources (tick data, news sentiment, indicators) to deliver accurate entry and exit points per minute.
Use Case
The system is designed for automated high-frequency trading in the forex market using real-time data and AI-powered
decisions. It fetches tick-level order book data, financial news, and technical indicators to make model-driven trading
decisions.
Model Architecture
1. DeepLOB v2 (Limit Order Book Model)
 - Predicts price movement from tick-level LOB data.
2. Temporal Fusion Transformer (TFT)
 - Handles multivariate time-series predictions.
3. FinBERT (Sentiment Analysis)
 - Scores financial news and integrates sentiment.
4. News-Impact Scorer (Custom BERT)
 - Assigns impact weights to headlines.
5. Multi-Armed Bandit (MAB)
 - Selects best-performing currency pairs adaptively.
6. CNN + Transformer Hybrid
 - Learns technical chart patterns (MACD, RSI, VWAP).
7. Volatility Predictor (Optional)
 - Filters trades in high noise environments.
Execution Pipeline
Data Collection (APIs: Tick, Indicators, News)
 -> Preprocessing (Lambda/SageMaker)
 -> Model Ensemble Execution
 -> Trade Decision (every 1 min)
 -> Broker Execution via Lambda API call
Deployment Strategy
Deploy each model as a multi-model SageMaker endpoint or sequential Step Function pipeline. Trigger execution using
EventBridge every minute. Use AWS Lambda for lightweight broker execution handling.
Project Goals
1. Maintain above 90% precision on directional predictions.
2. Execute trades with sub-1s latency post decision.
3. Optimize for scalability and modularity of models.
4. Qualify for Devin AI credits via active open-source maintenance and integration showcase.
Repository Setup Plan
1. Create GitHub repository (e.g., `hft-forex-execution`)
2. Add modular folders: `models/`, `pipeline/`, `deployment/`
3. Include README with architecture diagram, usage, and setup guide.
4. License: MIT or Apache 2.0
5. Perform weekly commits and issue tracking for qualification.

Forex Data Tools - Project Documentation
Introduction
Forex Data Tools is a simple Python toolkit for forex traders to fetch real-time exchange rates and build basic trading
logic. This open-source project is aimed at helping individual traders automate data collection and analysis for
high-frequency and minute-level trading.
Features
- Fetch real-time forex exchange rates (e.g., EUR/USD, GBP/USD)
- Minimal setup - ideal for lightweight trading bots
- Easily extendable for more complex strategies
- MIT Licensed - free to use and contribute
Getting Started
1. Clone the Repository:
 git clone https://github.com/Shershaah24/forex-data-tools.git
 cd forex-data-tools
2. Install Dependencies:
 pip install -r requirements.txt
3. Run the Script:
 python forex_fetcher.py
Example Output
{
 "Realtime Currency Exchange Rate": {
 "1. From_Currency Code": "EUR",
 "2. From_Currency Name": "Euro",
 "3. To_Currency Code": "USD",
 "4. To_Currency Name": "United States Dollar",
 ...
 }
}
Configuration
Edit the script (forex_fetcher.py) and replace:
 api_key = "YOUR_ALPHA_VANTAGE_KEY"
with your free Alpha Vantage API key: https://www.alphavantage.co/support/#api-key
Contributing
We welcome contributions and feature requests!
Ways to Contribute:
- Open an issue (e.g., Add GBP/USD support)
- Submit a pull request
- Improve documentation or error handling
License
Apache License Version 2.0
Project Goals
This project is the foundation for a broader suite of AI-powered forex tools using Devin. Future plans include:
- Automated backtesting support
- Candlestick pattern detection
- News sentiment scoring for macro insights
Maintainers
- Shershaah24 - GitHub Profile: https://github.com/Shershaah24
Disclaimer
This tool is for educational and experimental purposes only. Always use caution when trading live financial markets.
