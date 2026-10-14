# RASSINE for EXSPLOSYN

This branch adapts RASSINE for use with EXSPLOSYN, providing the
command-line interface, compatibility fixes, and configuration needed
to normalize PHOENIX reference spectra for RV measurements.

## Calling RASSINE

EXSPLOSYN uses the following command-line interface:

```sh
python Rassine.py <input_pickle> <output_directory> <rassine_directory>
```

The directory arguments must end with `/`. Set EXSPLOSYN's `[paths] rassine_root`
to this checkout. RASSINE runs with the same Python interpreter as EXSPLOSYN.
The required packages are NumPy, pandas, SciPy, Matplotlib, and Astropy.

## Configuration and execution

Continuum-fitting parameters are defined in [Rassine_config.py](Rassine_config.py).
The defaults are configured for synthetic PHOENIX spectra
(`synthetic_spectrum = True`), for which sigma clipping is skipped.

Processing runs without interactive feedback and does not require a Qt plotting
backend. Compatibility fixes for pandas 3 are included. Synthetic-spectrum
perturbations use a filename-derived random seed, so identical input spectra
with the same filename receive the same perturbations.

## Original software and citation

RASSINE was developed by Michael Cretignier and collaborators. The original
README and source attribution are retained in this fork.

- [Original RASSINE repository](https://github.com/MichaelCretignier/Rassine_public)
- Cretignier et al. (2020), *RASSINE: Interactive tool for normalising stellar spectra. I. Description and performance of the code*, A&A, 640, A42.
  [Publication](https://ui.adsabs.harvard.edu/abs/2020A%26A...640A..42C/abstract)

Please cite the original RASSINE paper when using this software in research.
