# fNIRS-SplineSG-Motion-Correction
MATLAB implementation of the SplineSG motion correction algorithm for fNIRS data, combining spline interpolation for baseline shifts and Savitzky-Golay filtering for spikes. (Jahani et al., Neurophotonics, 2018)

# UI Name :
SplineSG_Motion_Correction

# Syntax :
data_d = hmrR_MotionCorrectSplineSG(data_d, mlActAuto, p, FrameSize_sec, turnon)

# Description :
The function first identifies the baseline shifts and spikes in the signal. The baseline shifts are corrected using a spline interpolation method. The remaining spikes are corrected by Savitzky-Golay filtering, which is a digital smoothing filter that substitutes each value of the signal series with a new value obtained by applying a cubic fitting to a subset of adjacent data points. The length of the subset is defined by the parameter FrameSize_sec. The method is described in the following paper. Citation: Jahani et al., Neurophotonics, 2018; doi: 10.1117/1.NPh.5.1.015003.

# Inputs :
- data_d: SNIRF object containing time course data.
- mlActAuto:
- p: Parameter p used in the spline interpolation. The value recommended in the literature is 0.99. Use -1 if you want to skip this motion correction.
- FrameSize_sec:
- turnon: Optional argument to enable/disable this function in a processing stream chain.
- 
# Outputs :
- data_d: SNIRF object containing time course data after spline interpolation correction.

# Usage Options :
- SplineSG_Motion_Correction: dod = hmrR_MotionCorrectSplineSG(dod, mlActAuto, p, FrameSize_sec, turnon)

# Default Parameters :
- p=0.99
- FrameSize_sec=10
- turnon=1

# Prerequisites :
- Intensity_to_Delta_OD: dod = hmrR_Intensity2OD( intensity )
