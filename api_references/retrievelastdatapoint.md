# retrieveLastDataPoint

### Description

Use **HTTPs GET** to retrieve last data point values of a device


### Request URL

```
https://api.mediatek.com/mcs/v2/devices/:device_id/datachannels/:datachannel_id/lastdatapoints.{json/csv}

```

or

```
https://api.mediatek.com/mcs/v2/devices/:device_id/datapoints.{json/csv}
```

### Action
HTTPs GET

### Parameters

#### Header

Device Key
```
Device-Key: `device_key_here`
```

#### Return format
The return format can be in either JSON or CSV format

JSON:

when the request for resource ends with *datapoints.json*#


CSV:

when the reqeust for resouce ends with *datapoints.csv*


### Response

#### Response Code
200

#### Response Header
For JSON response:
```
Content-Type:`application/json`
```
For CSV response:
```
Content-Type: `application/text`
```

#### Response Body

***Data Format: JSON***

The response body will construct in JSON format with the following fields:

| Field Name | Type | Description|
| --- | --- | --- | --- |
| dataChannels | Object Array | Device Channels that contain the result data points |

**Detailed Object Fields**

**dataChannel**

| Field Name | Type | Description|
| --- | --- | --- | --- |
| dataChnId | Number | Data Channel ID |
| dataPoints | Object Array | Data Points |

**dataPoint**

| Field Name | Type | Description|
| --- | --- | --- | --- |
| createdAt | Number | Unix timestamp of the data point |
| value | String | Data Point Value |

**Example:**

Request URL
```
https://api.mediatek.com/mcs/v2/devices/a1234567890/datachannels/10001/lastdatapoints.json

```

Response Body

```
{
   "dataChnId": 10001,
   "createdAt": "2014-12-07T10:11:11.000Z",
   "value":"100"
}
```


Request URL

```
https://api.mediatek.com/mcs/v2/devices/a1234567890/datapoints
```

Response Body

```
{
   "deviceId":"a1234567890",
   "dataChannels":[
      {
         "dataChnlId":10001,
         "createdAt": "2014-12-07T10:11:11.000Z",
         "value":"100"
          }

      },
      {
         "dataChnId":10002,
         "isOverflow":false,
         "createdAt": "2014-12-07T10:11:11.000Z",
         "value":{
                   "latitude":"112",
                   "lontitude":"23.3",
                   "altitude":"50"
                 }
      }
   ]
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

