# Linear Regression Model in Python

to see how to apply linear Regression model in Python we start with a simple model ( one independent variable) and we will apply different methods
First let's generate a dataset with random points around a line to make it as simple as possible:

```
%matplotlib inline
import matplotlib.pyplot as plt 
import  numpy as np

state = np.random.RandomState(1)
x = 10 * state.rand(nsample) 
y = 2* x +1 + state.randn(nsample)

plt.scatter(x, y);

```


now build the regression model :

### 1. Using statsmodel

### 2. Using Sklearn

```
from sklearn.linear_model import LinearRegression
model = LinearRegression(fit_intercept=True) # fit_intercept = True is by default we can drop the argument

model.fit(x[:, np.newaxis], y) # the method fit accept a 2D first argument this is why we need newaxis to add a column to the x array

plt.scatter(x, y) # print dataset
y_model = model.predict(x[:,np.newaxis]) # method predict needs 2D argument
plt.plot(x,y_model, color='green', linewidth=1) # plot the represented line
plt.plot() 

```

as we see above we used the points in the data and the predict method to plot the regression line. 
We can use any other set of points, it will give the same result:

```
#xline = np.linspace(0, 10, 1000) 
#yline = model.predict(xfit[:, np.newaxis]) 

plt.scatter(x, y) # print dataset
plt.plot(xline, yline, color='red',linewidth=4)
y_model = model.predict(x[:,np.newaxis]) 
plt.plot(x,y_model, color='green', linewidth=1) 
plt.plot() 

```



### 3. Using stats

### 4. Using Simple matrix inverse
