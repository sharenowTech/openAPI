# Get all locations #
Provides a list of all locations car2go is operating for like ulm or austin in either XML or JSON format.

| **Access:** |public |
|:------------|:------|
| **URL:**    |http://www.car2go.com/api/v2.1/locations |
| **Method:** |GET    |



### Parameters ###
| **Name** | **Mandatory** | **Description** |
|:---------|:--------------|:----------------|
| oauth\_consumer\_key | true          | your assigned oauth consumer key |
| format   | false         | defines response format. Value "json" => JSON format, otherwise xml format is used |
| callback | false         | defines JSONP (JSON with Padding) callback function used as wrapper |
| test     | false         | has currently no effect |




### Request Examples ###
```

 GET http://www.car2go.com/api/v2.1/locations?oauth_consumer_key=consumerkey
 
```

```

 GET http://www.car2go.com/api/v2.1/locations?oauth_consumer_key=consumerkey&format=json
 
```





### Response ###
Each location consists of:
> <ul>
<blockquote><li>returnValue - see OpenApiReturnValue for more details</li>
</ul>
<ul>
<li>locationId - the unique identifier of the location</li>
<li>locationName - the name of the location</li>
<li>defaultLanguage - the default language of the location, according to ISO 639-1 alpha-2 code</li>
<li>countryCode - the country of the location, according to ISO 3166-1 alpha-2 code</li>
<li>timeZone - the timeZone of the location, Continent/City</li>
</ul>
mapSection - map informations:<br>
<ul>
<li>center - center of location (latitude/longitude)</li>
<li>upperLeft - upper left coordinates of operation area (latitude/longitude)</li>
<li>lowerRight - lower right coordinates of operation area (latitude/longitude)</li>
</ul></blockquote>



### Response Examples ###
A XML response example:
> <p />

```

  <?xml version="1.0" encoding="UTF-8" standalone="yes"?><locationResponse xmlns="http://www.car2go.com/openapi/xmlschema"><returnValue><code>0</code><description>Operation successful.</description></returnValue><location><locationId>1</locationId><locationName>Ulm</locationName><timezone>Europe/Berlin</timezone><countryCode>DE</countryCode><defaultLanguage>de</defaultLanguage><mapSection><center><latitude>48.398917</latitude><longitude>9.99139</longitude></center><upperLeft><latitude>48.4383</latitude><longitude>9.9146</longitude></upperLeft><lowerRight><latitude>48.3446</latitude><longitude>10.0459</longitude></lowerRight></mapSection></location></locationResponse>
 
```

A JSON response example:
> <p />

```

 {"location":[
 	 {"countryCode":"DE",
    "defaultLanguage":"de",
    "locationId":1,
    "locationName":"Ulm",
    "mapSection":{
   	"center":{
        	"latitude":48.398917,
        	"longitude":9.99139
      },"lowerRight":{
        	"latitude":48.3446,
        	"longitude":10.0459
      },"upperLeft":{
        	"latitude":48.4383,
        	"longitude":9.9146
      }
     },"timezone":"Europe/Berlin"
    }],
    "returnValue":{
      "code":0,
      "description":"Operation successful."
  }}
 
```





### TestMode ###




### Return Codes ###
The following return codes may occur:
| **Code** | **Description** | **Note** |
|:---------|:----------------|:---------|
| 0        | Operation successful. |          |






(c) 2010 car2go GmbH. All rights reserved. Generated 06.10.14 10:12