# Global Weather Analysis

## Introduction

"What's the weather like as we approach the equator?". Anecdotally we understand the relationship between weather and latitude, but how can we use analysis and visualization techniques to scientifically prove our hypothesis? This model uses various data analysis and visualization tools to objectively answer the above asked question. 

### Technologies

* Python 3.6
* Python requests
* OpenWeaterMap API
* Pandas
* Matplotlib
* JSON
* Jupyter Notebook
* Google Places API

## Weather Analysis

To perform the analysis the following was completed:

* 500 unique cities were randomly selected based on latitude and longitude.
* A weather check was performed on each of the cities using a series of successive API calls.
* A print log of each city was created with the city number and city name.
* A CSV of all retrieved data and a PNG image for each scatter plot were produced.

The scatter plots showcase the following relationships:

* Temperature (F) vs. Latitude
* Humidity (%) vs. Latitude
* Cloudiness (%) vs. Latitude
* Wind Speed (mph) vs. Latitude

![Temperature vs. Latitude](./WeatherPy/output_data/Lat_v_temp.png)

Once the scatter plots were created a linear regression was ran on each relationship. This time, the plots were seperated into Northern Hemisphere (greater than or equal to 0 degrees latitude) and Southern Hemisphere (less than 0 degrees latitude).

## Vacation Analysis

With data and weather collected for 500 cities, an analysis was completed to filter down our cities with the most ideal temperature and wind conditions. With the ideal weather conditions identified, Google Places API was used to find a hotel in the cities that met the criteria.

* Initially, a heat map was created to display the humidity conditions of the 500 cities selected.

  ![Heatmap](./Vacation Analysis/Global Heat Map.png)

* Next, a criteria was identified to choose the ideal weather conditions to filter down the cities:

  * A max temperature lower than 80 degrees but higher than 70.
  * Wind speed less than 10 mph.
  * Zero cloudiness.

* Google Places API was used to find the first hotel for each chosen city coordinates.

* Finally, a Plot was created with the hotels pinned on top of the humidity heatmap along with a tool tip containing the Hotel Name, City, and Country.

  ![Hotel_Map](./Vacation Analysis/Filtered Hotels.png)
