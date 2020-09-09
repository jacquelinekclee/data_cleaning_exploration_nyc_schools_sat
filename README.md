# Is the SAT Unfair? - NYC School Data Exploration and Linear Regression Project 

# Table of contents

- [Background](#background)
- [The Data](#the-data)
- [Linear Regression and Scatter Plot](#linear-regression-and-scatter-plot)
- [Development](#development)
- [Legality](#legality)

# Background

College Board SAT, the most common college admissions test, has been accused of being biased against certain racial groups and socioeconomic classes on numerous occasions. Since the COVID-19 pandemic, [many higher education institutions are suspending their testing requirements, due to accessibility issues](https://www.collegelifetoday.com/tips/organizing/college-not-requiring-sat/).

With these things in mind, I wanted to find out how much SAT scores vary across students/schools of different demographics and whether or not there is any sort evidence for these claims of the SAT's unfairness. I utilized data from New York City high schools that detail the class of 2012's [SAT scores](https://data.cityofnewyork.us/Education/2012-SAT-Results/f9bf-2cp4) and the [demographics](https://data.cityofnewyork.us/Education/School-Demographics-and-Accountability-Snapshot-20/ihfw-zy9j) of such schools. 

After cleaning the data, creating visualizations and performing exploratory data analysis, and executing an ordinary least squares Linear Regression, I found that there are notable discrepancies among the average SAT score of a school and the socioeconomic status of its students.

[(Back to top)](#table-of-contents)

# Usage

Refer to these Jupyter Notebook viewers to see all the code, tables, and visualizations.
- [Data cleaning](https://nbviewer.jupyter.org/github/jacquelinekclee/data_cleaning_exploration_nyc_schools_sat/blob/master/data_cleaning_sat_ny.ipynb)
- [Visualization/EDA](https://nbviewer.jupyter.org/github/jacquelinekclee/data_cleaning_exploration_nyc_schools_sat/blob/master/viz_eda_sat_ny.ipynb)
- [Linear Regression](https://nbviewer.jupyter.org/github/jacquelinekclee/data_cleaning_exploration_nyc_schools_sat/blob/master/linear_regression_sat_ny.ipynb)

# The Data

For how I cleaned the data, please refer to this [Jupyter Notebook viewer](https://nbviewer.jupyter.org/github/jacquelinekclee/data_cleaning_exploration_nyc_schools_sat/blob/master/data_cleaning_sat_ny.ipynb).

Here are some example visualizations. The barplot shows the distribution of NYC schools' average SAT scores; the center hovers around 1200 out of a maximum score of 2400 and there are several outliers. The boxplot shows how 'frl_percent,' the percent of students at a given school who receive free/reduced lunches, values differ across schools' average SAT scores in the different score ranges.

![boxplot](https://github.com/jacquelinekclee/data_cleaning_exploration_nyc_schools_sat/blob/master/sat_boxplot.png?raw=true)
![barplot](https://github.com/jacquelinekclee/data_cleaning_exploration_nyc_schools_sat/blob/master/frl_barplot.png?raw=true)

Below is an example histograms drawn to compare the SAT score distributions of schools with demographic against each other, as well as the expected nationwide distribution. This example illustrates that NYC schools with predominantly Asian or White students often score at or above the nationwide average. To see the code that created these visualizations and a more in depth explanation of them, refer to this [Jupyter Notebook viewer](https://nbviewer.jupyter.org/github/jacquelinekclee/data_cleaning_exploration_nyc_schools_sat/blob/master/viz_eda_sat_ny.ipynb)

![histogram](https://github.com/jacquelinekclee/data_cleaning_exploration_nyc_schools_sat/blob/master/aw_hist.png?raw=true)

[(Back to top)](#table-of-contents)

# Linear Regression and Scatter Plot

Using scikit-learn to perform linear regression and seaborn to draw scatter plots, I found a decently strong negative correlation between the percentage of Black or Hispanic students at a school and the average SAT score of a school. The percentage of Black or Hispanic students at a school was the independent variable that yielded the lowest root-mean-square error and highest correlation coefficient. This means that this independent variable did the best job in estimating the average SAT score for schools in NYC. For the code and the results of the other linear regressions, please refer to this [Jupyter Notebook viewer](https://nbviewer.jupyter.org/github/jacquelinekclee/data_cleaning_exploration_nyc_schools_sat/blob/master/linear_regression_sat_ny.ipynb). 

![scatterplot](https://github.com/jacquelinekclee/data_cleaning_exploration_nyc_schools_sat/blob/master/bh_scatter.png)

[(Back to top)](#table-of-contents)

# Findings/Conclusion

- Found negative associations between:
    - Percent of Black or Hispanic students at a school and the school's average SAT score (r = -0.72)
    - Percent of students receiving free/reduced lunch at a school and the school's average SAT score (r = -0.70)
- Found a positive association between:
    - Percent of Asian or White students at a school and the school's average SAT score (r = 0.71)
    
These findings do not demonstrate any sort of causation. In other words, these findings do not indicate that the cause for a school's average SAT score is rooted in a school's ethnic breakdown or the income level of its students. 

Nonetheless, such associations and the differences in score distributions are enough to raise concern. The data makes it seem that the SAT does not evaluate all students fairly and that students of a certain socioeconomic class or students at particular schools have an advantage over other students when it comes to the SAT. With colleges being able (and willing) to suspend standardized testing requirements and cases pointing towards how the SAT is biased, it is certainly time for higher education to think about how it evaluates students. But more importantly, it's time for the American education system as a whole to reflect on how it may be exacerbating systemic disadvantages some students face and to enact the appropriate change.

A more detailed conclusion can be found at the end of this [Jupyter Notebook](https://github.com/jacquelinekclee/data_cleaning_exploration_nyc_schools_sat/blob/master/linear_regression_sat_ny.ipynb) (located in this repository. 

# Legality

This personal project was made for the sole intent of applying my skills in Python thus far and as a way to learn new ones. It is intended for non-commercial uses only.

All data was obtained through [Open Data](https://opendata.cityofnewyork.us/), a source that publishes "free public data."

[(Back to top)](#table-of-contents)
