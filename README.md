# Crypto Trader Sentiment Analysis & Prediction
## 📌 Project Overview
This project analyzes the correlation between market sentiment (Fear & Greed Index) and trader behavior to predict next-day profitability. By merging 10,000+ historical trade records with daily sentiment data, we identify "Contrarian" trading patterns and build a predictive model to rank traders based on their probability of success.
## 📂 Repository Structure
ds_Manas_Singh/
├── csv_files/          # Raw and processed datasets
├── outputs/            # Visualizations (Charts, Heatmaps, Feature Importance)
├── notebook_1.ipynb    # Main analysis and modeling pipeline
├── ds_report.pdf       # Executive summary and findings
└── README.md           # Project documentation (You are here)

⚙️ Setup & Installation
Prerequisites
Python 3.8+
Jupyter Notebook or Google Colab
1. Clone the Repository
Bash
git clone [https://github.com/Manas/my-repo.git](https://github.com/Manas/my-repo.git)
cd ds_Manas
2. Install Dependencies
Ensure you have the required libraries installed. You can install them using pip:
Bash : pip install pandas numpy scikit-learn seaborn matplotlib

🚀 How to Run
Navigate to the project directory:
Bash : cd ds_Manas
Launch Jupyter Notebook:
jupyter notebook notebook_1.ipynb

📊 Methodology & Insights
Methodology
Data Integration: Historical trade data was combined with the daily Fear & Greed Index using time-series alignment to avoid look-ahead bias.

Feature Engineering
Sanitization: Leverage was capped at 125x to mitigate outliers.
Sentiment Encoding: One-Hot Encoding was used to distinguish between market conditions (Fear, Greed) as separate states.
Target Variable: A binary Next_Day_PnL target variable was defined to forecast performance.
Modeling: A Random Forest Classifier was used, with Time-Series Walk-Forward Validation to mimic actual trading environments and avoid data leakage.

Key Insights
The Fear Profitability Paradox: Contrary to the Fear market having lower trading volume, it actually produced the highest cumulative PnL of $3.35M, identifying a contrarian subset of traders making high-confidence trades during market panic.
Retail FOMO: On Extreme Greed days, there was a 500% relative increase in trade volume but a dramatic drop in PnL per trade, suggesting the presence of “noise” trading activity fueled by Retail FOMO.
Predictive Validity: The model achieved 60.2% accuracy with a precision of 0.60 to forecast winning days. Feature importance analysis showed Position Size and Sentiment Score to be better predictors of success than raw Leverage.
Strategy Recommendations
Dynamic Risk Governor: Systematically lower the maximum permissible leverage for retail traders when the Long/Short Ratio exceeds 2.0 during Extreme Greed.
“Smart Money” Copy Trading: Traders with positive PnL in Fear markets should be ranked higher since they are more stable.

👤 Author
Manas
MSc Data Science Student, Jain University
