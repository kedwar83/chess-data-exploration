# Chess Data Analysis

## Introduction

### Purpose
The purpose of this analysis is to understand how chess players improve as their skill level increases. The key questions include:
- Do players need to make fewer mistakes relative to a nearly perfect computer or just fewer mistakes than their opponent?
- Do better players adhere more closely to "opening theory," or do they deviate to catch their opponents off guard?
- Do mistakes by one player lead to mistakes by the other, or do they result in precise counterplay?

## Data Features
- **ELO**: Measure of a player's skill level.
- **ECO**: Code system describing the first few moves.
- **PLY**: The number of moves that follow opening theory (1 ply = both white and black move).
- **Average Centi-Pawn Loss**: Average number of pawns lost per move compared to a top engine (100 centipawns = 1 pawn).
- **Blunder**: Major mistake.
- **Mistake**: Minor mistake.
- **Inaccuracy**: Small mistake.

## Pre-Processing
The dataset was initially checked for null or missing values, but none were found. Some data types were converted from object to integer to avoid compiler errors. Overall, the dataset was clean and easy to work with.

## Visualizations and Analysis
- **Correlation Observations**: 
  - There are strong correlations between centi-pawn loss, inaccuracies, mistakes, and blunders since these are subsets of each other.
  - A more interesting observation is the correlation between mistakes made by white and black players. It seems that one player's mistake often leads to a mistake by the other, though it’s unclear whether these mistakes occur close together or are spread out through the game.

- **Rating and Errors**:
  - There is a significant correlation between white and black ratings due to skill-based matchmaking.
  - Surprisingly, there is little correlation between rating and the number of errors. Skilled players, even when matched with other skilled players, do not necessarily make fewer mistakes on average.

- **Opening Theory Adherence**:
  - A line plot shows that both white and black players tend to follow opening theory more closely as their skill increases. However, this trend levels off quickly and becomes noisier at higher skill levels.

- **Opening Move Difficulty**:
  - A scatter plot comparing different opening moves and the associated average centi-pawn loss shows that openings vary significantly in difficulty. Openings difficult for white are usually also difficult for black.

- **Predicting Rating**:
  - Attempting to predict a player’s rating based on various features yielded poor results. This may be due to skill-based matchmaking, where the relative difference in skill between players is more predictive of errors than absolute skill levels.

## Conclusion
The dataset was well-organized but limited in scope. While the analysis confirmed that more skilled players tend to adhere more to opening theory, there was no strong relationship between skill and the frequency of mistakes. Surprisingly, weaker players are relatively proficient in openings. Additionally, the dataset was skewed towards higher-rated players, with an average rating of 1775 compared to the Lichess average of 1500.

## Future Data Considerations
- **Time Control Settings**: Including time control settings would offer insights into how time constraints affect strategy.
- **Time Spent Per Move**: Understanding how much time players spend on each move could reveal deeper strategic decisions.
- **Additional Game Variables**: Factors such as the number of moves, the player's official title, and the type of game conclusion (resignation, checkmate, timeout) would enrich the dataset.

## Sources
1. Classroom demo
2. [Scatterplot using Seaborn in Python](https://www.geeksforgeeks.org/scatterplot-using-seaborn-in-python/)

