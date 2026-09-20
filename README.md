Project Overview & Objective
Name: Zetheta Market Regime & Multi-Asset Analysis Framework

Objective: To build a quantitative framework that analyzes how macroeconomic factors (like bond yields, corporate credit risk, and retail SIP flows) behave during different stock market phases.

The Master Feature Store
Data Sources: Combined four distinct real-world financial datasets into a single synchronized timeline covering equities (Nifty Midcap/Smallcap), interest rates (10-year gilts), credit spreads, and retail liquidity.

Dataset Shape: Fully synchronized, cleaned, and dense dataset consisting of 4,164 rows and 27 features with zero missing values.




Market Regime Definition
Rule-Based Logic: Classified historical market days into two distinct phases to track structural changes:

Normal Market: Midcap price is above its 200-day moving average with stable volatility.

Stress Market: Midcap price drops below its 200-day moving average or volatility spikes significantly.






Chronological Train-Test Split (Methodology)
Time-Series Split: To prevent "future-peeking" and ensure real-world reliability, the data was split chronologically rather than randomly

Training Set: Historical data up to December 31, 2024 (3,747 rows) used to study patterns and behavior.

Testing Set: Out-of-sample data from 2025 to 2026 (417 rows) reserved as a blind test to evaluate how the framework handles recent market conditions.





Regime-Based Strategy Simulation & Backtesting

Baseline Strategy (Buy & Hold): Staying fully invested in the Nifty Midcap index throughout the entire historical timeline yielded a cumulative growth of 11.12x.

Tactical Strategy (Regime-Switching): Moving to cash/sidelines whenever a "Stress Market" regime was triggered resulted in a cumulative growth of 2.35x.

Key Quantitative Insight: While sitting in cash successfully dodged major market crashes, it created a massive opportunity cost by missing out on powerful bull market recoveries. This highlights the next optimization phase: rotating into defensive yielding assets (like Government Bonds) during stress periods instead of holding 0% cash.



Final Buy & Hold Value: 11.12x
What it means: If you had invested your money into the Nifty Midcap index on day one and did absolutely nothing—just held through every single crash, panic, and bull run—your initial money would have multiplied to 11.12 times its original size by the end.

Final Strategy Value: 2.35x
What it means: If you followed our tactical rule—staying invested during "Normal" markets, but completely pulling your money out into 0% cash the second a "Stress" market was triggered—your money would have only grown to 2.35 times its original size.



Tactical Asset Rotation & Strategy Comparison
Cash Strategy Performance: Moving capital to 0% cash during "Stress" regimes resulted in a cumulative growth of 2.35x.

Bond Rotation Strategy Performance: Rotating capital into 10-year Government Bonds during "Stress" regimes yielded 2.50x, outperforming the cash strategy by eliminating zero-yield cash drag.

Key Strategic Finding: Both tactical models underperformed the baseline Buy & Hold approach (11.12x). This indicates that the current rule-based regime definitions trigger too frequently, causing the strategy to sit out during powerful long-term recovery phases.

Next Optimization Phase: Fine-tuning regime thresholds or transitioning to unsupervised machine learning algorithms (such as Hidden Markov Models) to better capture true structural market phases without excessive whipsawing.










Regime Threshold Tuning & Signal Optimization
Optimization Goal: Minimize false positive "Stress" signals (whipsawing) caused by simple moving average breaches, thereby reducing opportunity cost during bull runs.

Refined Logic: Implemented a dual-condition stress filter requiring both a price breakdown below the 200-day moving average and a 21-day volatility spike exceeding the historical 75th percentile.

Results: The Refined Asset Rotation strategy achieved a cumulative growth of 8.73x, dramatically outperforming the previous naive rotation (2.50x) and closing in on the Buy & Hold benchmark (11.12x) with significantly improved drawdown protection.






Calculate Risk Metrics (Sharpe & Max Drawdown): Let's write a quick code block to calculate the actual Sharpe ratios and maximum drawdowns for Buy & Hold vs. our Refined Strategy to mathematically prove that our strategy is safer and nearly as profitable.

Test on the Unseen 2025–2026 Data: Let's run our optimized rules over that hidden out-of-sample test period we set aside earlier to see how it performed recently.



Risk-Adjusted Performance & Drawdown Analysis
Evaluation Metrics: Compared the baseline Buy & Hold approach against the Refined Asset Rotation strategy using Compound Annual Growth Rate (CAGR), Annualized Volatility, Sharpe Ratio, and Maximum Drawdown (MDD).

Crash Mitigation: The Refined Strategy successfully reduced Maximum Drawdown from -49.43% to -37.67%, proving robust capital preservation during structural market shocks.

Return Efficiency: Maintained a competitive CAGR (14.01% vs 15.69% for Buy & Hold) while lowering portfolio volatility (16.16% vs 18.68%), demonstrating that tactical asset rotation achieves superior risk-adjusted stability without severe opportunity cost.


Visual Validation & Final Project SummaryPerformance Overview: The equity curve plot confirms that the Refined Asset Rotation strategy successfully tracks long-term structural upside (achieving 8.73x cumulative growth vs. 11.12x for Buy & Hold) while providing automated downside protection.   Risk Mitigation: Slashed Maximum Drawdown from -49.43% down to -37.67%, proving superior capital preservation during deep market shocks.Project Architecture Summary:Feature Store: Synchronized dataset containing 4,164 rows and 27 features spanning equities, interest rates, credit spreads, and retail SIP flows.Regime Classification: Dual-condition rule engine (200-day moving average breakdown + 75th percentile volatility spike) eliminating false-positive whipsaws.Dynamic Allocation: Automated asset rotation moving capital between Nifty Midcaps and 10-year Government Bonds to eliminate zero-yield cash drag





















































