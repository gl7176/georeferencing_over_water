# positional_georeferencing
Georeferencing aerial imagery using only positional information 

This script is designed to project aerial photographs onto an estimated flat surface without any "stitching" or surficial orthorectification. This allows imagery to be approximately geolocated in space without fixed/static features for reference. The use platform and gimbal orientation (pitch, yaw, roll) makes projected locations more accurate than an assumed nadir perspective. This treatment was developed for mapping of water surfaces (e.g. sea ice, surface chlorophyll, marine wildlife) where orthorectification is not necessary and static features are generally absent, but it may also find use in cases where images lack sufficient overlap for stitching—although relief distortions will be present in landscapes with dynamic elevation.

This is a work in progress, with **positional_georeferencing.ipynb** currently configured to handle imagery from a Sony a6100 camera mounted in a Wingtra One Gen II drone, but it can easily be modified to handle other cameras if the metadata are accessible through the exifread package.

A newer version, **positional_georeferencing_2.0.ipynb** has been redesigned to accommodate a variety of gimbaled DJI platforms. It has also been rewritten for parsimony, eliminating several dependencies, streamlining code, and separating the options for aux files, warped images, and shapefile outputs. It does not work with Wingtra imagery, has different metadata fields and requires rotational conversions to project camera perspectives. Additionally the shapefile output now contains only filenames, unlike the full metadata table included in the first version, although it would be easy to restore full attributes.

These scripts require geotagged aerial photos with positional metadata (pitch, yaw, roll) written to the image files. The Wingtra script also requires a CSV flight log with columns "time(UTC)" and "alt" (the script includes an option to use GPS altitude from exif data, but an offset will be necessary to account for the displacement of the vertical datum). The script is designed and annotated such that it should be straight-forward for a Python user to modify and troubleshoot for a new camera or platform. Familiarity with the pandas package, exif data, and rotational angles is recommended for the Wingtra script. 

I recommend that any outputs be "sanity checked" in a GIS to ensure that images closely align to their spatial context and shapefiles represent the expected flight characteristics.

![screenshot of georeferenced images and shapefile of footprints](https://github.com/gl7176/georeferencing_over_water/blob/main/ss.jpg)
Example 1: Georeferenced photos of glacial ice drifting on the sea surface. Ice movement is apparent as transects progress from lower-right to upper-left.

![screenshot of another georeferenced images and shapefile of footprints](https://github.com/gl7176/georeferencing_over_water/blob/main/ss2.png)
Example 2: Georeferenced photos of a coastal beach without orthorectification, overlaid on an orthomosaic from the same dataset.
