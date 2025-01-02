# Energy Consumption Forecasting

## Project Overview
This project aims to forecast power consumption across three zones using advanced deep learning models. By leveraging time-series data and incorporating temporal dependencies, the project demonstrates how models like LSTM and GRU can effectively predict future energy demand.

The dataset was preprocessed to include lagged features, rolling statistics, and temporal attributes, enabling the models to capture complex patterns and seasonal variations.

---

## Results

### Model Performance
1. **LSTM Model**:
   - **Test Loss (MSE)**: 0.001459
   - **Test MAE**: 0.0290
   - Captured trends effectively but exhibited slight overfitting during training.

2. **GRU Model**:
   - **Test Loss (MSE)**: 0.000783
   - **Test MAE**: 0.0209
   - Outperformed LSTM, delivering more accurate and consistent predictions with fewer residual errors.

| Metric             | LSTM           | GRU            |
|--------------------|----------------|----------------|
| **Test Loss (MSE)**| 0.001459       | 0.000783       |
| **Test MAE**       | 0.0290         | 0.0209         |

---

### Visual Insights
- **Predicted vs. Actual Values**:
  - GRU aligned more closely with actual trends compared to LSTM.
  - Both models captured general trends, but GRU handled variability better.
  
- **Residual Analysis**:
  - Residuals were centered around zero for both models.
  - GRU exhibited tighter distributions with fewer outliers, indicating superior accuracy.

---

## Methods

1. **Feature Engineering**:
   - Extracted temporal features (`Hour`, `Day`, `Weekday`, `Month`).
   - Created lagged features and rolling statistics for past time steps to capture temporal dependencies.

2. **Data Scaling**:
   - Applied `MinMaxScaler` to normalize features and targets for improved model convergence.

3. **Sequence Preparation**:
   - Used sliding window sequences of 24 time steps for training.
   - Output targets correspond to the subsequent time step for multi-zone forecasting.

4. **Modeling**:
   - Built and trained LSTM and GRU models using deep learning frameworks.
   - Employed early stopping to prevent overfitting and ensure generalization.

---

## Conclusion
The GRU model emerged as the optimal choice for forecasting power consumption due to its:
- Superior accuracy (lower MSE and MAE).
- Better ability to capture trends and fluctuations in power consumption.
- Fewer residual errors and better generalization.

Future work can integrate additional external factors, such as holidays, weather anomalies, or energy price data, to further refine predictions.

---
