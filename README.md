# India-Stocks-361-390-Historical-Data

Institutional Historical 1-Minute Market Data Archive for **India Equities (Constituents 361 to 390)** with automated daily cloud capture via GitHub Actions.

---

## 🏛️ Directory Hierarchy

```text
India-Stocks-361-390-Historical-Data/
├── .github/workflows/daily_ingest.yml
├── fetch_batch.py
├── README.md
├── <SYMBOL>/
│   └── 1m/
│       ├── README.md
│       └── <YYYY>/
│           └── <MM>/
│               ├── <SYMBOL>_1m_<YYYY-MM-DD>.csv
```

---

## ⏰ 4-Tier Automated Schedule (Mon–Fri)

| Trigger | Time (IST) | Cron (UTC) | Role |
|:---|:---:|:---:|:---|
| **Primary Trigger** | **15:45 IST** | `15 10 * * 1-5` | 15 mins post-market close |
| **Backup Trigger 1** | **16:45 IST** | `15 11 * * 1-5` | 1 hour safety net |
| **Backup Trigger 2** | **17:45 IST** | `15 12 * * 1-5` | 2 hours safety net |
| **Backup Trigger 3** | **18:45 IST** | `15 13 * * 1-5` | 3 hours safety net |

---

## 📦 Constituents (361 to 390)

| # | Symbol | Company Name | Yahoo Ticker |
|---|---|---|---|
| 361 | `INDIACEM` | India Cements Ltd. | `INDIACEM.NS` |
| 362 | `INDIAMART` | Indiamart Intermesh Ltd. | `INDIAMART.NS` |
| 363 | `IEX` | Indian Energy Exchange Ltd. | `IEX.NS` |
| 364 | `IGL` | Indraprastha Gas Ltd. | `IGL.NS` |
| 365 | `INOXWIND` | Inox Wind Ltd. | `INOXWIND.NS` |
| 366 | `INTELLECT` | Intellect Design Arena Ltd. | `INTELLECT.NS` |
| 367 | `IGIL` | International Gemological Institute Ltd. | `IGIL.NS` |
| 368 | `IKS` | Inventurus Knowledge Solutions Ltd. | `IKS.NS` |
| 369 | `JBMA` | JBM Auto Ltd. | `JBMA.NS` |
| 370 | `JKTYRE` | JK Tyre & Industries Ltd. | `JKTYRE.NS` |
| 371 | `JMFINANCIL` | JM Financial Ltd. | `JMFINANCIL.NS` |
| 372 | `JSWCEMENT` | JSW Cement Ltd. | `JSWCEMENT.NS` |
| 373 | `JAINREC` | Jain Resource Recycling Ltd. | `JAINREC.NS` |
| 374 | `JPPOWER` | Jaiprakash Power Ventures Ltd. | `JPPOWER.NS` |
| 375 | `J&KBANK` | Jammu & Kashmir Bank Ltd. | `J&KBANK.NS` |
| 376 | `JINDALSAW` | Jindal Saw Ltd. | `JINDALSAW.NS` |
| 377 | `JUBLINGREA` | Jubilant Ingrevia Ltd. | `JUBLINGREA.NS` |
| 378 | `JWL` | Jupiter Wagons Ltd. | `JWL.NS` |
| 379 | `JYOTICNC` | Jyoti CNC Automation Ltd. | `JYOTICNC.NS` |
| 380 | `KPITTECH` | KPIT Technologies Ltd. | `KPITTECH.NS` |
| 381 | `KSB` | KSB Ltd. | `KSB.NS` |
| 382 | `KAJARIACER` | Kajaria Ceramics Ltd. | `KAJARIACER.NS` |
| 383 | `KPIL` | Kalpataru Projects International Ltd. | `KPIL.NS` |
| 384 | `KARURVYSYA` | Karur Vysya Bank Ltd. | `KARURVYSYA.NS` |
| 385 | `KAYNES` | Kaynes Technology India Ltd. | `KAYNES.NS` |
| 386 | `KEC` | Kec International Ltd. | `KEC.NS` |
| 387 | `KFINTECH` | Kfin Technologies Ltd. | `KFINTECH.NS` |
| 388 | `KIRLOSBROS` | Kirloskar Brothers Ltd. | `KIRLOSBROS.NS` |
| 389 | `KIRLOSENG` | Kirloskar Oil Eng Ltd. | `KIRLOSENG.NS` |
| 390 | `KIMS` | Krishna Institute of Medical Sciences Ltd. | `KIMS.NS` |


---

## ⚡ 1-Line Pandas Stream Loader

```python
import pandas as pd

# Example: Stream INDIACEM 1m data
url = "https://raw.githubusercontent.com/parshant65-lang/India-Stocks-361-390-Historical-Data/main/INDIACEM/1m/2026/10/INDIACEM_1m_2026-10-12.csv"
df = pd.read_csv(url)
print(df.head())
```
