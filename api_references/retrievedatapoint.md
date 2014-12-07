# retrieveDataPoint

### Description

Use **HTTPs GET** to retrieve data point values of a device

**Maximum number of returned data points for each data channel: 1000**

### Request URL

```
https://api.mediatek.com/mcs/v2/devices/:device_id/datachannels/:datachannel_id/datapoints.{json/csv}?start=:start_time&end=:end_time&size=:size

```

or

```
https://api.mediatek.com/mcs/v2/devices/:device_id/datapoints.{json/csv}?start=:start_time&end=:end_time&size=:size
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


#### Querystring
Following fields should be constructed and appended to the end of the URL:


| Field Name | Type | Required |Description|
| --- | --- | --- | --- |
| start_time | Number | Optional | Start Timestamp of the query period |
| end_time | Number | Optional | End Timestamp of the query period |
| size | Number | Optional | number of the data points to be returned ( Default = 1 ) |

**Note:**

1.
Returns last *n (n=size)* data points when both *start_time* and *end_time* are not provided

2.
The parameters *start_time* and *end_time* have higher priority than *size*, i.e., when all three parameters are input, the parameter *size* will be ignored.

3.
Timestamp are received and returned in ISO 8601 format, with 3 decimal fraction of a second:

```
YYYY-MM-DDTHH:MM:SS.nnnZ
```



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
| isOverflow | Bool | Is the number of queried data points more than maximum number |
| dataPoints | Object Array | Data Points |

**dataPoint**

| Field Name | Type | Description|
| --- | --- | --- | --- |
| createdAt | Number | Unix timestamp of the data point |
| value | String | Data Point Value |

**Example:**

Request URL
```
https://api.mediatek.com/mcs/v2/devices/a1234567890/datachannels/10001/datapoints.json?start=2014-12-07T10:10:10.000Z&end=2014-12-07T10:20:10.000Z

```

Response Body

```
{
   "dataChnId": 10001,
   "isOverflow":false,
   "dataPoints":[
            {
               "createdAt": "2014-12-07T10:11:11.000Z",
               "value":"100"
            },
            {
               "createdAt": "2014-12-07T10:10:11.000Z",
               "value":"99"
            }
         ]
}
```


Request URL

```
https://api.mediatek.com/mcs/v2/devices/a1234567890/datapoints.json
```

Response Body

```
{
   "dataChannels":[
      {
         "dataChnlId":10001,
         "isOverflow":false,
         "dataPoints":[
            {
               "createdAt": "2014-12-07T10:11:11.000Z",
               "value":"100"
            },
            {
               "createdAt": "2014-12-07T10:10:11.000Z",
               "value":"99"
            }
         ]
      },
      {
         "dataChnId":10002,
         "isOverflow":false,
         "dataPoints":[
            {
               "createdAt": "2014-12-07T10:11:11.000Z",
               "value":{
                   "latitude":"112",
                   "lontitude":"23.3",
                   "altitude":"50"
               }
            },
            {
               "createdAt": "2014-12-07T10:10:11.000Z",
               "value":{
                   "latitude":"112",
                   "lontitude":"23.3",
                   "altitude":"50"
               }
            }
         ]
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

