# MobyDex Bike Availability

This repository contains historical data on the rental bike availability in the two pilot areas of [MobyDex](https://mobydex.org) (Ruhrgebiet and Karlsruhe) in Germany. The availabiliy has been gathered by periodically fetching the number of bikes available at the stations using an API endpoint of the operator. The temporal resolution of the bike availability is 30 minutes. However, the data contains a few gaps due to connectivity issues (caused by the nice people that hacked the Universität Duisburg-Essen).

To provide a basis for weather-dependent analyses and predictions, the availability data has been merged with historical weather data. As data source, we use open data provided by [Deutscher Wetterdienst (DWD)](https://www.dwd.de). Specifically, we are using the observations of the closest weather station available at the corresponding point in time. The temporal resolution of the weather data is 1 hour. The spatial resolution varies but is generally low enough to be meaningful (i.e. the stations are usually a few kilometers away). The weather data is licensed under the Creative Commons By 4.0 (CC BY 4.0) license and the raw dataset can be found [here](https://opendata.dwd.de/climate_environment/CDC/observations_germany/climate/hourly/).

The data is organized in gzipped csv files covering a year. Each row represents the bike availability and weather conditions at a particular station at a particular point in time. Columns are separated by a single semi-colon. Rows are separated by a single newline character. Decimal numbers are formated using an English locale (i.e. using dot as a decimal separator). Each file contains the following columns:

* *City*: The name of the city containing the bike station.
* *Station:* The name of the station.
* *Lat:* The (WGS) latitude of the station.
* *Lng:* The (WGS) longitude of the station.
* *Time:* The date and time of the observation.
* *Bikes Available:* The total number of available bikes.
* *Bikes Booked:* The number of bikes booked at the station.
* *Bikes Added:* The number of bikes that are now avaialbe at the station but were not at the station at the previous point in time.
* *Bikes Removed:* The number of bikes that is no longer available at the station but was available at the previous point in time.
* *Air Temperature:* The air temperature (2 meters above the ground) in centigrade (degree Celsius).
* *Rel. Humidity:* The relative humidity in percent.
* *Cloudiness:* The cloudiness ranging from 0 to 8 (on a linear scale) where 0 means no clouds and 8 means completely covered.
* *Pecipitation:* The precipitation in mm (liters per square meter). 
* *Wind:* The wind speed in meters per second.

If you publish a paper or an article that uses the data, send us an [email](mailto:marcus.handte@uni-due.de), so we can reference your work here. If you would like to cite MobyDex, consider using:

```
Marcus Handte, Alexander Golkowski, Christopher Frank, Pedro José Marrón, MobyDex: A Platform for Analyzing Multimodal Mobility Systems, In Heike Prof (ed.): New Players in Mobility, Wiesbaden: Springer Gabler, to appear in 2025
```

