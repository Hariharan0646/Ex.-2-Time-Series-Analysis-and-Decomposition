# Ex-02: Time Series Analysis and Decomposition
## NAME : Hariharan S
## REG NO : 2305001009
## Aim
To perform time series analysis and decomposition on the monthly average temperature of a city using Python.

## Objectives
To create monthly temperature time-series data using Pandas.
To visualize the temperature variations using Matplotlib.
To decompose the time series into observed, trend, seasonal, and residual components using the seasonal_decompose() function.
To understand the different components of additive time series decomposition.
## Program
```python
import pandas as pd
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose

# Step 1: Create monthly temperature data
temperature = [
    25, 27, 29, 32, 34, 33,
    32, 31, 30, 29, 27, 25
]

# Step 2: Create date index
dates = pd.date_range(
    start="2025-01-01",
    periods=12,
    freq="ME"
)

# Step 3: Create time series
data = pd.Series(temperature, index=dates)

# Step 4: Display data
print("Monthly Temperature:")
print(data)

# Step 5: Plot original time series
plt.figure(figsize=(10, 5))
plt.plot(data.index, data.values, marker="o")
plt.title("Monthly Average Temperature")
plt.xlabel("Month")
plt.ylabel("Temperature (°C)")
plt.grid()
plt.show()

# Step 6: Decompose the time series
result = seasonal_decompose(
    data,
    model="additive",
    period=12
)

# Step 7: Display decomposition
result.plot()
plt.show()
```
## Output
<img width="335" height="317" alt="image" src="https://github.com/user-attachments/assets/7ab0201b-ca4d-4dde-9bff-1a9811de66c5" />
<img width="841" height="470" alt="image" src="https://github.com/user-attachments/assets/2c0dbbb9-223e-44df-801c-f1e5a65d932c" />
<img width="630" height="469" alt="image" src="https://github.com/user-attachments/assets/6a615dc3-ac69-423c-9d80-330c9fa61e6f" />

## Result
The monthly temperature time series was successfully plotted and decomposed into observed, trend, seasonal, and residual components using Python.
