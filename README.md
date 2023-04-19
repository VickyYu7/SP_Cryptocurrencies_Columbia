# S&P: Market Sentiment effect on Cryptocurrencies Project (by MsBA students from Columbia)
This project is cooperated by S&amp;P Global and Columbia IEOR Deparment.
This project studies the effect of market sentiment indices on cryptocurrency return and volatility. The project contains major code for data processing, historical pattern exploratory analysis, causality test, machine learning, and deep learning.

## Project Structure
The project is organized into the following components:

<strong> Folder - variable construction: </strong> <br>
- 'Fear_Greed_Crawling.ipynb': This code shows how to web scrap the necessary crypto fear&greed index data from the official website using the provided API key.<br>
<br>

<strong> Folder - data processing: </strong> <br>
- 'google_trend_interpolate.ipynb': This code interpolates the raw weekly google trend data on 6 search strings into daily data for later use.<br>
- 'sentiment_interpolate_10.ipynb': This notebook interpolates the raw news sentiment index data into daily data without gaps for later use.<br>
- 'sentiment_interpolate_78.ipynb': This notebook interpolates the raw weekly CBDI sentiment indices data into daily data without gaps for later use.<br>
- 'data_interpolation_other.ipynb': This notebook interpolates all other raw crypto data and raw sentiment data into daily data without gaps for later use.<br>
<br>

<strong> Folder - historical pattern:</strong> <br>
- 'Volatility_graph.ipynb': This notebook computes the returns, 30-day rolling volatility and changes in volatility for all studies indices, and visualizes all of these.<br>
- 'return_corr_summary.ipynb': This notebook calculates the 100-day rolling correlation between each sentiment index return (exclude google trends indices) and crypto returns, with necessary 1, 3, 5, 7, 9 day lag applied. The best performing results are visualized.<br>
- 'return_corr_summary_gt.ipynb': This notebook calculates the 100-day rolling correlation between each google trend index return and crypto returns, with necessary 1, 3, 5, 7, 9 day lag applied. The best performing results are visualized.<br>
- 'rvrv_corr_summary.ipynb': This notebook calculates the 100-day rolling correlation between each sentiment index (exclude google trends indices) daily change in 30-day rolling volatility and crypto change in volatility, with necessary 1, 3, 5, 7, 9 day lag applied. The best performing results are visualized.<br>
- 'rvrv_corr_summary_gt.ipynb': This notebook calculates the 100-day rolling correlation between each google trend index daily change in 30-day rolling volatility and crypto change in volatility, with necessary 1, 3, 5, 7, 9 day lag applied. The best performing results are visualized.<br>
<br>

<strong> Folder - causality tests:</strong> <br>
- 'granger_test.ipynb': This notebook performs the two-way granger causality test on all sentiment indices against bitcoin, based on returns and volatilities. A max lag of 5 days is applied. The resulting significance table is provided. <br>
- 'transfer entropy.Rmd': Based on the 'RTransferEntropy' package in R, this R notebook performs the two-way transfer entropy test on all sentiment indices against bitcoin, based on returns. Lags from 1 to 7 days are studied for both directions. 
- 'transfer_entropy_plot.ipynb': The visualization of resulting information flow for each sentiment index is provided. <br>
<br>

## Installation and Usage
To run this project, you will need to install the following dependencies:
- numpy
- pandas
- matplotlib
- scikit-learn
- keras & tensorflow

To run the project, first download the crypto data from any open source coin exchange. Download publicly available market sentiment indices (news sentiment, fear and greed, S&P 500 Twitter, google trends, etc.) and construct twitter sentiment indices following steps in ' ' (Twitter API required). With all data ready, then process the data through files in 'data-processing'. Analyze the data following necessary tests and models.
<br>

To use this project, follow these steps:
Run data_processing.py to process the raw market sentiment data.
Open exploratory_analysis.ipynb to explore the historical patterns of cryptocurrency return and volatility.
Open causality_test.ipynb to investigate the relationship between market sentiment indices and cryptocurrency return and volatility.
Open machine_learning.ipynb to use machine learning algorithms to predict cryptocurrency return and volatility based on market sentiment indices.
Open deep_learning.ipynb to use deep learning models to predict cryptocurrency return and volatility based on market sentiment indices.
Results and Visualizations
We found that market sentiment indices have a significant impact on cryptocurrency return and volatility. In particular, we found that [insert key findings here]. We also created several visualizations to demonstrate these findings, which can be found in the notebooks.

## Acknowledgements
We used the [insert name of dataset/library here] library/dataset for [insert purpose here]. We would like to thank [insert authors of library/dataset here] for their contribution.

## Contact Information
If you have any questions or would like to collaborate on this project, please contact [yy3256@columbia.edu].
