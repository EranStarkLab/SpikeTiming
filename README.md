# SpikeTiming
Computational routines for calculating decoding quality, precision, and reliability of spike timing.
## Overview
The spike timing analysis implements the time-domain white-noise (WN) analyses for spike trains, yielding the results described in Levi, Spivak, Sloin, Someck, Stark, 2022, Cell Reports.

## Simulated spike trains
To demonstrate the entire pipeline for simulated spike trains, use st_sim.m.

## Neuronal spike trains
To demonstrate the entire pipeline for real neuronal spike trains, use st_neuronal.m is available.

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
  - Spike trains of four simulated units: High precision rate coder, high precision temporal coder, low precision rate coder, and low precision temporal coder.
- neuronal_spikes.mat 	
  - Spike trains of 3 recoded units: DA PYR, DA INT, and IDA INT.

### To run the code
- Download all routines and data
- For simulated spike trains, in MATLAB, write: st_sim 
- For real neuronal spike trains, in MATLAB, write: st_neuronal
