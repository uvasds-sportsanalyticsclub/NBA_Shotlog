# NBA_Shotlog
NBA Shotlog Data for the 2016/2017 Season

- There are over 210,000 shots in the data although there is a small number of shots with missing coordinates. 
- The data does not include free throws or shots where the shooter was fouled and missed.
- The x-axis variable (this is the sideline) ranges from 0 to 993, while the y-axis variable (this is the baseline) runs from 0 to 500.
- You can find the coordinates for the rim by looking for plays classified as a "Dunk". This might be useful for calculating distance of a shot.
- The dimensions of an NBA court are 94 feet by 50 feet. 
- Here's a guide to create heatmap using this data: https://www.kaggle.com/bhavishsalia/nba-16-17-heatmaps/notebook
- code for calculating distance:

nba['location_x_feet'] = nba['location_x'] * (94/nba['location_x'].max())
nba['location_x_feet'] = abs(nba['location_x_feet'] - 47)
nba['location_y_feet'] = nba['location_y'] * (50/nba['location_x'].max())
nba['location_y_feet'] = abs(nba['location_y_feet'] - 25)
nba['distance'] = ((nba['location_x_feet'])**2 + (nba['location_y_feet']-47)**2)**.5
