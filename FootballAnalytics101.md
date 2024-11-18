# Football Analytics 101

## Performance Metrics 

### Expected Goals (xG)
Expected Goals (xG) assign a numerical probability to the quality of a shot. It represents the likelihood of a shot resulting in a goal based on factors like distance, angle, position, type of shot, scenario, etc.

#### Key Metrics:
1. **xGF** (Expected Goals For): The sum of xG values for all shots a team takes.
2. **xGA** (Expected Goals Against): The sum of xG values for all shots a team allows.
3. **xGD** (Expected Goals Difference): The difference between xGF and xGA (`xGF - xGA`).

Each data provider has its own formula for calculating xG, so you may see different xG values for the same shot. This is because not all models account for the same factors.

xGD (Expected Goals Difference) can be a better measure of team strength than traditional goal difference. xG models allow us to look beyond current results to gain a deeper understanding of the underlying quality of both teams and players.

Penalty kick typically have an xG value of 0.76 in most models.


#### How xG is Calculated:
The possible values range between **0** (not probable to result in a goal) and **1** (almost certain to result in a goal).
A logistic regression is used to calculate the probability of a goal:

$$
P_{goal} = \frac{1}{1 + e^{-(\beta_0 + \beta_1 X_1 + \beta_2 X_2 + \dots + \beta_k X_k)}}
$$

Where:  
- \( X_i \) are factors such as distance, angle, position, type of shot, and scenario.
