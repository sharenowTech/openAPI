This project is not hosting api code, but rather makes use of the issue tracking and wiki to support the car2go OpenAPI. Beside the actual documentation of the OpenAPI you'll also find example code on how to use the api on various platforms like iPhone or the web.

## 09.06.2015 car2go App now offers deep-linking ##
Since v2.6 of the official car2go [Android](https://play.google.com/store/apps/details?id=com.car2go&hl=de) and [iOS](https://itunes.apple.com/de/app/car2go/id514921710?mt=8) App you can now deep-link from any third party App into the Apps with the details of a specific vehicle selected. Here the structure for deep-linking:

  * Android: [http|https]://car2go.com/vehicle/$VIN?location=$LOCATION\_ID
  * iOS: car2go://vehicle/$VIN?location=$LOCATION\_ID

$LOCATION\_ID - The numeric identifier of the LocationID (e.g. 3 for Hamburg)

$VIN - The vehicle identification number of the car


## 26.08.2011 OpenAPI goes Electric Drive ##

We are happy to announce the new version [2.1](index_v2_1.md) of the car2go OpenAPI. Those of you who are already familiar with version 2.0 should notice the improvements:
  * The /vehicles method now returns additional information on engine type and charging status (if the vehicle is an ED).
  * The /parkingspots call includes information on charging poles
  * /locations return more data to help developers keep their apps generic: Not only we added the locations default language, country code and timezone, but also a map section containing a center position and corner positions of the operating area
  * We fixed the JSON encoding for all API calls (arrays are no longer returned as strings)
  * For public API calls the oauth\_consumer\_key is now mandatory to prevent abuse

Since version 1.0 has been deprecated for quite a while now those calls are no longer available. Because the OpenAPI 2.1 is a full-blown replacement we also deprecated v2.0.

For security reasons we are going to increase the length of token and token secrets in the near future. Please take care of this ff your application has a limitation for those data.

Happy developing!



## 24.05.2010 OpenAPI 2.0 Released ##

Hip hip hooray, new stuff in May! We heard your calls for booking support and just released some really neat features. With our brand new [Open API version 2.0](overview.md) we not only introduce short-term bookings and user accounts support, but also changed to RESTful interfaces for more intuitive handling.

You can now provide more personalized features in you 3rd party apps. In order to support this, we started using [OAuth](oauth.md) as flexible at the same time powerful security concept.

Step into the details, [get your API key](oauth#Registration_as_consumer.md) and surprise the car2go users with cool apps!

Usage of the car2go Open API underlies our [Terms of use](http://www.car2go.com/api/tou.htm).