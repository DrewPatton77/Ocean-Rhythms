# Investigating Climate: Variability in Anomalous Sea Surface Temperature

An analysis of global sea surface temperature (SST) variability using the HadISST dataset (monthly, 1870 to present). It looks at which large-scale ocean cycles explain the most variance in SST anomalies, using climatologies, detrending, EOF analysis, and Fourier/wavelet time-series analysis.

The full write-up is in [`Our-Warming-Ocean.pdf`](Our-Warming-Ocean.pdf) (December 2023). The analysis behind it is in [`SST-Analysis.ipynb`](SST-Analysis.ipynb).

## Summary of findings

- Anomalies are computed against a 1991 to 2020 climatology. Detrending separates long-term warming from natural variability.
- The first EOF mode of global SST anomalies is localized over the Niño 3.4 region, so the El Niño-Southern Oscillation (ENSO) is the largest single contributor to SST variability (about 16% of the variance).
- Higher modes are concentrated in the North Pacific, which points to the Pacific Decadal Oscillation (PDO) and the North Pacific Gyre Oscillation (NPGO).

## What the notebook covers

1. **Loading the data:** opening a NetCDF file as an `xarray` dataset and plotting SST
2. **Climatology and anomalies:** a 30-year baseline (1991 to 2020) and SST anomalies relative to it
3. **ENSO:** latitude-averaged anomalies and the Niño 3.4 time series
4. **Trends and cycles:** detrending the anomalies
5. **EOF analysis:** the dominant spatial patterns and their principal components, correlated with climate indices
6. **Spectral analysis:** Fourier and wavelet transforms of ENSO, AMO, and PDO/NPGO time series

## Figures

The [`Figures/`](Figures) folder contains the detrending, ENSO, EOF, and principal-component correlation figures used in the report.

## Data

The HadISST dataset is not included in this repository. Download the HadISST NetCDF file from the [Met Office Hadley Centre](https://www.metoffice.gov.uk/hadobs/hadisst/) and place it next to the notebook as `HadISST.nc`, the name the notebook loads.

## Running it

```bash
pip install xarray netcdf4 numpy pandas scipy statsmodels matplotlib cartopy eofs xeofs pywavelets jupyter
jupyter notebook SST-Analysis.ipynb
```

## Stack

Python · xarray · NumPy · pandas · SciPy · statsmodels · eofs / xeofs · PyWavelets · Matplotlib · Cartopy · Jupyter
