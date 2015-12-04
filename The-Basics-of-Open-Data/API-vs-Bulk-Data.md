# Introduction

There are two primary methods of publishing open data—as bulk data or with an Application Programming Interface (API). There are benefits and drawbacks to both, and each is better suited to different scenarios.

As a general rule, you’ll want to publish bulk data, not an API.

# APIs

Think of an Application Programming Interface as software that communicates via the web. Here’s a request to the National Weather Service's API for the weather forecast for Washington DC ("WASD2"):

```
http://w1.weather.gov/xml/current_obs/WASD2.xml
```

The web server sends this response:

```
<?xml version="1.0" encoding="ISO-8859-1"?> 
<?xml-stylesheet href="latest_ob.xsl" type="text/xsl"?>
<current_observation version="1.0"
	 xmlns:xsd="http://www.w3.org/2001/XMLSchema"
	 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	 xsi:noNamespaceSchemaLocation="http://www.weather.gov/view/current_observation.xsd">
	<credit>NOAA's National Weather Service</credit>
	<credit_URL>http://weather.gov/</credit_URL>
	<image>
		<url>http://weather.gov/images/xml_logo.gif</url>
		<title>NOAA's National Weather Service</title>
		<link>http://weather.gov</link>
	</image>
	<suggested_pickup>15 minutes after the hour</suggested_pickup>
	<suggested_pickup_period>60</suggested_pickup_period>
	<location>8594900 - Washington, DC</location>
	<station_id>WASD2</station_id>
	<latitude>38.87</latitude>
	<longitude>-77.02</longitude>
	<observation_time>Last Updated on Nov 10 2014, 12:30 pm EST</observation_time>
        <observation_time_rfc822>Mon, 10 Nov 2014 12:30:00 -0500</observation_time_rfc822>
	<temperature_string>59.2 F (15.1 C)</temperature_string>
	<temp_f>59.2</temp_f>
	<temp_c>15.1</temp_c>
	<water_temp_f>52.5</water_temp_f>
	<water_temp_c>11.4</water_temp_c>
	<wind_string>South at 2.2 MPH (1.94 KT)</wind_string>
	<wind_dir>South</wind_dir>
	<wind_degrees>200</wind_degrees>
	<wind_mph>2.2</wind_mph>
	<wind_gust_mph>0.0</wind_gust_mph>
	<wind_kt>1.94</wind_kt>
	<pressure_string>1020.0 mb</pressure_string>
	<pressure_mb>1020.0</pressure_mb>
	<mean_wave_dir>North</mean_wave_dir>
	<mean_wave_degrees></mean_wave_degrees>
	<disclaimer_url>http://weather.gov/disclaimer.html</disclaimer_url>
	<copyright_url>http://weather.gov/disclaimer.html</copyright_url>
	<privacy_policy_url>http://weather.gov/notice.html</privacy_policy_url>
</current_observation>
```

This is Extensible Markup Language (XML)—readable by both software and humans.

This API request is exactly the same as typing in a website address and getting a webpage in response, only instead of getting a pretty-looking page, you get data that’s designed to be read by software. (Cleverly, the National Weather Service does both. If you [go to that API address now](http://w1.weather.gov/xml/current_obs/WASD2.xml), you’ll get a nice-looking web page. But if you view the source, you’ll see it’s created by the XML.)

## Pros

* For data that changes frequently, even constantly, APIs don’t require constant resynchronization.
* For datasets that are impractically large, or merely large but that most people only need a tiny portion of, APIs don’t require transferring and parsing large amounts of data.


## Cons

* APIs are only useful to programmers.
* There are scenarios in which it’s important to be able to analyze an entire dataset, and fragmenting it behind an API can make that very difficult.
* APIs can be technologically demanding to host and maintain.
* In the case of a temporary government shutdown, if servers are shut down, data within an API is totally inaccessible, making useless any software that depends on it.


# Bulk Data

"Bulk data" is really just a fancy way of saying "files." These might be JSON, XML, CSV, or any of dozens of other file formats. Considering the above example of weather data, imagine if instead of making one request and getting one forecast, if the request was instead for `http://w1.weather.gov/xml/current_obs.xml`, and the server responded with  XML file providing the current weather for every weather station in the United States. That's bulk data.

## Pros

* Common file formats—especially CSV—can be used by almost anybody, rather than just programmers.
* It’s easy to produce, in comparison to an API. Often data is already stored in a format useful to the public, and if it’s not, it generally can be automatically converted into such a format.
* It’s trivial to host and distribute, because it’s just files.
* In the case of a government shutdown, if servers are shut down, bulk data is easily mirrored. Properly written client software will continue to function just fine, using the locally cached copy of the file.

## Cons

* For data that changes frequently, even constantly, bulk data can be impractical, because clients may have to download updated files constantly.
* For datasets that are impractically large, or merely large but that most people only need a tiny portion of, bulk data can be an obstacle, because of the resources required to transfer and parse it.

# Hybrid Model

There is a hybrid model that lives between an API and the bulk data model.

For many types of data, one can _simulate_ an API via clever bulk downloads. A directory full of properly named JSON or XML files functions the same as an API, providing the ease of bulk data, but with the nimbleness of an API.

Imagine a dataset of restaurant health inspections with 1,000 inspection records, one per restaurant. You could create one file, `index.json`, that’s a list of every restaurant, providing each one’s name, address, aggregate health score, health department ID (e.g., `00000001`, `00000002`, etc.), and API URL (e.g., `http://www.example.gov/inspections/api/00000001.json`, `http://www.example.gov/inspections/api/00000002.json`, etc.) Then you could create one file for each restaurant, 1,000 in all, containing the actual inspection data, named `00000001.json`, `00000002.json`, etc. For good measure, you could zip all of them up into a single download, `health_inspections.zip`.

This faux API provides the best of bulk downloads and the best of APIs. It incurs no technical debt, creates a very simple API that requires little technological sophistication, has a bulk download component for those who would prefer to work with the data locally, and provides the granularity of an API.
