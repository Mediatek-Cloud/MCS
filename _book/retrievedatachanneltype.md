# retrieveDataChannelType


### Description

Use **HTTP GET** to retrieve Data Channel Types

### Request URL

```
http://api.mediatek.com/mcs/v2/datachanneltypes
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
| dataChannelTypeId | int | DataChannelType Id
| name | varchar(100) | name of the data channel Type ||

**Example: **

Request URL
```
http://api.mediatek.com/mcs/v2/retrievedatachanneltype
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
      dataChannelTypeId : 1,
      name : "Time-Value"
    },
    {
      dataChannelTypeId : 2,
      name : "ON/OFF"
    },
    {
      dataChannelTypeId : 3,
      name : "GPS"
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




