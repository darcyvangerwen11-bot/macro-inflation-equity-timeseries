# macro-inflation-equity-timeseries
# Macroeconomic Inflation Shocks & Equity Index Dynamics: Time-Series Forecasting

> **MSc Finance with Risk Management — University of Bath**  
> *Applied Econometrics & Time-Series Modeling*

## Project Overview
This project examines the stochastic properties, integration orders, and predictive time-series dynamics between US and European equity indices and macroeconomic inflation benchmarks from **2010 to 2025** ($N = 191$ monthly observations).

---

## Data Infrastructure & Integration
- **Equities (Yahoo Finance):** S&P 500 (`^GSPC`) and Euro STOXX 50 (`^STOXX50E`).
- **Inflation Metrics (FRED):** US Headline CPI (`CPIAUCSL`) and Euro Area HICP (`CP0000EZ19M086NEST`).
- **Transformations:** Log price levels, log monthly returns ($\Delta \ln(P_t)$), and second-difference inflation acceleration ($\Delta^2 \ln(\text{CPI}_t)$).

---

## Econometric Diagnostics & Unit Root Tests

### 1. Augmented Dickey-Fuller (ADF) Stationarity Analysis
| Series | Level ADF Stat | Level $p$-value | Order | Differenced ADF Stat | Diff $p$-value | Final Order |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **S&P 500 Index** | $0.1498$ | $0.9693$ | Non-Stationary | $-11.5707$ | $< 0.0001$ | **$I(0)$ at 1st Diff** |
| **Euro STOXX 50** | $-0.6562$ | $0.8578$ | Non-Stationary | $-14.2015$ | $< 0.0001$ | **$I(0)$ at 1st Diff** |
| **US CPI** | $0.4735$ | $0.9840$ | Non-Stationary | $-2.2599$ | $0.1852$ | **$I(0)$ at 2nd Diff ($p < 0.0001$)** |
| **Euro Area HICP** | $0.1689$ | $0.9705$ | Non-Stationary | $-2.4438$ | $0.1297$ | **$I(0)$ at 2nd Diff ($p = 0.0028$)** |

---

## Forecasting Models & Out-of-Sample Results

### ARIMA(1,0,1) Model Estimation (80/20 Train-Test Split)
- **S&P 500 Returns:** Modeled via ARIMA(1,0,1); Out-of-Sample RMSE = **0.03686**
- **Euro STOXX 50 Returns:** Modeled via ARIMA(1,0,1); Out-of-Sample RMSE = **0.03674**
- **Residual Diagnostics:** Ljung-Box test confirms white noise residuals ($Q = 0.01, p = 0.92$), verifying no remaining autocorrelation in the forecast errors.

---

## Darcy van Gerwen
* **MSc Finance with Risk Management**, University of Bath
