

# Quantitative analysis of coherence-induced imaging artefacts

This repository contains the Python analysis used to quantify the suppression of coherence-induced imaging artefacts presented in the supplementary material accompanying the manuscript:

**Absorption imaging of quantum gases near surfaces using incoherent light**
https://arxiv.org/abs/2602.13175

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

 `uv`

If `uv` is not already installed, follow the installation instructions at:

https://docs.astral.sh/uv/getting-started/installation/

Check that the installation was successful using:

```bash
uv --version
```

From the root directory run 

```bash 
uv sync
```

this will create a local `.venv` and install the package versions specified in the `pyproject.toml` and `uv.lock` files.

Once the file is opened you can select the Python interpreter from the local `.venv` directory as the Jupyter kernel

## Running the notebook

The analysis script is: `QuantitativeFringeAnalysis.ipynb`

The notebook performs the following steps:


1. Loads and crops the experimental images.
2. Estimates the slowly varying background using Gaussian filtering.
3. Normalises each image to the local background.
4. Applies a two-dimensional Tukey window.
5. Calculates the two-dimensional Fourier power spectra.
6. Integrates along $f_x$ to obtain one-dimensional Fourier-power spectra as a function of $f_y$.
7. Integrates the Fourier power over the selected fringe-frequency band.
8. Calculates the band-limited RMS fringe contrast.
9. Generates the final comparison figure.

Before running the notebook, check that the image directory defined near the beginning of the notebook points to the correct location of the experimental data.

## Data
The images are located inthe `RawImages' folder and contains 6 raw images which are the 'light' reference images taken during absorption imaging. These are the same images used in Fig.2.
The images are stored in order:

`img00001_X2:` Fully coherent, standard absorption imaging
`img00002_X2:` Partially coherent, F-lens = 55 mm (partial 1)
`img00003_X2:` Partially coherent, F-lens = 63 mm (partial 2)
`img00004_X2:` Partially coherent, F-lens = 73 mm (partial 3)
`img00005_X2:` Incoherent, No F-lens
`img00006_X2:` Static image of the diffuser



