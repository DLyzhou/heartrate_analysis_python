***********
Development
***********

Release Notes
=============

V0.8.1
~~~~~~

- Added changelog to repository
- Implemented clipping detection and interpolation functionality
- Changed FFT calculation flag to default False, as in some cases the FFT takes very long to compute. Possible causes and fixes to be investigated
- Pushed readthedocs.io documentation source structure to repository
- Added encoding argument to get_data function, per the NumPy deprecation of not using encoding. For more info: https://docs.scipy.org/doc/numpy-1.14.0/release.html#encoding-argument-for-text-io-functions

V0.8.2
~~~~~~

- RR_difference interval no longer taken into account when RR-intervals are not technically adjacent due to rejected peak presence in between
- Moved matplotlib import statement so that it is no longer necessary unless calling the plot functionality, reduces need to install irrelevant dependencies when plotting functionality not needed
- Added Hampel Filter with settable filtersize
- Added method to suppress noisy segments called 'Hampel Corrector', called such as it's simply a Hampel Filter with large window size. Computationally on the expensive side so disabled by default, but very good at suppressing noisy segments without influencing peak positions in the rest of the signal.
- Added breathing rate extraction method. Stores estimated breathing rate in measures['breathingrate']
- Made BPM threshold values settable
- Added Periodogram- and Welch-based PSD estimation
- Added support for edge case where clipping segment starts early in signal, meaning there is insufficient data to interpolate accurately.

V1.0
~~~~
- Released Version 1.0
- Added flag to disable scaling when interpolating clipping segments. Useful for data with large amplitude variations.
- Added marking of rejected segments in plotter
- Added automatic peak rejection when first peak occurs within 150ms, since the signal might start just after a peak, which creates slight inaccuracy.
- Added segment rejection based on percentage of incorrect peaks.

V1.0.1
~~~~
- Changed segmentwise rejection API to simplify plotting

V1.1
~~~~
- We are now officially called HeartPy
- Changed overall structure to get rid of global dicts, allows for modular or multithreaded use easier.
- Changed docs to reflect changes


Questions
=========
contact me at P.vanGent@tudelft.nl