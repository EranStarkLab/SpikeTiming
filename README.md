# SpikeTiming
Computational routine for calculating the decoding quality, precision and reliability of spike timing.
## Overview
The spike timing analysis does time-domain WN analysis for spike trains, yielding the results depicted in Levi et al. 

## Simulated spike trains
To demonstrate the entire pipeline for simulated spike trains, a st_sim.m is available. To run it, you will need the following:

## Neuronal spike trains
To demonstrate the entire pipeline for three recorded spike trains, a st_neuronal.m is available. To run it, you will need the following:

### Routines
- st_sim.m
  - the wrapper, calls stAnalysis routine for simulated spikes trains
- st_neuronal.m
  - the wrapper, calls stAnalysis routine for neuronal spikes trains
- stAnalysis.m
  - Does time-domain WN analysis for spike trains 
- streconstructXval.m
  - cross-validation wrapper for streconstruct.m
- streconstruct.m
  - reconstruct analog waveform from spike trains
- stwiener.m
  - construct modified Wiener filter for spike train and analog signal
- stprecision.m 			
  - estimate reliability (and precision) of single-cell spike trains

### Data
- WN10k.mat
  - WN pattern
  - WN Fs
- sim_spikes.mat 	
  - Spike trains of 4 simulated units: High precision rate coder, high precision temporal coder, low precision rate coder and low precision temporal coder
- neuronal_spikes.mat 	
  - Spike trains of 4 recoded units: Putative DA PYR, DA INT and IDA INT.

### To run the routine
- Download all routines and data
- In MATLAB, write: (1) stats = st_sim 
                    (2) stats = st_neuronal
