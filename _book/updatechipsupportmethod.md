# updateChipSupportMethod

### Description

Use **HTTP PUT** to update for chip communication protocol support methods, example includes TCP, UDP, TLS, HTTP, HTTPS

### Request URL

```
http://api.mediatek.com/mcs/v2/chipsupportmethods/:sptMthTypeId
```

### Action
HTTP PUT

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
| name | string | Chip Support Method Type Name|

**Example: **

Request URL
```
http://api.mediatek.com/mcs/v2/chipsupportmethods/1
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




