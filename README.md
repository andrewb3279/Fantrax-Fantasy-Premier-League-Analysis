# Fantrax-Fantasy-Premier-League-Analysis
Exploratory data analysis on the 2024-2025 Fantrax Fantasy Premier League season.

## Project Overview
This project analyzes player statistics from the 2024-2025 Premier League season and their relation to Fantrax Fantasy Premier League performance, using Python data science tools.

## Key Questions Addressed
- What statistics correlate with total fantasy points and fantasy points per 90?
- Is the common belief that players who take more set pieces get more fantasy points true?
- Do certain positions tend to score higher in Fantrax Fantasy Premier League than others?
- Can we predict a players points per 90 based on their statistcs?
- Can we predict a players position based on their statistics?

## Dataset
- **Source**: https://www.thedraftsociety.com/2024-25-fantrax-data, https://understat.com/league/EPL/2024
- **Size**: 842 players, 44 statistical columns
- **Features**: Key columns: 'Player', 'Team', 'Pos', 'RkOv', 'FPts', 'PPG', 'ADP', 'Starts', '% Starts', '% SiS', 'PPS', 'Median PPS', 'Median - Mean', 'PP90', 'xPP90', 'xPP90 Δ', 'gPPS', 'gPP90', 'Ceiling', 'Floor', 'GACS%', 'Mins', 'Total SP', 'SPP90', 'SP%', 'SP Reliance%'.

## Technologies & Libraries
- **Python 3.13.5**
- **pandas**, **NumPy** - Data manipulation and analysis
- **matplotlib & seaborn** - Data visualization
- **sklearn** - Machine learning - Preproccessing, models, and evaluation
- **scipy**, **statsmodels** - Statistical testing
- **datetime**

## Results & Key Findings
- Minutes played was the key statistic for total fantasy points
- We were able to develop a regression line that explained 99% of the variance in points per 90 earned: PP90 = 0.04(% Starts) + 0.08(% SiS) - 0.03(Median - Mean) + 0.04(xPP90 Δ) - 2.58(gPPS) + 2.22(gPP90) + 2.23(Ceiling) + 0.96(Floor) + 0.02(GACS%) - 0.06(Total SP) + 0.06(SPP90) + 0.05(SP%) - 0.04(SP Reliance%) + 8.99
- Set pieces accounted for much less in terms of total points than is commonly believed, though we found that being in the top 20% for set pieces taken % does result in a higher points per 90 (p-value = 0.0000000034)
- Over the course of the season, forwards scored 80.49 more total points on average than defenders (p-value = 0.001), and forwards also scored 55.4 more total points on average than midfielders (p-value = 0.0078).
- If we account fort minutes played, forwards outscored defenders by 3.64 PP90 (points per 90) (p-value = 0.001).  Midfielders also outscored defenders by 1.61 PP90 (p-value = 0.001).  Forwards outscored goalkeepers by 3.32 PP90 (p-value = 0.001).  Finally, forwards outscored midfielders by 2.02 PP90 (p-value of 0.001).
- We also found that ghost points, a typical metric used to find high value players, was not highly correlated with fantasy points per 90, with a number of other stats beating the metric.  However, ghost points per start and ghost points per 90 were two of the three most influential predictors in our best regression line.
- We were also able to use supervised learning in combination with Draft Society data to classify player positions at an effective rate.

## Visualizations
The notebook includes 67 visualizations including:
- Distribution plots of key statistics
- Correlation heatmap and correlations between key variables
- Residual plots and confusion matricies

## How to Use
1. Clone this repository
2. Ensure you have the required libraries 
3. Open in Jupyter
4. Run cells sequentially

## Next Steps / Improvements
- If I were to expand on this EDA I would certainly want to add more underlying data: key passes, shots on target, dribbles, tackles, and other more detailed performance metrics to dive into deeper analysis.

## Author
Andrew Booth | M.S. in Data Science Student | andrewb3279@gmail.com | https://www.linkedin.com/in/andrew-booth-600576173/
