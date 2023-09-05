# Fantacalcio_prediction

The objective of this project is to use a recurrent neural network, specifically a LSTM (Long short-term memory) network, to predict the average vote (the 'average Fanta-Vote') of each player for the current Serie A football season (2023-2024).
The data were taken from Fantacalcio.it and are related to the statistics of each player: goals scored, goals conceded, cautions, expulsions, average vote and average fanta vote.
There are two datasets for each year from the 2017/2018 season to 2022/2023, one related to Serie A data and one related to the most important player of the 5 major European leagues (La liga (Spain), Premier League (England), Ligue 1 (France), Bundesliga (Germany), Serie A (Italy)).
The 12 data were merged using the player's name. 
After merging, only players who have at least the grade in the last two seasons were retained, resulting in a dataset with 267 rows, hence 267 players. 
At this time, it is possible that there are players with missing values during one or more seasons, so an average replacement was applied to each row.


The dataset has been structured for a recurrent neural network in the following way:
- Inputs consist of pairs of columns, where each pair contains 2 out of 6 columns.
- Outputs consist of individual columns, where each output corresponds to one of the 5 remaining columns.
To illustrate this more clearly, let's label the columns from 1 to 6:
- Input: [Column 1, Column 2], Output: [Column 3]
- Input: [Column 2, Column 3], Output: [Column 4]
- Input: [Column 3, Column 4], Output: [Column 5]
- Input: [Column 4, Column 5], Output: [Column 6]
This configuration allows the recurrent neural network to learn patterns and relationships between the pairs of columns and predict the subsequent column's values.
The dataset was split into training and validation datasets before training the model.

After training the model, as previously explained, the same dataset was passed to the model to predict the 7th column, which corresponds to the predicted average Fantasy Football vote for the 2023/2024 season.
