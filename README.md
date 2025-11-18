# Ex.No: 03   COMPUTE THE AUTO FUNCTION(ACF)
Date: 02/09/2025

### AIM:
To Compute the AutoCorrelation Function (ACF) of the data for the first 35 lags to determine the model
type to fit the data.
### ALGORITHM:
1. Import the necessary packages
2. Find the mean, variance and then implement normalization for the data.
3. Implement the correlation using necessary logic and obtain the results
4. Store the results in an array
5. Represent the result in graphical representation as given below.
### PROGRAM:
```
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
from statsmodels.graphics.tsaplots import plot_acf

# Load the dataset
file_path = ("C:\\Users\\admin\\Downloads\\Netflix_stock_data.csv")  # Replace with your file path
data = pd.read_csv(file_path)

# Convert 'Date' column to datetime format
data['Date'] = pd.to_datetime(data['Date'])
data.set_index('Date', inplace=True)

# Select the column for ACF (Close price used for time series)
close_price = data['Close']

# Compute and plot ACF for the first 35 lags
plt.figure(figsize=(10, 6))
plot_acf(close_price, lags=35, alpha=0.05)   # 35 lags + confidence interval
plt.title('AutoCorrelation Function (ACF) for Netflix Stock Close Price')
plt.xlabel('Lags')
plt.ylabel('ACF Value')
plt.grid(True)
plt.show()

```


### OUTPUT:

<img width="951" height="612" alt="image" src="https://github.com/user-attachments/assets/b3a1ec49-b9a5-4ead-bfd1-297e94150eb7" />


### RESULT:
        Thus we have successfully implemented the auto correlation function in python.
