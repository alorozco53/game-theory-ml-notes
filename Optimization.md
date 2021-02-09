[[Decision Theory]]

# Optimization Theory

- Scribe notes: https://docs.google.com/spreadsheets/d/1hrsgsNlcdNPEXCSET515-Z22H16egqcKAIYzBnhqkYY/edit?usp=sharing 
- Boyd's course: https://web.stanford.edu/class/ee364a/videos.html

## Usual Goal in ML

_Empirical Risk Minimization_

- Two perspectives:
  - deterministic: minimize target function
  - expectation of empirical dataset distribution

## Gradient Descent

$$
\theta_{t+1} = \theta_t - \eta \nabla g
$$

### Convexity

- Local minima are _global_ minima
- We can prove convergence rates!
- We understand well convex functions
- [ ] We have _convex duality_
- Characterization: $\forall \theta$, $\nabla^2 g(\theta) \geq 0$.
- We assume **smoothness** of functions
- $\mu / L$ smoothness to strong convexity rate:
  - **closer to 1**: easier problem
  - **closer to 0**: harder problem
  - depends on the direction which the gradients point (circle-like to ellipse-like)

- Descent Lemma (Boyd book)
- Smoothness Lemma
- Lemma for strongly convex functions

## Steepest Descent

- Do gradient descent with the _steepest_ gradient directions every time

## Projected Gradient Descent
