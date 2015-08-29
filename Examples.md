

# Yahoo! Weather #

## Script ##

```
import pywapi
import pprint
pp = pprint.PrettyPrinter(indent=4)

result = pywapi.get_weather_from_yahoo('RSXX0199', 'metric')
pp.pprint(result)
```

## Result ##
```
[~] python examples/pywapi-yahoo-example.py

{   'astronomy': {   'sunrise': u'6:46 am', 'sunset': u'7:13 pm'},
    'atmosphere': {   'humidity': u'53',
                      'pressure': u'1013.1',
                      'rising': u'0',
                      'visibility': u'16.09'},
    'condition': {   'code': u'34',
                     'date': u'Wed, 27 Mar 2013 9:49 am EDT',
                     'temp': u'6',
                     'text': u'Fair',
                     'title': u'Conditions for New York, NY at 9:49 am EDT'},
    'forecasts': [   {   'code': u'34',
                         'date': u'27 Mar 2013',
                         'day': u'Wed',
                         'high': u'9',
                         'low': u'2',
                         'text': u'Mostly Sunny'},
                     {   'code': u'28',
                         'date': u'28 Mar 2013',
                         'day': u'Thu',
                         'high': u'10',
                         'low': u'2',
                         'text': u'Mostly Cloudy'},
                     {   'code': u'30',
                         'date': u'29 Mar 2013',
                         'day': u'Fri',
                         'high': u'11',
                         'low': u'3',
                         'text': u'Partly Cloudy'},
                     {   'code': u'30',
                         'date': u'30 Mar 2013',
                         'day': u'Sat',
                         'high': u'11',
                         'low': u'3',
                         'text': u'Partly Cloudy'},
                     {   'code': u'28',
                         'date': u'31 Mar 2013',
                         'day': u'Sun',
                         'high': u'10',
                         'low': u'7',
                         'text': u'Mostly Cloudy'}],
    'geo': {   'lat': u'40.67', 'long': u'-73.94'},
    'html_description': u'\n<img src="http://l.yimg.com/a/i/us/we/52/34.gif"/><br />\n<b>Current Conditions:</b><br />\nFair, 6 C<BR />\n<BR /><b>Forecast:</b><BR />\nWed - Mostly Sunny. High: 9 Low: 2<br />\nThu - Mostly Cloudy. High: 10 Low: 2<br />\nFri - Partly Cloudy. High: 11 Low: 3<br />\nSat - Partly Cloudy. High: 11 Low: 3<br />\nSun - Mostly Cloudy. High: 10 Low: 7<br />\n<br />\n<a href="http://us.rd.yahoo.com/dailynews/rss/weather/New_York__NY/*http://weather.yahoo.com/forecast/USNY0996_c.html">Full Forecast at Yahoo! Weather</a><BR/><BR/>\n(provided by <a href="http://www.weather.com" >The Weather Channel</a>)<br/>\n',
    'link': u'http://us.rd.yahoo.com/dailynews/rss/weather/New_York__NY/*http://weather.yahoo.com/forecast/USNY0996_c.html',
    'location': {   'city': u'New York', 'country': u'US', 'region': u'NY'},
    'title': u'Yahoo! Weather - New York, NY',
    'units': {   'distance': u'km',
                 'pressure': u'mb',
                 'speed': u'km/h',
                 'temperature': u'C'},
    'wind': {   'chill': u'2', 'direction': u'280', 'speed': u'16.09'}}
```


# NOAA #

## Script ##

```
import pywapi
import pprint
pp = pprint.PrettyPrinter(indent=4)

result = pywapi.get_weather_from_noaa('KJFK')
pp.pprint(result)
```

## Result ##

