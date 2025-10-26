# VariationalMonteCarlo-Helium

Estimate the helium ground-state energy with **Variational Monte Carlo (VMC)**. Python scripts implement Metropolis sampling, trial wavefunctions, and parameter optimization; plots show convergence and final estimates.

## Overview

* VMC for the helium atom (nonrelativistic, clamped nucleus).
* Trial wavefunctions with variational parameters (optionally Jastrow).
* Energy estimation via Monte Carlo integration and optimization.

## Theory (brief)

* Variational principle: (E[\Psi_\theta] \ge E_0).
* Local energy: (E_L(\mathbf{R}) = \frac{H\Psi_\theta}{\Psi_\theta}).
* Minimize (\langle E_L \rangle) over samples from (|\Psi_\theta|^2).

## Features

* Metropolis sampler (+ burn-in, thinning).
* Parameter sweeps or gradient-free optimization.
* Plots: running mean, histogram of (E_L), convergence.

## Install

```bash
pip install -r requirements.txt
```

## Quickstart

```bash
git clone https://github.com/yourusername/VariationalMonteCarlo-Helium.git
cd VariationalMonteCarlo-Helium
python vmc_helium.py --samples 200000 --burnin 5000 --step 0.5 --seed 42
```

## CLI (common flags)

```
--samples N         # total MCMC samples
--burnin N          # discard initial steps
--step float        # proposal step size
--optimize          # enable parameter search
--out results/      # save logs/plots
```



## Results

* Reports (\langle E \rangle \pm \sigma/\sqrt{N}) and best parameters.
* Saves convergence plots to `results/`.

## Notes

* Set a **random seed** for reproducibility.
* Tune `--step` to target ~30–50% acceptance.
* More samples → lower statistical error; model error depends on trial (\Psi).

## License

MIT

## References

* Hammond, Lester, Reynolds — *Monte Carlo Methods in Ab Initio QM*.
* Foulkes et al., RMP 73, 33 (2001).
