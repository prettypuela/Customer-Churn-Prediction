# Nigeria Food Price Prediction and Inflation Analysis

## Project Overview
This project analyzes historical food prices in Nigeria, focusing on rice prices and inflation trends. It also uses a simple linear trend model to forecast rice prices over 12 future periods at 30-day intervals.

## Objectives
- Examine historical rice prices in Nigeria.
- Analyze rice inflation trends.
- Visualize changes in rice prices over time.
- Build a simple forecasting model.
- Evaluate the model using historical test data.

## Dataset
The dataset was obtained from the World Bank's Nigeria Monthly Food Price Estimates.

## Tools and Libraries
- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn

## Methodology
1. Loaded and inspected the dataset.
2. Checked missing values and duplicate records.
3. Converted the date column to datetime format.
4. Analyzed and visualized historical rice prices and inflation.
5. Built a linear trend model to forecast future rice prices.
6. Split the historical data chronologically into 80% training data and 20% testing data.
7. Evaluated predictions using Mean Absolute Error (MAE) and Root Mean Squared Error (RMSE).
8. Compared predicted prices with actual prices.

## Evaluation Results
- MAE: approximately 2,503.50
- RMSE: approximately 2,803.21

The model underestimated actual rice prices during the displayed test period. These results indicate that the simple linear trend model has limitations.

## Conclusion
The project demonstrates how Python can be used to analyze historical food prices, visualize trends, and create a basic price forecast. The predictions should be interpreted cautiously because the model does not account for all factors affecting food prices in Nigeria.

## Limitations and Future Improvements
Future work could explore more advanced forecasting methods and additional economic variables to improve prediction performance.
