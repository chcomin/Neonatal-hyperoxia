Blood vessel quantification code for the accepted paper: Neonatal hyperoxia in mice impairs cerebrovascular function, neurogenesis, and behavior into adulthood, The Journal of Clinical Investigation.

The repository contains a single zip file because there are many empty subfolders in the "data" folder, included for facilitating the use of the software.


The software is organized as follows:

- Folder "data" contains the images to be processed and results from the software. There are a number of subfolders:

For blood vessels
Original: blood vessel images to be processed. The images must be inside a folder containing the experiment name
Interpolated: can contain the results after the interpolation step (making the image isotropic). Not used.
Binary: contains the results of the blood vessel binarization step. Folder numpy has the results as numpy arrays
Skeleton: contains the results for the blood vessel skeletonization step
Network: contains the generated blood vessel networks. 'original' and 'simple' are intermediate steps results. The final network is saved in folder 'core'.
tests: hold the results for threshold testing
thresholds.txt: contains the parameters to be used in the adaptive thresholding method. See read_thresholds() in file process_images.py

- Folder "source" contains all the source code. File process_images.py is the main script for processing blood vessels, used for binarizing, calculating the skeleton and generating the network. File quantify.py measures the length and number of bifurcation points of blood vessels and file tortuosity.py calculates their tortuosity. File detect_neurons.py detects neurons and quantify their density as a function of the distance to the cortex surface.

- Folder "results" contains the measured values (length, number of bifurcation points and tortuosity)

There is no user interface or terminal commands. Therefore, one needs to modifiy the scripts directly in order do adapt them to their own data. There is a compiled C code for calculating the skeleton that will only work on Linux (libskeleton.so).

An example batch folder is included in all data folders ("1 year"), but without the data, since it would make the size of the code repository very large.


Requirements (version number):
numpy (1.16.2)
scipy (1.2.1)
matplotlib (3.0.3)
scikit-image (0.15.0)
natsort (6.0.0)
igraph (0.7.1)
oiffile (2013.08.02)
tifffile (2019.7.2)
Czifile (2015.08.17)
pillow (6.1.0)
opencv (3.4.2)

Copyright (C) 2022 Prof. Cesar Henrique Comin, Department of Computer Science,
Federal University of São Carlos, São Carlos, SP, Brazil
chcomin@gmail.com
