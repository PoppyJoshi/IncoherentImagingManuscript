

# Quantitative analysis of coherence-induced imaging artefacts

This repository contains the Python analysis used to quantify the suppression of coherence-induced imaging artefacts presented in the supplementary material accompanying the manuscript:

**Absorption imaging of quantum gases near surfaces using incoherent light**

The analysis is contained in:

`QuantitativeFingeAnalsysis.ipynb`

The notebook compares images acquired at different degrees of spatial coherence using two complementary measures:

1. Fourier power contained within the spatial-frequency range associated with the observed fringe structure.
2. Band-limited RMS fringe contrast.

The analysis workflow includes:

- image loading and cropping;
- background estimation using Gaussian filtering;
- image normalisation;
- Tukey windowing;
- two-dimensional Fourier analysis;
- spatial-frequency calibration;
- one-dimensional Fourier-power spectra;
- integration of the Fourier power over the fringe-frequency band; and
- calculation of the band-limited RMS fringe contrast.

---

## Requirements

The analysis was written in Python and uses the following main packages:

- `numpy`
- `matplotlib`
- `pandas`
- `scipy`
- `pillow`
- `jupyter`
- `ipykernel`

The Python environment can be created using [`uv`](https://docs.astral.sh/uv/).

---

## Setting up the Python environment with `uv`

### 1. Install `uv`

If `uv` is not already installed, follow the installation instructions at:

https://docs.astral.sh/uv/getting-started/installation/

Check that the installation was successful using:

```bash
uv --version