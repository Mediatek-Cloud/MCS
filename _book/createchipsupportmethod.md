# createChipSupportMethod

### Description

Use **HTTP POST** to request for chip communication protocol support methods, example includes TCP, UDP, TLS, HTTP, HTTPS

### Request URL

```
http://api.mediatek.com/mcs/v2/chipsupportmethods
```

### Action
HTTP POST

### Parameters

#### Header

Authorization:Bearer `TOKEN_HERE`
Content-Type:application/json

#### Body

The body will construct in JSON format with the following fields:

| Field Name| Mandatory | Type |Description|
| --- | --- | --- | --- |
| name | Yes |varchar(100) | Supported communication protocol name |


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
| results | string | results of API
|sptMthTypeId | int | Id of supported communicaiton protocol Id ||

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

Request Body

```
{
  "name": "SSL"
}
```

Response Body

```
{
  "results": {
    "results" : "success",
    "sptMthTypeId": 1
    }
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




