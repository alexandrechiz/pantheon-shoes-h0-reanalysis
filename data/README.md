# Data provenance

This repository does not redistribute the Pantheon+SH0ES data products. The
main analysis notebook downloads the required public files directly into
memory from the official data release.

## Fixed data release

The download URLs are pinned to Git commit:

`c447f0fea703fcd0fff57de5000947b5ca81286b`

Official release directory:

https://github.com/PantheonPlusSH0ES/DataRelease/tree/c447f0fea703fcd0fff57de5000947b5ca81286b/Pantheon%2B_Data/4_DISTANCES_AND_COVAR

Data access date: 2026-08-30.

## Files used

- `Pantheon+SH0ES.dat`: corrected supernova magnitudes, redshifts,
  Cepheid distance moduli and published selection flags.
- `Pantheon+SH0ES_STAT+SYS.cov`: full statistical and systematic covariance
  used by the baseline analysis.
- `Pantheon+SH0ES_STATONLY.cov`: statistical-only covariance used for a
  predefined sensitivity test.

## Integrity checks

| File | SHA-256 |
|---|---|
| `Pantheon+SH0ES.dat` | `1cb0fc379ef066afdc2ffd1857681cc478024570d8a3eba284fb645775198cf8` |
| `Pantheon+SH0ES_STAT+SYS.cov` | `abf806d966485e64afdb359c87bffc0ecc00d05eff0a31ced66f247385df0fdc` |
| `Pantheon+SH0ES_STATONLY.cov` | `9f177129a332735d3637affd20054080d5260815f3ca0809120c05b2c902297f` |

The main data table and baseline covariance hashes are checked during
execution to prevent unnoticed changes to the inputs.

The diagonal uncertainty columns supplied for visualization are not used for
the baseline cosmological inference. A diagonal-covariance fit appears only
as a deliberately simplified diagnostic test.

## References

- Brout et al. (2022), [The Pantheon+ Analysis: Cosmological Constraints](https://arxiv.org/abs/2202.04077)
- Riess et al. (2022), [A Comprehensive Measurement of the Local Value of the Hubble Constant](https://arxiv.org/abs/2112.04510)
- [Pantheon+SH0ES public data release](https://github.com/PantheonPlusSH0ES/DataRelease)

The original authors' data-use and citation conditions remain applicable.