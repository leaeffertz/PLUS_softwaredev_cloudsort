Overview of Sorting Cloud Cover

This python group project attempts to sort and classify satellite images (sentinel imagery) acccording to the amount of cloud cover within a defined Area of Interest (AOI). The main aim of this project is to give users the ability to filter images based on cloud cover by using Google Earth Engine (GEE) and python (geemap).


Tasks:
Accessing GEE's Python API.
Filtering satellite images by AOI and date.
Sorting images by cloud coverage within the AOI.
Providing a Jupyter Notebook with the code.
documentation.


Table Contents

Existing Classifications for Cloud Coverage
How Current Algorithms work
Project Setup
Gaining Entry to GEE
Filter Image Collection
Cloud Coverage Sorting
User Guide
Package for Python (Optional)
Educational Materials


Existing Classifications for Cloud Coverage
It's critical to comprehend the current cloud cover categories used in remote sensing before creating our own approach. Numerous satellite data sources currently use automated methods to classify cloud coverage, including Sentinel-2 and Landsat.

Sentinel-2 detects and categorizes clouds using the Sen2Cor algorithm.
Clouds are hidden by Landsat using the Fmask algorithm.
These algorithms determine the percentage of cloud cover at the pixel level and label image accordingly. By including user-defined thresholds and pixel-level cloud masking inside a custom AOI, this project expands on previous techniques.

How Current Algorithms Operate
Current cloud detection algorithms examine spectral bands that record specific light wavelengths, aiding in the differentiation of clouds from other elements such as land, water, and vegetation.

Project Setup

1. Gaining Access to GEE
Make sure you have access to the Google Earth Engine (GEE) Python API before beginning to use the project. For further information on how to install the required tools (geemap) and obtain access to the API, you can refer to Open Geospatial Solutions' tutorial.
Output: All project group member should be able to access and utilize GEE in Python by the time this phase is finished.

2. Collection of Filtered Images

AOI (Area of Interest) definition
To begin, define an area of interest (AOI) by creating a bounding box on a map or by using a shapefile.

Filter by Date
The next action is to apply a date range filter on satellite images. For instance, we decide to use pictures taken between 2020 and 2021.

Select the Image Source
We will extract the image collection from GEE using an exemplary imaging source, like Sentinel-2 or Landsat 8.

Python code
# Sample code for filtering images
import ee
import geemap

# AOI Definition: 
aoi = ee.Geometry.Rectangle([min_lon, min_lat, max_lon, max_lat])

# Filter by clouds coverage and date.
sentinel2 = ee.ImageCollection('COPERNICUS/S2_SR_HARMONIZED') \
    .filterBounds(aoi) \
    .filterDate('2020-01-01', '2021-01-01') \
    .filterMetadata('CLOUDY_PIXEL_PERCENTAGE', 'less_than', 50)

3. Sorting Cloud Coverage
We will filter the image collection to only include images with cloud cover below 50-60% in the AOI.

Cloud Masking at the pixel level
To further refine our data, we will apply a pixel-level cloud mask using GEE's built-in tools. This ensures that the images selected for analysis have minimal cloud interference over our AOI.

python code
# Create a cloud mask for Sentinel-2 images
def cloud_mask(image):
    cloud_prob = image.select('MSK_CLDPRB')
    cloud_mask = cloud_prob.lt(20)
    return image.updateMask(cloud_mask)
Sorting by Cloud Coverage
After applying the cloud mask, we will sort the resulting images by their 
cloud coverage percentage to ensure we are working with the clearest images possible.

python code
# Sort images by cloud coverage in the AOI
sorted_images = sentinel2.sort('CLOUDY_PIXEL_PERCENTAGE')

4. Jupyter Notebook

We provide a Jupyter Notebook that combines the code used in this project. 
The notebook is well-documented, and the code is structured for ease of understanding.

Important Sections:

Accessing and filtering GEE data.
Implementing cloud masking.
Sorting and displaying results.

5. Educational Materials
For additional learning, see the resources in the learning_resources.md file, which include links to pertinent guides, instructions, and videos for the GEE, geemap, and cloud cover classification techniques.
The goals of the project, the workflow, and the ways in which users can engage with the tool are all explained in detail by this framework. 
Depending on the requirements of your project, you can change certain elements or add more specifics.