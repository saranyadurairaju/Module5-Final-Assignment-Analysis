# Pyber Ride Analysis with Pandas & Matplotlib

Matplotlib is a two dimensional plotting library for the Python programming language and its numerical mathematics extension NumPy. It provides an object-oriented API for embedding plots into applications.

* Explicitly create figures and axes, and call methods on them (the "object-oriented (OO) style").
* Rely on pyplot to automatically create and manage the figures and axes, and use pyplot functions for plotting.

Matplotlib consists of several plots like line, bar, scatter, histogram etc. And we can create these wide range of basic charts with few lines of code.

* Hightly customizable
* Visually Stunning
* Display data in detail


## Overview of Project

Pyber is a Python base ride sharing App company. And we have ride and city base data with Ride fare, Type of city, Number of drivers etc. And we would like to find the relationship between Type of City and the Number of riders & drivers. Also we are finding below details with Omar to present the analysis to CEO V. Isualize.

  •	The number of rides for each city type.
  *	The fares for each city type.
  *	The number of drivers for each city type.
  *	The percent of total fares.
  *	The percent of total rides.
  *	The percent of total drivers.
 
### Purpose

We wants to perform the Analysis based on many criterias with Large number of data and then need to present the Visualization of the outcome. For that, Matplotlib will help us create different type of charts with the given data. It will be easy to do the comparison with Charts in Jupyter Notebook and decide how to improve the ride sharing in all types of city. 

Also, from the results we want to suggest some ideas to the CEO to improve the business. 

## Analysis 

Before we start doing our Analysis, we need to setup the depencies Panda and Numpy libraries in our code to work with Data and Calculations. We have to load the file  with the path and use .read function of Panda to read the data. Merging the two data files will help us to work better and bring the results. 

### Summary DataFrame

* Ride count and Sum of Fare, drivers

Since we are dealing with three different type of Cities **Rural, Suburban and Urban**, we are counting the rides, and calculation the sum of fares and drivers using **groupby(), count() and sum()** functions. 

!image

* Average fare, driver

With Total fare, we can find the average fare by dividing it by ride count. Also we can find the average driver fare by dividing total fare by driver count. 

!image

* Below is the Summary dataframe code:

![image](https://user-images.githubusercontent.com/85472349/125236251-43d03100-e2a9-11eb-84a9-84b90df33688.png)

### Multi line plot to show weekly fare for each City Type
	
* Dataframe with Date and Type

As we are focusing to create a weekly fare, we are creating a new Dataframe with **Total fare** for with date & type using groupby() & sum() functions. Then we have to reset the index to look as a proper dataframe.

!image

* Pivot table and Date conversion

We are creating a pivot date from the new dataframe using .pivot() with index, columns & values attribute. 


As we are only interested in date range 2019-01-01 through 2019-04-29, we can use .loc to create a new dataframe with only that particular rows. 


Then we need to set the date column as **datetime** datatype with .index.


* Resample() function by Week('w')

We are using .resample() function to sum up the weekly fare amount of each city type.


* Dataframe to create a plot
 


## Results

Below is the full Pandas code to determine the Pyber Analysis. 

![Pyber_Challenge](.ipynb)

Here are the summary data and line plot for each city type

#### The Summary Data



![image]( .png)


#### The multi line chart


![image](https://user-images.githubusercontent.com/85472349/125233872-171a1a80-e2a5-11eb-823c-7660af7729fd.png)


#### Difference in ride-sharing data amoung cities

* There is a very minimal change in Passing Percentages in the district summary report.

* Same way in the School Summary report, the values are impacted little bit.

* Math and Reading scores by Grade is replaced with NaN for Thomas High School.

* After the changes in Data, there is no impact in Top Performing schools and Score Values. 


## Summary

* There is a very minimal change in Passing Percentages in the district summary report.

* Same way in the School Summary report, the values are impacted little bit.

* Math and Reading scores by Grade is replaced with NaN for Thomas High School.

* After the changes in Data, there is no impact in Top Performing schools and Score Values. 

* But we need to find the right number of Students during every Value calculation is important. 

_Maria and her team can provide a nice and perfect **City School Analysis Report** with Clean Data to the School Board. Hurry!!!_
