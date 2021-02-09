[[Optimization]]
# Game Theory and ML Math Background

- Optimization $\min \max P_n(\mathbf{X})$
	-  Minimax problems
	-  Convex optimization
- [Algorithmic Game Theory Book](https://www.cs.cmu.edu/~sandholm/cs15-892F13/algorithmic-game-theory.pdf)

### Prisoner's Dilemma
- Single eqilibrium _when confessing_

### COP 21 Game

- Paris climate change agreement
- US didn't entered the agreement, during the Trump administration
- NOT POLLUTION vs POLLUTION
- Cooperative strategie

### Rock Paper Scissors

- **No optimal** strategy
- [x] Yet there is a distribution (?) of optimal support of strategies
  - **Strategy**: set of actions, sometimes directed towards minimizing a loss.
- Zero-sum game:
  $$
  \sum^n_k=1 \mathcal{l}_k = 0
  $$
- W=1, L=-1, T=0

## Multi-Player Game

- Loss of a single player, wrt the other n-1:

	$$
	\mathcal{l}_k(s_1,\cdots,s_n) = \mathcal{l}_k(s_k, s_{-k})
	$$

- Goal of the player: _minimize its loss_

## Nash Equilibrium

- Best _worst-case_ move

	$$
	s* \in \text{Nash}
	\longleftrightarrow
	\mathcal{l}_k(s_k^*,s_{-k}) = \mathcal{l}_k(s_k, s^*_{-k})
	\forall s
	$$

- No incentive to change strategies
- **NO EQUILIBRIA IN GENERAL**
- Hard to compute for more than 3 players

Yet, **THERE IS A NASH EQUILIBRIUM** for any game with finite set of players and finite set
of strategies.

## Correlated Equilibrium

- Players can coordinate using a recommendation from a _third party_.
- Recommender ($p \in \Delta_{nm}$) advices players towards a goal.
- **Equilibrium*: point where there is no incentive to follow
  a recommendation.
- Linear Programming can crack this equilibria!
- [x] Is a recommender considered also a player?
  - No, it is a third party entity.

### Traffic Game

- [ ] FInd equilibria
