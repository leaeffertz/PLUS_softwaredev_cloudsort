
I am mostly interested in using the other API which is a Python library this is a pretty comprehensive guide to setting up and getting ready to code in the Python API.

# Import the Earth Engine Python Package
import ee

# Initialize the Earth Engine object, using the authentication credentials.
ee.Initialize()

# Print the information for an image asset.
image = ee.Image('srtm90_v4')
print(image.getInfo())

Will return
![alt tag](http://www.acgeospatial.co.uk/wp-content/uploads/2016/12/image1.png)

Get this far and you are ready to access and process all the data on Earth Engine. These are the datasets available, how many? 275! (NDVI, NSDI, Reflectance, NBRT etc etc).

Python API

There is not much information on the https://developers.google.com/earth-engine/ about Python, so GitHub is the place to now dive into.

So, just like ordering a sandwich, you can use the API to order whatever you want. Here I am asking for

    an edge detection on one tile of the panchromatic band of Landsat 8 and on a different Landsat 8 tile a true colour RGB (4,3,2) and then clipped to a region of my choice. 

No more downloading an image and then doing the processing; I am asking for exactly what I want.

![alt tag](http://www.acgeospatial.co.uk/wp-content/uploads/2016/12/image2-768x311.png)

Run the above script and go to the Earth Engine Code Editor (JavaScript) and you can see what is running and its status.

![alt tag](http://www.acgeospatial.co.uk/wp-content/uploads/2016/12/image3.png)

When its done

![alt tag](http://www.acgeospatial.co.uk/wp-content/uploads/2016/12/image4.png)

You’ll get a link as well to your google drive account

![alt tag](http://www.acgeospatial.co.uk/wp-content/uploads/2016/12/image5.png)

Click on the output link (I created a folder after running the script called imagery)

![alt tag](http://www.acgeospatial.co.uk/wp-content/uploads/2016/12/image6.png)

And here I go, out1.tif (its georeferenced aswell!)

![alt tag](http://www.acgeospatial.co.uk/wp-content/uploads/2016/12/image7-768x456.png)

And out 2

![alt tag](http://www.acgeospatial.co.uk/wp-content/uploads/2016/12/image8-768x456.png)
![alt tag](http://www.acgeospatial.co.uk/wp-content/uploads/2016/12/image9-768x456.png)

And to prove it is georeferenced, here is the OpenStreetMap data sitting behind it

![alt tag](http://www.acgeospatial.co.uk/wp-content/uploads/2016/12/image10-768x456.png)

