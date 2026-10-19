# Discovery and Orbits

## Background

In this exercise, we will use publicly available data from the Zwicky Transient Facility (ZTF) and/or Asteroid Terrestrial-impact Last Alert System (ATLAS) surveys to demonstrate how asteroid discoveries are made. The aim of these surveys is to detect transient events—that is, objects in the night sky that change in brightness (such as supernovae and variable stars) or position (including Solar System objects like asteroids). In practice, the ZTF and ATLAS use automation to detect asteroids—in this exercise, we will do the same process by hand. 

Astronomical images returned from telescopes are typically stored using the Flexible Image Transfer System (FITS). These files typically consist of a header, which stores information in the form of keyword-data pairs and typically includes a lot of technical information about the instrument setup, telescope location, and image properties. Following the header, the image is stored as an array of values corresponding to the measured brightness at every pixel of the detector. We will use [ds9](https://sites.google.com/cfa.harvard.edu/saoimageds9/), a free program commonly used to examine FITS images that is available for Windows, Mac, and Linux. 

- To **open an image**, click file > open and use the file browser to select an image
- To **adjust the brightness of a frame**, click scale > zscale
- To **add a frame**, click frame > new, then open an image in the new frame
- To **blink between frames**, click frame > next *or* use the Tab key to cycle through all open frames
- To **align the frames**, click frame > match > Frame > wcs
- To **examine the header** of an image click file > header
- To **estimate the location of an object** simply move your cursor over the pixels in the image and exame the $\alpha$ (RA) and $\delta$ (Dec.) fields in the upper left corner. If needed, switch between sexagesimal and decimal degrees by clicking wcs > sexagesimal or wcs > decimal.
- To **determine the exact location of an object**:
    - Enter region editing mode, by clicking edit > region of use Ctrl + R
    - Click the approximate location of the object in the image to draw a circle there
    - Click on the outline of the circle to select it
    - Click region > centroid to center the circle on the brightest part of the encircled area
    - Click region > get information to obtain its coordinates

## Instructions

1. [Download and install ds9](https://sites.google.com/cfa.harvard.edu/saoimageds9/).
2. Each dataset consists of a series of images of the asteroid over the course of several different nights. Download all the images corresponding to your asteroid. Identify which set of frames belong to each night. For each night, open the series of images as frames and blink between them to identify which object is the asteroid.
3. For each image, record the position of the object in sexagesimal (hours/degrees, minutes, seconds) and the time and date the image was taken (see the DATE-OBS keyword header) and the location of the telescope that took the image (see header keywords SITELONG, SITELAT, and SITEELEV and table below):

|Site Code | Longitude |Latitude | Altitude (m)|Site Name|
|--|--|--|--|--|
|M22|20.81059|-32.380158|1802|ATLAS South Africa|
|T05|203.74299|+20.707553|3046|ATLAS Haleakala|
|T08|204.42395|+19.536152|3426|ATLAS Mauna Loa|
|W68|289.23502|-30.471012|1600|ATLAS Chile|
|I41|243.14021|+33.180866|1664|Palomar Mountain (ZTF)|



4. Determine the orbit of your object based on the measurements you took in Step 3. There are several ways to do this:
    - Use the [Project Pluto webapp](https://www.projectpluto.com/fo.htm). This app expects each line of the input data to be in a very specific format (the leading spaces are important!):
      
      `     EXAMPLE  CYYYY MM DD.DDDDDDD RA RA RA.RA +DEC DEC DEC.DEC          0.00         XXX`
      
       Where YYYY is the four digit year, MM is the two digit month, DD.DDDD is the day + fraction of the day (you will need to calculate this), RA RA RA.RA is the right ascension in sexagesimal, DEC DEC DEC.DEC is the (signed) declination in sexagesimal. XXX is the three digit observatory code (see table). 
    - Install and use the Python package [kete](https://dahlend.github.io/kete/auto_examples/plot_orbit_fit.html) to perform orbit fitting if you have some familiarity with Python. An example notebook is available. If you do not wish to install Python and kete on your own computer, you can run the notebook in your web browser using [Binder](https://mybinder.org/v2/gh/oriel-humes/open-asteroids/HEAD).

        Using the file browser on the left, you can navigate to the Orbit-Fitting-Demo notebook you would like to run and open it. Select the cell you wish to run and press Shift+Enter or the ► icon to run the code. You can also modify the code in place in your browser and re-run it to examine how the results change as you change the code. You may also upload your own files (such as your dataset) so that the program can read them by clicking the file folder icon > upward arrow icon and selecting a file from your computer, and download files generated by the code by right clicking them in the file browser and selecting 'Download'.

5. Answer the following questions:
    - What can you say about the orbit of this asteroid, based on these results? What is the physical meaning of each orbital element?
    - What dynamical class does this asteroid belong to?
    - Sketch, plot, or otherwise visualize the orbit of the asteroid relative to the orbits of the planets.
    - How big are the uncertainties on the orbital parameters? How do the estimated uncertainties change as additional datapoints are included?

## Discussion Questions

1. What is the theoretical minimum number of data points needed to uniquely determine an orbit? Why (from a physical/mathematical point of view) is this the minimum?
2. How would you automate the detection process for asteroid discovery? Research methods present day surveys (ATLAS, ZTF, LSST, etc.) use to detect moving objects and determine their orbits.
3. Consider the effect of measurement errors on orbit determination. How would you identify and correct for outliers or erroneous position measurements in a large, heterogenous dataset? How would you account for variations in data quality (i.e. some telescopes can measure positions more precisely than others)?
4. How do measurement errors affect the quality of the fitted orbit? Why are some orbital parameters able to be more precisely determined while others are more uncertain? How do errors/uncertainties in fitted orbital parameters affect planning considerations for future observations?
