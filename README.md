# Ex.No: 05  IMPLEMENTATION OF TIME SERIES ANALYSIS AND DECOMPOSITION
### Date: 30/09/2025
## Name : Dheena Darshini Karthik Dheepan
## Regno: 212223240030


### AIM:
To Illustrates how to perform time series analysis and decomposition on the monthly average temperature of a city/country and for airline passengers.

### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the decomposition process for the required data.
4. Plot the data according to need, either seasonal_decomposition or trend plot.
5. Display the overall results.

### PROGRAM:
~~~
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose

# Step 1: Load the dataset,Convert 'date' column to datetime format,Set it as index
data = pd.read_csv('tsla_2014_2023.csv', parse_dates=['date'], index_col='date')

# Step 2: Perform seasonal decomposition using the 'close' column
# Using period=5 for weekly seasonality (5 trading days)
decomposition = seasonal_decompose(data['close'], model='additive', period=5)

# Step 3: Plot the decomposition
plt.figure(figsize=(10, 12))

# Original Data
plt.subplot(411)
plt.plot(data['close'], label='TSLA Close Price')
plt.legend(loc='upper left')
plt.title('Original Time series data: TSLA Close Price')

# Trend Plot
plt.subplot(412)
plt.plot(decomposition.trend, label='Trend', color='orange')
plt.legend(loc='upper left')
plt.title('Linear Trend plot')

# Seasonal Plot
plt.subplot(413)
plt.plot(decomposition.seasonal, label='Seasonal', color='green')
plt.legend(loc='upper left')
plt.title('Seasonality plot')

# Residual Plot
plt.subplot(414)
plt.plot(decomposition.resid, label='Residual', color='red')
plt.legend(loc='upper left')
plt.title('Residual plot')

plt.tight_layout()
plt.show()
~~~

### OUTPUT:
FIRST FIVE ROWS:
<img width="2585" height="780" alt="Screenshot 2025-09-30 091238" src="https://github.com/user-attachments/assets/b22f99ad-a943-4556-81c9-194ffa16de1a" />

PLOTTING THE DATA:

ORIGINAL TIME SERIES DATA:
<img width="1978" height="594" alt="Screenshot 2025-09-30 091445" src="https://github.com/user-attachments/assets/1886e422-ffcd-4cb6-90db-2a14d93ebdbb" />

SEASONAL PLOT REPRESENTATION :
<img width="1974" height="601" alt="Screenshot 2025-09-30 091508" src="https://github.com/user-attachments/assets/545e489e-b096-4aa7-919a-adb02ad5fa3d" />


LINEAR TREND PLOT REPRESENTATION :
<img width="1962" height="594" alt="Screenshot 2025-09-30 091457" src="https://github.com/user-attachments/assets/c7f54ae6-37a7-49fc-8bd0-371908d43c28" />

RESIDUAL PLOT REPRESENTATION:
<img width="1974" height="590" alt="Screenshot 2025-09-30 091517" src="https://github.com/user-attachments/assets/e79a9e4b-3921-4ce0-a5e1-fd1c1844bdcd" />



### RESULT:
Thus we have created the python code for the time series analysis and decomposition.
