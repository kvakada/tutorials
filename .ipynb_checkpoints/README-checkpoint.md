# 🧠 Time Series Analysis of Bitcoin Prices Using s3fs

**Author:** Karthik Vakada  
**Email:** kvakada@umd.edu  
**Project Tag:** TutorTask114_Spring2025_Time_Series_Analysis_of_Bitcoin_Prices_Using_s3fs  
**Date:** May 2025

---

## 📁 Project Files

This project contains the following key files and folders:

```
TutorTask114_Spring2025_Time_Series_Analysis_of_Bitcoin_Prices_Using_s3fs/
├── README.md                          <- This file
├── bitcoin_utils.py                   <- Utility functions for fetching and saving data
├── Spring2025_s3fs.API.ipynb          <- Demonstrates usage of s3fs and API integration
├── Spring2025_s3fs.API.md             <- Describes the native API integration
├── Spring2025_s3fs.example.ipynb      <- End-to-end notebook showing data loading, analysis, and S3 export
├── Spring2025_s3fs.example.md         <- Markdown overview of the example notebook
├── requirements.txt                   <- Python dependencies
├── Dockerfile                         <- Docker environment specification
├── bitcoin_prices.csv                 <- Raw price data (if needed for fallback)
├── bitcoin_prices_with_forecast.csv   <- Forecast output (for optional extension)
```

---

## ⚙️ Setup and Dependencies

The project is built using:

- **Python 3.9+**
- `pandas`, `matplotlib`, `statsmodels` for data analysis and visualization
- `s3fs` for interacting with AWS S3 using a filesystem-like interface
- Jupyter for notebooks
- Docker for reproducible environments

All dependencies are listed in `requirements.txt`.

---

## 🐳 Building and Running the Docker Container

> 📍 Run the following steps from the project root:

1. **Build Docker Image**

```bash
docker build -t tutor114 .
```

2. **Run Container**

```bash
docker run -it -p 8888:8888 -v $(pwd):/app -v ~/.aws:/root/.aws tutor114
```

3. **Launch Jupyter Notebook**

Open your browser and navigate to:

```
http://localhost:8888
```

> 🔐 If using AWS S3, make sure your `~/.aws/credentials` are correctly mounted.

---

## 🌐 Environment Setup (Non-Docker)

1. Create a virtual environment (optional):

```bash
python -m venv venv
source venv/bin/activate
```

2. Install dependencies:

```bash
pip install -r requirements.txt
```

3. Run the notebook using Jupyter:

```bash
jupyter lab
```

---

## 🔐 API Key Configuration

The API fetch logic resides in `bitcoin_utils.py`. You can use:

```python
df = fetch_bitcoin_data(days=365)
```

This will retrieve daily Bitcoin prices from CoinGecko API.

> ⚠️ Avoid hardcoding keys. Use environment variables or `.env` files where possible.

---

## 🧪 Native API: `Spring2025_s3fs.API.*`

- `Spring2025_s3fs.API.ipynb` demonstrates:
  - Mounting AWS buckets using `s3fs`
  - Reading/writing directly to S3 with `pd.read_csv()` / `.to_csv()`
- `Spring2025_s3fs.API.md` explains:
  - Why use `s3fs`
  - How it abstracts boto3
  - When it is optimal (quick S3 I/O, simple scripts)

---

## 🧑‍💻 Project Example: `Spring2025_s3fs.example.*`

- `Spring2025_s3fs.example.ipynb` performs:
  - Fetching price data
  - Decomposing time series into trend/seasonal/residual
  - Plotting moving averages
  - Saving results locally and optionally pushing to S3
- `Spring2025_s3fs.example.md` contains:
  - Description of the problem
  - Summary of the methodology
  - Key takeaways from analysis

---

## 📊 Visual Output

- 📈 Price chart with moving average
- 📉 Trend/seasonal/residual plots from decomposition
- 📤 Optional forecast (for extension)
- ☁️ Data upload to S3 confirmed via `s3fs` logs

---

## 📌 Optional Improvements

- Add anomaly detection (e.g., Z-score method or Prophet)
- Add time series forecasting (ARIMA, Exponential Smoothing)
- Use S3-hosted datasets only (avoid local CSVs)

---

## ✅ Final Notes

This project was developed as part of **DATA605 – Spring 2025** following Causify AI project conventions. It is fully reproducible using Docker, follows modular design using utility functions, and is documented both in code and markdown.

For questions or contributions, contact: **kvakada@umd.edu**
