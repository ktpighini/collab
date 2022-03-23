## Basic Shakedown Notebook for GUFI data (23/03/22)

### Purpose is to have a rough & ready means of extracting & processing data

#### Steps

1. Locate files (bias, flats, science)
2. Find out what biases match to flats/science frames
3. Process flats
4. Process science frames (using biases/flats)
5. Dump out stacked science frame
6. Align stack of frames
7. Do basic aperture photometry & create time-series
8. Do more advanced photometry (using annuli) & create time-series

For this example we're going to work with data taken on December 20th 2017, the target was the binary LP349-25

From the log

- 4 observations of LP349, in I band, 5 sec exposures, in 600 exposure blocks (airmass ~ 1.03 - 1.3)
  - some cloud for exposure 3, and 4
- 6 flat field observations in I, 5 sec exposure with the following information as regards total depth in photons
  1. 1 x 1 (3k)
  2. 1 x 1 (5k)
  3. 5 x 10 (7k)
  4. 5 x 10 (9k)
  5. 3 x 60 (9k)
  6. 1 x 6 (8k)
- no information on biases, presume they ran the standard pattern (which is to run a script that generates a stack of biases for the different settings `Electron Multiplying`/`Conventional`, `PREAMP` and `READTIME`)
- seeing was ~ 1.6" $\rightarrow$ 2.3"

Some idiosyncracies

- the bias files listed are a result of some sort of crazy shell  script, which generates a masterbias FITS for a specific blend of  instrumentation Andor settings
- the flats and/or science frames are usually at one of these settings
- the original GUFI pipeline automagically finds which is which - in practise it never does, we'll have to do it the hard way here   

---

#### Notebook 1 

- locate files
- Find out what biases match to flats/science frames

