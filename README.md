# Nigerian COVID-19 Market Regimes: Analysis Pipeline

WorldQuant University MScFE 690 Capstone (Group 17844). Instructor: Prof. Ken Abbott.

**Project:** The Impact of COVID-19 on Nigerian Financial Markets: A Statistical Analysis of Market Regime Shifts Using a Hidden Markov Model (2017-2025).

## Markets analysed
- NGX All-Share Index (NGX ASI)
- USD/NGN exchange rate
- Federal Government of Nigeria (FGN) bond yields (four tenors)
- Brent crude oil (FRED series DCOILBRENTEU)

Analysis window: 2017-01-01 to 2025-12-31. Periods: Pre-COVID (to 2020-02-26), COVID (2020-02-27 to 2021-12-31), Post-COVID (from 2022-01-01); the naira float date used for sub-period analysis is 2023-06-14.

## Methods
- Descriptive statistics, ADF and KPSS stationarity tests
- ARIMA(1,0,1) and GARCH(1,1)
- PCA on standardised yield changes
- Correlations with Fisher-z confidence intervals and change tests
- Welch's t-test and Levene's (Brown-Forsythe) test, with Holm and Bonferroni corrections
- Gaussian Hidden Markov Model (two and three states, BIC comparison); states labelled by mean realised volatility
- Out-of-sample validation with frozen parameters and filtered probabilities, forward test, threshold benchmark
- Robustness: VaR, volatility-window and initialisation sensitivity
- Additions after instructor feedback (Steps 19 and 20): Brent with and without 21 April 2020, NGX in US-dollar terms (NGX/USDNGN), HMM on the dollar series, volatility by calendar year

## Files
| File | Purpose |
| --- | --- |
| `Nigeria_COVID_Final_Pipeline.ipynb` | Executed notebook with all outputs |
| `Nigeria_COVID_Final_Pipeline.py` | Same pipeline as a script |
| `Brent Oil.csv`, `NGX All-Share Index (ASI).csv`, `USD_NGN Historical Data.csv`, `Nigeria_Bond_Yields_2017_2025_Redone.csv` | Raw input data |
| `results/` | Result tables written by Steps 19 and 20 and earlier steps (Holm-adjusted tests, dollar-terms analysis, calendar-year volatility, and others) |
| `requirements.txt` | Python dependencies |

## How to run
1. Open the notebook in Google Colab (or run the `.py` file in Python 3.10+ after `pip install -r requirements.txt`).
2. Upload the four raw CSV files to the working folder (`/content/` in Colab); otherwise set `DATA_DIR` at the top of the script.
3. Run all cells in order. Outputs are written to `OUT_DIR` (`/content/results/` by default).

## Authors
Towobola Oluwatunmise Moses, Abdurrahman Mubarak Derie and Jeffrey Ted Johnattan Mbongo Nkounga. See `CONTRIBUTORS.md`.
