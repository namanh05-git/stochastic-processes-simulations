# Computational Methods in Stochastic Processes

Python simulations from a course on computational methods for stochastic processes: random
number generation, sampling methods, Poisson processes, Markov chains, and Markov chain Monte
Carlo. Everything is implemented from scratch with `numpy`; no datasets are needed.

## Contents

### Random numbers and sampling

| Notebook | Topic |
|---|---|
| `01_rng_quality_ggl_ran3_mersenne_twister.ipynb` | Compares three generators: the GGL linear congruential generator, a RAN3-style lagged generator, and Python's Mersenne Twister. Plots pairs of consecutive values to expose the serial correlation in GGL. |
| `02_uniform_points_in_circle.ipynb` | Three ways to sample uniformly in a disc: rejection, naive polar coordinates (which cluster at the center), and scaled polar coordinates (`r = R·√U`). |
| `03_inverse_transform_power_law_binning.ipynb` | Inverse transform sampling of a power-law distribution (density ∝ x^-3/2), plotted with linear and logarithmic binning on log-log axes; compared with rejection sampling. |
| `04_random_walks_clt_lognormal.ipynb` | Sums of independent random changes across 500,000 agents: symmetric steps (binomial → normal), asymmetric steps, and multiplicative changes (→ lognormal). |

### Markov chains and Poisson processes

| Notebook | Topic |
|---|---|
| `05_markov_chain_carpet_sales.ipynb` | A 10-level Markov chain model of a salesman's excitement level: transition matrix, simulated sales, distribution of the time to reach 5 sales, and the probability of selling fewer than 5. |
| `06_poisson_process_thinning_traffic.ipynb` | Non-homogeneous Poisson process of car arrivals over 24 hours with piecewise-constant rates, simulated by interval-wise inversion and by thinning; average and cumulative arrivals, daily totals, and first-arrival time. |
| `07_poisson_decay_half_time_fixed_step.ipynb` | Half-time of a decaying population of 10,000 cells, simulated with fixed time steps and Poisson-distributed decays: constant rate vs. rate proportional to remaining cells. |
| `08_poisson_decay_half_time_inverse_transform.ipynb` | The same half-time problem, simulated event by event with inverse transform sampling, including the time-varying (inhomogeneous) case via cumulative intensity inversion. |

### Markov chain Monte Carlo

| Notebook | Topic |
|---|---|
| `09_gibbs_sampler_normal_posterior.ipynb` | Gibbs sampler for the posterior of a normal model's mean and precision: trace plots, marginal and joint posterior distributions. |
| `10_metropolis_hastings_gamma.ipynb` | Metropolis-Hastings for Ga(3,1) with an exponential proposal: tuning the proposal rate by acceptance rate, resulting mean and variance, and a comparison with Gibbs sampling. |
| `11_hamiltonian_monte_carlo_exponential.ipynb` | Hamiltonian Monte Carlo (leapfrog integration) for an exponential distribution with a positivity constraint, checked against the exact density. |

## Repository layout

```
.
├── README.md
├── requirements.txt
```

Apart from the deterministic generators in notebook 01, the notebooks don't fix a random seed, so exact values differ slightly between runs.
Some notebooks refer to separate PDF write-ups for mathematical derivations (e.g. the inverse
transform formulas); those are not included here.
