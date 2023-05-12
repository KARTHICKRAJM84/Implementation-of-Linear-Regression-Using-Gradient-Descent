# Implementation-of-Linear-Regression-Using-Gradient-Descent

## AIM:
To write a program to predict the profit of a city using the linear regression model with gradient descent.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. 
2. 
3. 
4. 

## Program:
```
NAME:KARTHICK RAJ M 
REG NO:212221040073
```
```
import numpy as np
import matplotlib.pyplot as plt
import pandas as pd

data=pd.read_csv("/content/ex1.txt",header=None)

plt.scatter(data[0],data[1])
plt.xticks(np.arange(5,30,step=5))
plt.yticks(np.arange(-5,30,step=5))
plt.xlabel("Population of City (10,000s)")
plt.ylabel("Profit ($10,000)")
plt.title("Profit Prediction")

def computeCost(x,y,theta):
  m=len(y)
  h=x.dot(theta)
  square_err=(h-y)**2
  return 1/(2*m)*np.sum(square_err)
  
data_n=data.values
m=data_n[:,0].size
x=np.append(np.ones((m,1)),data_n[:,0].reshape(m,1),axis=1)
y=data_n[:,1].reshape(m,1)
theta=np.zeros((2,1))

computeCost(x,y,theta)
def gradientDescent(x,y,theta,alpha,num_iters):
  m=len(y)
  J_history=[]

  for i in range(num_iters):
    predictions = x.dot(theta)
    error = np.dot(x.transpose(),(predictions -y))
    descent=alpha*1/m*error
    theta-=descent
    J_history.append(computeCost(x,y,theta))

  return theta,J_history
  theta,J_history = gradientDescent(x,y,theta,0.01,1500)
print("h(x) *"+str(round(theta[0,0],2))+"+"+str(round(theta[1,0],2))+"x1")

plt.plot(J_history)
plt.xlabel("Iteration")
plt.ylabel("$J(\theta)$")
plt.title("Cost frunction using Gradient Descent")

plt.scatter(data[0],data[1])
x_value=[x for x in range(25)]
y_value=[y*theta[1]+theta[0]for y in x_value]
plt.plot(x_value,y_value,color="r")
plt.xticks(np.arange(5,30,step=5))
plt.yticks(np.arange(-5,30,step=5))
plt.xlabel("Population of City (10,000s)")
plt.ylabel("Profit ($10,000)")
plt.ylabel("Profit predictions")

def predict(x,theta):
  predictions=np.dot(theta.transpose(),x)
  return predictions[0]

predict1=predict(np.array([1,3.5]),theta)*10000
print("For population = 35,000, we predict a profit of $"+str(round(predict1,0)))

predict2=predict(np.array([1,7]),theta)*10000
print("For population = 70,000, we predict a profit of $"+str(round(predict2,0)))
```

## Output:
![image](https://github.com/KARTHICKRAJM84/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/128134963/30f04ea4-b9db-46f0-9ba6-4ee23b4d15db)



![image](https://github.com/KARTHICKRAJM84/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/128134963/90fecdc8-7eb5-4fe0-942c-4248b0251c38)




![image](https://github.com/KARTHICKRAJM84/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/128134963/272faec1-7e51-4896-879e-f8afb520a41e)




![image](https://github.com/KARTHICKRAJM84/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/128134963/fd36e06c-2c10-4ee0-853b-faef352b34be)





![image](https://github.com/KARTHICKRAJM84/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/128134963/796f9536-3309-4bce-9a67-203c20b43658)



![image](https://github.com/KARTHICKRAJM84/Implementation-of-Linear-Regression-Using-Gradient-Descent/assets/128134963/14a94a6c-3813-4c9d-8ae8-64db3d2344a7)


## Result:
Thus the program to implement the linear regression using gradient descent is written and verified using python programming.
