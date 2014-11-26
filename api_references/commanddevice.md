# commandDevice

### Description

Use **HTTPs POST** to create a command to a device's data channel

### Request URL

```
https://api.mediatek.com/mcs/v2/devices/:device_id/commands

```

### Action
HTTPs POST

### Parameters

#### Header

Authorization: Bearer '{token}'

#### Body
The request body can be constructed in free string format by following a command type code, therfore, the complete command format is like:

*commandType,free command content*

**Detail Fields**

| Field Name | Type | Required |Description|
| --- | --- | --- | --- |
| commandType | Number | Yes | Command Type ( 0 = Custom Command, 1 = Data Channel Command )|
| commands | String | Yes | Command Contents |


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
https://api.mediatek.com/mcs/v2/devices/d1234567890/commands
```

Request Body

```
0,This is my command
```

Response Body

```
{
  "results": {
    "createdAt":1286705410
  }
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





