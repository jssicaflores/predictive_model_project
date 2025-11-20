# Donation Forecasting with Annual Giving Data

This project uses a real fundraising dataset to predict future annual donations. The data includes several years of donor giving history. I reshape that information into a clean time series and use an ARIMA model to forecast future giving.

The goal is to show how a nonprofit or fundraising team can use historical trends to support planning and budgeting.

---

## Data

The dataset comes from the **Data Science for Fundraising** sample files on Kaggle.

Each donor record includes several columns with yearly giving history:

- `CurrFYGiving`
- `PrevFYGiving`
- `PrevFY1Giving`
- `PrevFY2Giving`
- `PrevFY3Giving`
- `PrevFY4Giving`

Each of these represents giving in a different fiscal year. I map those columns to actual calendar years and aggregate across all donors to create a single annual time series from 2009 to 2014.

> Note  
> The original CSV is **not** stored in this repository.  
> To run the notebook, download `data_science_for_fundraising_donor_data.csv` from the Kaggle project and place it in the `data/` folder.

---

## Project Workflow

1. **Load and inspect the data**  
   Read the donor file and explore the key columns.

2. **Clean the giving fields**  
   The giving amounts are strings with symbols (for example `$200`).  
   I remove dollar signs and commas and convert them to numeric values so they can be summed.

3. **Reshape into a time series**  
   Each donor has multiple columns for different fiscal years.  
   I map each column to a specific calendar year, then sum giving across all donors to get total giving per year.

4. **Build a forecasting model**  
   Because the data is annual and there are only a few points, I use a simple ARIMA model from `statsmodels`.  
   ARIMA works well here because:
   - there is a clear overall trend  
   - there is no strong seasonal pattern at the yearly level  
   - the dataset is small

5. **Generate the forecast**  
   The model predicts the next five years of total giving and returns a confidence interval around those estimates.

6. **Visualize the results**  
   The final chart shows:
   - Historical giving from 2009 to 2014  
   - Forecasted giving from 2015 to 2019  
   - A shaded confidence band to show model uncertainty  


