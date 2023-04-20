# S&P: Market Sentiment effect on Cryptocurrencies Project (by MsBA students from Columbia)
This project is cooperated by S&amp;P Global and Columbia IEOR Deparment.
This project studies the effect of market sentiment indices on cryptocurrency return and volatility. The project contains major code for data processing, historical pattern exploratory analysis, causality test, machine learning, and deep learning.

## Project Structure
The project is organized into the following components:

<strong> Folder - variable construction: </strong> <br>
- 'Fear_Greed_Crawling.ipynb': This code shows how to web scrap the necessary crypto fear&greed index data from the official website using the provided API key.<br>
- 'Bitcoin_Vader.ipynb': This code shows how to extract daily sentiment from tweets containing 'Bitcoin' using VADER Analysis.<br>
- 'Bitcoin_Crash_Vader.ipynb': This code shows how to extract daily sentiment from tweets containing 'Bitcoin Crash' using VADER Analysis.<br>
- Other variables were downloaded directly from CoinCodex.<br>
<br>

<strong> Folder - data preprocessing: </strong> <br>
- 'google_trend_interpolate.ipynb': This code interpolates the raw weekly google trend data on 6 search strings into daily data for later use.<br>
- 'sentiment_interpolate_10.ipynb': This notebook interpolates the raw news sentiment index data into daily data without gaps for later use.<br>
- 'sentiment_interpolate_78.ipynb': This notebook interpolates the raw weekly CBDI sentiment indices data into daily data without gaps for later use.<br>
- 'data_interpolation_other.ipynb': This notebook interpolates all other raw crypto data and raw sentiment data into daily data without gaps for later use.<br>
<br>

<strong> Folder - historical pattern:</strong> <br>
- 'Volatility_graph.ipynb': This notebook computes the returns, 30-day rolling volatility and changes in volatility for all studies indices, and visualizes all of these.<br>
- 'return_corr_summary.ipynb': This notebook calculates the 100-day rolling correlation between each sentiment index return (exclude google trends indices) and crypto returns, with necessary 1, 3, 5, 7, 9 day lag applied. The best performing results are visualized.<br>
- 'return_corr_summary_gt.ipynb': This notebook calculates the 100-day rolling correlation between each google trend index return and crypto returns, with necessary 1, 3, 5, 7, 9 day lag applied. The best performing results are visualized.<br>
- 'rvrv_corr_summary.ipynb': This notebook calculates the 100-day rolling correlation between changes in 30-day rolling volatility of each sentiment index (exclude google trends indices) and changes in 30-day rolling volatility of crypto, with necessary 1, 3, 5, 7, 9 day lag applied. The best performing results are visualized.<br>
- 'rvrv_corr_summary_gt.ipynb': This notebook calculates the 100-day rolling correlation between changes in 30-day rolling volatility of each google trend index daily and changes in volatility of crypto, with necessary 1, 3, 5, 7, 9 day lag applied. The best performing results are visualized.<br>
<br>

<strong> Folder - causality tests:</strong> <br>
- 'Granger_Causality_Test.ipynb': This notebook performs the two-way granger causality test on all sentiment indices against bitcoin, based on returns and volatilities. A max lag of 5 days is applied. The resulting significance table is provided. <br>
- 'transfer entropy.Rmd': Based on the 'RTransferEntropy' package in R, this R notebook performs the two-way transfer entropy test on all sentiment indices against bitcoin, based on returns. Lags from 1 to 7 days are studied for both directions. 
- 'transfer_entropy_plot.ipynb': The visualization of resulting information flow for each sentiment index is provided. <br>
<br>

<strong> Folder - Regression & Boost:</strong> <br>
- 'Compare.ipynb': This notebook is about two Boost model: XGboost & Gradient boost for using sentiment indices on crypto directionality forcaset. Four different models are created for each crypto index(BTC, ETH, SPCBDM, SPCBXL), which are with & without sentiment<br>
- 'Linear Regression.ipynb': This notebook uses Linear regression to analyze the directionality of 'Bitcoin', 'Ether', SPCBXL, and SPCBDM with 15 sentiment indexes & no control varible.<br>
- 'Statsmodel.ipynb' : This notebook uses logistic regression to analyze the directionality of 'Bitcoin', 'Ether', SPCBXL, and SPCBDM with 15 sentiment indexes & no control varible.<br>
- 'Lag Regression.ipynb': This notebook uses logistic regression to analyze the directionality of 'Bitcoin', 'Ether', SPCBXL, and SPCBDM. The Predictors here is the Lag varible from the previous causality test.<br>
- 'Russell&VIX.ipynb': This notebook uses logistic regression to analyze the directionality of 'Bitcoin', 'Ether', SPCBXL, and SPCBDM with 15 sentiment indexes. The control varible here is only Ruseell 2000 & VIX.<br>.<br>
- 'ONLY VIX.ipynb': This notebook uses logistic regression to analyze the directionality of 'Bitcoin', 'Ether', SPCBXL, and SPCBDM with 15 sentiment indexes. The control varible here is only VIX.<br>
- 
<br>

<strong> Folder - deep learning:</strong> <br>
- 'LSTM_final_version.ipynb': This notebook is about LSTM models for verifying the impact of sentiment indices on crypto prices forcast. Four different models are built for each crypto index (BTC, ETH, SPCBDM, SPCBXL), which are with/without sentiment & with/without shifted price.<br>
<br>

## Installation and Usage
To run this project, you will need to install the following dependencies:
- numpy
- pandas
- matplotlib
- scikit-learn & statsmodels
- keras & tensorflow
- nltk
<br>

To use this project, follow these steps:
- first download the crypto data from any open source coin exchange. Download publicly available market sentiment indices (news sentiment, fear and greed, S&P 500 Twitter, google trends, etc.) and construct twitter sentiment indices following steps in 'Bitcoin_Vader.ipynb' (Twitter API required)  <br>
- Use notebooks in 'historical_pattern' folder to explore the historical patterns of cryptocurrency return and volatility, and conduct simple correlation tests. <br>
- Use notebooks in 'causality_tests' folder to investigate the pairwise causality between market sentiment indices and cryptocurrency return and volatility.
- Use notebooks in 'machine_learning' folder to run logistic regression on crypto directionality, linear regression on crypto volatility, and SVM, Boosting models on directionality. <br>
- Use notebooks in 'deep_learning' folder to build LSTM and GRU models on predicting crypto prices/levels. 

## Results and Visualizations
We found that market sentiment indices have some significant impact on cryptocurrency return and volatility. In particular, we found that Twitter negative sentiment on 'bitcoin', Google trends on 'bitcoin', the crypto fear&greed and S&P 500 Twitter Index are particularly important in analyzing causality and making predictions. We also created several visualizations to demonstrate feature importances and prediction performances which can be found in the corresponding notebooks.

## Acknowledgements
We used the Crypto Fear & Greed index data from "alternative.me", two CBDI indices developed by Yizhi W. et. al., the news sentiment index developed by Adam Hale Shapiro et.al. for academic research purpose. We would like to thank the authors for their contribution.

## Contact Information
If you have any questions or would like to collaborate on this project, please contact [yy3256@columbia.edu, wy2407@columbia.edu, gz2343@columbia.edu].
