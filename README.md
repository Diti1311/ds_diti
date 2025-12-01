# ds_diti

# Trader Behavior Analysis – Data Science Task

This repository contains the complete solution to the Trader Behavior Analysis assignment.  
The goal of the project is to understand how trader performance (PnL, win-rate, behavior patterns) varies with market sentiment (Fear / Neutral / Greed), using the provided historical trader dataset and the Fear & Greed Index.

---

## Methodology (High-Level Overview)

The analysis follows these steps:

### **1. Data Loading**
- Imported trader dataset (`historical_trader_data`)
- Imported Fear/Greed dataset (`fear_greed_index`)
- Performed sanity checks on column data types and missing values

### **2. Data Cleaning**
- Parsed `Timestamp IST` into a proper datetime format (`time_parsed`)
- Normalized daily date field (`date`) used for merging
- Converted numeric columns (`Size USD`, `Closed PnL`, `Fee`) to numeric types
- Cleaned categorical columns (`Side`, `Direction`, `Coin`, `Account`)
- Cleaned Fear/Greed sentiment labels from `classification`

### **3. Data Merging**
- Merged trader dataset with sentiment dataset on the `date` column (many trades → one daily sentiment)
- Ensured alignment by normalizing both timestamps to daily granularity

### **4. Feature Engineering**
Created useful analytical features:
- **Win-rate** → percent of profitable trades per group  
- **Mean/Median PnL** → central tendency of performance  
- **Hourly trade behavior** → extracted from `time_parsed`  
- **Coin-level stats** → top performing tickers  
- **Account-level consistency** → top traders by PnL & win-rate  
- **Daily PnL time-series** → aggregated by date

### **5. Exploratory Data Analysis**
Computed aggregations across:
- **Sentiment** (Fear / Neutral / Greed)
- **Coin**
- **Direction** (long/short)
- **Hour of day**
- **Account**
- **Daily performance**

### **6. Visualization**
Generated clear charts for:
- Distribution of PnL across sentiments
- Win-rate across sentiments
- Mean/median PnL comparisons
- Coin-level performance (PnL & trade volume)
- Time-of-day patterns
- Fee vs Trade Size scatter relationships
- Overall PnL distribution

(All plots saved in `/outputs/`)

### **7. Findings & Insights**
You will fill these with your own observations from the output images.

---

## Notebook

The entire analysis is implemented in this Colab notebook:

**https://colab.research.google.com/drive/1-hHo-IECgsSBBRCe0XZ_r8z0Ju38OFjo?usp=sharing**

---

## How to Run

1. Open the notebook in Google Colab  
2. Run all cells from top to bottom  
3. Output CSVs will be saved in `csv_files/`  
4. All plots will be saved in `outputs/`  
5. Export the final PDF report using your own summary  

---

## Contact

**Your Name**  
Email: diti.solanki13@gmail.com  
GitHub: Diti1311
