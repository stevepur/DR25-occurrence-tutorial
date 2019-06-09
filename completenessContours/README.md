# DR25-occurrence-tutorial/completenessContours

These files support the creation of DR25 completeness contours.  They are a modified version of the code in https://github.com/nasa/KeplerPORTs.

If you downloaded this directory from https://github.com/stevepur/DR25-occurrence-tutorial then the completeness contour created by running the steps below "out_sc0_GK_baseline.fits.gz" is already included.  You do not need to run software in this directory to run this tutorial.

To use this code, you need the complete set of Window Function and One-sigma Depth Functions from https://exoplanetarchive.ipac.caltech.edu/docs/Kepler_completeness_reliability.html.  This is 397,418 files taking 588.29 GB of storage, downloaded with a wget script.  We assume this data is stored in completenessFiles/ below.

Before running this code, the following files must exist:
../stellarCatalogs/dr25_stellar_supp_gaia_clean_GK.txt (you may have this as a .zip file which needs to be decompressed)
../GKbaseline/vetCompletenessTable.pkl
These files are included as part of the tutorial package.

If these two files do not exist, run the Python notebooks ../createStellarCatalogs.ipynb and ../GKbaseline/binomialVettingCompleteness.ipynb.

Run the code with the following steps:

1) Edit "./make_contours_multiproc.txt" and change "/Volumes/yoru/dr25/dr25CompletenessFits" to the location of your Window Function and One-sigma Depth Functions downloaded above.  You may want to set the number of threads as appropriate to your machine via the variable nworkers in this script.  Currently nworkers = 8.  Then run "./make_contours_multiproc.txt" . This takes about 4 hours on a 12-processor machine.

2) wait until all the out*.fits files are converted to out*.fits.gz

3) run "python accumulate.py", which will create a file "out__.fits.gz".  Wait until the file "out__.fits" is deleted by the program.

4) rename "out__.fits.gz" to "out_sc0_GK_baseline.fits.gz"

5) run "python examgrid.py" to generate diagnostic plots.  

You're done!  Now you can run ../GKbaseline/computeOccurrence.ipynb.

