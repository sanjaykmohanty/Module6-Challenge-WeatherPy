# Module6-Challenge-WeatherPy

## Overview 
The purpose of this project was to use the weather description data to identify potential travel destinations and nearby hotels. Uesrs were allowed to choose four cities from the list of potential travel destinations to create a travel itinerary. In the end, using the Google Maps Directions API,a travel route between the four cities and a marker layer map was created.

This project consists of three technical analyses:
- Retrieve Weather Data
- Create a Customer Travel Destinations Map
- Create a Travel Itinerary Map

## Resources
Data Source: OpenWeatherMap's API, Google API (Places, Maps JaveScript, Directions), Software: Python 3.9.12, Jupyter Notebook 6.4.12

## Summary Report
Considering the requirements and deliverables, the project was dived into 3 different modules. 

- **First Module:** Retrive waether data using Python functions and making OpenWeatherMap's API calls and save the information in a CSV file
- **Second Module:** Take customer preferences and identify potential travel destinations and nearby hotels 
- **Third Module:** Create a travel itinerary showing the route between four cities chosen from the customer’s possible travel destinations 

### Retrieve Weather Data
In this module, the nearest city was retrieved from the randomly generated coordinates and waether data was retrieved by making OpenWeatherMap API calls for each city.

Following steps were perfomed in this module:
1. A set of 2,000 random latitudes and longitudes were generated using the NumPy random(np.random.uniform) function.
2. CitiPy module was used to get the nearest city for each latitude and longitude combination.
3. OpenWeatherMap's API call was made to retrieve below listed informatuion for each city:
- Latitude and longitude
- Maximum temperature
- Percent humidity
- Percent cloudiness
- Wind speed
- Weather description
4. The weather data was was added to a new DataFrame and exported the dataframe as a CSV file and saved as WeatherPy_Database.csv

### Create a Customer Travel Destinations Map
In this module, potential travel destinations and nearby hotels were identified based on customer's weather preference. 

Following steps were perfomed in this module:
1. The CSV file <code>WeatherPy_Database.csv</code> was imported into a Pandas DataFrame named <code>city_data_df</code>.
2. Users are allowed to enter their minimum and maximum temperature prefernce criteria for their vacation.
3. A new Pandas DataFrame <code>preferred_cities_df</code> was created by filtering the <code>city_data_df</code> DataFrame for the temperature criteria collected. 
4. The DataFrame was cleaned up by dropping the records with empty columns and hotel information was retrieved making Google <code>Places API</code> calls using City Name and coordinates. 
5. A CSV file <code>WeatherPy_vacation.csv</code> was created from the DataFrame
6. A marker layer map was created with a pop-up marker for each city.

### Create a Travel Itinerary Map
In this module, Google Directions API was used to create a travel itinerary showing the route between four cities. These four cities were chosen from the customer’s possible travel destinations. 

Following steps were perfomed in this module:
1. The CSV file <code>WeatherPy_vacation.csv</code> was imprted into a DataFrame named vacation_df.

In this step, you will set-up the pop-up markers. Review the code to create a marker layer map of the vacation search results. This code is the same as in Deliverable 2.

From the vacation search map, choose four cities that a customer might want to visit. They should be close together and in the same country. Use the variables we have provided and the loc method to create separate DataFrames for each city on the travel route.


