# retrieveChipSupportMethod

### Description

Use **HTTP GET** to retrieve for chip communication protocol support methods, example includes TCP, UDP, TLS, HTTP, HTTPS

### Request URL

```
http://api.mediatek.com/mcs/v2/chipsupportmethods
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
|  sptMthTypeId | int | Chip Support Method Type Id
| name | string | name of the support Method Type ||

**Example: **

Request URL
```
http://api.mediatek.com/mcs/v2/chipsupportmethods
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
      sptMthTypeId : 1,
      name : "TCP"
    },
    {
      sptMthTypeId : 2,
      name : "UDP"
    },
    {
      sptMthTypeId : 3,
      name : "TLS"
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




