# Capstone

## Problem Statement

Right-to-Work laws in the United States have gained attention in the past few years, due to the controversial nature of their claimed benefits and effects. A Right To Work law means that no person can be compelled to join or not to join a labor union as a condition of employment. This is claimed to prevent workers from being denied work at certain companies if they are not union-affiliated. However, it also lessens the power of unions in these states, with many employers being allowed the ability to fire at will.     
<br>
Despite less than savory beginnings, unions in the United States offer workers safety and protection from employers who are concerned with profit over safety. This is especially noticeable in industries with higher than usual risks. The benefit of unions on workers' overall safety and benefits is well documented.    
In many states, fatalities have risen as a result of weakened labor laws. Less powerful workers' groups also correspond to lower wages in states where workers lack the power of collective bargaining.    
<br>
This project will explore the relationship between union membership, worker safety (defined as fatality count) and the poverty rate of states, focusing on those employed in the construction industry. Using historical data (2010-2017) on union membership, individual states' fatality counts, and wages (fro all industries and for the construction industry), we will predict whether a state will fall above or below the poverty line for each year, to establish the clear correlation between these factors.

## Relevant Files

* [Datasets](https://github.com/rows317/Capstone1/tree/master/Data)
* [Code Notebooks](https://github.com/rows317/Capstone1/tree/master/code)
* [Presentation]

## Executive Summary

As with any predicative model, one must begin with data collection. Using the United States Bureau of Labor Statistics website, the US Census website, and Governing.com, we were able to collect necessary data for our desired population. Given 2/3 of these are government websites, it is safe to assume their accuracy. The third website drew from these websites to create more detailed analysis graphs.<br>    
We encountered an issue early on. When attempting to further group our population statistics by key demographics such as race, gender, etc., we discovered there is little to no reliable data for these subsets of the employed populations in the areas of interest. Therefore, we chose to use an industry subset: the construction industry. Our desired data was: total population employed, population employed in the construction industry; mean & median annual wage for total employed population, mean & median annual wage for population employed in the construction industry; union membership rates for population employed in all industries, union membership rates for population employed in the construction industry; total fatalities in all industries, total fatalities in the construction industry; and, finally, the percentage of population below the country poverty threshold. This data was gathered for all 50 US States and compiled into tables by year. <br>  
Data cleaning was an extensive process. Many of these tables were available only in HTML format. Using the text editor Atom, we were able to manipulate these tables into a more readable form, and then download them into Jupyter notebook. After importing all data, it was necessary to turn them into comprehensive dataframes, removing any data not relevant to our model, ensuring all numerical values were integers (to prevent issues in the later modeling stage), and ensuring uniform index across all tables of information. This uniform index was state name, making the merging of multiple dataframes seamless. Fortunately, due to our sources' scrutiny when compiling the original data, we encountered no missing values. There was no need for questionable imputation, thus preserving the quality of our data.
<br>
Analyzing the correlations between our feature variables, we found high correlations (both negative and positive) in many of the obvious areas (e.g. - average annual wage across all industries is negatively correlated with percentage of population below the poverty threshold), there were also some standouts that supported our initial expectations. There was a noticeable positive correlation between total union membership percentage and average annual wages across *all* industries. Also, a negative correlation between construction industry union membership percentage and percentage of population below the poverty line supports our hypothesis that there is a clear relationship between union membership in this single industry and the overall poverty rate.
<br>
We trained our model on these factors, using poverty rate as a binarized column (dependent upon the US rate for the given year in which the data was analyzed) as our y variable. After building a successful model on our first dataset for 2010 (success being measured as an accuracy rate of ~85%), we tested this model on the remaining seven years of data, to see just how accurately it would carry over to other years.

## Conclusions/Recommendations

Because poverty rate of a given state is such a multilayered statistic, it is impossible to expect a model with fewer than 100s of features, made up of precisely gathered data, to predict it with total accuracy. Because our model focuses on particular datapoints (union membership and wages for population within the construction industry) to show that a prediction is possible based on these factors realtion to poverty rate, this accuracy rate is very acceptable.    
That accurate predictions of poverty threshold of states can be made using our chosen features, shows a clear relationship.

