# python-api-challenge

## Overview

Using a random sampling of at least 500 cities from around the world, determine if several weather conditions, when compared to the city's latitude, can predict what the weather will be like as we approach the equator. The analysis will be based on several scatter plots that need to be created. 

Then using the dataset created in the first part, plot the humidity for each of those cities on a heatmap. Afterwards, Filter those cities down to approximately 10 cities based on your ideal weather conditions, find the closest hotel to each of their coordinates, and add markers to the heatmap that show, when clicked, the hotel name, city and country.

## Observations and Insights

After reviewing all the scatter plot results, these are my observable trends:
* Of all the data points compared, the only pair that showed strong potential for further analysis was the latitude and maximum temperature pair. The closer a city was to the equator, it was likely that its temperature would be warmer than a city farther from the equator. That was shown in both the plotting of the cities and in the linear regression lines for each hemisphere. The r-squared values were midway between 0 and 1 so there was a moderate correlation.
* Humidity and wind speed have a weak to no relationship to how close a city is to the equator. Based on the plots and linear regressions, there's no correlation between a city's latitude and humidity or wind speed. They did show some grouping of points either toward the top or bottom of the plots and were somewhat linear in shape but were still pretty scattered in both plots so no relationship. Their linear regressions were also pretty flat. The r-squared values were very close to 0 so a weak or no correlation. It would be difficult to predict either humidity or wind speed based on a city's known latitude.
* Of all the variable pairs plotted, the plot points for cloudiness and latitude were the most scattered so no apparent relationship between the two. It was also difficult to determine visually if there were outliers because the plot points were so scattered. Their linear regressions were also pretty flat. The r-squared values were very close to 0 so a weak or no correlation. It would be really difficult to predict a city's cloudiness based on its known latitude.

### Files
#### WeatherPy

All the files for this analysis can be found in the **WeatherPy** folder. The dataset result files are in the **output_data** subfolder and the scatter plot images are in the **images** folder.

* **Jupyter Notebook** (WeatherPy/WeatherPy.jpynb) - The Jupyter Notebook file that contains the scripts and results
* [City Data](WeatherPy/output_data/City_Data.csv) - this output file contains the approximately 500 cities that were used in the first part of this challenge 
* [Scatter Plot Images](WeatherPy/images/) - this folder contains the various scatter plots generated in the first part of this challenge

#### VacationPy

The files for this analysis can be found in the **VacationPy** folder (except for the City Data source file which is in the WeatherPy folder's output_data subfolder). 

* **Jupyter Notebook** (VacationPy/VacationPy.jpynb) - The Jupyter Notebook file that contains the scripts and results
* [City Data](WeatherPy/output_data/City_Data.csv) - this data source file contains the approximately 500 cities that were used in the first part of this challeng and is the output file from that 

## Notes

API keys are needed for the OpenWeatherMap and Google Places APIs. Both keys need to be in a file called **api_keys.py** and located in the **WeatherPy** and the ***VacationPy** folders. Keys should use the following variable names:
* OpenWeatherMap API: api_key
* Google Places API: g_key

I didn't have any cities with humidities greater than 100% but I coded that section in just in case that should happen with a future pull.

I created the function for plotting linear regressions but didn't actually use it. I created it after I had already completed everything else. Since my analysis was based on the data I had originally pulled, I didn't want to re-run everything to use the function and end up with different cities.

The heatmap and the heatmap with the marker layer for hotels show repeating world maps when they first run. You have to zoom in to see just one world map. The heatmap with the markers layer also doesn't fill the whole cell so scrolling is involved. I have not yet figured out why this is occurring and how to fix it. 

I ended up having cities that didn't pull a hotel name so I removed those rows from the dataframe before adding the marker layer.