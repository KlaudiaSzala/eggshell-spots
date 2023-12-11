# eggshell-spots

INSTALLATION

These scripts require installation of ImageJ (Schneider et al. 2012) with MICA Toolbox plugin (Troscianko & Stevens 2015). To use the scripts directly from ImageJ, you should place them in imagej/plugins folder.

DESCRIPTION

The scripts use normalised digital images created with the MICA Toolbox software (Troscianko &amp; Stevens 2015). A binary mask needed to cut eggshell's spots from the background is prepared using local thresholding with Phansalkar method (Phansalkar et al. 2011). Green channel is recommended for thresholding, as it match the spectral sensitivity of avian double cones (Spottiswoode & Stevens 2010).


- percent_spots: counts percent of spots on eggs from multispectral images (.mspec)
- spots_size: measures average size of spots on eggshells from multispectral images (.mspec)
- spots_colour: measures brightness and colour of spots on eggshells from multispectral images (.mspec).


REFERENCES

Phansalkar, N., More, S., Sabale, A., Joshi, M. (2011) Adaptive local thresholding for detection of nuclei in diversity stained cytology images. ICCSP 2011 - 2011 Int. Conf. Commun. Signal Process. 218–220. https://doi.org/10.1109/ICCSP.2011.5739305

Schneider, C.A., Rasband, W.S., Eliceiri, K.W. (2012) NIH Image to ImageJ: 25 years of Image Analysis. Nat. Methods 9: 671–675. https://doi.org/10.1007/978-1-84882-087-6_9

Spottiswoode, C. N. & Stevens, M. (2010) Visual modeling shows that avian host parents use multiple visual cues in rejecting parasitic eggs. Proceedings of the National Academy of Sciences of the United States of America 107 (19): 8672–8676. https://doi.org/10.1073/pnas.0910486107

Troscianko, J. & Stevens, M. (2015) Methods in Ecology & Evolution 6(11): 1320-1331. https://doi.org/10.1111/2041-210X.12439
