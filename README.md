# perishable-goods
The purpose is to run models to predict sales and reduce wasted perishable goods. The daily demand is not used yet because the demand is too low compared to the units sold.
1. The daily sales forecast of perishable goods for each stores, using ARIMA method
    https://github.com/pnth1912/perishable-goods/blob/main/src/perishable-goods-sales-arimaforecast-pipeline
2. Simulation of markdown to find the optimal markdown percentage for each product name, also forecast sales and wastes
   Model used: HistGradientBoostingRegressor (Histogram-based Gradient Boosting Regression Tree)
   https://github.com/pnth1912/perishable-goods/blob/main/src/perishable-goods-markdown-optimization
Comparing the sales forecast using 2 methods, the HistGradientBoostingRegressor performed completely outperformed the ARIMA. Because the ARIMA is designed to predict single time series.
From the metrics files in the output, RMSE of ARIMA is extremely high, meaning ARIMA has large prediction errors for some periods. On the contrary, the HistGradientBoostingRegressor had low RMSE scores and also captured more of the features than ARIMA: Product differences, Store differences, Price sensitivity, Expiry impact, Spoilage risk; therefore, the results from HistGradientBoostingRegressor was selected as the primary model for markdown optimization and dashboard visualization.
