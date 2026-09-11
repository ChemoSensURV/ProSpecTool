# ProSpecTool: A MATLAB Toolbox for Spectral Preprocessing Selection

This repository contains **ProSpecTool**, a MATLAB toolbox for the automated selection of spectral preprocessing methods for Partial Least Squares Regression (PLSR). It accompanies the paper *ProSpecTool: A MATLAB toolbox for spectral preprocessing selection*.

ProSpecTool uses objective criteria inspired by expert analysis to assess raw spectral data, select appropriate preprocessing families, test sensible combinations, and help users identify robust and parsimonious PLSR models. It is intended for vibrational spectroscopic data, including near-infrared (NIR), mid-infrared (MIR), Raman, and UV-Visible spectra.

## Main features

- Graphical user interface that guides the analysis workflow
- Preliminary visualization of the imported X- and Y-blocks
- Optional detection and removal of spectral and response outliers
- Quantification of spectral noise and additive and multiplicative scatter effects
- Automated selection and iteration of suitable preprocessing methods
- Gaussian, Savitzky-Golay, and wavelet smoothing
- First- and second-order derivatives
- Baseline correction, detrending, and standard normal variate normalization
- Mean centering and autoscaling
- PLSR model comparison using RMSECV, cross-validated R-squared, regression-vector noise, and the J-Score
- Interactive inspection, sorting, filtering, and saving of candidate models

## Requirements

ProSpecTool was developed using MATLAB R2021b (version 9.11). It requires:

- MATLAB
- Signal Processing Toolbox
- Statistics and Machine Learning Toolbox
- Wavelet Toolbox when processing Raman data

No other third-party utilities are required.

## Installation and launch

1. Download or clone this repository.
2. Add the ProSpecTool folder and its contents to the MATLAB path.
3. In the MATLAB Command Window, run:

```matlab
ProSpecTool
```

The individual functions are designed to be used through the graphical interface rather than called directly from the MATLAB Command Window.

## Input data

- **X-block:** an `I x J` numeric matrix, where `I` is the number of samples and `J` is the number of spectral variables (such as wavelengths or wavenumbers).
- **Y-block:** an `I x 1` numeric column vector containing the reference or response value for each sample.

Replicate measurements should be averaged before analysis. Otherwise, random cross-validation may produce overly optimistic results. Users should also account for classes, populations, or other data structures that could be overfitted or under-represented.

## Recommended workflow

1. Import the X- and Y-blocks and inspect the spectra.
2. Configure the cross-validation folds, maximum number of latent variables, and spectroscopy type.
3. Check for outliers when their absence is uncertain.
4. Run the preprocessing analysis.
5. Sort and filter the resulting models by J-Score, RMSECV, or other relevant properties.
6. Inspect the leading candidates and validate the selected model independently outside ProSpecTool.

ProSpecTool is an exploratory aid. The analyst remains responsible for selecting, validating, and interpreting the final model.

## Citation

If you use ProSpecTool in your research, please cite:

> Ezenarro, J., Schorn-García, D., Busto, O., & Boqué, R. (2024). *ProSpecTool: A MATLAB toolbox for spectral preprocessing selection*. Chemometrics and Intelligent Laboratory Systems, 247, 105096. https://doi.org/10.1016/j.chemolab.2024.105096

## License

ProSpecTool is licensed under the [Creative Commons Attribution-NonCommercial 4.0 International License](LICENSE.txt). You may share and adapt the material for non-commercial purposes, provided appropriate attribution is given and changes are indicated. See `LICENSE.txt` for details.
