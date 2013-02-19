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

```
Auth-Token: YOUR-AUTH-TOKEN
```

# API methods

- **[<code>POST</code> /apps/{appId}/auth/device/{deviceId}](#device-authorization)**
- **[<code>POST</code> /apps/{appId}/users/{userId}/iap/apple](#iap-apple-post)**
- **[<code>POST</code> /apps/{appId}/users/{userId}/events](#events-post)**

## <a id="auth-post"></a>Device Authorization

<code>POST /apps/{appId}/auth/device/{deviceId}</code>

### Description

This resource allows you to authorize an anonymous user and post events for logging new installation and session events.

Logged events:

- <code>server_INSTALL</code> - New installation event
- <code>server_SESSION_START</code> - New session event

### Parameters

Url parameters:

`appId` | *An application id*
`deviceId` | *An arbitrary device id or [UUID](http://en.wikipedia.org/wiki/Universally_unique_identifier)*

Json Parameters:
<code>body</code> | *An arbitray JSON blob contains platform and/or custom information* 


```http
Request:
POST /apps/app-000001/auth/device/mydeviceId HTTP/1.1
Host: example.org
Content-Type: application/json; charset=utf-8

{"status": "ok", "extended": true}

Response:
```

