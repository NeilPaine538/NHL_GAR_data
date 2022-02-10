# Historical NHL Data
This repo contains my updating NHL player stats, including Position-Relative [Game Score](https://hockey-graphs.com/2016/07/13/measuring-single-game-productivity-an-introduction-to-game-score/) above average metrics -- see NHL-GameScore-WAR-data.csv -- and Modified [Point Shares](https://www.hockey-reference.com/about/point_shares.html) -- see modified-point-shares.csv.

Each metric has its own strengths and weaknesses:

MPS is good for explaining "past-looking" value. It has Hockey-Reference's Point Shares as its base, but redistributes league value so that 60 percent goes to forwards, 30 percent to defensemen and 10 percent to goalies (which is in line with the share of league salaries paid to each position group). It also further allocates value such that 40 percent goes to forwards' offense and 10 percent to defensemen's offense (adding up to 50 percent, offense being half the game), while 20 percent goes to forwards' defense, 20 percent to defensemen's defense and 10 percent to goalies (again, adding up to 50 percent on the defense/goaltending side of the game). That gives MPS an internal consistency while still maintaining the simplicity of adding up to roughly match a team's point total for the season. Over the 2009-2021 seasons, the game-weighted sum of players' MPS/GP has a 0.99 correlation with their team's goals-per-game differential, which is higher than the equivalent for Evolving Hockey's [Goals Above Replacement](https://evolving-hockey.com/glossary/goals-above-replacement/) (0.93), my Game Score-based WAR metric (0.89) or Position-Relative Game Score Above Average per game (0.82).

However, MPS performs less well when predicting future team success or failure. The game-weighted sum of players' MPS/GP from the previous season has just a 0.52 correlation with team goal differential per game from the current season, which underscores the need for a metric that focuses more on evaluating persistent performance over time. My research has found that a better metric for this purpose is per-game Game Score -- a statistic originally developed by Dom Luszczyzyn (now of The Athletic) -- with an adjustment for the league's positional average each season. The game-weighted sum of players' Position-Relative Game Score Above Average from the previous season has a correlation of 0.57 with the team's current-season goal differential per-game, which is superior to not just MPS (0.52) but also Game Score WAR (0.55), old-school original Point Shares (0.51) and Evolving-Hockey GAR (0.49). To my mind, this makes Position-Relative Game Score Above Average a good forward-looking complement to a purer value metric like MPS, particularly considering Position-Relative Game Score Above Average contains extra data on 1st vs. 2nd assists, face-offs, shot-blocking, on-ice Corsi and more.

# Historical Elo Data and Playoff Odds

This repo used to contain ratings and projections for each team. The Elo model and forecast has been revamped and will now be [hosted at FiveThirtyEight](https://projects.fivethirtyeight.com/2022-nhl-predictions/).
