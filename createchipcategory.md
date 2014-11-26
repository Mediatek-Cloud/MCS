# createChipCategory

### Description

Use **HTTP POST** to request for chip category creation

### Request URL

```
http://api.mediatek.com/mcs/v2/chipcategories
```

### Action
HTTP POST

### Parameters

#### Header

Authorization:Bearer `TOKEN_HERE`

Content-Type:application/json

#### Body

The body will construct in JSON format with the following fields:

| Field Name | Type |Description|
| --- | --- | --- |
| name | varchar(100) | Name of category ||


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
|chipCateTypeId | int | Id of created Chip Category ||

**Example: **

Request URL
```
http://api.mediatek.com/mcs/v2/chipcategories
```

Request Header

```
Authorization:Bearer 32fff343frg45434

Content-Type:application/json
```

Request Body

```
{
  "name": "Wearable"
}
```

Response Body

```
{
  "results": {
    "results" : "success",
    "chipCateTypeId": 1
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




