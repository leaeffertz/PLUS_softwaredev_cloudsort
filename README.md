# Sorting of Cloud Cover in Sentinel Imagery using (Python and Google Earth Engine) #

This python group project aims to sort, filter, classify and remove cloud-contaminated pixels from satellite imagery (sentinel imagery) within a defined Area of Interest (AOI) by downloading a shapefile, using Google Earth Engine (GEE) and python (geemap). Cloud removal in Google Earth Engine allows you to hide or highlight specific parts of an image based on certain conditions or criteria. The main objective is to ensure that we are able to identify cloud free image which can be used for futher analysis.

# Installation

1. Install Python: We installed anaconda to create and activate a new working environment.
2. Install the necessary packages such as geemap and geopandas, using pip.
3. Install a Jupyter Notebook which contains sections for accessing and filtering GEE data, implementing cloud masking, and sorting the results. The code is organized for ease of understanding and reusability.

# code to install the necessary packages using pip in python
!pip install geopandas
!pip install geemap


# code to create a new envirronment in python
conda create -n gee_env python=3.9
conda activate gee_env


# code to install jupyter notebook
pip install jupyter
jupyter notebook


# After installing the packages, We authenticate with Google Earth Engine account to access it in jupyter.
import ee
ee.Authenticate()
ee.Initialize()


# Path to the shapefile
We use an AOI by downloading a shp file of a region around salzburg
shapefile_path = "C:\Users\owhor\Downloads\PLUS_softwaredev_cloudsort-main\PLUS_softwaredev_cloudsort-main\Sample_data\Sample_AOI\AOI_Salzachauen_buffer_150m_WGS84_33N_gcs.shp"


# Setting the Time for the Sentinel-2 image collection.
start_date = "2020-01-01"
end_date = "2021-01-01"


# Visualizing our AOI on a Map
Create an interactive map and display our AOI:
Map = geemap.Map()
aoi = geemap.shp_to_ee("C:\Users\owhor\Downloads\PLUS_softwaredev_cloudsort-main\PLUS_softwaredev_cloudsort-main\Sample_data\Sample_AOI\AOI_Salzachauen_buffer_150m_WGS84_33N_gcs.shp")


# Add AOI to the map and center it
Map.addLayer(aoi, {}, "AOI")
Map.centerObject(aoi, 11)


# Display the map
Map


# Educational Materials
For further learning, refer to the learning_resources.md file, which contains guides, instructions, and videos relevant to GEE, geemap, and cloud cover classification techniques.


# Contributors
Owhorji Miracle Chinwe
Yana Nikolova
Damilola Oluwaseun Alfred
Lea Effertz
