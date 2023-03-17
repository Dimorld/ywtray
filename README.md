YWTRAY     🌦
=============
YWTRAY is a simple current weather indicator. It was written using GNU bash 5.0.17, and YAD 12.3 on a system with PuppyLinux FossaPup64 9.5 . It uses curl 7.68.0, and GNU Awk 5.2.0. 
It is a project initiated as a way to learn bash, expect unefficient solutions to problems.

DETAILS
======
The package/directory consists of the following:


![Alt text](/read_assets/structure01-20230317_42.png.png?raw=true "Directory Main Structure")

The importante scripts are:

* ywtray
* ywtray-core
* ywtray-settings

**ywtray** is a launcher script, It takes decisions based in the configuration file located in **.config/ywtray/ywtray.conf**, if it is the first time YWTRAY is run, then **ywtray-settings** is started and will ask for a location, and prefferred measuring units. Once the questions are answered, the responses are stored in **ywtray.conf**, and **ywtray-core** started.   

**ywtray-core** is the script in charge of showing the notification in your tray. It updates the weather icon, and weather conditions every 27 minutes. The weather data is obtained from [open meteo](https://open-meteo.com/en/docs "open-meteo.com") to then be parsed into useful information using the **ywtray-functions** file. 

**ywtray-functions** is a text file, it contains a function to parse the json data stream provided by the weather api, a function to parse the latitude and longitude coordinates, code to select the appropiate current weather icon and conditions, code to select the appropiate temperature suffix, and code to select the appropiate wind speed suffix.  


Notificador del clima escrito en yad

![screenshot](https://i.postimg.cc/cJXscvTS/image-16.png)
 
![screenshot](https://i.postimg.cc/P5MLBrK6/image-20.png)

![screenshot](https://i.postimg.cc/HxnTvTP7/image-19.png)

En construcción

##Dependencias##
=================

- Curl
- Api de Meteo
