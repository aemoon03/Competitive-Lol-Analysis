# Project 3 – Competitive League of Legends Match Analysis 📊

# Introduction
Our dataset consists of information on competitive matches from the tier one league of Legends. The dataset includes relevant columns such as 'league', 'champion', and 'result'. The dataset provides insights into the performance of different champions in competitive matches.The question of our analysis is: "If someone plays Jinx in a competitive League of Legends game in a major region, are they more likely to win?"

Readers of our website should care about this dataset and the question for several reasons, one of them being that Jinx is a popular champion in League of Legends known for her strong late-game damage potential. Our analysis aims to shed light on the effectiveness of Jinx in competitive play specifically in major regions. This information can be useful for professional players, teams, and fans who closely follow the competitive scene and want to gain insights into champion performance trends.

The dataset contains a certain number of rows, but the exact number is not provided in the question. However, the relevant columns for our question are:
1. 'league': Indicates the league in which the competitive match took place.
2. 'champion': Specifies the champion played by a player in the match.
3. 'result': Denotes the outcome of the match, indicating whether the player won or lost.

# Cleaning and EDA
### Data Cleaning
In order to clean the data, we took these following steps: 
1. Remove the summary rows: In this data set, every twelve rows corresponds to one game: ten for each player in the game, and then two for the summary in each team. These rows are not needed for our analysis, so they were filtered and removed from our dataset. 
2. Filter by relevant leagues: In our analysis, we were mainly only intereseted in major leagues, that being the LCK, LEC, LPL, and LCS. Therefore, any games that were not played in those major regions were filtered out and removed from our dataset. 
3. Select relevent columns: After filtering out our data, we only need the columns that are relevant to our query. Therefore, only 'result' and 'champion' are required. 
Our table is as follows: 
```py
print(lol[['champion', 'result']].head().to_markdown(index=False))
```

| champion   |   result |
|:-----------|---------:|
| Gwen       |        1 |
| Jarvan IV  |        1 |
| Syndra     |        1 |
| Jinx       |        1 |
| Nautilus   |        1 |

### Univariate Analysis

<iframe src="assets/univariate.html" width=800 height=600 frameBorder=0></iframe>

The histogram plot displays the frequency distribution of champions in the dataset, showing the popularity of each champion in competitive matches. It reveals that certain champions are more popular than others, indicating that they are played more frequently. However, no specific trends or patterns are apparent from the histogram, suggesting that champion popularity does not follow a distinct pattern in this dataset.
### Bivariate Analysis

<iframe src="assets/bivariate.html" width=800 height=600 frameBorder=0></iframe>

The scatterplot above visualizes the relationship between the "champion" and "winrate" columns. Each point represents a specific champion and its corresponding winrate.

### Interesting Aggregates

```py
print(winrates.head().to_markdown(index=False))
```

| champion   |   result |   Number of Games |   winrate |
|:-----------|---------:|------------------:|----------:|
| Aatrox     |       52 |               120 |  0.433333 |
| Ahri       |      234 |               461 |  0.507592 |
| Akali      |       97 |               197 |  0.492386 |
| Akshan     |        9 |                18 |  0.5      |
| Alistar    |       56 |               124 |  0.451613 |

Our winrate column is aggregated with the champion, in order to find the amount of games played. This is significant, as our hypothesis question relates to winrates, so we must group by champion in order to find their individual total games played, as well as the total games won in order to calculate the winrate. 

# Assessment of Missingness
### NMAR Analysis
### Missingness Dependency 

# Hypothesis Testing 
