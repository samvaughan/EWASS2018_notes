# Wednesday- Software in Astronomy

## Software Engineers as Partners in Astronomy SoftwareDevelopment -John Wenskovitch

"Software is the most prevalent of all the instruments used in modern science." Institutions need individuals with a new professional designation- the "research software engineer". These individuals combine a professional attitude to the exercise of software engineering and a deep understanding of research topics. 

The specialist should _not_ be an IT helpdesk or a downtrodden developer! Nobody gets into CS to only write code. Give them interesting jobs and plenty of feedback. 

Tips:

* Communication
* Prioritised Feature list
* Testing! Unit tests, regression tests, usability tests. Tests should be short- test one thing!
* Documentation

## Research Software Engineering- The DiRAC facility experience- Mark Wilkinson

Research software engineers allow you to take your code from one HPC cluster (e.g a university cluster) and transition into a bigger cluster (e.g DiRAC). DiRAC has 114 Tb of RAM in its "memory intensive" Durham centre!

Science requirements for DiRAC-3 require 10-40x increases in computing power to stay competitive. This can't be done by hardware alone! We can no longer rely on the "free lunch" from the Xeon era. You used to be able to write some code, wait for new hardware in two years time and make it run as quickly as needed. Not any more- getting the best from new hardware is _not simple_.

## Research Programming- David Perez-Suarez

Pretty much everyone uses software. Not many people are _taught_ to code, however.
Software Carpentry- introductory two day courses. 
Contribute to open source
Use version control!

## Test-driven development in astronomy- James Nightingale

The astronomer's development cycle:

* Write code
* Write mode code
* Something works, so I better not change it
* 6 months later... :-( 

Structure and planning is the difference between surgery and cutting people's bodies open. But we're not taught or encouraged so structure and plan our code properly. 

The test-driven development cycle:

* Write a unit-test _first_
* Run the test and _make sure it fails_
* Now you write the code
* Run the test to check it passes

Trivial examples make it hard to understand how this works though! Example- PyAutoLens. Check the [github](https://github.com/Jammy2211/PyAutoLens)! One step had to transform from Cartesian to elliptical coordinates. James couldn't think of a single unit test to check this issue. So break it down! Find the smallest chunk that you know how to test. TDD forces you to see a big problem in terms of simpler smaller ones. You then end up with a set of well tested functions which you can stack together nicely. 

Test Driven Development is _not_ a testing process, it's a development process! It makes you focus on the code you should write before you do so. 

The fifth step of this process is "refactoring". This terrifies astronomers! You certainly have no confidence that you haven't accidentally broken something silently. 

## Sustaining the Montage Image Mosaic Engine since 2002- Bruce Berriman

[Montage](http://montage.ipac.caltech.edu/) is a toolkit for assembling fits images into custom mosaics. It can make really nice images. It's a toolkit, not an application. It's command-line driven, easily built, written in C. No reliance on shared memory or third-party packages. 

It was developed such that each module performs one task, and only one task. One crucial package is background rectification, i.e. rescaling all images to have the same background level. Crucial for making sensible maps!

Berriman's law- the grumpier the user, the more helpful the feedback. Montage had to respond to user feedback that they couldn't write scripts with it and it was too slow. Furthermore, backwards compatibility was always at the forefront of development- scripts written in 2003-2004 will still run on the latest version of the code. 

There's now a python version/package. 

## A walk through the python ecosystem- Amruta Jaodand

Python started in 1989 when Guido van Rossum started a "hobby" programming language in the week before Christmas. Check out [The Zen of Python](https://en.wikipedia.org/wiki/Zen_of_Python) and [Python4Astronomers](http://python4astronomers.github.io/). PyPI has 134,000 packages available for download

Key packages:

* IPython and Jupyter notebooks
* Scipy
* NumPy

I'll need to look up [AstroML](http://www.astroml.org/user_guide/index.html).

## The Astropy Project: A community Python library and ecosystem of astronomy package- Brigitta Sipocz

Open source does not mean open development. Astropy is an example of open development, made for the community and by the community. It aims to foster an ecosystem of interoperable packages to avoid everyone writing their own code to do simple things. 

It's optimised for python 3. There are affiliated packages which adhere to astropy coding, testing and documentation guidelines and add features not suitable/too specialised for the general astropy codebase. They use astropy wherever possible and share resources. A few examples are "ccdproc" and "astroplan", for planning astronomical observations. 

# Final Session

## MADCUBA and SLIM- Sergio Martin

Software to analyse datacubes. Two key principles are efficiency and "easyness". Implemented as a plug in within the ImageJ framework. ImageJ is an open source image processing program, similar to DS9 I think. Mainly used in life sciences. 

Handles a wide range of intensity units, etc- fits files are not standardised! Only available for ALMA and Herschel datasets though it seems? Great for many individual cubes (e.g example with 4x10^9 pixels across 100 cubes). Ability to run scripts is very nice. 

SLIM is the Spectral Line Identification and LTE Modelling library for MADCUBA. 

## M/L of Globular clusters- Hannah Dalgleish 

GCs are ideal labs for kinematic studies, since they're relatively simple systems. M/L ratios are a proxy for the ratio of high to low mass stars, and GCs can help to constrain single stellar population models. 

It was recently found that the predicted M/L is not obsvered- M/L decreases with metallicity (Djorgovski+97, Strader+09, Kimmig+15). Metal-rich GCs have M/L values less than half of that predicted by the models.

WiFeS is an IFU on the ANU 2.3m telescope. WAGGS is the Wifes Atlas of Galactic Globular cluster Spectra (Usher+17). 84 MW GCs, and 30 MW satellites. 

Extracted using PampelMuse to extract spectra from crowded fields. Find T and surface gravity from MIST isochrones for NGC 6121. Seem to get good masses and velocities, in agreement with other studies.
