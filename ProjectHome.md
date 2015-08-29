

# Introduction #

The module provides a python wrapper around the Yahoo! Weather, Weather.com and NOAA APIs.

Authors:
  * Eugene Kaznacheev <qetzal@gmail.com>
  * Joshua Tasker <jtasker@gmail.com>

(**pywapi** - Python Weather API)

# Building #

## From source ##

Download the latest pywapi library from: https://launchpad.net/python-weather-api/trunk/0.3.8/+download/pywapi-0.3.8.tar.gz


Untar the source distribution and run:
```
  $ python setup.py build
  $ python setup.py install
```

# Getting the code #

View the trunk at:
http://python-weather-api.googlecode.com/svn/trunk/

Check out the latest development version anonymously with:
```
svn checkout http://python-weather-api.googlecode.com/svn/trunk/ python-weather-api-read-only
```

# Documentation #

## Yahoo! Weather ##
Use the following function, that fetches weather report from Yahoo

### **pywapi.get\_weather\_from\_yahoo(** _location\_id_ **,** _units = 'metric'_ **)** ###


**location\_id**: A five digit US zip code or location ID. To find your location ID, use function **get\_location\_ids(** _search\_string_ **)**.

**units**: type of units. 'metric' for metric and 'imperial' or '' for non-metric.
Note that choosing metric units changes all the weather units to metric, for example, wind speed will be reported as kilometers per hour and barometric pressure as millibars.
Default value is 'metric'.