```
[~] python examples/pywapi-noaa-example.py

{   'dewpoint_c': u'-3.3',
    'dewpoint_f': u'26.1',
    'dewpoint_string': u'26.1 F (-3.3 C)',
    'icon_url_base': u'http://forecast.weather.gov/images/wtf/small/',
    'icon_url_name': u'sct.png',
    'latitude': u'40.66',
    'location': u'New York/John F. Kennedy Intl Airport, NY',
    'longitude': u'-73.78',
    'ob_url': u'http://www.weather.gov/data/METAR/KJFK.1.txt',
    'observation_time': u'Last Updated on Mar 27 2013, 10:51 am EDT',
    'observation_time_rfc822': u'Wed, 27 Mar 2013 10:51:00 -0400',
    'pressure_in': u'29.92',
    'pressure_mb': u'1013.2',
    'pressure_string': u'1013.2 mb',
    'relative_humidity': u'44',
    'station_id': u'KJFK',
    'suggested_pickup': u'15 minutes after the hour',
    'suggested_pickup_period': u'60',
    'temp_c': u'8.3',
    'temp_f': u'47.0',
    'temperature_string': u'47.0 F (8.3 C)',
    'two_day_history_url': u'http://www.weather.gov/data/obhistory/KJFK.html',
    'weather': u'Partly Cloudy',
    'wind_degrees': u'310',
    'wind_dir': u'Northwest',
    'wind_gust_mph': u'20.7',
    'wind_mph': u'13.8',
    'wind_string': u'from the Northwest at 13.8 gusting to 20.7 MPH (12 gusting to 18 KT)',
    'windchill_c': u'5',
    'windchill_f': u'41',
    'windchill_string': u'41 F (5 C)'}
```


# Weather.com #

## Script ##
```
import pywapi
import pprint
pp = pprint.PrettyPrinter(indent=4)

kalamata = pywapi.get_weather_from_weather_com('GRXX0036')

pp.pprint(kalamata)
```

## Result ##

```
[~] python examples/pywapi-weather-com-example.py

{   'current_conditions': {   'barometer': {   'direction': u'rising',
                                               'reading': u'1009.1'},
                              'dewpoint': u'12',
                              'feels_like': u'18',
                              'humidity': u'68',
                              'icon': u'30',
                              'last_updated': u'3/27/13 4:20 PM Local Time',
                              'moon_phase': {   'icon': u'15', 'text': u'Full'},
                              'station': u'Kalamata, GREECE',
                              'temperature': u'18',
                              'text': u'Partly Cloudy',
                              'uv': {   'index': u'1', 'text': u'Low'},
                              'visibility': u'10.0',
                              'wind': {   'direction': u'170',
                                          'gust': u'N/A',
                                          'speed': u'13',
                                          'text': u'S'}},
    'forecasts': [   {   'date': u'Mar 27',
                         'day': {   'brief_text': u'N/A',
                                    'chance_precip': u'40',
                                    'humidity': u'N/A',
                                    'icon': u'44',
                                    'text': u'N/A',
                                    'wind': {   'direction': u'N/A',
                                                'gust': u'N/A',
                                                'speed': u'N/A',
                                                'text': u'N/A'}},
                         'day_of_week': u'Wednesday',
                         'high': u'N/A',
                         'low': u'10',
                         'night': {   'brief_text': u'Shwrs Late',
                                      'chance_precip': u'40',
                                      'humidity': u'91',
                                      'icon': u'45',
                                      'text': u'Showers Late',
                                      'wind': {   'direction': u'308',
                                                  'gust': u'N/A',
                                                  'speed': u'3',
                                                  'text': u'NW'}},
                         'sunrise': u'6:25 AM',
                         'sunset': u'6:50 PM'},
                     {   'date': u'Mar 28',
                         'day': {   'brief_text': u'AM Showers',
                                    'chance_precip': u'40',
                                    'humidity': u'65',
                                    'icon': u'39',
                                    'text': u'AM Showers',
                                    'wind': {   'direction': u'222',
                                                'gust': u'N/A',
                                                'speed': u'8',
                                                'text': u'SW'}},
                         'day_of_week': u'Thursday',
                         'high': u'21',
                         'low': u'10',
                         'night': {   'brief_text': u'M Cloudy',
                                      'chance_precip': u'20',
                                      'humidity': u'81',
                                      'icon': u'27',
                                      'text': u'Mostly Cloudy',
                                      'wind': {   'direction': u'335',
                                                  'gust': u'N/A',
                                                  'speed': u'2',
                                                  'text': u'NNW'}},
                         'sunrise': u'6:23 AM',
                         'sunset': u'6:50 PM'},
                     {   'date': u'Mar 29',
                         'day': {   'brief_text': u'Cloudy',
                                    'chance_precip': u'0',
                                    'humidity': u'58',
                                    'icon': u'26',
                                    'text': u'Cloudy',
                                    'wind': {   'direction': u'223',
                                                'gust': u'N/A',
                                                'speed': u'13',
                                                'text': u'SW'}},
                         'day_of_week': u'Friday',
                         'high': u'23',
                         'low': u'13',
                         'night': {   'brief_text': u'P Cloudy',
                                      'chance_precip': u'0',
                                      'humidity': u'69',
                                      'icon': u'29',
                                      'text': u'Partly Cloudy',
                                      'wind': {   'direction': u'154',
                                                  'gust': u'N/A',
                                                  'speed': u'0',
                                                  'text': u'CALM'}},
                         'sunrise': u'6:22 AM',
                         'sunset': u'6:51 PM'},
                     {   'date': u'Mar 30',
                         'day': {   'brief_text': u'P Cloudy',
                                    'chance_precip': u'0',
                                    'humidity': u'57',
                                    'icon': u'30',
                                    'text': u'Partly Cloudy',
                                    'wind': {   'direction': u'155',
                                                'gust': u'N/A',
                                                'speed': u'19',
                                                'text': u'SSE'}},
                         'day_of_week': u'Saturday',
                         'high': u'25',
                         'low': u'13',
                         'night': {   'brief_text': u'M Cloudy',
                                      'chance_precip': u'0',
                                      'humidity': u'73',
                                      'icon': u'27',
                                      'text': u'Mostly Cloudy',
                                      'wind': {   'direction': u'175',
                                                  'gust': u'N/A',
                                                  'speed': u'3',
                                                  'text': u'S'}},
                         'sunrise': u'6:20 AM',
                         'sunset': u'6:52 PM'},
                     {   'date': u'Mar 31',
                         'day': {   'brief_text': u'M Cloudy',
                                    'chance_precip': u'0',
                                    'humidity': u'74',
                                    'icon': u'28',
                                    'text': u'Mostly Cloudy',
                                    'wind': {   'direction': u'131',
                                                'gust': u'N/A',
                                                'speed': u'8',
                                                'text': u'SE'}},
                         'day_of_week': u'Sunday',
                         'high': u'21',
                         'low': u'11',
                         'night': {   'brief_text': u'P Cloudy',
                                      'chance_precip': u'10',
                                      'humidity': u'87',
                                      'icon': u'29',
                                      'text': u'Partly Cloudy',
                                      'wind': {   'direction': u'344',
                                                  'gust': u'N/A',
                                                  'speed': u'0',
                                                  'text': u'CALM'}},
                         'sunrise': u'7:19 AM',
                         'sunset': u'7:53 PM'}],
    'location': {   'lat': u'37.04',
                    'lon': u'22.11',
                    'name': u'Kalamata, Greece'},
    'units': {   'distance': u'km',
                 'pressure': u'mb',
                 'rainfall': u'mm',
                 'speed': u'km/h',
                 'temperature': u'C'}}
```


