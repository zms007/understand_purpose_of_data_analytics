Practical 6 Understand the purpose of data analytics
===============

1.1  	Description
=====
One of the starting points of becoming data scientist is programming skill, this lab guide will be exploring the use of Python programming to perform basic analytics. This lab will be using Anaconda to setup the data analytic environment. In addition to that, this lab guide will also introduce Spyder, Python development IDE and Jupyter notebook.  The same platforms can be used for Artificial Intelligence.  

1.2  	Lab Objective(s)
=====
To setup python programming environment for data analytics 
To use python programming to analyze data 
To use python programming to implement simple AI
1.3  	Grouping Method
This lab guide is to be completed individually.

1.4  	Lab Environment
=====
For this lab, we will be using Windows 10 operating system and 
Ubuntu 24.04 LTS.  

1.5  	Task
==========
1.5.1  	Setting up the data analytic environment on Windows 
=====
1. 	 Anaconda is an open-source solution that allow individual user to setup data analytics and machine learning programming environment easily. It is the toolbox that equips with thousands of open-source packages and libraries. 
2. 	 Download and install Anaconda from the following URL. https://www.anaconda.com/products/individual 
3. 	After downloaded it, install the package. In this lab guide, we are using Windows 10, thus we will be installing the Windows version.  
4. 	In order to test the installation, you can run Python IDE called Spyder from your windows search box.  
5. 	Let’s try to do hello world program using IDE. When you started Spyder you will see the follow UI. The temp.py file is created by default and we can try our python code on it. 
6. 	Let’s try the following hello world code and see the output when we click the green play button at the ribbon above.  
7. 	You will see the output of our code at the right bottom column. This is definitely more convenient than using the command line. 
8. 	You can explore the content of our variables using the right top column. 
Activity: Can you write a program to generate a list of random number. 

Suggested Answer:  
 
import random 
randomlist = [] 
for i in range(0,5): 
n = random.randint(1,30) 
randomlist.append(n) 
print(randomlist) 

1.5.2  	Introduction to Jupyter Notebook
=====
1. 	The Jupyter Notebook is an open-source web application that allows us to create and share documents that contain live code, equations, visualizations and comment text. 
2. 	To start Jupyter Notebook, use the Search Box and enter Jupyter, you will see the following option. 
3. 	After you hit enter, a command prompt will appear. Leave it as it is the back end of your Jupyter notebook. A browser will be started.
4. 	Before you create a new Notebook, you need to set your path right. In this lab guide, we will be using the Desktop. You can start a new notebook
5. 	Then you create new notebook by clicking at the new button at the top right corner.   
6. 	A new Jupyter Notebook will be ready for us to use. We can use it to try our hello world program on it. 
7. 	At the first row, we will make use of it as our text block. Select Heading and enter out Text.
8. 	You will get the following output. Now let’s add a new line so that we can put in out code. Press the “+” button.
9. 	Then you put in the code is the newly created column and press run. You will see the output of our code appended beneath it. 
10. 	As such, we can have our code arrange nicely together with comments and outputs. This is one of the popular tools used by many data analysts and data scientists.  


1.5.3  	Introduction to Linear Regression with Python
=====
1. 	In this section, we will be using linear regression to study the relation between 2 variables also to make prediction based on the linear regression formula that we find.  
2. 	First, we will need to have data. Lets create some dummy data between two variables, x and y. Let’s use the folllowing data. 
 
x = [4,6,9,8,3,18,3,10,5,12,13,8,7] 
y = [95,84,86,87,114,49,105,89,96,76,78,86,85] 
 
3. 	Let’s plot these points on a scatter plot chat to see the relationship. 

import matplotlib.pyplot as plt 
x = [4,6,9,8,3,18,3,10,5,12,13,8,7] 
y = [95,84,86,87,114,49,105,89,96,76,78,86,85] 
plt.scatter(x, y) 
plt.show() 

4. 	Let’s compute the linear regression of this relationship using the following code.
  
from scipy import stats 
slope, intercept, r, p, std_err = stats.linregress(x, y) 
 
5. 	We then display the line with the following function and a for loop.  
 
def myfunc(x): 
  return slope * x + intercept 
 
mymodel = list(map(myfunc, x)) 
 
plt.scatter(x, y) 
plt.plot(x, mymodel) 
plt.show() 

6. 	In order to use the model to do prediction, we just have to supply the x value, and the linear regression will compute the y value. For instance when the value x value is 16,what is the y?  
 
y = myfunc(16) 
print(y) 
 
7. 	 Complete this use case yourself, given that a lemonade hawker found that his sales is better when the average temperature is high. He collected his data for 2 weeks the following are the data.  The hawker would like to estimate the amount that he can sell when the temperature is 28 Celcius. 

temp = [ 24 23 26 22 26 27 30 31 34 35 36 36 34 25]  
sales = [ 80 89 90 70 80 99 89 101 102 110 120 101 89 75] 



1.5.4  	Introduction to Logistic Regression with Python
=====
1. 	In this section, we will be using logistic regression to study the relation between 2 variables also to make prediction based on the formula that we find. The dependent variable is often binary value.  
 
x = [4,6,9,8,3,18,3,10,5,12,13,8,7] 
y = [0,0,1,0,0,1,0,1,0,1,1,0,0] 
 
2. 	If we use linear regression, the model will not work. Therefore we will need to use logistic regression.  

3. 	In order to make use of linear regression, we will need to include library for calculating the logistic regression.  
from sklearn.linear_model import LogisticRegression 
 
4. 	 Then we need to do a transformation to the data into 2 dimensions data. Therefore, we need to do run the following code.  

import numpy as np 
x = np.asarray(x) 
x = x.reshape(-1, 1) 
 
5. 	Next, we need to do the fitting. 

logreg = LogisticRegression() 
logreg.fit(x,y) 

6. 	After fitting, we can use it to do prediction. 

value_x = 5 
print(logreg.predict([[value_x]]))  

Activity: Now that you know the steps, implement it using Python on Jupyter. 


1.6  	Additional Tasks  
=====
Complete this use case yourself, given that a lemonade hawker found that his sales is better when the average temperature is high. He collected his data for 2 weeks the following are the data. The hawker would like to estimate if he can sell more than 100 when the temperature is 29 Celcius. 

temp = [ 24 23 26 22 26 27 30 31 34 35 36 36 34 25]  
sales = [ 80 89 90 70 80 99 89 101 102 110 120 101 89 75] 
sales_more_hundred = [0 0 0 0 0 0 0 1 1 1 1 1 0 0] 

