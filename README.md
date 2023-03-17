YWTRAY     🌦
=============
YWTRAY is a simple current weather indicator. It was written using GNU bash 5.0.17, and YAD 12.3 on a system with PuppyLinux FossaPup64 9.5. It uses curl 7.68.0, and GNU Awk 5.2.0. 
It is a project initiated as a way to learn bash, expect unefficient solutions to problems. **Use at your on risk!**

DETAILS
======
The package/directory consists of the following:


![Alt text](/read_assets/structure01-20230317_42.png.png?raw=true "Directory Main Structure")

The important scripts are:

* ywtray
* ywtray-core
* ywtray-settings

**ywtray** is a launcher script, It takes decisions depending on what is found in the configuration file located on **.config/ywtray/ywtray.conf**. If It is the first time YWTRAY is run, then **ywtray-settings** is executed and It will ask for a location, a temperature measuring unit, and a wind speed measuring unit. Once the questions are answered, the latitude and longitude coordinates are retrieved from [Free Geocoding API](https://geocode.maps.co/ "Free Geocoding API"), then the information is writen to the file  **ywtray.conf**, and the script **ywtray-core** is executed.   

**ywtray-core** is in charge of showing the notification in the tray. It updates the weather icon, and weather conditions every 27 minutes. The weather data is retrieved from [open meteo](https://open-meteo.com/en/docs "open-meteo.com") to then be parsed into useful information utilizing the **ywtray-functions** file. 

**ywtray-functions** is a text file, It contains a function to parse the json data stream provided by the weather API, a function to parse the latitude and longitude coordinates, code to select the appropiate current weather icon and current weather conditions, code to select the appropiate temperature suffix, and code to select the appropiate wind speed suffix.

THINGS TO CONSIDER
===============

* The meteo API states weather data is updated every hour on the top of the hour, a user can have up to 10,000 calls to the api per 24 hrs cycle, and is free for non commercial use. If You have privacy concerns read their website.
* YAD updates information to the tray via a named pipe, the named pipe is created in /tmp and file descriptor 6 is used, inspired in [yad wiki example](https://github.com/v1cont/yad/wiki/Frontend-for-find(1) "yad wiki example")
* The geolocation API is free to use, again if You have privacy concerns read their website.

Notificador del clima escrito en yad

![screenshot](https://i.postimg.cc/cJXscvTS/image-16.png)
 
![screenshot](https://i.postimg.cc/P5MLBrK6/image-20.png)

![screenshot](https://i.postimg.cc/HxnTvTP7/image-19.png)

En construcción

##Dependencias##
=================

- Curl
- Api de Meteo
