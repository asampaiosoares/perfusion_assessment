Measure tissue oxygen saturation and fluorescence intensity in colonic segments using calibrated cameras

This script calculates the distance from a stereo camera to a face using a pair of images, one from an infrared (IR) camera and the other from a multispectral imaging (MSI) camera. It also analyzes oxygen saturation (SO2), total hemoglobin (THb), and the concentration of lipids (cLd) in the region of interest, and plots their intensities at different distances.
Features

    Loads stereo parameters for IR and MSI calibration images
    Reads in a stereo pair of images and resizes them if necessary
    Undistorts the images using stereo parameters
    Triangulates equidistant points on a line segment in both images
    Marks distances at 1 cm (or smaller) intervals on the line segments
    Calculates the mean intensities of IR, SO2, THb, and cLd at each distance
    Plots the intensity measurements against the distance

Usage

    Set the following variables at the beginning of the script:
        to_print: Set to 1 to print images and figures, 0 otherwise
        to_save: Set to 1 to save images and figures in the "results" folder, 0 otherwise
        wind_or_regmask: Set to 1 to use the mean of a window size, 2 to use the mean of the whole region obtained using the mask
    Load stereo parameters, image paths, and calibration data for the desired case.
    Run the script to obtain the mean intensities of IR, SO2, THb, and cLd at different distances.
    The script will generate and save images and plots, if to_print and to_save are set to 1.

Functions

    sb_triangulate: Triangulates equidistant points on a line segment in both images and returns the coordinates of those points in both images and the new distances.
    MSI_IR_intensity_per_cm: Calculates the mean intensities of IR, SO2, THb, and cLd at each distance and returns their mean intensities.

Requirements

    MATLAB
    Image Processing Toolbox
    A pair of stereo images (IR and MSI) and their corresponding masks
    Stereo calibration data

Limitations

    The script is designed to work with specific input data and might not be directly applicable to other datasets without modification.
    The accuracy of the results depends on the quality of the input images and calibration data.
