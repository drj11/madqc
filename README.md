Median Absolute Deviation Quality Control
=========================================

This software will apply a very minimal QC stage to monthly
temperature data (for example, from GHCN-M or ISTI), using the
Median Absolute Deviation estimator.

## Method

For each combination of (station-id, element, named-month) the
median and the median absolute deviation are calculated (MAD,
which is the median of the distances of each datum from the
median). At least 20 monthly values are required, if the number
of values is insufficient, they are all rejected. Any value whose
distance from the median exceeds 5 times the MAD is rejected.

## Status

Experimental.

## Running

    ./mad.py [tavg.dat] > big.json

The input file should be in GHCN-M v3 .dat format. If the
filename is not specified as an argument, a file matching the
path

    ~/.local/share/data/isti/merged*.dat

is used. If there are several, the ASCIIbetically last is
chosen.
