README


# Author
This code is developed by Maria B. Stone.

# Last Updated
October 17th, 2025


# SFR_ChebyFit_example
A minimal example notebook with code demonstrating **Chebyshev polynomial fitting** to correct star formation rate (SFR) values from one estimator to the baseline for another estimator.

This code was written for a research project (paper Stone et al. in review, ApJ) which looks into the star formation history parameters of low-redshift quasars.
This research project utilized SFR data produced by CIGALE and MAGPHYS programs, and thus there was a need to bring everything to the same baseline.


# Background
In this paper, we have two SFR estimators: CIGALE-based and MAGPHYS-based.
Both CIGALE and MAGPHYS are tools to model the spectral energy distribution of a galaxy.
https://cigale.lam.fr/documentation/
https://www.iap.fr/magphys/

The quasar sample in this paper does not have reliable MAGPHYS estimates, only CIGALE-based estimates for SFR parameter.
The control sample of galaxies has SFR estimates from both methods, on the other hand,
so it is used to obtain a correction curve to bring the quasar sample value to MAGPHYS baseline.
Thus, the Chebyshev fit correction for SFR is based on the data of a control sample of galaxies.

We first calculate the offsets between the two SFR values for each galaxy in the control sample, 

offset = $\\Delta$SFR = SFR$_{CIGALE}$ - SFR$_{MAGPHYS}$

All SFR values are expressed in log(10). 
The units of SFR are in solar masses per year.

We identified median offset values per dex of SFR$_{CIGALE}$ for control galaxies.
The data regarding these median offset points for normal galaxies is saved in the file
'sfroffset.fits'.

-------

The code demonstrates:
- How to construct a Chebyshev fit to median offsets for a control galaxy sample
- How to apply the correction to quasar host galaxies
- How to clip input values to the fit domain safely
- How to visualize in plots the fit results and the final histogram of corrected SFRs.



## Acknowledgments
Guidance on coding workflow and documentation provided by OpenAI’s ChatGPT (GPT-5).



## Citation

If you use this example or its concepts, please cite:

**Stone, M. (in review, ApJ)**, *SFR Chebyshev Fit Example*,  
Zenodo: [10.5281/zenodo.17381579](https://doi.org/10.5281/zenodo.17381579)  
ASCL: [ascl:2510.013](https://ascl.net/2510.013)



--------


## Files

- `SFR_Chebyshev_fit.ipynb` — example Jupyter notebook with the fitting and correction steps  
- `sfroffset.fits` — control sample offsets  
- `quasar_subsample_sfrcigale.fits` — quasar sample data  
- `figure_fit_demo.pdf`, `figure_corrections.pdf`, `figure_histogram.pdf` — visual outputs  
- `README.md` — this documentation file  


