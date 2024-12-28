# Linear-Regression-Models
Implimenting Regression Model by using Python. First of all, we will try to implement OLS procedure
without using any built-in function
```python
import matplotlib.pyplot as plt
import numpy as np
import pandas as pd
```
## Load data from a file manually
```python
data = np.loadtxt('housing.txt', delimiter=',', skiprows=1, dtype=str)
```

## Scatter Plot

``` python
font1 = {'family':'serif','color':'blue','size':15}
font2 = {'family':'serif','color':'darkred','size':10}

plt.plot( 'size', 'price', data=df, linestyle='none', marker='x', c='green', markersize=8)
plt.xlabel("Size ($feet^2$)", fontdict = font2)
plt.ylabel("Price (in 1000s of dollars)", fontdict = font2)
plt.title('Housing Prices (Portland)', loc = 'left', fontdict = font1)
plt.grid()
plt.show()
```
<img width="431" alt="LR-1" src="https://github.com/user-attachments/assets/40c50d35-0027-462e-8f56-8cffbd353473" />

``` python
x = df['size'].values
y = df['price'].values
# calculate mean of x & y using an inbuilt numpy method mean()
mean_x = np.mean(x)
mean_y = np.mean(y)
[128]: # total no.of input values
m = len(x)
# using the formula to calculate theta_1 & theta_1
numer = 0
denom = 0
for i in range(m):
numer += (x[i] - mean_x) * (y[i] - mean_y)
denom += (x[i] - mean_x) ** 2
theta_1 = numer / denom
theta_0 = mean_y - (theta_1 * mean_x)
print (f'theta_1 = {round(theta_1, 3)} \ntheta_0 = {round(theta_0, 3)}')
# calculating line values x and y
yhat = theta_0 + theta_1 * x
plt.plot(x, yhat, color='red', label='Regression Line')
plt.scatter(x, y, marker='x', c='green', label='Actual data points')
plt.vlines(x, yhat, y, color='b')
plt.xlabel("Size ($feet^2$)", fontdict = font2)
plt.ylabel("Price (in 1000s of dollars)", fontdict = font2)
plt.title('Housing Prices (Portland)', loc = 'left', fontdict = font1)
plt.legend()
plt.grid()
plt.show()
```
<img width="422" alt="LR-2" src="https://github.com/user-attachments/assets/253c416e-db53-49c5-9bfc-0e6827eb3c82" />
