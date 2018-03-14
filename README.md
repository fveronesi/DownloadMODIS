# DownloadMODIS
Code to download multiple MODIS titles in R

## Introduction
Several packages and functions already exist to download and process MODIS tiles. Examples are [her](http://r-gis.net/?q=ModisDownload) and [here](https://cran.r-project.org/web/packages/rts/index.html). I tried all functions but unfortunately I was not able to make them work in my scripts. The downloading phase was smooth, but then the processing always had some issues, particularly with the execution of the [MODIS Reprojection Tool](https://lpdaac.usgs.gov/tools/modis_reprojection_tool).
For this reason I had to improvise and write an _ad hoc_ script for my needs. However, I used chuncks of the code from the script on r-gis.net, particularly to create the .prm files needed for the MODIS reprojection tool to work.

## Usage
The function `DownloadMODIS` allows to download a single title from any folder from the MODIS website. In there the only setting that needs to be changed are `username` and `password`, which are required to access the NASA website and download data. 
