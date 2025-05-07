# georeferencing_over_water
Georeferencing aerial imagery over water using only positional information

This is a work in progress, with positional_georeferencing.ipynb currently designed only to handle imagery from a Sony a6100 camera mounted in a Wingtra One Gen II drone, but can easily be modified to handle other cameras if the metadata are accessible through the exif call. Requires a set of geotagged aerial photos with full metadata and a CSV flight log from the drone. Script is annotated such that it should be a straight-forward process to modify at the input stage or once everything is in a pandas dataframe. I recommend that outputs be "sanity checked" in a GIS to ensure that cameras aren't upside down, the rotation matrix is appropriate, etc..

![screenshot of georeferenced images and shapefile of footprints](https://github.com/gl7176/georeferencing_over_water/blob/main/ss.jpg)
Example 1: Georeferenced photos of glacial ice drifting on the sea surface. Ice movement is apparent as transects progress from lower-right to upper-left.

![screenshot of another georeferenced images and shapefile of footprints](https://github.com/gl7176/georeferencing_over_water/blob/main/ss2.png)
Example 2: Georeferenced photos of a coastal beach without orthorectification, overlaid on an orthomosaic from the same dataset.
