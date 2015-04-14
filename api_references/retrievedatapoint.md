# retrieveDataPoint

## Description

Use **HTTPs GET** to retrieve data point values of a device


## Request URL

To retrieve the data points for specific data channel:

```
https://api.mediatek.com/mcs/v2/devices/:deviceId/datachannels/:datachannelId/datapoints?start=:startTime&end=:endTime&limit=:limit&offset=:offset

```


The API will by default assume the json format, if you want to use the csv, please add`.csv` after the datapoints.

The API enables you to retrieve four kinds of data:

* To get the last data point:



    `https://api.mediatek.com/mcs/v2/devices/:deviceId/datachannels/:datachannelId/datapoints`


* To get the data points within a time frame:


    Use the `?start=:startTime&end=:endTime` at the end.


* To limit the number of data points that you will get (eg, if you enter the limit=5, you will get the first 5 data points.):


    Use the `?limit=:limit&offset=:offset`at the end.


* To retrieve the data points from a specific point(eg, if you enter offset=5, you will not get the first 5 datapoints and start with 6th one):


    Use the `?offset=:offset` at the end.



You can choose to combine those conditions.






**Maximum number of returned data points for each data channel: 1000**


## Action
HTTPs GET

## Parameters

### Header

Device Key
```
deviceKey: `device_key_here`
```

### Return format
The return format can be in either JSON or CSV format

JSON:

when the request for resource ends with *datapoints*


CSV:

when the reqeust for resouce ends with *datapoints.csv*


### Querystring
Following fields should be constructed and appended to the end of the URL:


| Field Name | Type | Required |Description|
| --- | --- | --- | --- |
| start_time | Number | Optional | Start Timestamp of the query period |
| end_time | Number | Optional | End Timestamp of the query period |
| limit | Number | Optional | number of the data points to be returned ( Default = 1 ) |
| offset | Number | Optional | offset of the data points being retrieved |

**Note:**

1.
Returns last *n (n=size)* data points when both *start_time* and *end_time* are not provided

2.
The parameters *start_time* and *end_time* have higher priority than *size*, i.e., when all three parameters are input, the parameter *size* will be ignored.



## Response

### Response Code
200

### Response Header
For JSON response:
```
Content-Type:`application/json`
```
For CSV response:
```
Content-Type: `text/csv`
```

### Response Body

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
| isOverflow | Bool | Is the number of queried data points more than maximum number|
| dataPoints | Object Array | Data Points |


**dataPoint**

| Field Name | Type | Description|
| --- | --- | --- | --- |
| createdAt | Number | Unix timestamp of the data point|
| values | Object | Data Point Value |

Please note, the unix time is in milliseconds, for human readable time conversion, please refer to http://www.epochconverter.com/

**Example:**

Request URL
```
https://api.mediatek.com/mcs/v2/devices/a1234567890/datachannels/10001/datapoints?start=946684800&end=946784800

```

Response Body in json

```
{
    "deviceId": "DXLQwmnN",
    "dataChannels": [
        {
            "dataChnId": "test01",
            "isOverflow": false,
            "dataPoints": [
                {
                    "recordedAt": 1426457820600,
                    "values": {
                        "value": "HI"
                    }
                }
            ]
        }
    ]
}
```

Response Body in csv

```
test_data_channel,94668480,100
```



## Error Response

When error is incurred, the response code will be non-200 and the response body will construct in JSON format with the following fields:

| Field Name | Type |Description|
| --- | --- | --- |
| code | Integer | Error Code |
| url | String | url to API Error detail page |
| description | String | Error Description |

**Example:**

```
{
  apiVersion: "0.0.1",
  code: 401,
  message: "401 Unauthorized",
  errors: [
    {
      code: 401,
      message: "401 Unauthorized"
    }
  ],
  results: "You don't have permission!",
  statusCode: 401,
  options: { }
}
```

