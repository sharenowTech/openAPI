# Cancel booking #
This function provides cancellation of an existing booking. Currently only HTTP DELETE is allowed. Access to this function is restricted. See <a href='../oauth.html'>OAuth documentation</a> for more details.

| **Access:** |protected |
|:------------|:---------|
| **URL:**    |https://www.car2go.com/api/v2.1/booking/bookingId |
| **Method:** |DELETE    |



### Parameters ###
| **Name** | **Mandatory** | **Description** |
|:---------|:--------------|:----------------|
| bookingId | true          | the identifier of the reservation to be canceled. |
| format   | false         | defines response format. Value "json" => JSON format, otherwise xml format is used |
| callback | false         | defines JSONP (JSON with Padding) callback function used as wrapper |
| test     | false         | activates test mode if set to "1". See below for more details. |




### Request Examples ###
```
DELETE https://www.car2go.com/api/v2.1/booking/1234
```

```
DELETE https://www.car2go.com/api/v2.1/booking/8152
```





### Response ###
The cancellation information of a booking consists of:
> <ul>
<blockquote><li>returnValue - see list of return codes below and  <a href='index.html#returnvalues'>return values</a> for more details</li>
<li>cancelFeeExists - flag indicating if any cancel fee exists</li>
<li>cancelFee - the amount of the cancellation fee. Period is used as decimal separator.</li>
<li>cancelFeeCurrency - the currency of the cancellation fee</li>
</ul></blockquote>



### Response Examples ###
A XML response example of cancel booking request:
> <p />
```

 <?xml version="1.0" encoding="UTF-8" standalone="yes"?>
 <cancelBookingResponse xmlns="http://www.car2go.com/openapi/xmlschema">
     <returnValue>
         <code>0</code>
         <description>Operation successful.</description>
     </returnValue>
     <cancelBooking>
         <cancelFeeExists>true</cancelFeeExists>
         <cancelFee>4.00</cancelFee>
         <cancelFeeCurrency>EUR</cancelFeeCurrency>
     </cancelBooking>
 </cancelBookingResponse>
 
```


> <p />
> A JSON example:
```

 {"cancelBooking":[{
   "cancelFee":"4.00",
   "cancelFeeCurrency":"EUR",
   "cancelFeeExists":true
 }],
 "returnValue":{
   "code":0,
   "description":"Operation successful."
 }}
 
```





### TestMode ###
Deletion of a booking in test mode requires one of test booking ids to be passed. <br />
> Note: You won't be charged any cancellation fees even if the result says "cancelFeeExists=true" <br />
> Furthermore the deletion has no impact on the result of <a href='getbookings.html'>Get Bookings</a> called in test mode.



### Return Codes ###
The following return codes may occur:
| **Code** | **Description** | **Note** |
|:---------|:----------------|:---------|
| 0        | Operation successful. |          |
| 2        | UserId invalid. |          |
| 6        | Invalid url parameter provided. |          |
| 11       | Booking id invalid. |          |






(c) 2010 car2go GmbH. All rights reserved. Generated 06.10.14 10:12