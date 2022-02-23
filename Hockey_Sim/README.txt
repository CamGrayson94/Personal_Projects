This readme file is meant to give some guidance on the Hockey_Sim project created by Cameron Grayson.

**Note: This project is for recreational purposes only. Please do not attempt to use this for any other purposes.**

This project takes NHL game data (sourced from hockey-reference.com), calculates further insights, 
	and creates a basic game result predictor using logistic regression  using a Python notebook. 

This is a work in progress, so please keep this in mind. The current version was uploaded on 02/23/2022 and contains
	data from 2015. If you don't want to take a look at the Python notebook, here is some info on the data in the
	output Excel sheet:

	Test Features Shape: 	 (308, 15)
	Training Features Shape: (922, 15)
	[[ 47  87]
 	[ 45 129]]


	This tells us that out of 308 predictions, our model predicted 176 correctly, for an accuracy of about 57.1%
	I've randomized the dataset and retrained the model a few times, and the accuracy tends to be between 53% and 57%
	for the most part.

Visualizations are coming soon! 

The filenames are listed below in order from most to least importance:

Hockey_Simluator.ipynb		| This is the Jupyter notebook where column calculations
				  and predictions are made.

game_data_total_2015.xlsx	| This is our output excel sheet with all of our final 
				  data, including predictions.

2015_game_data.xlsx		| This file is filled with sheets for each team's game
				  data as exported from hockey-reference.com


What are we looking at in our output Excel file? I'll tell you!

Prediction_Type will have either 'Test' or 'Train' as its output.
	'Train' means the model was still learning the dataset. This is not a 'real' prediction.
	'Test' means the model is actually making predictions in its final form. These are 'real' predictions.

Prediction represents whether the model predicted a win or a loss. You may notice that these will differ from
	the 'Result' column, even when training. This is because the model will make a prediction and then compare
	with the result to continue building. The value in the prediction column is simply the guess the model  made.

Result = Win or Loss
GP = # Games Played
Date = Date game was played
Home = Home Team
Vistors = Visiting Team
GF = Goals For
GA = Goals Against
Goal_Diff = Goal Differential for the entire season to that point.
W = Total season Wins
L = Total season Losses
OTL = Total season  Overtime Losses
Points = Total season Points. In hockey, Win is 2 points, Loss is 0 points, Overtime Loss is 1 point.
Point_perc = Percentage of total points earned over total points possible for the season.
Streak = Win/Loss streak. Positive for Win streak, negative for Loss streak

ss_[column] = This means 'season series.' This is totalled across the season, but only for matchups
	between the two teams playing. For example, the first time the Nashville Predators play
	the St. Louis Blues, the ss_columns will reflect the totals only for that game. The second 
	time the Predators play the Blues, these columns will reflect the totals of those two games,
	and so on.