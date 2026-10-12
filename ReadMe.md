# Open Science Exercises for Asteroids and Comets 

We are living in a golden age of open astronomical data, with more and more astronomical facilities providing access to their data archives. With an internet connection and a laptop, anyone can access a wealth of research-quality astronomical data in minutes. 

**Even you!**

This repository is just a brief introduction to some of the resources available, presented in the form of ready-to-be assigned problem sets focusing on investigating small Solar System bodies (asteroids, comets, and TNOs). I (Oriel Humes) developed during my postdoc at Technische Universität Braunschweig to supplement the Solar System Physics masters elective courses on small bodies (asteroids, comets, and TNOs). 

The exercises are inspired by a real research problem: when we discover a new or unknown Solar System object, how do we characterize it? Besides being a compelling question for those of us interested in small Solar System bodies as a subject of basic research, this question has broad potential applications for planetary defense, spacecraft mission planning, and in situ resource utilization. Through these exercises, over the course of a semester, students are given their own premade collection of datasets containing information about a mystery asteroid whose identity is unknown to them. Over the course of the semester, students use different techniques to analyze these datasets to learn about the properties of their mystery asteroid. At the end of the semester, given what the students have learned from the datasets, they attempt to identify which asteroid they have been studying based on the information they have extracted from the datasets. My general philosophy in designing these exercises was to:
* Encourage critical analysis of real astronomical data 
* Engage students with analysis tasks, software, and tools used by professional working astronomers
* Empower students (and instructors!) to engage with the wealth of publically available astronomical datasets
* Encourage students to invest a personal interest in investigating science questions
* Lower barriers to accessing educational resources pertaining to Solar System astronomy
  
Alongside the exercises, you will find supplementary materials including pre-made datasets, example Python notebooks for data analysis tasks, as well as a guide for instructors on how to produce your own sample dataset(s). You are encouraged to adapt this material for your own teaching/learning needs!

## Acknowledgements 

Without the dedication of the following individuals, groups, and institutions to transparently archiving data and/or curating free analysis tools, this repository would not exist:

* NASA's [Planetary Data System's](https://pds.nasa.gov/) [Small Bodies Node](https://sbn.psi.edu/pds/) (PDS SBN)
* The NASA/Caltech [Infrared Science Archive](https://irsa.ipac.caltech.edu/frontpage/) (IRSA)
* The International Astronomical Union's [Minor Planet Center](https://www.minorplanetcenter.net/) (IAU MPC)
* * The [JPL Horizons](https://ssd.jpl.nasa.gov/tools/) online ephemerides and database tools
* The [Fink Collaboration](https://fink-broker.org/)
* The [Institut de mécanique céleste et de calcul des éphémérides](https://www.imcce.fr/services/ephemerides/) (IMCCE)
* The [Asteroid Lightcurve Photometry Database](https://alcdef.org/) (ALCDEF)
* The [Database of Asteroid Models from Inversion Techniques](https://damit.cuni.cz/projects/damit/) (DAMIT)
* The [Small Bodies: Near and Far (SBNAF) database](https://ird.konkoly.hu/) of thermal infrared measurements of small Solar System bodies
* The [Gaia Data Processing and Analysis Consortium (DPAC)](https://www.cosmos.esa.int/web/gaia/data-release-3)
* [Project Pluto](https://projectpluto.com/home.htm) 
* [Comet-toolbox](https://www.comet-toolbox.com/index.html), created and maintained by Dr. Jean-Baptiste Vincent
* Lowell Observatory's [Minor Planet Services](https://asteroid.lowell.edu/)

The following Python packages were used to make much of the material in this repository possible

* [numpy](https://numpy.org/)
* [matplotlib](https://matplotlib.org/)
* [astropy](https://www.astropy.org/)
* [astroquery](https://astroquery.readthedocs.io/en/latest/)
* [pandas](https://pandas.pydata.org/)
* [kete](https://dahlend.github.io/kete/)

## Licenses

Except where otherwise noted, the exercise texts are provided under the Creative Commons 4.0 license and the Python code written by me is provided under the MIT license. Image and data credits (and licenses) can be found where they are referenced. *Please refer to the original authors of papers when using their datasets for original research.* Many of the databases and analysis tools also request specific acknowledgement statements if their services are used in original research, please see the respective websites for the texts such acknowledgements.