Returns:
**weather\_data**: a dictionary of weather data that exists in XML feed. See http://developer.yahoo.com/weather/#channel

  * [Example of XML response from Yahoo](ExampleOfYahooXML.md)
  * [Example of return data](Examples#Yahoo!_Weather.md)



## Weather.com ##

Use the following function, that fetches weather report from Weather.com

### **pywapi.get\_weather\_from\_weather\_com(** _location\_id_ **,** _units = 'metric'_ **)** ###

**location\_id**: A five digit US zip code or location ID. To find your location ID, use function **get\_location\_ids(** _search\_string_ **)**.

**units**: type of units. 'metric' for metric and 'imperial' or '' for non-metric.
Note that choosing metric units changes all the weather units to metric, for example, wind speed will be reported as kilometers per hour and barometric pressure as millibars.
Default value is 'metric'.

Returns:
**weather\_data**: a dictionary of weather data that exists in XML feed.

  * [Example of XML response from Weather.com](ExampleOfWeatherComXML.md)
  * [Example of return data](Examples#Weather.com.md)


## NOAA ##
Use the following function, that fetches weather report from NOAA: National Oceanic and Atmospheric Administration (United States)

### **pywapi.get\_weather\_from\_noaa(** _station\_id_ **)** ###

**station\_id**: the ID of the weather station near the necessary location

To find your station ID, perform the following steps:
  1. Open this URL: http://www.weather.gov/xml/current_obs/seek.php?state=az&Find=Find
  1. Select the necessary state state. Click 'Find'.
  1. Find the necessary station in the 'Observation Location' column.
  1. The station ID is in the URL for the weather page for that station.

For example if the weather page is http://weather.noaa.gov/weather/current/KPEO.html -- the station ID is KPEO.

Other way to get the station ID: use this library: http://code.google.com/p/python-weather/ and _Weather.location2station_ function.

Returns:
**weather\_data**: a dictionary of weather data that exists in XML feed.

  * [Example of XML response from NOAA](ExampleOfNoaaXML.md)
  * [Example of return data](Examples#NOAA.md)

(useful icons: http://www.weather.gov/xml/current_obs/weather.php)



# Examples #

### [More examples](Examples.md) ###

## Script ##
```
import  pywapi
import string

weather_com_result = pywapi.get_weather_from_weather_com('10001')
yahoo_result = pywapi.get_weather_from_yahoo('10001')
noaa_result = pywapi.get_weather_from_noaa('KJFK')

print "Weather.com says: It is " + string.lower(weather_com_result['current_conditions']['text']) + " and " + weather_com_result['current_conditions']['temperature'] + "C now in New York.\n\n"

print "Yahoo says: It is " + string.lower(yahoo_result['condition']['text']) + " and " + yahoo_result['condition']['temp'] + "C now in New York.\n\n"

print "NOAA says: It is " + string.lower(noaa_result['weather']) + " and " + noaa_result['temp_c'] + "C now in New York.\n"
```

## Result ##
```
[~] python examples/pywapi-example.py

Weather.com says: It is overcast and 15C now in New York.

Yahoo says: It is fog and 14C now in New York.

NOAA says: It is overcast and 15C now in New York.

```

# Where is it used? #
Weather script for `GeekTool`: http://www.leancrew.com/all-this/2009/06/new-weather-script-for-geektool/

Google Wave robot: http://code.google.com/p/firstwave/wiki/DrWeather

http://blog.chrisramsay.co.uk/2009/08/11/getting-weather-information-with-python/

Weather plugins for Dreambox E2: http://linux-sat.tv/index.php/topic,314.msg1328/topicseen.html#msg1328.

# NEWS #
```
v0.3.8 (14 February 2014)
! Set all missing Weather.com XML tag values to an empty string

v0.3.7 (21 January 2014)
! Updated Weather.com URLs
! Better handling of Weather.com data when current daytime has passed

v0.3.6 (3 September 2013)
! Fix for Py3k compatibility in get_weather_from_weather_com()

v0.3.5 (14 August 2013)
! Better handling of Weather.com data when current conditions are empty

v0.3.4 (17 July 2013)
! Fix for Unicode decoding issue in get_woeid_from_yahoo()

v0.3.3 (2 June 2013)
+ Added suggested dependency on unidecode Python module, used to get
  location IDs for place names containing non-ascii characters.
+ Added __version__ string to module for version tracking
! Now uses json module to parse json replies instead of unsafe eval()
! Unicode strings are now correctly handled by all methods
! Fixes for Py3k compatibility

v0.3.2 (21 May 2013)
+ Added function get_loc_id_from_weather_com(), which is same as
  get_location_ids(), but with return format like get_woeid_from_yahoo().
+ Added function get_where_on_earth_ids(), which is same as
  get_woeid_from_yahoo(),  but with return format like get_location_ids().

v0.3.1 (17 May 2013)
+ Added function to calculate Heat Index from specified temperature and humidity.
+ Added conversion to Beaufort scale for more wind unit types.
! get_woeid_from_yahoo() now returns number of results as a dictionary key.
! Returned get_weather_from_google() to module for backwards compatibility,
  now always returns 'error' dictionary.

v0.3 (13 March 2013)
+ Now compatible with Python 2.x and Py3k
+ Added support of Weather.com XML feeds
- Google Weather service was removed. It has been discontinued as of Sep 2012.
! Functions now return a dictionary with one key, 'error', if something goes wrong.
! When connecting, now fails gracefully if a URLError occurs.
! Some changes to prevent possible IndexError issues.

v0.2.2 (31 August 2009)
+ Ability to get countries and cities lists from Google was added.
+ Shebang was added to the example scripts. Thank you, Runa.
! Small corrections to fix some pychecker warnings.
! get_weather_from_google() now supports non-English languages. Thank you, Shinysky.
! "400: Bad Request" error was fixed. It appeared when Google API is used and
  location contains special characters (for example spaces). Thank you, Dan.y.tang.
! Some changes to prevent possible IndexError issues.

v0.2.1 (07 July 2009)
+ GisMeteo service was removed. It does not provide XML feeds anymore.
! IndexError issue was fixed. Thank you, Dr. Drang.

v0.2 (29 May 2009)
+ Added support of NOAA XML feeds
+ Added support of GisMeteo XML feeds
+ Re-organized files: no more package, only one Python module
+ Added some example scripts
+ Added CHANGELOG and README files

v0.1 (18 May 2009)
+ Inital release: it is possible to get weather reports from Yahoo and Google
```