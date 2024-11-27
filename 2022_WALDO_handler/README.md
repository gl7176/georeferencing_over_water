This folder contains a heavily adapted version of the original script, modified to handle Waldo imagery with the IRMA csv format (https://doi.org/10.57830/2302816).

Resulting shapefiles and projected photographs are not exactly accurate image locations, but rather approximate estimated locations, assuming a perfectly level aircraft (in the absence of inclinometer measurements), with variation by altitude and heading (which is estimated from consecutive photo locations).

Example of projected photos on top of a footprint polygon:
![screenshot of georeferenced images and shapefile of footprints](https://github.com/gl7176/georeferencing_over_water/blob/main/2022_WALDO_handler/footprints_r.png)

Without examining on-land imagery it is difficult to tell whether gaps correspond to lags in the camera or lags in the GPS tags. I suspect the latter, but future work should examine more projected imagery and possibly incorporate a smoothing algorithm for GPS locations across a transect.
