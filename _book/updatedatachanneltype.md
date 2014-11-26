# updateDataChannelType


### Description

Use **HTTP PUT** to update for retrieve Data Channel Types


### Request URL

```
http://api.mediatek.com/mcs/v2/datachanneltypes/:datachanneltypeid
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
| name | varchar(100) | name of the data channel Type |

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
| results | string | result of API call |

**Example: **

Request URL
```
http://api.mediatek.com/mcs/v2/datachanneltypes/1
```


Request Header

```
Authorization:Bearer 32fff343frg45434

Content-Type:application/json
```

Response Body

```
{
  "results": "success"
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




