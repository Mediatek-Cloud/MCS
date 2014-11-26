# uploadDataPoint

### Description

Use **HTTPs POST** to upload data points

### Request URL

```
https://api.mediatek.com/mcs/v2/devices/:device_id/datapoints

```

### Action
HTTPs POST

### Parameters

#### Header

Device Key

#### Body
The request body should be constructed in the following csv format:

*Number of Data Points,Data Channel ID 1,Value 1,Data Channel ID 2,Value 2,...*



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
| createdAt | Number | Command created timestamp |


**Example: **

Request URL
```
https://api.mediatek.com/mcs/v2/devices/d1234567890/datapoints
```

Request Body

```
3,1,100,2,0,3,1
```

Response Body

```
{
    "createdAt":1286705410
}
```

### Error Response

When error is incurred, the response code will be non-200 and the response body will construct in JSON format with the following fields:

| Field Name | Type |Description|
| --- | --- | --- |
| code | Integer | Error Code |
| url | String | url to API Error detail page |
| description | String | Error Description |

**Example:**

```
{
  "results": {
    "code": 1002,
    "url": "http://mcs.mediatek.com/api_errorcode?code=1002",
    "description": "You do not have access right to this API"
  }
}
```





