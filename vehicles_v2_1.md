# Get all free vehicles #
Provides a list of all free car2go vehicles for a given location like ulm or austin in KML format.
KML is a file format used to display geographic data in an Earth browser such as Google Earth, Google Maps, and Google Maps for mobile. More information about KML can be found here: <a href='http://code.google.com/intl/de/apis/kml/documentation/kmlreference.html'>KML Reference at code.google.com</a>


| **Access:** |public |
|:------------|:------|
| **URL:**    |http://www.car2go.com/api/v2.1/vehicles |
| **Method:** |GET    |



### Parameters ###
| **Name** | **Mandatory** | **Description** |
|:---------|:--------------|:----------------|
| loc      | true          | location identifier string of the home location for which the vehicles are searched for, e.g. "ulm", "austin". |
| oauth\_consumer\_key | true          | your assigned oauth consumer key |
| format   | false         | defines response format. Value "json" => JSON format, otherwise xml format is used |
| callback | false         | defines JSONP (JSON with Padding) callback function used as wrapper |
| smartPhoneRequired | false         | parameter to filter vehicles which can only be opened with a smartphone and authorized smartphone app; possible values: true or false |
| test     | false         | has currently no effect |




### Request Examples ###
```

 GET http://www.car2go.com/api/v2.1/vehicles?loc=ulm&oauth_consumer_key=consumerkey
 
```

```

 GET http://www.car2go.com/api/v2.1/vehicles?loc=austin&oauth_consumer_key=consumerkey&format=json
 
```





### Response ###
The response is provided as KML file which defines a placemark tag for each free car2go vehicle. The placemark tag
> defines following sub tags:
> <ul>
<blockquote><li>name - contains the license plate of the vehicle</li>
<li>description - contains the address, the interior, the exterior state and the fuel level of the vehicle. The address,<br>
the interior state, the exterior state and the fuel are also defined in the extendeddata tag.</li>
<li>point - the coordinates of the vehicle</li>
<li>extendeddata - the extended data contains the vehicle identification number(vin), the address, the interior state,<br>
the exterior state, the fuel level and the charging state of the vehicle.<br>
<ul>
<li>The interior and exterior state can contain one of the following values:<br />
GOOD<br />
BAD<br>
</li>
</ul>
<ul>
<li>The engine of the vehicle can be a combustion engine or an electric drive:<br />
CE<br />
ED</li>
</ul>
<ul>
<li>The charging flag is only relevant for ED vehicles. The flag is true when the vehicle is being loaded at a charging<br>
pole, otherwise false.</li>
</ul>
<ul>
<li>The fuel value is the percentage of fuel left in the fuel tank or the state of charge of a vehicle. 100 means the fuel<br>
tank is full or the vehicle is fully charged. A 0 value means the fuel tank is empty or the vehicle is fully discharged.</li>
</ul>
<ul>
<li>The vin is the vehicle identification number of the car2go. The vehicle identification number is a unique id for a<br>
car2go vehicle.</li>
</ul>
<ul>
<li>The flag smartPhoneRequired is true when the vehicle can not be opened without a smartphone and authorized smartphone app, otherwise false.</li>
</ul>
</li>
</ul></blockquote>



### Response Examples ###
```

 <kml xmlns:ns3="urn:oasis:names:tc:ciq:xsdschema:xAL:2.0" xmlns:ns2="http://www.w3.org/2005/Atom"
 	xmlns="http://www.opengis.net/kml/2.2">
 	<Document>
 		<description>Available CAR2GO Vehicles</description>
 		<Style id="car2go">
 			<IconStyle>
 				<Icon>
 					<href>http://www.car2go.com/common/img/desktop/map_pin_car.png
 					</href>
 				</Icon>
 				<hotSpot y="0.0" x="0.0" />
 			</IconStyle>
 		</Style>
 		<Style id="car2go_ed">
 			<IconStyle>
 				<Icon>
 					<href>http://www.car2go.com/common/img/desktop/map_pin_car_ed.png
 					</href>
 				</Icon>
 				<hotSpot y="0.0" x="0.0" />
 			</IconStyle>
 		</Style>
 		<Placemark>
 			<name>UL-C5887</name>
 			<description>Sudetenweg, 89075 Ulm<br/>Fuel
 				24<br/>Interior GOOD<br/>Exterior GOOD
 			</description>
 			<styleUrl>#car2go_ed</styleUrl>
 			<ExtendedData>
 				<Data name="fuel">
 					<value>24</value>
 				</Data>
 				<Data name="interior">
 					<value>GOOD</value>
 				</Data>
 				<Data name="exterior">
 					<value>GOOD</value>
 				</Data>
 				<Data name="vin">
 					<value>WME4513001K154655</value>
 				</Data>
 				<Data name="engineType">
 					<value>ED</value>
 				</Data>
 				<Data name="charging">
 					<value>true</value>
 				</Data>
 			    </Data name="smartPhoneRequired">
                  <value>false</value>
               </Data>
 			</ExtendedData>
 			<Point>
 				<coordinates>10.029,48.4362,0</coordinates>
 			</Point>
 		</Placemark>
 		<Placemark>
 			<name>UL-C5889</name>
 			<description>Heilmeyersteige, 89075 Ulm<br/>Fuel
 				58<br/>Interior GOOD<br/>Exterior GOOD
 			</description>
 			<styleUrl>#car2go</styleUrl>
 			<ExtendedData>
 				<Data name="fuel">
 					<value>58</value>
 				</Data>
 				<Data name="interior">
 					<value>GOOD</value>
 				</Data>
 				<Data name="exterior">
 					<value>GOOD</value>
 				</Data>
 				<Data name="vin">
 					<value>WME4513001K154655</value>
 				</Data>
 				<Data name="engineType">
 					<value>CE</value>
 				</Data>
 			    </Data name="smartPhoneRequired">
                  <value>false</value>
              </Data>
 			</ExtendedData>
 			<Point>
 				<coordinates>9.947235,48.410497,0</coordinates>
 			</Point>
 		</Placemark>
 	</Document>
 </kml>
 
```

A JSON response example:
> <p />
```

 {"placemarks":[{"address":"Reuttier Strasse 133, 89231 Neu-Ulm","coordinates":[10.023925,48.383125,0],"exterior":"GOOD","fuel":98,"interior":"GOOD","name":"UL-C5704","vin":"WME4513001K155530","engineType":"CE","smartPhoneRequired": false}]}
 
```





### TestMode ###










(c) 2010 car2go GmbH. All rights reserved. Generated 06.10.14 10:12