# Countries from Google #

## Script ##

```
import pywapi
import pprint
pp = pprint.PrettyPrinter(indent=4)

countries = pywapi.get_countries_from_google('en')

pp.pprint(countries)
```

## Result ##

```
[~] python examples/pywapi-countries-example.py

[   {   'iso_code': u'US', 'name': u'United States'},
    {   'iso_code': u'UK', 'name': u'United Kingdom'},
    {   'iso_code': u'FR', 'name': u'France'},
    {   'iso_code': u'IT', 'name': u'Italy'},
    {   'iso_code': u'DE', 'name': u'Germany'},
    {   'iso_code': u'ES', 'name': u'Spain'},
    {   'iso_code': u'NL', 'name': u'Netherlands'},
    {   'iso_code': u'CH', 'name': u'Switzerland'},
    {   'iso_code': u'JP', 'name': u'Japan'},
    {   'iso_code': u'KR', 'name': u'Korea'},
    {   'iso_code': u'BR', 'name': u'Brazil'},
    {   'iso_code': u'MX', 'name': u'Mexico'},
    {   'iso_code': u'AU', 'name': u'Australia'},
    {   'iso_code': u'IN', 'name': u'India'},
    {   'iso_code': u'RU', 'name': u'Russia, CIS and Baltics'},
    {   'iso_code': u'CA', 'name': u'Canada'},
    {   'iso_code': u'SE', 'name': u'Sweden'},
    {   'iso_code': u'DK', 'name': u'Denmark'},
    {   'iso_code': u'FI', 'name': u'Finland'},
    {   'iso_code': u'IE', 'name': u'Ireland'},
    {   'iso_code': u'NO', 'name': u'Norway'},
    {   'iso_code': u'NZ', 'name': u'New Zealand'},
    {   'iso_code': u'CN', 'name': u'China Mainland'},
    {   'iso_code': u'TW', 'name': u'Taiwan'},
    {   'iso_code': u'HK', 'name': u'Hong Kong'},
    {   'iso_code': u'MO', 'name': u'Macao'},
    {   'iso_code': u'BE', 'name': u'Belgium'},
    {   'iso_code': u'AT', 'name': u'Austria'},
    {   'iso_code': u'CL', 'name': u'Chile'},
    {   'iso_code': u'CO', 'name': u'Colombia'},
    {   'iso_code': u'CZ', 'name': u'Czech Republic'},
    {   'iso_code': u'GR', 'name': u'Greece'},
    {   'iso_code': u'HU', 'name': u'Hungary'},
    {   'iso_code': u'MY', 'name': u'Malaysia'},
    {   'iso_code': u'PH', 'name': u'Philippines'},
    {   'iso_code': u'PL', 'name': u'Poland'},
    {   'iso_code': u'PT', 'name': u'Portugal'},
    {   'iso_code': u'RO', 'name': u'Romania'},
    {   'iso_code': u'SG', 'name': u'Singapore'},
    {   'iso_code': u'TH', 'name': u'Thailand'},
    {   'iso_code': u'TR', 'name': u'Turkey'},
    {   'iso_code': u'UA', 'name': u'Ukraine'},
    {   'iso_code': u'VN', 'name': u'Vietnam'},
    {   'iso_code': u'ZA', 'name': u'South Africa'},
    {   'iso_code': u'IL', 'name': u'Israel'},
    {   'iso_code': u'DZ', 'name': u'Algeria'},
    {   'iso_code': u'EG', 'name': u'Egypt'},
    {   'iso_code': u'MA', 'name': u'Morocco'},
    {   'iso_code': u'OM', 'name': u'Oman'},
    {   'iso_code': u'SA', 'name': u'Saudi Arabia'},
    {   'iso_code': u'TN', 'name': u'Tunisia'},
    {   'iso_code': u'AE', 'name': u'United Arab Emirates'},
    {   'iso_code': u'JO', 'name': u'Jordan'},
    {   'iso_code': u'LB', 'name': u'Lebanon'},
    {   'iso_code': u'BG', 'name': u'Bulgaria'},
    {   'iso_code': u'PK', 'name': u'Pakistan'},
    {   'iso_code': u'AR', 'name': u'Argentina'},
    {   'iso_code': u'PE', 'name': u'Peru'},
    {   'iso_code': u'VE', 'name': u'Venezuela'},
    {   'iso_code': u'CR', 'name': u'Costa Rica'},
    {   'iso_code': u'DO', 'name': u'Dominican Republic'},
    {   'iso_code': u'GT', 'name': u'Guatemala'},
    {   'iso_code': u'UY', 'name': u'Uruguay'},
    {   'iso_code': u'EC', 'name': u'Ecuador'},
    {   'iso_code': u'BO', 'name': u'Bolivia'},
    {   'iso_code': u'PY', 'name': u'Paraguay'},
    {   'iso_code': u'PR', 'name': u'Puerto Rico'},
    {   'iso_code': u'PA', 'name': u'Panama'},
    {   'iso_code': u'HN', 'name': u'Honduras'},
    {   'iso_code': u'SV', 'name': u'El Salvador'},
    {   'iso_code': u'HR', 'name': u'Croatia'},
    {   'iso_code': u'SI', 'name': u'Slovenia'},
    {   'iso_code': u'YU', 'name': u'Serbia'},
    {   'iso_code': u'ID', 'name': u'Indonesia'},
    {   'iso_code': u'IS', 'name': u'Iceland'},
    {   'iso_code': u'LT', 'name': u'Lithuania'},
    {   'iso_code': u'LV', 'name': u'Latvia'},
    {   'iso_code': u'SK', 'name': u'Slovakia'}]
```


