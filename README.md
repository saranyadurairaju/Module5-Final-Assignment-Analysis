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

  *	The number of rides for each city type.
  *	The fares for each city type.
  *	The number of drivers for each city type.
  *	The percent of total fares.
  *	The percent of total rides.
  *	The percent of total drivers.
 
### Purpose

We wants to perform the Analysis based on many criterias with Large number of data and then need to present the Visualization of the outcome. For that, Matplotlib will help us create different type of charts with the given data. It will be easy to do the comparison with Charts in Jupyter Notebook and decide how to improve the ride sharing in all types of city. Also, from the results we want to suggest some ideas to the CEO to improve the business. 

## Analysis 

Before we start doing our Analysis, we need to setup the depencies Panda and Numpy libraries in our code to work with Data and Calculations. We have to load the file  with the path and use .read function of Panda to read the data. Merging the two data files will help us to work better and bring the results. 

### Summary DataFrame

**Ride count and Sum of Fare, drivers**

Since we are dealing with three different type of Cities **Rural, Suburban and Urban**, we are counting the rides, and calculation the sum of fares and drivers using **groupby(), count() and sum()** functions. 

![image](https://user-images.githubusercontent.com/85472349/126057526-e459c1d1-bacf-463b-ae5a-a42b06b266e9.png)

**Average fare per ride & per driver**

With Total fare, we can find the average fare by dividing it by ride count. Also we can find the average driver fare by dividing total fare by driver count. 

![image](https://user-images.githubusercontent.com/85472349/126057568-e3135733-4b35-4b51-ad29-20d8fa6a90e8.png)

**Below is the Summary dataframe code**

![image](https://user-images.githubusercontent.com/85472349/126057614-c4e300de-9776-4179-ab4b-ad5fcb7e9b08.png)

### Multi line plot to show weekly fare for each City Type
	
**Dataframe with Date and Type**

As we are focusing to create a weekly fare, we are creating a new Dataframe with **Total fare** for with date & type using groupby() & sum() functions. Then we have to reset the index to look as a proper dataframe.

![image](https://user-images.githubusercontent.com/85472349/126057643-14e22f15-520c-4c9d-800f-fc0d47f47913.png)

![image](https://user-images.githubusercontent.com/85472349/126057653-e28bc393-0abe-4d05-bc83-94f97beefa8b.png)

**Pivot table and Date conversion**

We are creating a pivot date from the new dataframe using .pivot() with index, columns & values attribute. 

![image](https://user-images.githubusercontent.com/85472349/126057665-cedd6039-6994-447c-8a11-13d59639e527.png)

As we are only interested in date range 2019-01-01 through 2019-04-29, we can use .loc to create a new dataframe with only that particular rows. 

![image](https://user-images.githubusercontent.com/85472349/126057673-d8891a26-317c-46ef-a0e3-376ce92402a4.png)

Then we need to set the date column as **datetime** datatype with .index.

![image](https://user-images.githubusercontent.com/85472349/126057684-0e5b8ba3-e880-4289-b48e-c081bf7b45e7.png)

**Resample() function by Week('w')**

We are using .resample() function to sum up the weekly fare amount of each city type.

![image](https://user-images.githubusercontent.com/85472349/126057692-589f35c3-cec1-4fd9-a82f-5d1561a6514b.png)

**Dataframe to create a plot**
 
![image](https://user-images.githubusercontent.com/85472349/126057711-ceb2e7b3-bdfe-4740-b8a7-1f29c55757c1.png)

## Challenges

Comparing the right data and creating a perfect chart matters a lot when we are doing a Analysis with Matplotlib. With all those trial and checking the data properly, made us create a perfect result for the presentation.

## Results

Below is the full Pandas Matplotlib code to determine the Pyber Analysis. 

![Pyber_Challenge](https://github.com/saranyadurairaju/Module5-Final-Assignment-Analysis/blob/main/PyBer_Challenge.ipynb)

Here are the summary data and line plot for each city type

#### The Summary Data

![Summary_Data](https://github.com/saranyadurairaju/Module5-Final-Assignment-Analysis/blob/main/Summary_df.png)

#### The multi line chart

![Multi_line_chart](https://github.com/saranyadurairaju/Module5-Final-Assignment-Analysis/blob/main/analysis/PyBer_fare_summary.png)


#### Difference in ride-sharing data amoung cities

Below are the conclusion or points we can make out of our two results:

* The total rides and drivers counts are always high in Urban, low in Rural and moderate in Suburban.

* As the total fares are proportionate to the ride, driver counts, its high in Urban, low in Rural and moderate in Suburban.

* If we consider only Rural area, the Average fare per ride and Average fare per Driver is high as the total ride and drivers are less. 

* But in Urban area, the Average fare per ride and Average fare per Driver is low as the total ride and drivers are high. 

* As expected its moderate in Suburban and proportionate to the counts. 

* But Average Fare per ride in Rural(high) and Average Fare per Driver in Urban(low) is not good for the business. 

* Either the rider or the driver will struggle in those cases. So, using our Analysis we need to find some solution for that. 

## Summary

Below are the business suggestion for Pyber to improve the access & affordability:

**Since the driver counts are very high in Urban, we have to increase the total rides with the following strategies and distribute the drivers properly among all areas.**

	1.Reduce Driver Downtime 
	2.Allow scheduled pick-ups 
	3.Create Loyalty Programs 
	4.Customize the Experience
	5.Own Local Event Recommendations
	
**Also the same way in the Rural area, we have to increase the total rides and the drivers counts are fine considering the size of the area.**
 
	1.Inform rural residents and potential riders about the ride services 
	2.Tie up with local partnerships to increase awareness
	3.Rebrand already-existing transit/transportation services 
	4.Attract potential riders with offers and special programs
	5.Hire contract drivers

* So, if we follow the above methods, the total fare for the ride will be optimal for the riders also drivers will get enough money for their work.  

_We have presented **Pyber ride sharing Analysis Report** with a perfectly clear data, chart and suggestions for business, which indeed satisfied the CEO. Happy riding !!!_
