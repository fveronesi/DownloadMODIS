# DownloadMODIS
Code to download multiple MODIS titles in R

## Introduction
Several packages and functions already exist to download and process MODIS tiles. Examples are [her](http://r-gis.net/?q=ModisDownload) and [here](https://cran.r-project.org/web/packages/rts/index.html). I tried all functions but unfortunately I was not able to make them work in my scripts. The downloading phase was smooth, but then the processing always had some issues, particularly with the execution of the [MODIS Reprojection Tool](https://lpdaac.usgs.gov/tools/modis_reprojection_tool).
For this reason I had to improvise and write an _ad hoc_ script for my needs. However, I used chuncks of the code from the script on r-gis.net, particularly to create the .prm files needed for the MODIS reprojection tool to work.

## Usage
The function `DownloadMODIS` allows to download a single title from any folder from the MODIS website. In there the only setting that needs to be changed are `username` and `password`, which are required to access the NASA website and download data. I also included a script named `ExampleNDVI` where the function is used to download NDVI data from MODIS.

## Example
The first is a simple example of the function being use to download a single MODIS tile. Here I just included the ID and version of the dataset (which can be found here: [MODIS Product Table](https://lpdaac.usgs.gov/dataset_discovery/modis/modis_products_table)), plus date and tile ID (which can be identified here: [MODIS Grid](https://modis-land.gsfc.nasa.gov/images/MODIS_sinusoidal_grid1.gif)):
```
DownloadMODIS(MODIS="MOD13Q1", VERSION="006", DATE="2015.10.16", TILE="h18v05")
```

The second example is a loop to download several tiles from several dates automatically. The first thing to do is create some set-up parameters, like an object for the MODIS ID and version. We also need to write the path to the [MODIS Reprojection Tool](https://lpdaac.usgs.gov/tools/modis_reprojection_tool)

