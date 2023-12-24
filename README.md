# Fitting Poisson  distribution

## NAME : AVINASH T

## REG NO : 212223230026

# Aim : 

To fit poisson distribution for the arrival of objects per minute from the feeder

# Software required :  

Python and Visual component tool

# Theory:

The Poisson distribution is the discrete probability distribution of the number of events occurring in a given time period, given the average number of times the event occurs over that time period.

![image](https://user-images.githubusercontent.com/104613195/166248326-fd042076-8b0b-40c4-8b11-1d8e8fcb74db.png)

 Conditions for Poisson Distribution:

1. An event can occur any number of times during a time period.
2. Events occur independently. I
3. The rate of occurrence is constant.
4. The probability of an event occurring is proportional to the length of the time period. 
 
# Procedure :

![image](https://user-images.githubusercontent.com/104613195/166251988-d0c53205-6080-4f7b-ae4c-398178586637.png)

# Experiment :

![image](https://user-images.githubusercontent.com/103921593/230282876-f4a5afbf-cac1-4648-a1b0-c78840638a8e.png)

# Program :


```
import numpy as np
import math
import matplotlib.pyplot as plt 
x=[int(i) for i in input().split()]
y=[int(i) for i in input().split()]
N=len(x)
sx=0
sy=0
sxy=0
sx2=0
sy2=0
for i in range(0,N):
    sx=sx+x[i]
    sy=sy+y[i]
    sxy=sxy+x[i]*y[i]
    sx2=sx2+x[i]**2
    sy2=sy2+y[i]**2
r=(N*sxy-sx*sy)/(math.sqrt(N*sx2-sx*2)*math.sqrt(N*sy2-sy*2))
print("The correlation cofficient of %0.3f"%r)
byx=(N*sxy-sx*sy)/(N*sx2-sx**2)
xmean=sx/N
ymean=sy/N
print("The Regression line Y on X is ::: %0.3f + %0.3f (x-%0.3f)"%(ymean,byx,xmean))
plt.scatter(x,y)
def reg(x):
    return ymean+byx*(x-xmean)
x=np.linspace(0,80,51)
y1=reg(x)
plt.plot(x,y1,'r')
plt.xlabel('x-data')
plt.ylabel('y-data')
plt.legend(['Regression Line','Data points'])
plt.show()
```












 # OUTPUT
![image](https://github.com/AVINASH05T/Poisson_distribution/assets/151514286/0b134de5-0b21-4262-bea0-298d02670b9c)



# Results

The Poisson distribution is fitted for the objects arrived from feeder per minute and the data is tested using Chi-square test. 
 
