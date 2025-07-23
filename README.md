
i all, this is a Data Analytics Project with A/B testing

# Project Objective
The purpose of this project is to learn how to apply A/B testing and understand if company should move gate from level 30 to level 40 or keep gate on level 30 by examining which version is more popular for users.

# Technologies
- Python 
- Jupyter Notebook
- Pandas
- NumPy
- Matplotlib
- Seaborn
- StatsModels
- SkiPy

# Data 
The data is from 90,189 players that installed the game while the AB-test was running from Kagle. The variables are:
**userid**: A unique number that identifies each player.
**version**: Whether the player was put in the control group (gate_30 - a gate at level 30) or the group with the moved gate (gate_40 - a gate at level 40). When a player installed the game, he or she was randomly assigned to either.
**sum_gamerounds**: the number of game rounds played by the player during the first 14 days after install.
**retention_1**: Did the player come back and play 1 day after installing?
**retention_7**: Did the player come back and play 7 days after installing?


# Analysis 
- Check there are not missing values
- Check the distribution is uniform 
- Performed statistical anlysis - The chi2 test of equal frequencies
- Checked there isn't overlaps
- Calculated conversion rate for each group
- Calculated average engagement  
- Calculated percentage of active users
- Performed Levene’s test of the equality of variances
- Discovered the normality of the distribution
- Compute p-value by Mann-Whitney U test
- Calculated bootstrapping
- Visualized plot with confidence intervals for two grous 

# Conclusion
The experiment compared two groups of players based on the position of a paywall (gate_30 vs gate_40) in the game Cookie Cats.

Although the chi-square test indicated a statistically significant difference in group sizes (p = 0.0086), the actual distribution (50.4% vs. 49.6%) suggests that the groups are practically balanced. Such a small difference is considered acceptable for an A/B test.

### Retention on Day 1 and Day 7:
Users in the gate_30 group show slightly better retention:
- Day 1: 44.8% (vs. 44.2% in gate_40)
- Day 7: 19.0% (vs. 18.2% in gate_40)
While the differences are small, gate_30 demonstrates slightly stronger user retention.

### Average engagement (number of game rounds played):
Players in gate_30 have higher average engagement: 52.46 rounds vs. 51.30 in gate_40.
This suggests slightly deeper engagement with the game in the gate_30 group.
However, the difference is small, so statistical testing is required to determine significance

### Conclusion after interpreting the QQ plot:
Normality is violated.
Therefore:
- The t-test should not be used directly, as one of its key assumptions — normal distribution — is not met.
- Instead, it's better to use non-parametric tests - e.g. Mann-Whitney U test to compare differences between groups

### Conclusion after Mann-Whitney U test:
p-value ≥ 0.05 
There is no statistically significant difference in the number of game rounds between the gate_30 and gate_40 groups. The p-value is close to the threshold, indicating a possible trend. That may require further investigation

The bar chart of confidence intervals shows the average number of game rounds for the two groups (gate_30 and gate_40) with 95% confidence intervals.
Although group gate_30 has a slightly higher mean, the confidence intervals partially overlap, indicating that the difference may not be statistically significant.
This visual supports the earlier result of the Mann–Whitney U test (p = 0.0502), suggesting marginal evidence for a difference in performance between the two versions.

Therefore, I conclude that moving the paywall to level 40 does not significantly impact player engagement.
