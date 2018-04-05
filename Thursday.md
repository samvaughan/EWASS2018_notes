# Thursday- Galaxies

##  Fueling and quenching star formation in galaxies: from the filaments to the cluster cores. Pascale Jablonka 

The cluster-centric distance -local density relation is only valid in a statistical sense. The most massive and quiescent galaxies are the closest to the filament axis. They've also been there for the longest time, since these overdensities only get more dense. 

Maybe we should change the question from "How much are galaxies transformed by their environments?" to "How much do galaxies define their environments?". We should be able to find specific features to each type of density at a given look-back time. 

Ram-pressure stripping is often seen in HI gas. It's more difficult to strip cold gas (HII, CO) since it's more tightly bound in a gravity's potential well. There's no _clear_ evidence for cold-gas stripping, but we also see low SFR in cluster galaxies. Maybe there are distinct molecular gas properties in high-density environments?

SEEDisCS- Alma CO measurements at z~0.5. We need to enter a routine regime of surveys of cold gas in galaxies, putting them in context both spatially and in look-back time. 

## Kiloparsec scale [CII] gaseous and start formation at z~5-7- Stefano Carniani

[CII] is a great tracer for high-redshift studies. It's not affected by absorption along the line of sight like Lyman-alpha. First observations of (possible) rotating disks in [CII] emission at z>5 (Smit 2018, Nature). Are these common? 

z~5 LBG galaxy with interesting [CII] line profiles. Is the [CII] offset from the stellar light? Does it trace something else we don't see in the deep HST images? Hints of a multi-clump morphology, which would be expected from simulations. 

The "Himiko" galaxy is one of the brightest Ly-$\alpha$ emitters at z~6.6. It has three clumps in the rest-frame UV, The [CII] clumps don't trace the UV well though!  

29 high-z have been detected in [CII]. 40% of these have a multi-component morphology (in [CII] and UV). Can we use L[CII] as a SFR indicator? We see a similar trend to the local universe (calibrating from Ly-$\alpha$) but a scatter which is twice as large as z~0. 

Where does this dispersion come from? One possibility is metallicity- [CII] emission is higher in more metal-rich galaxies. Lyman-$\alpha$ shows the opposite trend with [Z/H], and indeed L[CII] and EW(Ly-$\alpha$) are (weakly) anticorrelated. 

Galaxy at z~7.1- [OIII] emission is offset spatially and in velocity (400km s$^{-1}$) from the UV. Again, to be expected from simulations- the UV can be obscured by dust. 

## Ly-$\alpha$ emission in the AzTEC-3 proto-cluster field- Lucia Guaita

Proto-cluster at z~5.3. Well studied- MUSE, HST, VLA. Discovered via sub-millimetre galaxies. Proto-cluster members identified using the MUSE cube. The region is confirmed as an overdensity, with 20 "members". Possibly the progenitors of massive Abell clusters today. 

We don't see galaxies distributed uniformly on the sky in this proto-cluster. Evidence for a filament of SMGs and a number of close pairs. Very preliminary work might indicate that Ly-$\alpha$ flux decreases towards the centre of the cluster- but no errorbars! 

# Software in Astronomy

##  Deep learning to study the noise in gravitational wave interferometers- Massimiliano Razzano

We're in the era of advanced GW detectors. But more detectors and sensitivity leads to more noise too! We need to detect and classify these glitches/noise sources as quickly as possible. 

Glitches come in a number of varieties, including "whistle" and "blip" in a frequency-time plot. They use deep convolutional networks to classify these "images". Network has 6 convolutional layers, 5 layers of pooling and a number of dropout layers. Runs on a GPU using CUDA, Keras, Tensorflow, etc. 

Deep network outperforms a linear SVM. Full results in Razzano & Cuoco 2018. Interestingly, you'd probably have to train a CNN on each individual GW detector, rather than having a single one across all detectors. 

## Selection of Spitzer YSO candidates using deep learning classifier- David Cornu

Classify young stellar objects into two classes. Inputs are IRAC and MIPS24 fluxes. Labels come from a previous data set (the Orion Catalogue). Only one hidden layer with 30 neurons. 

Results are good when you train and test on Orion YSOs. But things get a bit worse when you train on Orion and test on NGC 2664, and vice versa. Cross training seems to work better. 

Next steps are to try 'semi-supervised' methods, train with a better mix of clouds and add in distance measures from Gaia. Bespoke code with self-written back-propagation! Very cool, but perhaps explains why they only have one layer. 

## Data science for direct imaging of exoplanets. Machine learning applied to astronomical high-contrast imaging- Carlos Alberto Gomez Gonzalez

We've only directly imaged 1% of the number of known exoplanets. Like trying to detect a firefly next to a lighthouse! High contrast imaging is hard, and we need to do a lot of things to decrease the dynamic range of the image (e.g. coronagraphs) and get everything out of our data reduction.

The Vortext Image Processing Library is a package for exoplanet imaging and PSF subtraction, written in Python. Machine learning tries to detect exoplanets in these images. 

## k-means clustering in galaxy feature data- Sebastian Turner

Things like Galaxy Zoo will fail when it comes to future datasets like LSST and Euclid! we'll need to classify 10^7 galaxies (Galaxy Zoo has 10^5~6). 

k-means is pretty simple- pick some points in your parameter space, label each data-point with its nearest label, then move each label to the centre of the points, and iterate this until it converges. The best solution will be "compact". However your initialisation of your labels does affect the outcome (as well as obviously the number of clusters you want, i.e. the value of k).

Really nice examples of choosing which value of k to choose for a test dataset. 

In the galaxy example, interesting clusters appear on the colour-mass diagram. Forgot to write down the input parameters here. Should check out this work, it looks really interesting!

## Spatial inference of astronomical datasets with INLA- Emille Ishida

Spatial auto-correlations. Do correlations arise from physical effects or instrumental effects? Current approaches to IFU astronomy normally uses binning- e.g voronoi binning, Bayesian voronoi, etc. Instead, we can phrase it as a hierarchical model!

Take our physical property and model it as a Gaussian Markov random field. Add things to include the spatial correlation of pixels, and resolve the bayesian models. We end up with a posterior for each pixel- which is computationally impossible! Instead, use INLA (Integrated Nested Laplace Approximation ). Also can be useful for missing data to reconstruct maps. 

Read [Gonzalez-Gaitan 2018](https://arxiv.org/pdf/1802.06280.pdf). 

## Imbalanced Learning In Astronomy- Robert Lyon

Imbalanced data has one class which outnumbers another by a large extent. Sometimes this is fine, if the data is truly separable. More commonly, classes overlap, there are disjuncts (data from the same class occurs in different areas of parameter space) or one class is intrinsically very rare. Normal ML techniques find this very difficult to overcome. 

SKA can produce 72 million pulsar candidates per day! There are a few techniques we can use to fix imbalanced data. 

* Undersample the majority class (or oversample the minority class)
* Generate synthetic examples- GANs
* Decision trees find imbalanced issues easier than other ML techniques. 

See the [notebook!](https://zenodo.org/record/1212631)

