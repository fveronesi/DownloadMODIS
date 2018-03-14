# DownloadMODIS
Code to download multiple MODIS titles in R

## Introduction
Several packages and functions already exist to download and process MODIS tiles. Examples are [her](http://r-gis.net/?q=ModisDownload) and [here](https://cran.r-project.org/web/packages/rts/index.html). I tried all functions but unfortunately I was not able to make them work in my scripts. The downloading phase was smooth, but then the processing always had some issues, particularly witht he execution of the [MODIS Reprojection Tool](https://lpdaac.usgs.gov/tools/modis_reprojection_tool) 
