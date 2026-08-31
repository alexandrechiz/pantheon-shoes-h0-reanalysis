# A covariance-aware reanalysis of Pantheon+SH0ES

> **Scope:** Educational, compressed reanalysis of public calibrated
> Pantheon+SH0ES products; not an independent SH0ES measurement.

## Overview

This repository contains a progressive sequence of six notebooks on
likelihood-based inference, MCMC and the local distance ladder. The final
notebook performs a covariance-aware analysis of the public Pantheon+SH0ES
distance products.

The baseline analysis combines 77 calibrator rows and 277 Hubble-flow rows,
uses the published full statistical and systematic covariance matrix, and
adopts a third-order cosmographic distance-redshift relation. The two-parameter
model for the Hubble constant \(H_0\) and standardized supernova absolute
magnitude \(M_{\rm SN}\) is solved analytically with generalized least squares
and cross-checked with MCMC.

## Main result

The analytic baseline fit gives

\[
H_0 = 73.529 \pm 1.048\ {\rm km\,s^{-1}\,Mpc^{-1}}.
\]

The corresponding MCMC result is

\[
H_0 = 73.55^{+1.06}_{-1.03}\ {\rm km\,s^{-1}\,Mpc^{-1}}.
\]

The agreement provides an internal validation of the likelihood and sampling
implementation.

## Main robustness findings

- Reasonable changes to the cosmographic parameters, sample selection and
  covariance treatment leave the central value close to the baseline.
- Replacing the cosmographic distance relation with the first-order
  approximation \(d_L \simeq cz/H_0\) shifts \(H_0\) by
  \(-2.955\ {\rm km\,s^{-1}\,Mpc^{-1}}\) and increases \(\chi^2\) by 32.68.
- Ignoring off-diagonal correlations shifts \(H_0\) by only
  \(-0.033\ {\rm km\,s^{-1}\,Mpc^{-1}}\), but reduces its reported uncertainty
  by approximately 37.3%.
- The additional-scatter extension gives a 95% upper limit of
  \(\sigma_{\rm extra}<0.0290\) mag.

## Repository structure

- `notebooks/`: six progressively more advanced analysis notebooks.
- `data/`: data provenance, integrity hashes and download information.
- `figures/`: selected report- and slide-ready figures.
- `results/`: machine-readable result tables.
- `report/`: source files for the technical project report.

## Notebook sequence

1. `01_linear_fit_with_uncertainties.ipynb`
2. `02_gaussian_likelihood_linear_fit.ipynb`
3. `03_bayesian_linear_fit_with_emcee.ipynb`
4. `04_distance_ladder_toy_model.ipynb`
5. `05_real_supernova_hubble_diagram.ipynb`
6. `06_covariance_aware_h0.ipynb`

Notebooks 1–5 provide the pedagogical progression. Notebook 6 is the main
covariance-aware analysis and can be executed independently of the earlier
notebooks.

## Reproducing the analysis

Create the environment from the repository root:

```bash
conda env create -f environment.yml
conda activate pantheon-shoes-h0
jupyter lab
```

Open `notebooks/06_covariance_aware_h0.ipynb`, then use **Restart Kernel and
Run All**.

An internet connection is required because the public data products
are downloaded at runtime from a fixed Git commit and checked against recorded
SHA-256 hashes.

The final notebook was tested with Python 3.12.10.

## Scientific scope and limitations

The analysis uses corrected magnitudes, Cepheid distance moduli and covariance
matrices that have already been calibrated by Pantheon+SH0ES. It is therefore
a pedagogical reproduction of a compressed local inference, not a
reconstruction of the complete distance ladder and not a statistically
independent measurement of \(H_0\).

## References

- [Brout et al. (2022), Pantheon+ cosmological constraints](https://arxiv.org/abs/2202.04077)
- [Riess et al. (2022), SH0ES measurement of the local Hubble constant](https://arxiv.org/abs/2112.04510)
- [Pantheon+SH0ES public data release](https://github.com/PantheonPlusSH0ES/DataRelease)

## License

The original notebook content and code in this repository are released under
the [BSD 3-Clause License](LICENSE).

External Pantheon+SH0ES data products are not redistributed and are not covered
by this license. The technical report may carry a separate content license when
it is finalized.

This is an independent student project and is not an official analysis endorsed
by EPFL, Pantheon+ or SH0ES.