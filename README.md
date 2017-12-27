# CGI-flux-ratio-plot
This contains the python code to plot the flux ratio vs separation plot. It also contains the text files with the contrast curves and planet contrast values. Each datafile has a full description of its comment section; a brief explanation (auto_caption.txt) is auto-generated by the script from these headers, including only those data you choose plot.

## python requirements
* python 2
* matplotlib
* astropy (tables, ascii, units)
* numpy
* yaml

## Plot options
To customize what is plotted, edit the file "config.yml"

Available WFIRST modes:
* planet imaging BTR
* disk imaging BTR
* spectroscopy BTR
* HLC & SPC disk mask predictions

Available instruments:
* Gemini GPI IFS
* VLT SPHERE: IFS & IRDIS
* HST ACS
* HST NICMOS
* HST STIS
* JWST NIRCam

Available planets:
* known self-luminious directly imaged planets: measured H-band contrasts & extrapolations.
* known RV planets: extrapolated reflected light brightness
* Earth & Jupiter at 10pc
* Tau Ceti e & f

Other available plotting options:
* color coding by bandpass: none, simple color, full color

## Data file format
Datafiles should be formatted in the following way to allow for auto import by astropy.io.ascii & auto generation of caption.txt:
```
#col_name1  col_name2
#Short caption: Write a short explanation, suitable for a figure caption. This line is automatically fed into "auto_caption.txt" when contrast_plot.py is run. This line must begin with the phrase "short caption:" & be all on one line (ie: no "return" characters).
#Full explanation: Optional. Any other info that you don't want to appear in auto_caption.
#References
#URLs or paper references or other source information
data11  data12
data21	data22
...
```
## Data description
As mentioned above, "auto_caption.txt" contains a description of each quantity you choose to plot.

Below is a suggested figure caption; however, because this is NOT automatically generated by the scipt, please check to make sure it matches the information in "auto_caption" and is appropriate for the plot options you have chosen.

Predicted WFIRST performance in the context of known planets and existing and planned high-contrast instruments. The y-axis indicates the flux ratio between a planet and its host star (for individual planets) or between the star and the dimmest source detectable at 5-sigma after post-processing (for instrument performance curves). The lower x-axis is projected separation in arcseconds, and the upper x-axis is the corresponding physical separation for the Tau Ceti system. Points and lines are color-coded by wavelength of observation. Solid and dashed lines are 5-sigma point source detection limits versus separation from the host star; these limits are calculated from post-processed data. The predicted performance for the future observatory, JWST, is plotted as a dashed line. Lines labeled BTR are WFIRST Baseline Technical Requirements. Black triangular points are estimated reflected light flux ratios for known gas giant radial velocity-detected (RV) planets at quadrature, with assumed geometric albedoes of 0.5. Red squares are 1.6μm flux ratios of known self-luminous directly-imaged (DI) planets. Dotted lines connect each DI planet’s known 1.6μm flux ratio to its predicted flux ratio at 750nm (yellow diamonds) or 550nm (blue circles), based on COND or BT-Settl planet






