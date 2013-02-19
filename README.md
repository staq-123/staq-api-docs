# //staq REST API documentation V1.0

[//staq](http://staq.io) is a platforms to mange and operate service-based games.

Version 1 of the API is limited to event tracking and IAP purchase server verification.

The API is a [REST API](http://en.wikipedia.org/wiki/Representational_State_Transfer "RESTful")
and uses an AppSecret specified in the http header for authenticating request.
You can signup at [http://staq.io](http://staq.io) or login at [https://dashboard.staq.io](https://dashboard.staq.io).
AppSecret and AppId are visible in the dashboard by clicking on **User => Show Api Keys**.
Input and output format for all endpoints is [JSON](http://json.org/ "JSON").

***

## Endpoint

**<code>Base url</code>**: https://api.staq.io/v1

## Authenticating requests

In order to authenticate your requests you need to specifiy the following parameter in the <code>HTTP HEADER</code>:

```HTTP
Auth-Token: YOUR-AUTH-TOKEN
```HTTP


