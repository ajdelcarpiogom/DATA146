# Project 1

### Package - A namespace that organizes a set of related classes and interfaces. It's very similar to different folders on your computer.
### Library - Contains data types that would normally be considered part of the “core” of a language, such as numbers and lists.

### In order to install a package and make it accessible to my workspace in Python, we must do import() and library()
  #### import numpy as np
  #### library(np)
  
  #### import pandas as pd
  #### library(pd)


### DataFrame - The most common structured API and represents a table of data with rows and columns.
  ### A library of functions that specifically make it easier to work with dataframes is pandas.
  
### In order to read a file in its remote location within the file system of your operating system, we will use read_csv()
  ### For example:
  #### data = data.read_csv("file")
  
  
### The read() method returns the specified number of bytes from the file. Default is -1 which means the whole file.

### Data that is saved as a file in a different type of format requires a particular argument in order to inform Python that our data is in a different format, we need to add an additional argument following the path_to_data object. We can use the \t specification if separated by tabs.

### Also, provide an example that describes the dataframe you created:
  #### cars = {"Make": ["Honda", "Toyota", "Ford"], "Price": [22, 25, 28]}
  #### df = pd.DataFrame(cars, columns = ["Make", "Price")
  
### In order to determine rows and columns in a dataframe, we can do:
  #### df.shape() in order to get the number of rows and columns.
  #### len(df) in order to get the number of rows.
  #### len(df.columns) in order to get the number of columns.
  
### Other terminology for a row and a column can be "tuple".

#### file = open("gapminder.tsv")
#### readf = pd.read_csv(file, delimiter = "\t")
#### readf = pd.DataFrame(readf)
#### readf["year"].min()
  #### 1952
#### readf["year"].max()
  #### 2007
#### readf["year"]

### The intervals are 5 years in the gapminder.tsv file.
### I would add 2012 and 2017 to the raw data.

#### readf.loc[readf["year"] == 1952].count()

### Here we see that 142 outcomes are in every year, so adding these two years would output 284 more outcomes.

### Below, the results show that Rwanda had the lowest life expectancy in 1992. The health quality of Rwanda has been relatively low as well as the maternal mortality ratio due to poverty, poor roads rural areas, and misleading traditional beliefs and inadequate knowledge on pregnancy related issues.
  ### 23.599
#### readf["country"].loc[readf["lifeExp"] == 23.599]
#### readf["year"].loc[readf["lifeExp"] == 23.599]


### Using the data frame you created by importing the gapminder.tsv data set, multiply the variable pop by the variable gdpPercap and assign the results to a newly created variable.
#### readf["product"] = readf["pop"] * readf["gdpPercap"]

### Then subset and order from highest to lowest the results for Germany, France, Italy and Spain in 2007. 
#### subs = readf.loc[readf["year"] == 2007]
#### subs = readf.loc[readf["year"] == 2007]
#### subs = subs[subs["country"].isin(["Spain", "Germany","Italy","France"])]
#### subs = subs.sort_values(by = "product")
#### subs

### & - AND, sets each bit to True or 1 if both bits are True
#### a = 3
#### b = 2
#### if a == 3 & b == 2:
####  return a*b
### == - EQUALS, sets bit to True or False if the bits

### | - OR, sets each bit to True or 1 if one of two bits is True
#### a == b || a == 3
 
### ^ - XOR, sets each bit to True or 1 if only one of two bits is True
#### a == b ^ a == 3


### .iloc gets rows (or columns) at particular positions in the index (so it only takes integers) whereas .loc gets rows (or columns) with particular labels from the index.

### API stands for Application Programming Interface. An API is a software intermediary that allows two applications to communicate with each other. 
### API acts as a messenger that delivers your request to the provider that you're requesting it from, and then delivers the response back to you.

  #### pip install requests
  #### import requests
  #### response = requests.get("http://api.open-notify.org/this-api-doesnt-exist")
  #### print(response.status_code)


### The function .apply() takes a function as an input and applies this function to an entire DataFrame. It serves as an alternative to using a loop to iterate over a the entire DataFrame making it easier and ensuring that it was applied to the whole df. 

### Instead of using .iloc, we can use other approaches in order to select, filter and assign a subset number of variables to a new data frame by:
### Selecting a single or multiple columns by label
  ### df.[string]
  ### df.[list of strings]
### Selecting a single or multiple rows by label
  ### df.loc[string]
  ### df.loc[list of strings]
### Select a single row by position
  ### df.iloc[integer]
  ### df.iloc[list of integers]
### Selecting rows and columns simultaneously
  ### df.loc[row_labels, col_labels]
  ### df.iloc[row_pos, col_pos]
  
  
  
