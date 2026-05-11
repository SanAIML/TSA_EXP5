# Ex.No: 05  IMPLEMENTATION OF TIME SERIES ANALYSIS AND DECOMPOSITION
### Date: 11-05-2026


### AIM:
To Illustrates how to perform time series analysis and decomposition on the monthly average temperature of a city/country and for airline passengers.

### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the decomposition process for the required data.
4. Plot the data according to need, either seasonal_decomposition or trend plot.
5. Display the overall results.

### PROGRAM:
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose

data = pd.read_csv('/content/DailyDelhiClimateTest.csv',parse_dates=['date'],index_col='date')

decomposition = seasonal_decompose(data['humidity'], model='additive',period=12)

plt.figure(figsize=(10, 12))

plt.subplot(411)
plt.plot(data['humidity'], label='Humidity')
plt.legend(loc='upper left')
plt.title('Humidity')


plt.subplot(412)
plt.plot(decomposition.trend, label='Trend', color='orange')
plt.legend(loc='upper left')
plt.title('Linear Trend Plot')

plt.subplot(413)
plt.plot(decomposition.seasonal, label='Seasonal', color='green')
plt.legend(loc='upper left')
plt.title('Seasonality Plot')


plt.subplot(414)
plt.plot(decomposition.resid, label='Residual', color='red')
plt.legend(loc='upper left')
plt.title('Residual Plot')
plt.tight_layout()
plt.show()
```

### OUTPUT:
PLOTTING THE DATA:
<img width="560" height="146" alt="image" src="https://github.com/user-attachments/assets/3217d56a-fe79-430e-be83-e1945acaa67a" />

TREND PLOT REPRESENTATION :

<img width="595" height="146" alt="image" src="https://github.com/user-attachments/assets/53f93cb2-7047-4406-863d-5bba45e6343c" />


SEASONAL PLOT REPRESENTATION :
<img width="576" height="146" alt="image" src="https://github.com/user-attachments/assets/7b319b29-e328-4974-94f8-0187a365b4f7" />


RESIDUAL REPRESENTATION:
<img width="629" height="144" alt="image" src="https://github.com/user-attachments/assets/eb5bea8c-30b0-466e-a648-bdbd3dd88e39" />



### RESULT:
Thus we have created the python code for the time series analysis and decomposition.
