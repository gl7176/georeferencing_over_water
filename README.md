# georeferencing_over_water
Georeferencing aerial imagery over water using only positional information

This is a work in progress, currently designed only to handle imagery from a Sony a6100 camera mounted in a Wingtra One Gen II drone. Requires a set of aerial photos with full metadata and a CSV flight log from the drone. Script is annotated such that it should be a straight-forward process to modify inputs for different metadata formats.

## THERE IS CURRENTLY AN ERROR IN THE CAMERA TRANFORM FUNCTIONS ##
owing to a misinterpretation of the roll parameter; it will need some re-calculation to tranform Tait–Bryan angles to Euler angles

![screenshot of georeferenced images and shapefile of footprints](https://github.com/gl7176/georeferencing_over_water/blob/main/Screenshot%202024-10-23%20170137.png)
