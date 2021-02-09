[[Optimization]]

# Decision Theory

## Setting

## Losses

## Risks

- _Expected Risk_: expected loss wrt to the probability distriburion of the model
- _Empirical Risk_: expected loss wrt to the dataset
  - Also called **training** (or testing) **error**
  
## Bayes Predictor

- **What is the _best_ predictor we can expect?**
  - Answer: Bayes Predictor
- But, what is the goal?
  - Find the minimum risk of a predictor
  - This may require access to all measurable functions (predictors)

## Learning with Empirical Risk Minimization

- Notation:
  - $R(f_\theta)$ -> the expected risk of your currently trained model
  - $\hat{R}(f_\theta)$ -> the emperical risk of your currently trained model
  - $R*$ -> bayes risk 
  - $R(f_\theta^*)$ -> expected risk of our best function in the hypothesis class
  - $\hat{R}(f_\theta^*)$ -> emperical risk of best our best function in the hypothesis class 
