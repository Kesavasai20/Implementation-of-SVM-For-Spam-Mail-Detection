# Implementation-of-SVM-For-Spam-Mail-Detection

## AIM:
To write a program to implement the SVM For Spam Mail Detection.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import the necessary python packages using import statements.

2.Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

3.Split the dataset using train_test_split.

4.Calculate Y_Pred and accuracy.

5.Print all the outputs.

6.End the Program.

## Program:
```
Program to implement the SVM For Spam Mail Detection..
Developed by: K KESAVA SAI
RegisterNumber: 212223230105 
```
```PY
import chardet
file='spam.csv'
with open (file,'rb') as rawdata:
    result = chardet.detect(rawdata.read(100000))
result

import pandas as pd
data=pd.read_csv("spam.csv",encoding='windows-1252')

data.head()

data.info()

data.isnull().sum()

x=data["v1"].values
y=data["v2"].values

from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=0)

from sklearn.feature_extraction.text import CountVectorizer
cv=CountVectorizer()

x_train=cv.fit_transform(x_train)
x_test=cv.transform(x_test)

from sklearn.svm import SVC
svc=SVC()
svc.fit(x_train,y_train)
y_pred=svc.predict(x_test)
y_pred

from sklearn import metrics
accuracy=metrics.accuracy_score(y_test,y_pred)
accuracy
```
## Output:
## Encoding:
![image](https://github.com/Kesavasai20/Implementation-of-SVM-For-Spam-Mail-Detection/assets/138849303/5307a16e-0dce-4319-82ff-2df61579dcad)

## Head():
![image](https://github.com/Kesavasai20/Implementation-of-SVM-For-Spam-Mail-Detection/assets/138849303/c62f4edc-fe8c-4bb1-903f-3f1fcd6111d7)

## Info()
![image](https://github.com/Kesavasai20/Implementation-of-SVM-For-Spam-Mail-Detection/assets/138849303/db4b39c0-b6bf-4944-bb1c-59d577b25b3c)

## isnull().sum()
![image](https://github.com/Kesavasai20/Implementation-of-SVM-For-Spam-Mail-Detection/assets/138849303/fef69882-3bc5-412e-8206-3c887fb8f73a)

## Prediction of y
![image](https://github.com/Kesavasai20/Implementation-of-SVM-For-Spam-Mail-Detection/assets/138849303/22e27702-2950-4428-aca7-ae37646d326c)

## Accuracy
![image](https://github.com/Kesavasai20/Implementation-of-SVM-For-Spam-Mail-Detection/assets/138849303/aef7454a-0036-4532-a60a-8ee9b5497275)

## Result:
Thus the program to implement the SVM For Spam Mail Detection is written and verified using python programming.
