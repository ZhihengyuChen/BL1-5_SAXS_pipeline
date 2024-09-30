# BL1-5_SAXS_pipeline #
pipeline about SAXS data processing at BL1-5, SSRL

I would recommend to install [pyFAI-calib2](https://www.silx.org/doc/pyFAI/dev/man/pyFAI-calib2.html)to generate mask and calibration file. GUI is easier for masking and ring picking.

Name pattern is sometimes problematic. When you write the macro for data acquisition, it is important make sure **all the numbers have same digits**. Otherwise it will be painful when python scripts process them in batch

Some of the scripts are primarily written by [Anjani Maurya](https://github.com/anjanikmaurya). Check more details on his page.

At BL1-5, there is a Pilatus1M detector for SAXS and a Pilatus100k detector for WAXS (optional), and two different sample-detector distances (~1 and ~3 meters). Saved files from beamtimes include, .txt macros setting measurement parameters, 2D scattering patterns saved as .raw, .raw.pdi recording instrument parameters, and .csv files saving the readings from detectors.

## 1. Convert 2D images ##
The integration by pyFAI-calib2 needs .cbf files. See details in BatchRAWprocessor.

## 2. Calibrate and mask ##
Use GUI of pyFAI-calib2 to calibrate the sample geometry and mask bad pixels on the detector. Save your .poni and .edf files for calibration and masking. BatchRAWprocess also has the scripts for calibration. But it does not iterate well unless the initial values are close enough.

## 3. Integrate in batch ##
Run the rest of BatchRAWprocessor. Output the integrated files.
