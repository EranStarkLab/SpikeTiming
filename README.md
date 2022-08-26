# SpikeTiming
Computational routines for calculating decoding quality, precision, and reliability of spike timing.
## Overview
The spike timing analysis implements the time-domain white-noise (WN) analyses for spike trains, yielding the results described in Levi, Spivak, Sloin, Someck, Stark, 2022, Cell Reports.

## Simulated spike trains
To demonstrate the entire pipeline for simulated spike trains, use st_sim.m.

## Neuronal spike trains
To demonstrate the entire pipeline for real neuronal spike trains, use st_neuronal.m.

## Routines

### Wrappers
- st_sim.m
  - a wrapper, calls stAnalysis routine for simulated spikes trains
- st_neuronal.m
  - a wrapper, calls stAnalysis routine for neuronal spikes trains
- stAnalysis.m
  - Does time-domain WN analysis for spike trains

### Analysis
- sta.m
  - compute sta from spike train and analog vector
- stacalc.m
  - compute multi-sta from tagged spike trains and an analog vector
- stahat.m
  - reconstruct analog signal
- stcodertypes.m
  - classify reliability profiles into rate or temporal coders
- stmix.m
  - shuffle/jitter spikes in a sparse array
- streconstruct.m
  - reconstruct analog waveform from spike trains
- streconstructXval.m
  - cross-validation wrapper for streconstruct.m
- streliability.m
  - estimate reliability of single-cell spike trains
- stwiener.m
  - construct a modified Wiener filter for spike train and analog signal

### Utilities
- bayescount.m
  - compute the number of bins for bias calculation, using the Bayes counting procedure of Panzeri&Treves 96
- calc_bias_PT.m
  - calculate an analytical estimate of MI bias from a joint probability table
- calc_fwhh.m
  - determine full-width at half-height
- calc_pearson.m
  - compute Pearson's correlation coeffiecient
- calc_spearman.m
  - compute Spearman's correlation coeffiecient
- isisort.m
  - sort spikes into ISI groups
- mixmat.m
  - mix matrix elements
- mutinf.m
  - mutual information from empirical distributions/counts
- my_xcorr.m
  - compute the column-wise cross-correlation between real matrices
- myjet.m
  - modified jet with extreme values in pure R,B.
- nangeomean.m
  - geometric mean
- ParseArgPairs.m
  - flexible argument assigning
- plot_raster.m
  - raster display for spike trains
- resampleSig.m
  - wrapper for resample.m

### C Utilities
These Utility functions are operating system sepcific and require compiling in MATLAB (see section 'To run the code' below). 
- calc_cor.c
  - calculate delays by enumerating on first spike train only
- zcs.c
  - Compute the Z-score of the columns of a given matrix

### Data
- WN10k.mat
  - WN pattern
  - WN Fs
- sim_spikes.mat 	
  - Spike trains of four simulated units: High precision rate coder, high precision temporal coder, low precision rate coder, and low precision temporal coder.
- neuronal_spikes.mat 	
  - Spike trains of 3 recoded units: DA PYR, DA INT, and IDA INT.

## To run the code
- Download all routines and data
- Compile the C utility functions using the 'mex' commend in MATLAB:
  - to compile calc_cor.c, in MATLAB, write: mex('calc_cor.c')
  - to compile zcs.c, in MATLAB, write: mex('zcs.c')
- For simulated spike trains, in MATLAB, write: st_sim 
- For real neuronal spike trains, in MATLAB, write: st_neuronal
