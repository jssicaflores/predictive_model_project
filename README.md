Donation Forecasting Model Using Annual Giving Data


This project explores a real fundraising dataset and uses it to predict future giving. The data includes several years of donor giving history. I reshaped that information into a clean time series and built a forecasting model to estimate donations for the next few years.
The goal is to show how organizations can use historical trends to understand how contributions may shift over time.


About the Data
The dataset comes from the “Data Science for Fundraising” sample files. Each donor record contains yearly giving history across multiple fiscal years. Because the data is donor-level and each year’s gifts are stored in separate columns, the first step was converting everything into a single annual giving timeline.
The final time series includes annual totals from 2009 to 2014.


Project Steps
1. Clean the giving fields
The giving amounts were formatted as strings with symbols, so I removed dollar signs and commas and converted everything to numeric values.
2. Reshape into a usable time series
Each donor had separate columns for gifts from different fiscal years. I mapped those columns to actual years, then summed across all donors to build a single year-by-year donation total.
3. Build a forecasting model
Because the dataset is yearly and fairly small, a simple ARIMA model was a good fit. ARIMA handles broad trends without needing seasonal patterns.
4. Generate the forecast
The model predicted the next five years of giving. I added a confidence interval so it’s clear how much uncertainty to expect this far out.
5. Visualize the results

   
The final chart shows:<br>
Historical giving from 2009 to 2014<br>
Predictions from 2015 to 2019<br>
A shaded confidence band around the forecast<br>
This makes it easy to compare past trends with expected future values.<br>


What This Project Demonstrates


This notebook shows how a nonprofit or fundraising team could take the data they already have and turn it into a practical forecast. Even with limited history, basic time series models can help guide planning and budgeting.<br>


For me, it was also a hands-on way to practice:<br>
Data cleaning<br>
Time series preparation<br>
Model building<br>
Forecast visualization<br>
Storytelling with real nonprofit-style data<br>
Notebook<br>
The full workflow is in the Colab notebook, including the code to clean, reshape, model, and visualize the forecast.
