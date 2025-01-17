# Implementation-of-Logistic-Regression-Using-Gradient-Descent

## AIM:
To write a program to implement the the Logistic Regression Using Gradient Descent.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
```
1.Import the required packages.
2.Read the given dataset and assign x and y array.
3.Split x and y into training and test set.
4.Scale the x variables.
5.Fit the logistic regression for the training set to predict y.
6.Create the confusion matrix and find the accuracy score, recall 7.7.7.7 7.sensitivity and specificity
8.Plot the training set results.
```

## Program:
```
/*
Program to implement the the Logistic Regression Using Gradient Descent.
Developed by: RAKSHITHA DEVI J
RegisterNumber:212221230082  
*/
```
```
#importing packages
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
#reading and displaying dataframe
df=pd.read_csv("Social_Network_Ads (1).csv")
df

#assigning x and y and displaying them
x=df.iloc[:,[2,3]].values
y=df.iloc[:,4].values 

#splitting data into train and test
from sklearn.model_selection import train_test_split
xtrain,xtest,ytrain,ytest=train_test_split(x,y,test_size=0.25,random_state=0)

#scaling values and obtaining scaled array of train and test of x
from sklearn.preprocessing import StandardScaler
sc_x=StandardScaler()
xtrain=sc_x.fit_transform(xtrain)
xtest=sc_x.fit_transform(xtest)

#applying logistic regression to the scaled array
from sklearn.linear_model import LogisticRegression
c=LogisticRegression(random_state=0)
c.fit(xtrain,ytrain)

#finding predicted values of y
ypred=c.predict(xtest)
ypred

#calculating confusion matrix
from sklearn.metrics import confusion_matrix
cm=confusion_matrix(ytest,ypred)
cm

#calculating accuracy score
from sklearn import metrics
acc=metrics.accuracy_score(ytest,ypred)
acc

#calculating recall sensitivity and specificity
r_sens=metrics.recall_score(ytest,ypred,pos_label=1)
r_spec=metrics.recall_score(ytest,ypred,pos_label=0)
r_sens,r_spec

#displaying regression 
from matplotlib.colors import ListedColormap
import matplotlib.pyplot as plt
xs,ys=xtrain,ytrain
x1,x2=np.meshgrid(np.arange(start=xs[:,0].min()-1,stop=xs[:,0].max()+1,step=0.01),
               np.arange(start=xs[:,1].min()-1,stop=xs[:,1].max()+1,step=0.01))
plt.contourf(x1,x2,c.predict(np.array([x1.ravel(),x2.ravel()]).T).reshape(x1.shape),
                            alpha=0.75,cmap=ListedColormap(("pink","purple")))
plt.xlim(x1.min(),x2.max())
plt.ylim(x2.min(),x1.max())
for i,j in enumerate(np.unique(ys)):
    plt.scatter(xs[ys==j,0],xs[ys==j,1],
                c=ListedColormap(("white","violet"))(i),label=j)
plt.title("Logistic Regression(Training Set)")
plt.xlabel("Age")
plt.ylabel("Estimated Salary")
plt.legend()
plt.show()
```

## Output:
## Dataset:
![image](https://user-images.githubusercontent.com/94165326/173839838-a3f6139f-7f8f-40de-9bfd-0fb118e8bbc9.png)

## Predicted y array:
![image](https://user-images.githubusercontent.com/94165326/173839943-dbe2963f-83c8-4e71-9030-67b728ca605e.png)

## Confusion matrix:
![image](https://user-images.githubusercontent.com/94165326/173840037-f7356dea-73f5-4062-ad8a-c3af11a2fc6a.png)

## Accuracy score:
![image](https://user-images.githubusercontent.com/94165326/173840144-ec3e8872-12e5-496e-9b74-ecaa1882a7a4.png)

## Recall sensitivity and specificity:
![image](https://user-images.githubusercontent.com/94165326/173840222-6c8d3228-6d33-4702-9724-1043d5bf15e4.png)

## Logistic Regression graph:
![image](https://user-images.githubusercontent.com/94165326/173840324-a9d9cda8-063f-4a38-b656-3b08b6366d9f.png)




## Result:
Thus the program to implement the the Logistic Regression Using Gradient Descent is written and verified using python programming.

