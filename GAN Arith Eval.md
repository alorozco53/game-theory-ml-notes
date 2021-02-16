---
title: GAN Arithmetics & Evaluation
tags: evaluation, gan, game theory, machine learning
---

[[GANs]]

# GAN Arithmetics & Evaluation

- Prior papers:
    -
    -
    -
    
## Arithmetics in the Latent Space

- Perform simple arithmetic operations to change image features
- Similar to word embeddings
- Each feature has its own direction in the space
    - e.g. direction of glasses 😎 within a face image

![](https://i.imgur.com/IIgfarE.jpg)
![](https://camo.githubusercontent.com/e811b2803e9b27bf477a389477f48a57f51dfd2af9f2ce3b95b7d9344634d85b/687474703a2f2f692e696d6775722e636f6d2f646d6d464f69472e676966)

https://github.com/ajbrock/neural-photo-editor


- **IDEA**: Learn the _latent_ direction of these features (gender, pose, age, eyeglasss).
- [ ] What about videos and text?
- [x] ~~Can we know, a priori, what are the directions in the latent space where each particular feature lives?~~
    - No, that's why we learn them 

## Evaluation of Generative Models

_How do we evaluate sample fidelity and diversity?_

- Samples
- What do we care at the end?
- Everyone is biased towards the output (namely, images)
- [x] Can we take an approach similar to how one evaluates a language model? (e.g. use perplexity to compare outputs to another corpus)
    - We can, but images don't work the same way as language does.
- **IDEA** Automate the process of using a classifier to assess a model.

### Inception Score

- Uses a standard pretrained classifier (Inception model)
- Estimates label distribution:
$$
p_g(y \mid x) \approx f_\theta(x)\\
p_g(y) \approx \mathbb{E}_{x \sim p_g}[f_\theta(x)]
$$
- _Probability of doing a good classification of the generated dataset, by a pretrained classifier_.
- [x] What is the intuition behind $p_g(y)$ being uniform?
    - Theres is no in $y$ that makes $p_g(y)$ distinguishable enough from $p_g(y \mid x)$
    - [ ] High KL divergence
    - https://medium.com/octavian-ai/a-simple-explanation-of-the-inception-score-372dff6a8c7a

$$
IS(G) := \exp\left(\mathbb{E}_{x \sim p_g}[KL(p(y \mid x)\mid \mid p(y))]\right) 
$$

**OBSERVATION**: IS correlates well with performances.
- Caveat: Depends on the weights $\mathbf{\theta}$ of different implementations
  (namely pytorch and tensorflow)
- Not reporting overfitting
- [ ] Only cares about label diversity

### Fréchet Inception Distance

Assume $x_{\text{data}} \sim \mathbb{N}(\mu_1, \Sigma_1)$ and $x_{\text{fake}} \sim \mathbb{N}(\mu_2, \Sigma_2)$,

Then,

$$
d(p_{\text{data}}, p_g) =
||\mu_1 - \mu_2|| +
Tr\left(\Sigma_1 + \Sigma_2 -
2\left(\Sigma_1 \Sigma_2\right)^{\frac{1}{2}}\right)
$$

- [ ] Intra-class mode dropping

Caveats:
 - Still impossible to detect overfitting
 - Not really a distance (only for Gaussians)

