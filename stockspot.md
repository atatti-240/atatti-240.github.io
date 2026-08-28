## StockSpot

**Project description:** StockSpot is a solo-built algorithmic trading system that has evolved since mid-2025 from a basic trading dashboard into a multi-signal machine learning pipeline. The current focus is a weather-driven signal stack, built through a Polygence research mentorship, extending toward crypto, sports arbitrage, and shipping signals.

### Weather ML Model

Three strategies backtested against Kalshi markets across NYC, Chicago, LA, Denver, Boston, and Houston:

- S1 Tomorrow Temperature — R² = 0.70
- S2 Extreme Weather — still refining (currently negative R²)
- S3 Three-Day Trend — R² = 0.137

<img src="images/dummy_thumbnail.jpg?raw=true"/>

### Tech Stack

Python 3.14, XGBoost, LightGBM, and scikit-learn, pulling data from Open-Meteo and the Kalshi API, running on a DigitalOcean droplet via cron.

### Roadmap

Seven additional signals (NWS station bias, model-ensemble spread, coastal marine layer, snowfall, hurricane track uncertainty, and more), then portfolio optimization via Kelly/Markowitz sizing, followed by crypto, sports arbitrage, and shipping-index signals.

For more, [view my GitHub profile](https://github.com/atatti-240).

[← Back to Portfolio](/)
