# Geographic coordinates to UTM Converter
## About
This project is a Python program that converts geographic coordinates from a CSV file into UTM coordinates.
## Motivation
As a environmental analyist, one of my responsabilities is to gather information about water extraction sites located near the project area. To do this, I download datasets (excel format) from  Brazilian environmental agencies (i.e Water Use Permits from SP Águas).  
Some of the information in these datasets is relevant because of the proximity of the sites to the project location. However, the coordinates are usually provided as geographic coordinates in decimal degree. At work, I use ArcMap as my Geographic Information System (GIS) software, and needed the coordinates in UTM format for my workflow.

So, the usual workflow would be:  

Clean and organize coordinates -> Import the data to Google Earth -> locate the points of interest -> save them as KML -> import KML points to ArcMap -> convert KML to shapefile.  

However, I was spending too much time doing all those steps. While learning Python, I realized that I could automate part of this workflow by creating a program that converts geographic coordinates directly to UTM coordinates, reducing the steps to:  

Clean and organize coordinates -> input csv file with geographic coordinates to Python and create output csv file -> open csv file with UTM coordinates on ArcMap.  

This process allowed me to reduce some steps to the workflow and save time. And it was also an opportunity to apply Python to a real problem from my professional field.
## Features 
- Reads geographic coordinates (DMS and decimal degrees) from a CSV file.
- Converts coordinates to UTM.
- Processes multiple coordinates.
- Generates a new CSV file with the converted coordinates.

## Technologies
- Python
- CSV module
- Regular expressions (`re`)
- PyProj

## Input and Output
### Input
The program reads geographic coordinates from:  
`data/outorgas.csv`  

The input file <ins>**must**</ins> contain columns for:
- Point ID
- Longitude
- Latitude
  
The converted coordinates are saved to:  
`output/outorgas_utm.csv`  

The output file contains the following columns:  
- Point
- UTM zone
- UTM X coordinate
- UTM Y coordinate
