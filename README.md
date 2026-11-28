# League of Legends 15-Minute Mark Analysis
This is an analysis on Oracle's 2026 Tier-One League of Legends dataset. We take the statistics at the 15-minute mark, and predict which team will win!

Authors: Khloe Wong, Noah Tung

## Introduction
Welcome to Summoner's Rift! League of Legends (LoL) is a multiplayer online battle arena (MOBA) game developed by Riot Games that has 2 teams of 5 playing against each other with one main objective: destroy the enemy nexus (the giant crystal in their base) to win the game. We will be working with Oracle’s Elixir dataset of tier-one professional LoL matches from throughout the 2026 season.

This dataset contains key statistics from throughout the game and outcomes for each of the matches, including individual player performances, overall team performances,  with a total of 118,980 rows.

## Data Cleaning and Exploratory Data Analysis

### Data Cleaning
Since not every column is useful for our analysis, we only grabbed the columns that were relevant which for our purposes, consisted mainly of columns pertaining to stats at fifteen minutes in game time. We also are looking strictly at team results so we only grabbed rows in which the ‘position’ was ‘team’. We also noticed that there was a column that indicated whether or not the data for the section was complete or not, completely simplifying the process, so we only extracted data that was indicated to be complete. We also checked how much data we would lose if we only filtered for complete data since there were hundreds of thousands of rows. We only lost about two percent of the data.


|   result |   goldat15 |   csat15 |   xpat15 |   golddiffat15 |   csdiffat15 |   xpdiffat15 |   killsat15 |   deathsat15 |   assistsat15 |
|---------:|-----------:|---------:|---------:|---------------:|-------------:|-------------:|------------:|-------------:|--------------:|
|        0 |      29607 |      482 |    32613 |           1107 |          -14 |          654 |          12 |           13 |            11 |
|        1 |      28500 |      496 |    31959 |          -1107 |           14 |         -654 |          13 |           12 |            11 |
|        1 |      24401 |      555 |    32478 |          -1260 |           33 |        -1997 |           2 |            6 |             2 |
|        0 |      25661 |      522 |    34475 |           1260 |          -33 |         1997 |           6 |            2 |             6 |
|        0 |      26963 |      518 |    33030 |           -223 |          -16 |         -377 |           6 |            9 |             8 |

### Univariate Analysis
The plot below shows the distribution of gold amongst teams at fifteen minutes after game start. It follows approximately a normal distribution with the mean around 25.9k to 26.2k gold. These numbers are hard to interpret since we’ve grouped together teams that won and the teams that lost but is still noteworthy nonetheless.

<iframe
  src="assets/hist_goldat15.html"
  width="800"
  height="600"
  frameborder="0"
></iframe>

### Bivariate Analysis
We saw previously the distribution of gold amongst all teams whether they won or lost and saw that most teams get around 25.9k to 26.2k gold. Even before we see the plot, we expect that teams that won should on average get more gold than teams that lost. The plot below shows the distribution of gold amongst teams fifteen minutes after game start, but now separately shows the distribution of gold amongst teams that won their games compared to teams that lost their games. We see that our prediction that teams that win get more gold on average compared to teams that lost is correct as the difference in the means is about 1.7k gold. Both distributions still follow a normal distribution.

<iframe
  src="assets/hist_goldat15_winloss.html"
  width="800"
  height="600"
  frameborder="0"
></iframe>

Interesting Aggregates

|   result |   assistsat15 |      csat15 |    goldat15 |   killsat15 |      xpat15 |
|---------:|--------------:|------------:|------------:|------------:|------------:|
|        0 |         60495 | 5.22454e+06 | 2.51298e+08 |       39277 | 3.11679e+08 |
|        1 |         90939 | 5.444e+06   | 2.68164e+08 |       59208 | 3.25026e+08 |

Assessment of Missingness
NMAR Analysis

Missingness Dependency
Hypothesis Testing

Framing a Prediction Problem

Baseline Model

Final Model

Fairness Analysis (Do later)
