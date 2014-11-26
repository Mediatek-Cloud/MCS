# retrieveControllerType


### Description

Use **HTTP GET** to retrieve Controller Types

### Request URL

```
http://api.mediatek.com/mcs/v2/controllertypes
```

### Action
HTTP GET

### Parameters

#### Header

Authorization:Bearer `TOKEN_HERE`
Content-Type:application/json

#### Body


### Response

#### Response Code
200

#### Response Header

Content-Type:`application/json`
#### Response Body

***Data Format: JSON***

The response body will construct in JSON format with the following fields:

| Field Name | Type |Description|
| --- | --- | --- |
| ctlrTypeId | int | Controller Type Id
| name | varchar(100) | name of the controller Type
| description | varchar(1000) | description of the controller type |
| format | varchar(1000) | format of the controller type |

**Example: **

Request URL
```
http://api.mediatek.com/mcs/v2/controllertypes
```

Request Header

```
Authorization:Bearer 32fff343frg45434

Content-Type:application/json
```

Response Body

```
{
  "results": [
    {
      controllerTypeId : 1,
      name : "Switch",
      description : "This is a simple switch"
      format : "ON,OFF"
    },
    {
      controllerTypeId : 2,
      name : "GPS",
      description : "This is a GPS controller to dictate desired position",
      format : "Lat, Long"
    }
   ]
}
```

### Error Response

When error is incurred, the response code will be non-200 and the response body will construct in JSON format with the following fields:

| Field Name | Type |Description|
| --- | --- | --- |
| code | int | Error Code |
| url | string | url to API Error detail page |
| description | string | Error Description |

**Example: **
```
{
  "results": {
    "code": 1002,
    "url": "http:\\mcs.mediatek.com\api_errorcode?code=1002",
    "description": "You do not have access right to this API"
  }
}
```




