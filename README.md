# Project: TMDb movie data analysis
This project's goal is to Investigate a data set. Share and communicate my findings. Below are the steps I took and the analysis performed on the project.

## Table of Contents
<ul>
<li><a href="#intro">Introduction</a></li>
<li><a href="#wrangling">Data Wrangling</a></li>
<li><a href="#eda">Exploratory Data Analysis</a></li>
<li><a href="#conclusions">Conclusions</a></li>
</ul>

<a id='intro'></a>
## Introduction

I have selected the TMDb dataset for this analysis. The dataset was downloaded from 
[here](https://www.google.com/url?q=https://d17h27t6h515a5.cloudfront.net/topher/2017/October/59dd1c4c_tmdb-movies/tmdb-movies.csv&sa=D&ust=1532469042115000) 
and I have the .csv file on my project folder.  

#### Given the following features of this data set
> id, imdb_id, popularity, budget, revenue, original_title, cast, homepage, director, tagline, keywords
> overview, runtime, genres, production_companies, release_date, vote_count, vote_average, release_year, budget_adj, revenue_adj


#### The relevant questions to ask include;
* Which genres are most popular from year to year?
* What kind of properties are associated with movies that has high revenues?

### General Properties of the data
To find the general properties of the movie data, I will be looking at the following
1. What data types the features of the dataset has using the `dtypes` method
2. The number of non null columns for each column using the `info()` method
3. The number of unique values available in each column using the `nunique` method
4. Get more insight as to mean, median, 25 percentile, 50 percentile, and 75 percentile, using the `describe()` method
5. Know the number of rows and columns available on the data set using the `shape` method
6. Calculate the number of null values of each column using the `isnull()` method
7. Check for the sum of duplicate data I have on the dataframe using the `duplicated()` method

### Data Cleaning 
A couple of problems can be observed with this data after accessing the dataset which include
1. Some columns are not useful for our data analysis. They are not required in answering the questions I raised from the dataset
2. The release_date column has a data type of string. For a date column, a data type of datetime object would be better.
3. The dataset contains a lot of null values which can be observed on the following columns `imdb_id`, `cast`, `homepage`, `director`, 
`tagline`, `keywords`, `production_companies`, `genres`, `overview`. 
4. The dataset has one duplicate data

All of the problems listed above woud be fixed to get a better quality data set to work with. This is done subsequently below. 
1. The columns that are not relevant to the questions I want to answer can be dropped. A couple of columns that fall into 
this category include `homepage`, `tagline` and `keywords`
2. Update the data type for `release_date` to datetime
3. Delete rows with null values
4. Delete duplicate data


<a id='eda'></a>
## Exploratory Data Analysis

### Which genres are most popular from year to year?

In order to answer this question, I did some analysis below. I grouped the dataset by `release_year` and `genres`, 
then saved it in a new dataframe `df_grouped_data`. After which I will check for the popularity of this dataframe using describe() method.

### What kind of properties are associated with movies that has high revenues?
Plot a bar chart of release year against the count of movies produced in each year. From the bar chart I can see that 
movie production increased over the years.
