---
title: Adversarial Examples
tags: adversarial, gan, game theory, machine learning
---

[[Optimization]]

# Adversarial Examples

> Examples that are close to the data distribution yet, they are not the same
  
  
![Panda](https://openai.com/content/images/2017/02/adversarial_img_1.png)

- $\epsilon$ depends on the norm
- [ ] Can the _panda-gibbon_ example be explained through lack of a model's generalization ability?
- [ ] Can the _panda-gibbon_ example be explained through the model's expressiveness abilities?
- [ ] How is random noise perturbation able to change a model's confidence?

## Finding the Best Attack

$$
x' \in \text{argmax}_{x' \in \mathcal{X}}
\mathcal{l}(f_t(x'),y), \text{such that }
d(x,x') \leq \epsilon
$$

### White Box Threat Model

- One option is to use **projected gradient ascent** as solution
- [x] But all we need is to consider the largest gradient direction, w.r.t. the attack, because we consider all the pixels! ($L_\infty$)
    - $\text{sign}\nabla_x\mathcal{l}(f(x),y)$
    - [x] Why is this target equivalent to maximize the $L_\infty$ norm? (Convince myself)


## Fancier Attacks

## Black Box Attack

- **IDEA**: Approximate the gradient
- Zeroth order optimization

## Defenses

- [ ] Gradient Masking https://openai.com/blog/adversarial-example-research/
- Preprocessing the input
- Adversarial Training
- https://www.robust-ml.org/defenses/
- [ ] What are common non-image benchmarks for adversarial attacks?