Zetheta Market Regime & Multi-Asset Analysis Framework

📌 Project Overview & Objective

Objective: Build a quantitative framework to analyze how macroeconomic factors (bond yields, corporate credit risk, and retail SIP flows) behave during distinct stock market phases.

🛠️ The Master Feature Store
Data Sources: Combined four distinct real-world financial datasets into a single synchronized timeline covering equities (Nifty Midcap/Smallcap), interest rates (10-year gilts), credit spreads, and retail liquidity.

Dataset Shape: Fully synchronized, cleaned, and dense dataset consisting of 4,164 rows and 27 features with zero missing values.

🔍 Market Regime Definition (Rule-Based Logic)
Classified historical market days into two structural phases:

Normal Market: Midcap price is above its 200-day moving average with stable volatility.

Stress Market: Midcap price drops below its 200-day moving average or volatility spikes significantly.

⏳ Chronological Train-Test Split (Methodology)
To prevent "future-peeking" and ensure real-world reliability, data was split chronologically rather than randomly:

Training Set: Historical data up to December 31, 2024 (3,747 rows) used to study patterns and behavior.

Testing Set: Out-of-sample data from 2025 to 2026 (417 rows) reserved as a blind test to evaluate how the framework handles recent market conditions.

📈 Regime-Based Strategy Simulation & Backtesting
Baseline Strategy (Buy & Hold): Staying fully invested in the Nifty Midcap index yielded a cumulative growth of 11.12x.

Tactical Strategy (Regime-Switching to Cash): Moving to cash/sidelines during "Stress" regimes resulted in a cumulative growth of 2.35x.

Key Quantitative Insight: Sitting in cash dodged major market crashes but created a massive opportunity cost by missing out on powerful bull market recoveries. This highlighted the need to rotate into defensive yielding assets (Government Bonds) instead of holding 0% cash.

🔄 Tactical Asset Rotation & Strategy Comparison
Cash Strategy Performance: Moving capital to 0% cash yielded 2.35x.

Bond Rotation Strategy Performance: Rotating capital into 10-year Government Bonds during stress periods yielded 2.50x, outperforming the cash strategy by eliminating zero-yield cash drag.

Key Strategic Finding: Both initial tactical models underperformed the baseline Buy & Hold approach (11.12x) due to frequent whipsawing during recovery phases.

⚙️ Regime Threshold Tuning & Signal Optimization

Optimization Goal: Minimize false-positive "Stress" signals caused by simple moving average breaches.

Refined Logic: Implemented a dual-condition stress filter requiring both a price breakdown below the 200-day moving average and a 21-day volatility spike exceeding the historical 75th percentile.

Refined Results: The Refined Asset Rotation strategy achieved a cumulative growth of 8.73x, dramatically outperforming naive rotation and closing in on the Buy & Hold benchmark with improved drawdown protection.

📉 Risk-Adjusted Performance & Drawdown Analysis
Crash Mitigation: The Refined Strategy successfully reduced Maximum Drawdown from -49.43% to -37.67%, proving robust capital preservation during structural market shocks.

Return Efficiency: Maintained a competitive CAGR (14.01% vs 15.69% for Buy & Hold) while lowering portfolio volatility (16.16% vs 18.68%).

🏆 Project Architecture Summary
Feature Store: Synchronized dataset containing 4,164 rows and 27 features spanning equities, interest rates, credit spreads, and retail SIP flows.

Regime Classification: Dual-condition rule engine (200-day moving average breakdown + 75th percentile volatility spike) eliminating false-positive whipsaws.

Dynamic Allocation: Automated asset rotation moving capital between Nifty Midcaps and 10-year Government Bonds to eliminate zero-yield cash drag.























































































































































































































































