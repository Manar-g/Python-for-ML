## Random Numbers in Python
one of the uses of random numbers when learning ML models is to generate a data set of random numbers to work on it.
Examples follows:

### 1. Using built in Random module
seed()
randint()

### 2. Using Random Sampling from NumPy


```
import numpy as np
import matplotlib as plt


state = np.random.RandomState(1)

x = 10 * state.rand(100) 
y = 2* x +1 + state.randn(100)

plt.scatter(x, y);

```
![random dataset Numpy](https://user-images.githubusercontent.com/64541754/156778715-8add9144-0d31-4447-b0a3-9aa4bf68bb3a.png)


in the above example we have:
<span style="color:yellow">np.random.RandomState(1)</span>  To define state to use when generating the data this is to get the same data every time we execute

<span style="color:yellow">x = 10 * state.rand(100)</span>  To define 100 point on the x-Axis 
                          rand() returns random numbers in the interval \[0,1) so multiplied with 10 to get numbers in \[0,10)
other possibilities: randint(0,10,100) to generate 100 integer with values between 0(included) and 10(excluded)
                     state.random_sample(100) to get 100 random numbers in the interval \[0,1) with unifom distrubt
                     state.randn(100) to get 100 numbers with standard normal distrubtion

<span style="color:yellow">y = 2* x +1 + state.randn(100)</span> To define 100 points on the y-Axis so we get 100 2D points 
                                                                one possibility is using the same functions as before
To get random points around a straight line, use the line equation and add random diplacement to each point as follows:
in the example above the random points will be around the line with the equation y = 2x +1
                      Without using rand() we get 100 points exactly on the line with x-value between 0 and 10

