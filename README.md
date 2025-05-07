# georeferencing_over_water
Georeferencing aerial imagery over water using only positional information 

This script is designed to project aerial photographs onto an estimated flat surface without any "stitching" or orthorectification. This allows imagery to be approximately geolocated in space without fixed/static features for reference. The incorporation of platform orientation (pitch, yaw, roll) makes projected locations more accurate than an assumed nadir perspective. This treatment was developed for mapping of water surfaces (e.g. sea ice, surface chlorophyll, marine wildlife) where orthorectification is not necessary and static features are generally absent, but it may also find use in cases where images lack sufficient overlap for stitching (although relief distortions will be present in landscapes with dynamic elevation).

This is a work in progress, with positional_georeferencing.ipynb currently configured to handle imagery from a Sony a6100 camera mounted in a Wingtra One Gen II drone, but it can easily be modified to handle other cameras if the metadata are accessible through the exifread package. Requires a set of geotagged aerial photos with full positional metadata and a CSV flight log from the Wingtra with columns [ time(UTC) | lat | lon | alt ] (script can be modified to use GPS time from image timestamps, but an offset will be necessary to account for vertical datum displacement). Script is annotated such that it should be a straight-forward process to modify at the input stage or once everything is in a pandas dataframe. I recommend that outputs be "sanity checked" in a GIS to ensure that cameras aren't upside down, the rotation matrix is appropriate, etc..

![screenshot of georeferenced images and shapefile of footprints](https://github.com/gl7176/georeferencing_over_water/blob/main/ss.jpg)
Example 1: Georeferenced photos of glacial ice drifting on the sea surface. Ice movement is apparent as transects progress from lower-right to upper-left.

![screenshot of another georeferenced images and shapefile of footprints](https://github.com/gl7176/georeferencing_over_water/blob/main/ss2.png)
Example 2: Georeferenced photos of a coastal beach without orthorectification, overlaid on an orthomosaic from the same dataset.
