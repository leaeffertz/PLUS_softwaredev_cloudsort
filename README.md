# Sorting of Cloud Cover in Sentinel Imagery using (Python and GEE) #

This python group project aims to sort, filter, classify and remove cloud-contaminated pixels from satellite imagery (sentinel imagery) within a defined Area of Interest (AOI), using Google Earth Engine (GEE) and python (geemap). Cloud masking on GEE involves the identification and removal of cloud-contaminated pixels from satellite imagery. Sentinel-2, equipped with the MultiSpectral Instrument (MSI), captures high-resolution multispectral data. However, cloud cover can hinder the interpretation of Earth’s surface features. Removing cloud contaminated pixels using python technique (GEE) enhances the usability of Sentinel-2 imagery for various applications, including land cover classification, vegetation and environmental monitoring, and change detection. The main objective is to ensure that we are able to identify cloud free image which can be used for futher analysis.

# Tasks
Access GEE's Python API

Filter satellite images by AOI and date

Sort images by cloud coverage within the AOI

Provide a Jupyter Notebook with the code. Documentation

# Features
Automatically gets Sentinel-2 imagery within a given area of interest (AOI) and time period which help detects and categorizes clouds using the Sen2Cor algorithm.

Uses the cloud masking method of Google Earth Engine to sort the images according to the amount of cloud cover.

Visualization of cloud coverage for each image in the collection.

Exports the clearest pictures for futher examination.

Interactive widgets for configuring parameters, such as start and finish dates and cloud thresholds, are optional.


# 1. Gaining Access to GEE
We all gained access to the Google Earth Engine (GEE) Python API before commencing the project. we also followed different tutorial online. Examples are Open Geospatial Solutions' tutorial to authenticate and install the necessary tools (geemap) using python API(anaconda).

# 2. Filtered Images
We define an Area of Interest (AOI) either by downloading a folder that contains the shp filee.

# 3. Sort Cloud Coverage
Cloud Masking at Pixel Level: Use GEE's cloud masking method to refine the imagery, ensuring minimal cloud interference in the AOI.

# 4. Jupyter Notebook
All code and steps have been combined into a well-documented Jupyter Notebook. The notebook contains sections for accessing and filtering GEE data, implementing cloud masking, and sorting the results. The code is organized for ease of understanding and reusability.

# Educational Materials
For further learning, refer to the learning_resources.md file, which contains guides, instructions, and videos relevant to GEE, geemap, and cloud cover classification techniques.

# Contributors
Owhorji Miracle Chinwe
Yana Nikolova
Damilola Oluwaseun Alfred
Lea Effertz
