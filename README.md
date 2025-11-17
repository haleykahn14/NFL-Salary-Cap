# NFL Salary Cap Optimization
A data-centric AI project analyzing NFL player salaries and team performance to determine optimal salary cap allocation strategies for maximizing team success.

### Project Overview
This project investigates how NFL teams can optimize their salary cap spending to maximize wins. Using historical data from 2013-2022, the analysis explores the relationship between salary distribution patterns and team performance. It combines salary cap data with historical data such as previous year win percents and player continuity across years to find the most important factors leading to success.

## Key Question: How should NFL teams distribute their salary cap across their roster to maximize wins?

### Limitations of Sports Modeling

"Best models often explain only about 10%-30% of variance"​ - The Signal and the Noise by Nate Silver​

"For team sports with small sample seaons (NFL, NBA), models often produce R^2 values in the 0.10-0.25 range"​ - Sports Analytics by Benjamin Alamar​

"NFL outcomes contain 'a very high degree of randomness.'"​ - The Difficulty of Predicting NFL Games – Beggs, Bond, Emmonds, et al.​

### Key Findings

Optimal Top-10 Spending: 47.0% of salary cap

Current League Average: 54.6%

Potential Improvement: Teams are over-investing in top players by 7.6%

Expected Impact: Optimal allocation projects to 8.2 wins per 16-game season

The most important features found so far are: Median Salary, Previous Season's Point Differential, Continuity, Salary Gini, Percent of Salary Cap Allocated to Safety, Quartback Continuity, and Percent of Salary Cap Allocated to Tight-End (respectively).

The latest model which incldues these features reached a Test R^2 value of 0.1904, and a Test RMSE of 0.1685 (+ or - 2.70 wins).


### Project Structure
NFL-Salary-Cap/

├── CS3892.ipynb                              # Basic Regression on Positional Salary Cap Spending

├── salary_neural_networks.ipynb              # Neural Network models based on salary data + more

├── merged_salaries_2013_2022_cleaned.xlsx    # Cleaned salary data scraped from salary websites

├── NFL_Salary_By_Position_Group.xlsx         # Spending per positional group per team and win percentage

└── README.md

### Methodology
##### Data Sources

NFL player salary data (2013-2022)
Team performance metrics (wins, win percentages, point differentials)
Salary cap information by season
Position group spending distributions

#### Analysis Approaches

##### Statistical Analysis

Correlation analysis between salary spending patterns and team wins
Polynomial regression modeling
Top-10 player spending optimization


##### Machine Learning Models

The group started with using basic linear regressions for analyzing salary cap percent spent on each positional group, however quickly realized the correlation was too complicated. We then worked on feature engineering from the salary distributions to come up with features such as salary gini, continuity, median salary, point differentials, etc. After some model analysis and comparison, we moved forward with an ensemble model that combined a Ridge Model, a Random Forest Model, and a Gradient Boosting Model.


### Technologies Used

Python 3.x
Pandas - Data manipulation and analysis
NumPy - Numerical computing
Matplotlib/Seaborn - Data visualization
Scikit-learn - Machine learning models
TensorFlow/Keras - Neural network implementation
Google Colab - Development environment

### Getting Started
Prerequisites
bashpip install pandas numpy matplotlib seaborn scikit-learn tensorflow openpyxl
Running the Analysis

Clone the repository:

bashgit clone https://github.com/haleykahn14/NFL-Salary-Cap.git
cd NFL-Salary-Cap

Open the notebooks in Google Colab or Jupyter:

CS3892.ipynb - Start here for the main analysis
salary_neural_networks.ipynb - Neural network models


Ensure data files are in the same directory as the notebooks


### In Progress

1. Classification model using a neural network to predict if a team will make playoffs
2. Experiment with other positional continuity (and potentially head coach continuity)

