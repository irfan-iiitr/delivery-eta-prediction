# Delivery ETA Prediction

This project aims to predict delivery durations for DoorDash orders using historical data and machine learning models. The analysis leverages feature engineering, visualization, and regression techniques to identify key factors affecting delivery times and optimize ETA predictions.

## Dataset

The dataset (`historical_data.csv`) contains order-level information, including:
- **Time Features:** Market ID, order creation and delivery timestamps.
- **Store Features:** Store ID, primary category, order protocol.
- **Order Features:** Total items, subtotal, distinct items, min/max item price.
- **Market Features:** On-shift and busy drivers, outstanding orders.
- **Model Predictions:** Estimated order place and driving durations.

## Features Engineered

- **Datetime Features:** Hour, day of week, weekend, holiday indicator.
- **driver Features:** drivers per order, percent drivers available.
- **Price Features:** Price range, average item price, price volatility.
- **Interaction Features:** Order intensity, delivery difficulty.
- **Delivery Speed:** Historical average delivery time, delivery speed ratio.

## Outlier and Missing Value Handling

- Outliers removed using IQR method for key numerical columns.
- Missing values imputed using median (numerical) and mode (categorical).

## Modeling

- **Linear Regression:** Baseline model for delivery duration prediction.
- **LightGBM:** Gradient boosting model for improved accuracy.

## Results

| Model                | MAE (minutes) | RMSE (minutes) |
|----------------------|---------------|----------------|
| LightGBM             | 7.82          | 10.16          |
| Linear Regression    | 8.11          | 10.52          |

LightGBM outperforms linear regression, capturing complex relationships in the data.

## How to Run

1. Place `historical_data.csv` in the project directory.
2. Open and run `delivery-eta-prediction.ipynb` in Jupyter or VS Code.
3. Follow the notebook for data processing, visualization, and modeling steps.

## Recommendations

- Integrate real-time traffic and weather data for dynamic ETA adjustment.
- Optimize driver allocation and routing based on peak times and market congestion.
- Regularly update models with new data and feedback.