# Cities from Google #

## Script ##

```
import pywapi
import pprint
pp = pprint.PrettyPrinter(indent=4)

cities = pywapi.get_cities_from_google('fr', 'de') # or (country = 'fr', hl = 'de')

pp.pprint(cities)
```

## Result ##

```
[~] python examples/pywapi-cities-example.py

[   {   'latitude_e6': u'43529742',
        'longitude_e6': u'5447427',
        'name': u'Aix-en-Provence'},
    {   'latitude_e6': u'49894067',
        'longitude_e6': u'2295753',
        'name': u'Amiens'},
    {   'latitude_e6': u'47478419',
        'longitude_e6': u'-563166',
        'name': u'Angers'},
    {   'latitude_e6': u'43580418',
        'longitude_e6': u'7125102',
        'name': u'Antibes'},
    {   'latitude_e6': u'44837789',
        'longitude_e6': u'-579180',
        'name': u'Bordeaux'},
    {   'latitude_e6': u'47081012',
        'longitude_e6': u'2398782',
        'name': u'Bourges'},
    {   'latitude_e6': u'48390394',
        'longitude_e6': u'-4486076',
        'name': u'Brest'},
    {   'latitude_e6': u'49182863', 'longitude_e6': u'-370679', 'name': u'Caen'},
    {   'latitude_e6': u'50951290',
        'longitude_e6': u'1858686',
        'name': u'Calais'},
    {   'latitude_e6': u'45777222',
        'longitude_e6': u'3087025',
        'name': u'Clermont-Ferrand'},
    {   'latitude_e6': u'47322047', 'longitude_e6': u'5041480', 'name': u'Dijon'},
    {   'latitude_e6': u'51034560',
        'longitude_e6': u'2375201',
        'name': u'D\xfcnkirchen'},
    {   'latitude_e6': u'45188529',
        'longitude_e6': u'5724524',
        'name': u'Grenoble'},
    {   'latitude_e6': u'46160329',
        'longitude_e6': u'-1151139',
        'name': u'La Rochelle'},
    {   'latitude_e6': u'49494370',
        'longitude_e6': u'107929',
        'name': u'Le Havre'},
    {   'latitude_e6': u'48006110',
        'longitude_e6': u'199556',
        'name': u'Le Mans'},
    {   'latitude_e6': u'50629250', 'longitude_e6': u'3057256', 'name': u'Lille'},
    {   'latitude_e6': u'45833619',
        'longitude_e6': u'1261105',
        'name': u'Limoges'},
    {   'latitude_e6': u'45764043', 'longitude_e6': u'4835659', 'name': u'Lyon'},
    {   'latitude_e6': u'43296482',
        'longitude_e6': u'5369780',
        'name': u'Marseilles'},
    {   'latitude_e6': u'49119666', 'longitude_e6': u'6176905', 'name': u'Metz'},
    {   'latitude_e6': u'43610769',
        'longitude_e6': u'3876716',
        'name': u'Montpellier'},
    {   'latitude_e6': u'47750839',
        'longitude_e6': u'7335888',
        'name': u'M\xfclhausen'},
    {   'latitude_e6': u'47218371',
        'longitude_e6': u'-1553621',
        'name': u'Nantes'},
    {   'latitude_e6': u'43836699',
        'longitude_e6': u'4360054',
        'name': u'N\xeemes'},
    {   'latitude_e6': u'43696036', 'longitude_e6': u'7265592', 'name': u'Nizza'},
    {   'latitude_e6': u'47902964',
        'longitude_e6': u'1909251',
        'name': u'Orleans'},
    {   'latitude_e6': u'48856614', 'longitude_e6': u'2352221', 'name': u'Paris'},
    {   'latitude_e6': u'43295100', 'longitude_e6': u'-370797', 'name': u'Pau'},
    {   'latitude_e6': u'42698684',
        'longitude_e6': u'2895871',
        'name': u'Perpignan'},
    {   'latitude_e6': u'46580224',
        'longitude_e6': u'340375',
        'name': u'Poitiers'},
    {   'latitude_e6': u'49258329', 'longitude_e6': u'4031696', 'name': u'Reims'},
    {   'latitude_e6': u'48113475',
        'longitude_e6': u'-1675708',
        'name': u'Rennes'},
    {   'latitude_e6': u'50692704',
        'longitude_e6': u'3177847',
        'name': u'Roubaix'},
    {   'latitude_e6': u'49443232', 'longitude_e6': u'1099971', 'name': u'Rouen'},
    {   'latitude_e6': u'45439695',
        'longitude_e6': u'4387177',
        'name': u'Saint-Etienne'},
    {   'latitude_e6': u'48583148',
        'longitude_e6': u'7747882',
        'name': u'Stra\xdfburg'},
    {   'latitude_e6': u'43124228',
        'longitude_e6': u'5928000',
        'name': u'Toulon'},
    {   'latitude_e6': u'43604652',
        'longitude_e6': u'1444209',
        'name': u'Toulouse'},
    {   'latitude_e6': u'50724993',
        'longitude_e6': u'3162070',
        'name': u'Tourcoing'},
    {   'latitude_e6': u'47394144', 'longitude_e6': u'684840', 'name': u'Tours'},
    {   'latitude_e6': u'45771944',
        'longitude_e6': u'4890170',
        'name': u'Villeurbanne'}]
```