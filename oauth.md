# Access protected functions via OAuth #
Some API functions are marked as protected. You need to authenticate via OAuth to access these functions.


See [oauth.net](http://www.oauth.net) for more details on OAuth.


As a developer you must register as a so called "consumer" at car2go. See [registration](oauth#Registration_as_consumer.md) for more details.

## Restrictions ##
  * Use HMAC-SHA1 for signing requests.
  * We ignore callback URLs passed to request token endpoint. You may provide a callback URL during registration as a consumer.
  * Access to car2go API is limited to a few calls per second (see [Error Codes](oauth#Error_codes.md)). Keep this in mind during development of your application.

## Hints ##
  * The nonce must not exceed a maximum of 40 characters
  * Your application should be able to handle oauth tokens up to 80 characters
  * Even though we ignore callback URL passed to the request token endpoint this parameter is mandatory and has to be set to "oob"

## OAuth Endpoints ##
| **Name** | **Url** | **Note** |
|:---------|:--------|:---------|
| Get request token | https://www.car2go.com/api/reqtoken | Token is valid for some hours. |
| Authorize token | https://www.car2go.com/api/authorize | Pass request token as parameter, e.g. "?oauth\_token=`[token]`" |
| Get access token | https://www.car2go.com/api/accesstoken | Token is valid for about one month. User can revoke token via car2go portal. |

## Error codes ##
Error codes are based on [Problem Reporting (oauth.net)](http://wiki.oauth.net/ProblemReporting).


| **HTTP Code** | **OAuth problem** | **Notes** |
|:--------------|:------------------|:----------|
| 400           | version\_rejected |           |
| 400           | parameter\_absent |           |
| 400           | parameter\_rejected |           |
| 400           | timestamp\_refused |           |
| 400           | signature\_method\_rejected |           |
| 401           | nonce\_used       |           |
| 401           | signature\_invalid |           |
| 401           | consumer\_key\_unknown |           |
| 503           | consumer\_key\_refused |           |
| 401           | token\_expired    |           |
| 401           | token\_rejected   |           |
| 401           | permission\_unknown |           |
| 503           | user\_refused     |           |
| 401           | verifier\_invalid |           |


## Registration as consumer ##
To register as consumer at car2go send an email to [openapi@car2go.com](mailto:openapi@car2go.com).  We ask you to provide some background information on you and the cool app you are about to create.


### Mandatory Information ###

  * Full name
  * Email
  * Country you reside in
  * Type of project: Do you develop in private/for education or studies/for a company/...
  * Project or product name
  * Project description (what's the intend and goal, which functionality is focussed)
  * Target Platform/Technology (Web Application/Mobile App/iOS/Android/Nokia Sxyz/Blackberry/Palm/RichClient/...)


### Optional Information ###

  * Envisioned development timeline (when do you want to release the app?)
  * CallbackURL for Applicationredirect (optional)
  * For potential future linkin in car2go portal: URL, Email, Icon
  * Info whether test user is required
  * Address

As soon as we receive the details, we will complete the registration process and you're ready to go!


(c) 2010 car2go GmbH. All rights reserved. Generated 17.08.11 16:28