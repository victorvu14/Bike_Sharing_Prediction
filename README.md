# Bike_Sharing_Prediction

For this project, we were given two datasets from Kaggle https://www.kaggle.com/marklvl/bike-sharing-dataset/home containing information about the Bike Sharing service in Washington D.C. "Capital Bikeshare"

One dataset contains hourly data and the other one has daily data from the years 2011 and 2012.

The following variables are included in the data:

- instant: Record index
- dteday: Date
- season: Season (1:springer, 2:summer, 3:fall, 4:winter)
- yr: Year (0: 2011, 1:2012)
- mnth: Month (1 to 12)
- hr: Hour (0 to 23, only available in the hourly dataset)
- holiday: whether day is holiday or not (extracted from Holiday Schedule)
- weekday: Day of the week
- workingday: If day is neither weekend nor holiday is 1, otherwise is 0.
- weathersit: (extracted from Freemeteo) 1: Clear, Few clouds, Partly cloudy, Partly cloudy 2: Mist + Cloudy, Mist + Broken   clouds, Mist + Few clouds, Mist 3: Light Snow, Light Rain + Thunderstorm + Scattered clouds, Light Rain + Scattered clouds 4: Heavy Rain + Ice Pallets + Thunderstorm + Mist, Snow + Fog
- temp: Normalized temperature in Celsius. The values are derived via (t-t_min)/(t_max-t_min), t_min=-8, t_max=+39 (only in hourly scale)
- atemp: Normalized feeling temperature in Celsius. The values are derived via (t-t_min)/(t_max-t_min), t_min=-16, t_max=+50 (only in hourly scale)
- hum: Normalized humidity. The values are divided to 100 (max)
- windspeed: Normalized wind speed. The values are divided to 67 (max)
- casual: count of casual users
- registered: count of registered users
- cnt: count of total rental bikes including both casual and registered (Our target variable)

We are tasked with building a predictive model that can determine how many people will use the service on an hourly basis, therefore we take the first 5 quarters of the data for our training dataset and the last quarter of 2012 will be the holdout against which we perform our validation. Since that data was not used for training, we are sure that the evaluation metric that we get for it (R2 score) is an objective measurement of its predictive power.


## Conclusions

We created two different models to predict bike usage, with our results we believe that we can provide an accurate estimation of usage which can be of great importance for all of the involved parties.

The two models were created since we determined that there was a great difference in usage from weekends to normal working days, this situation would need to be considered by the company to supply the correct amount of bicicles depending on the day of the week, since the demand changes drastically.

Initially we had a baseline model with an r2 score of 0.765, however, after performing multiple data preparation steps and transformations we achieved a score of 0.897, which proves that our predicting capabilities improved immensely.

When analyzing the data, we found that there are many patterns that we could have used to create even more models to get an even higher accuracy score, specifically the patters of time (based on peak hours) would probably give us great results, however, we felt that our models needed to work on a global scale, and that creating more would make them too specific to this particular case.

With these two models, many different bike-sharing companies accross the world can use them to estimate usage, planify better for expected demand and even help their governments transportation requirements. Measuring the impact of new bike infrastructure on cycling traffic and behavior is top of mind for many planners and advocacy groups.
