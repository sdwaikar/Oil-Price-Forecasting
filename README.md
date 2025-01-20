# Oil Price Analysis and Forecasting 📈

This project involves analyzing daily oil price data (2013–2017) and forecasting future trends using advanced time series techniques. The analysis includes data imputation, trend exploration, and predictive modeling using **Holt-Winters** and **ETS (Error, Trend, Seasonality)** methods.

## Features

- **Data Preprocessing**: Cleaned and imputed missing values using **linear interpolation**, ensuring a smooth and reliable dataset for analysis.
- **Exploratory Data Analysis**: Visualized trends and potential seasonal patterns in oil prices with **ggplot2**, identifying key periods of fluctuation.
- **Predictive Modeling**: Implemented **Holt-Winters** and **ETS models** for forecasting, comparing their performance metrics to identify the most accurate model.

## Dataset

- **Source**: Daily oil price data  
- **Size**: 1,218 records  
- **Features**:  
  - Date  
  - Daily oil price (USD)  

## Results

- **Holt-Winters Model**:  
  - RMSE: **0.976**  
  - MAE: **0.755**  
  - MAPE: **1.30%**  

- **ETS Model**:  
  - RMSE: **1.177**  
  - MAE: **0.896**  
  - MAPE: **1.55%**  

## Key Insights

- The **Holt-Winters model** outperformed ETS, delivering lower errors across all metrics.
- A significant price drop was observed between **2014–2016**, with stabilization in subsequent years.
- Linear interpolation effectively handled missing values, maintaining the integrity of trends.

## Installation

1. Clone the repository:  
   ```bash
   git clone https://github.com/YourUsername/OilPriceForecasting.git
   ```

2. Navigate to the directory:  
   ```bash
   cd OilPriceForecasting
   ```

3. Install required R libraries:  
   ```R
   install.packages(c("readr", "ggplot2", "forecast", "zoo"))
   ```

## Usage

1. Load the dataset:  
   ```R
   oil_data <- read_csv("path_to/oil.csv")
   ```

2. Impute missing values:  
   ```R
   oil_data$dcoilwtico <- na.approx(oil_data$dcoilwtico, na.rm = FALSE)
   ```

3. Implement time series models:  
   - Holt-Winters:  
     ```R
     hw_model <- HoltWinters(oil_ts)
     ```
   - ETS:  
     ```R
     ets_model <- ets(oil_ts)
     ```

4. Visualize forecasts:  
   ```R
   plot(forecast(hw_model, h=30))
   ```

## Skills Demonstrated

- Time Series Analysis  
- Predictive Modeling (Holt-Winters, ETS)  
- Data Imputation and Preprocessing  
- R Programming  

## License

This project is licensed under the MIT License. See the `LICENSE` file for more details.
