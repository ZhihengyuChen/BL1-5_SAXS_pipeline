# BL1-5_SAXS_pipeline
pipeline about SAXS data processing at BL1-5, SSRL

I would recommend to install [pyFAI-calib2](https://www.silx.org/doc/pyFAI/dev/man/pyFAI-calib2.html)to generate mask and calibration file. GUI is easier for masking and ring picking.

Name pattern is sometimes problematic. When you write the macro for data acquisition, it is important make sure **all the numbers have same digits**. Otherwise it will be painful when python scripts process them in batch

Some of the scripts are primarily written by [Anjani Maurya](https://github.com/anjanikmaurya). Check more details on his page.
