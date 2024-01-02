SPOTS v2

Date: 2023-11-03
Author: Klaudia Szala

INSTALLATION ====================================================================

These scripts require installation of ImageJ 1.54g (Schneider et al. 2012) with MICA Toolbox plugin
(Troscianko & Stevens 2015, http://www.empiricalimaging.com/). To use the scripts directly from ImageJ,
you should place them in ImageJ/plugins/spots folder. Then you can access them through plugins -> spots
in the menu bar.

DESCRIPTION ====================================================================

The scripts use normalised digital images (.mspec files) created with the MICA Toolbox software (Troscianko &
Stevens 2015).

A binary mask needed to segment an egg into spots and background coloration is created using local thresholding
with Phansalkar method (Phansalkar et al. 2011). In the current version, images can be converted
to selected visual models. First you have to prepare a custom visual model for your own camera set, check for more
information here: http://www.empiricalimaging.com/knowledge-base/ . The current version works with visible and
UV light and supports tri- and tetrachromatic models. If you don't have information in the UV light, you
can use e.g. Bluetit LMS model for UVS species and Peafowl LMS for VS species.

Spots are detected from avian double cones channel. If an image is not converted to any visual model,
normalised images are used for measurements and green channel is selected for spots detection, as it match the
spectral sensitivity of avian double cones (Spottiswoode & Stevens 2010).

I cannot guarantee that spots detection will be accurate, especially in the case when photographs were not taken
in diffused light. Because of their shape, eggs are difficult objects to measure and their edges are often shaded
what makes spots detection much more difficult. In the current version of the program, you can shrink selection
around the egg, to avoid measuring very dark edges. I also introduced a correction of uneven illumination using
Gaussian blur (following Gómez et al. 2018). But always the first and very important step will be to make effort
to take the best pictures you can, for example use a sheet of PTFE to diffuse light, don't photograph in very
variable light conditions, etc. It will be also a good practice to select a subset of highly variable eggs from
your set and check spots detection using "preview spotsDetection" function to work out the best settings and make sure
there are no surprises (for example distinct shades or light bouncing off the shell that makes pixels overexposed).
You can also save images of eggs with detected spots for preview using "percent spots" function. More details in the instruction.


Here is a brief description of all functions:

	- preview spotsDetection: it allows to preview the performance of the spots detection with different
		settings to work out the best settings for your set of photos
	- check overexposition: it checks what percent of an egg's area in pixels is overexposed, separately in
		every channel. It is best to avoid measuring overexposed pixels, so if there are some, try to use
		a picture with shorter exposition.
	- percent spots: counts percent of an egg's surface that is covered with spots
	- spots size: measures average size of spots (in pixels)
	- pattern dispersion: measures dispersion of patterning along the egg
	- spots colour trichromats: measures brightness and colour of spots and background separately. If a visual model
		is selected, then luminance and colour in terms of quantum catches is calculated (in linear, log or
		hiperbolic scale). Additionally, you can calculate coordinates in trichromatic colour space. These
		are X, Y coordinates and saturation in the Maxwell triangle if no visual model was selected and
		red-green and blue-yellow opponency (and saturation) in Receptor Noise Limited models (Vorobyev
		& Osorio 1998) for a selected visual model. Finally, it calculates achromatic and chromatic contrast
		between spots and background. IT WORKS ONLY WITH TRICHROMATIC MODELS AND WITH NORMALISED IMAGES WITH
		NO UV CHANNELS (only red, green and blue channels).
	- spots colour tetrachromats: measures brightness and colour of spots and background separately. If a visual model
		is selected, then luminance and colour in terms of quantum catches is calculated (in linear scale). It also
		calculates achromatic contrast between spots and background. IT WORKS ONLY WITH TETRACHROMATIC MODELS AND
		WITH NORMALISED IMAGES WITH BOTH VISIBLE AND UV CHANNELS (red, green, blue, UVB and UVR channels).
	

All images should be uniformly scaled for spots measurements to be comparable across photographs. First use
plugins -> micaToolbox -> Image Analysis -> Batch Scale Bar Calculation to calculate minimum px/mm factor
in the whole folder of images. You should use this value or round it down (Troscianko & Stevens 2015). For example if minimum
px/mm is 27.78 you can use 27.78, or round it down to for example 27.5, 27 or 25 (but do not round it up to 28!).
You will need this value in most of functions - just provide it next to "Scale images (px/mm)" in the window
with settings that will pop up when you select one of scripts and the code will do the rest.


REFERENCE =====================================================================

Gómez, J., Ramo, C., Troscianko, J., Stevens, M., Castro, M., Pérez-Hurtado, A., Liñán-Cembrano,
Gustavo Amat, J.A., 2018. Individual egg camouflage is influenced by microhabitat selection and use of 
nest materials in ground-nesting birds. Behav. Ecol. Sociobiol. 72, 1–10.

Phansalkar, N., More, S., Sabale, A., Joshi, M. (2011) Adaptive local thresholding for detection of nuclei
in diversity stained cytology images. ICCSP 2011 - 2011 Int. Conf. Commun. Signal Process. 218–220.
https://doi.org/10.1109/ICCSP.2011.5739305

Schneider, C.A., Rasband, W.S., Eliceiri, K.W. (2012) NIH Image to ImageJ: 25 years of Image Analysis. Nat.
Methods 9: 671–675. https://doi.org/10.1007/978-1-84882-087-6_9

Spottiswoode, C. N. & Stevens, M. (2010) Visual modeling shows that avian host parents use multiple visual
cues in rejecting parasitic eggs. Proceedings of the National Academy of Sciences of the United States of
America 107 (19): 8672–8676. https://doi.org/10.1073/pnas.0910486107

Troscianko, J. & Stevens, M. (2015) Methods in Ecology & Evolution 6(11): 1320-1331.
https://doi.org/10.1111/2041-210X.12439

Vorobyev, M., Osorio, D., 1998. Receptor noise as a determinant of colour thresholds. Proc. R. Soc. B Biol. Sci.
265, 351–358. https://doi.org/10.1098/rspb.1998.0302
