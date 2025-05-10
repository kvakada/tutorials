# Time Series Analysis of Bitcoin Prices Using s3fs

## Description
This project analyzes historical Bitcoin prices using time series techniques. Data is accessed directly from AWS S3 using the `s3fs` library.

## Setup Instructions

### Build Docker
```bash
docker build -t tutor114 .



### fetch_bitcoin_data()

This function uses the CoinGecko public API to retrieve Bitcoin price data for the past N days.

- Inputs:
  - `api_key`: your CoinGecko API key
  - `days`: number of days of historical data to fetch
  - `interval`: `daily` or `hourly`

- Returns:
  - A Pandas DataFrame with `Timestamp` and `Price` columns

- Usage:
```python
from bitcoin_utils import fetch_bitcoin_data
df = fetch_bitcoin_data(api_key="YOUR_KEY", days=365)
