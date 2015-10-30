# car2go API v2.0 #
## Endpoints ##
| **Name** | **Method** | **Url** | **Access** |
|:---------|:-----------|:--------|:-----------|
| [Get all parking spots](parkingspots_v2_0.md) |GET         | http://www.car2go.com/api/v2.0/parkingspots | public     |
| [Get all locations](locations_v2_0.md) |GET         | http://www.car2go.com/api/v2.0/locations | public     |
| [Get all gas stations](gasstations_v2_0.md) |GET         | http://www.car2go.com/api/v2.0/gasstations | public     |
| [Get all free vehicles](vehicles_v2_0.md) |GET         | http://www.car2go.com/api/v2.0/vehicles | public     |
| [Get all accounts](accounts_v2_0.md) |GET         | https://www.car2go.com/api/v2.0/accounts | protected  |
| [Get bookings](getbookings_v2_0.md) |GET         | https://www.car2go.com/api/v2.0/bookings | protected  |
| [Create booking](createbooking_v2_0.md) |POST        | https://www.car2go.com/api/v2.0/bookings | protected  |
| [Get booking](getbooking_v2_0.md) |GET         | https://www.car2go.com/api/v2.0/booking | protected  |
| [Cancel booking](delbooking_v2_0.md) |DELETE      | https://www.car2go.com/api/v2.0/booking/bookingId | protected  |


See [OAuth Documentation](oauth.md) if you want to learn how to access protected API functions.



## Return values ##
Response format is defined in [openapi.xsd openapi.xsd]



The following return codes may occur:

| **Code** | **Description** |
|:---------|:----------------|
| 0        | Operation successful. |
| 1        | Location invalid. |
| 2        | UserId invalid. |
| 3        | No valid accounts found. |
| 4        | Not all necessary url parameters provided. |
| 5        | A technical error occured. |
| 6        | Invalid url parameter provided. |
| 7        | No valid driver license information could be found. |
| 8        | The account is locked. |
| 9        | The vehicle can not be booked. |
| 10       | Vehicle invalid. |
| 11       | Booking id invalid. |
| 12       | No reserved vehicle found. |




Some API functions result in KML response. More information can be found here: [KML Reference at code.google.com](http://code.google.com/intl/de/apis/kml/documentation/kmlreference.html)





(c) 2010 car2go GmbH. All rights reserved. Generated 06.10.14 10:12