# Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student
## NAME: S.SANJAY BALAJI
## REGISTER NUMBER: 212223240149
## AIM:
To write a program to implement the the Logistic Regression Model to Predict the Placement Status of Student.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the standard libraries.
2. Upload the dataset and check for any null or duplicated values using .isnull() and .duplicated() function respectively.
3. Import LabelEncoder and encode the dataset.
4. Import LogisticRegression from sklearn and apply the model on the dataset.
5. Predict the values of array.
6. Calculate the accuracy, confusion and classification report by importing the required modules from sklearn.
7. Apply new unknown values.

## Program:
```
/*
Program to implement the the Logistic Regression Model to Predict the Placement Status of Student.
Developed by: S.Sanjay Balaji
RegisterNumber:  212223240149
*/
```
```
import pandas as pd
data=pd.read_csv("C:/Users/admin/Downloads/Placement_Data.csv")
data.head()
```
```
data1=data.copy()
data1=data1.drop(["sl_no","salary"],axis=1)
data1.head()
```
```
data1.isnull()
```
```
data1.duplicated().sum()
```
```
from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data1["gender"]=le.fit_transform(data1["gender"])
data1["ssc_b"]=le.fit_transform(data1["ssc_b"])
data1["hsc_b"]=le.fit_transform(data1["hsc_b"])
data1["hsc_s"]=le.fit_transform(data1["hsc_s"])
data1["degree_t"]=le.fit_transform(data1["degree_t"])
data1["workex"]=le.fit_transform(data1["workex"])
data1["specialisation"]=le.fit_transform(data1["specialisation"])
data1["status"]=le.fit_transform(data1["status"])
data1
```
```
x=data1.iloc[:,:-1]
x
```
```
y=data1["status"]
y
```
```
from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=0)
```
```
from sklearn.linear_model import LogisticRegression
lr=LogisticRegression(solver='liblinear')
lr.fit(x_train,y_train)
y_pred=lr.predict(x_test)
y_pred
```
```
from sklearn.metrics import accuracy_score
accuracy=accuracy_score(y_test,y_pred)
accuracy
```
```
from sklearn.metrics import classification_report
classification_report1=classification_report(y_test,y_pred)
print(classification_report1)
```
```
lr.predict([[1,80,1,90,1,1,90,1,0,85,1,85]])
```

## Output:
![image](https://github.com/SanjayBalaji0/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/145533553/04af9c92-7a52-4be7-870c-123ea5fa26fc)
![image](https://github.com/SanjayBalaji0/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/145533553/66a981c8-c17f-450d-ad4b-c2b849cf5712)
![image](https://github.com/SanjayBalaji0/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/145533553/8edf02ef-3722-4394-9a8f-9e6d97970438)
![image](https://github.com/SanjayBalaji0/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/145533553/1db6bc0b-7be1-4e30-a994-0eadde420d68)
![image](https://github.com/SanjayBalaji0/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/145533553/fd73cc30-90a8-430b-87fc-7fccb6d9b77d)
![image](https://github.com/SanjayBalaji0/Implementation-of-Logistic-Regression-Model-to-Predict-the-Placement-Status-of-Student/assets/145533553/65eb51a7-c1ce-4bef-9329-5fc084c820de)



## Result:
Thus the program to implement the the Logistic Regression Model to Predict the Placement Status of Student is written and verified using python programming.
