# Data-x project: Solar panel identification in satellite rooftop imagery

## Setting up environment

# Install and set up poetry

Poetry is used to create a self-isolated virtual environment with the specific package versions used in our model code. Packages are specified in the "pyproject.toml" file, located within the poetry-solar folder.

# Steps:

Change directory to location of cloned Github repo:
```bash
cd (path_to_solar-model)
```

Install Poetry:
```bash
curl -sSL https://raw.githubusercontent.com/python-poetry/poetry/master/get-poetry.py
```

Install the packages specified in pyproject.toml:
```bash
poetry install
```
Create kernel for virtual environment:
```bash
poetry run ipython kernel install --user --name=solar-kernel
```

## Run and evaluate model

Open jupyter notebook:
```bash
poetry run jupyter notebook
```

The notebook (entitled "solar_model_notebook.ipynb") contains instructions for how to run and evaluate model. The model can be trained from scratch using the training dataset, or the pre-trained model weights can be loaded in instead. Training from scratch takes a significant amount of time to run (even on a GPU), so it is recommended to instead install the pre-trained model.

## Other files contained in repository

# Code for image collection

The "image_collection.ipynb" notebook contains the functions used to fetch images from the Google Static Maps API. Satellite images were requested with size 300x300 and zoom level 21.

# Hayward geojson files

The files "hayward_with_predictions.geojson" and "hayward_with_probabilities.geojson" contain the binary classifications and probabilities, respectively, as well as the centroid coordinates and polygons for the buildings we analyzed in Hayward, California. These were used for the creation of the Hayward maps shown in our presentation.

# 2D map of solar probabilities for Hayward, California

The file "hayward_cartoDB_solar.html" contains a 2D chloropleth map visualizing the model's output for each building in Hayward. Buildings assessed as having solar panel installations are shaded dark red, while buildings without solar are shaded white. This map shades the model's raw output probabilities, with darker colors signifying a higher probability of the presence of solar.

# 3D map of binary solar classifications for Hayward, California

This map can be found at http://city.lumen.energy/hayward-solar-prediction. This map shows the binary classifications for buildings in Hayward, with buildings assessed as having solar panel installations shaded blue. Please note that the satellite images on this map are from the Mapbox API, and thus may have been taken at a different time than the images fed into our model, which were from the Google Static Maps API. We observed several cases in which this discrepancy incorrectly led to the appearance of false positives.