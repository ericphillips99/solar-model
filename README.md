# Data-X Project: Solar Panel Identification in Satellite Rooftop Imagery

# Run and evaluate model

## Packages Used

The packages and versions used in our model code are specified in the "pyproject.toml" file. Our code is written in Python 3.

## Model Notebook

The notebook containing our model code (entitled "solar_model_notebook.ipynb") contains instructions for how to run and evaluate our model. The model can be trained from scratch using the training set, or the pre-trained model weights can be loaded in instead. Training from scratch takes a significant amount of time, so it is recommended to instead install the pre-trained model (which can be done by executing a cell in the notebook).

# Other files contained in repository

## Code for image collection

The notebook "image_collection_functions.ipynb" contains the functions used to fetch images from the Google Static Maps API. Satellite images were requested with size 300x300 and zoom level 21. Our dataset mostly contains images sourced from buildings across California, as well as some from other states including Colorado and Texas.

## 2D map of solar probabilities for Hayward, California

The file "hayward_cartoDB_solar.html" contains a 2D chloropleth map visualizing the model's output for each building in Hayward. This map was created using the Folium package in Python. Buildings assessed as having solar panel installations are shaded dark red, while buildings without solar are shaded white. This map shades the model's raw output probabilities, with darker colors signifying a higher probability of the presence of solar.

## 3D map of binary solar classifications for Hayward, California

This map can be found at http://city.lumen.energy/hayward-solar-prediction. This map shows the binary classifications for buildings in Hayward, with buildings assessed as having solar panel installations shaded blue. Please note that the satellite images on this map are from the Mapbox API, and thus may have been taken at a different time than the images fed into our model, which were from the Google Static Maps API. We observed several cases in which this discrepancy incorrectly led to the appearance of false positives.

## Hayward geojson files

The files "hayward_with_predictions.geojson" and "hayward_with_probabilities.geojson" contain the binary classifications and probabilities (respectively) as well as the centroid coordinates and polygons for the buildings analyzed in Hayward, California. These were used for the creation of the Hayward maps shown in our presentation.
