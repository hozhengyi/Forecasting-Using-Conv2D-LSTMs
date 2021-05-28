# Spatiotemporal forecasting with multivariate cells.


# Code Organisation
## Dependencies  
1. Tensorflow 2.4 
2. Numpy
3. tensorflow_addons
4. jupyter-lab 
5. Pandas 

## Data files
The data used in this work is provided by the National Solar Radiation Database (NSRDB) and can be downloaded via API requests. Detailed download instructions are provided [here](https://nsrdb.nrel.gov/data-sets/api-instructions.html). Download the relative humidity values over mainland United States from 1998 to 2019, totalling 192720, and extract relative humidity values from Station ID: 878848 (GMT -6). 

The following file contains the training/validation data used in this work.

## Scripts
The following list is a description of each Python script contained in this repository.
`multivar_v3.csv` contains the results of the pure multivariate run.  
`singlevar_v0.csv` contains the results of the pure univariate run.  
`spatio_v0.csv` contains the results of the spatiotemporal-multivariate run.  
`multivar_v3.png` contains the model architecture overview for the multivariate model.  
`singlevar_v0.png` contains the model architecture overview for the univariate model.  
`spatio_v0.png` contains the model architecture overview for the spatiotemporal-multivariate model.  
`multivar_model.ipynb` contains the code used for the multivariate run.  
`singlevar_model.ipynb` contains the code used for the univariate run.  
`spatio_model.ipynb` contains the code used for the spatiotemporal-multivariate run.  

# Running
1. Download the dependencies using `pip install`
2. Acquire an API key from the NSRDB site [here](https://developer.nrel.gov/signup/).
3. Download the data for weather stations over the entire US continent.
4. Using pandas, wrangle each station's data and transform it to the equivalent Numpy array. The variables to keep are Relative Humidity, GHI, SZA and dew point temperature. Each station's data should be timezone corrected by removing the tail and head ends of the data columns. The equivalent Numpy array should have four dimensions (timesteps, variables, area_height, area_width).  
5. Using either `multivar_model.ipynb`, `singlevar_model.ipynb` or `spatio_model.ipynb`, run jupyter-lab, define your tensorboard logs save paths and path to the equivalent Numpy array. Train the model.
