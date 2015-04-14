# retrieveDeviceInfo

## Description

Use **HTTPs GET** to retrieve devices

## Request URL

```
https://api.mediatek.com/mcs/v2/devices/:deviceId

```

## Action
HTTPs GET

## Parameters

### Header

Authorization: `Bearer '{token}'`

Content-Type:`application/json`


## Response

### Response Code
200

### Response Header

Content-Type:`application/json`
### Response Body

***Data Format: JSON***

The response body will construct in JSON format with the following fields:

| Field Name | Type |Description|
| --- | --- | --- |
| deviceId | String | Device ID |
| deviceKey | String | Device Key |
| name | String | Device Name |
| description | String | Device Description |
| product | Object | Product Info |
| dataChannels | Object Array | Data Channels |
| fw | Object | Firmware Info |
| trustIpRange | String Array | Trusted IP range from where the device is allowed to conntect to MCS |
| lastIp | String | Last IP the device seen from |
| deviceImageURL | String | Device image URL |
| isHeartbeating | Bool | Is the device currently online |
| isVerified | Bool | Has the device registration been verified |
| isActive | Bool | Is the device active |
| isTest | Bool | Is the device a test device |
| activatedAt | Number | Timestamp of the device activation |
| deactivatedAt | Number | Timestamp of the device deactivation ( Default = null if the device is active and has not been deactivated ) |
| tags | Object Array | Tags of the device |
| privilege | String | User's privilege on the device |

**Detailed Object Fields**

**product**

| Field Name | Type |Description|
| --- | --- | --- |
| prodId | String | Product ID |
| prodVersion | String | Product Version |
| name | String | Product Name |
| description | String | Product Description |
| displayConfigs | Object Array | A JSON format object indicatig how each data channel will be displayed |
| chip | String | Product Chip |


**dataChannel**

| Field Name | Type | Description|
| --- | --- | --- |
| dataChnId | Number | Data Channel ID |
| isAvailable | Bool | Is the device normal |
| name | String | Channel Name |
| channelType | Object | Data Channel Type |
| isHidden | Bool | Is the data channel hidden to end users? |
| isControllable | Bool | Is the data channel controllable by cloud commands |
| description | String | Data Channel Description |
| unitType | Object | Data Unit Type |
| format | String | Refer to confluence for content format |


**fw**

| Field Name | Type |Description|
| --- | --- | --- |
| fwId | String | Firmware ID |
| name | String | Frimware Name |
| description | String | Firmware Description |
| version | Number | Firmware Version |

**displayConfig**

| Field Name | Type |Description|
| --- | --- | --- |
| displayType | Number  | How to display |
| displayOrder | Number | The order of displaying the component |
| dataChnIds | Number Array | ID of data channel that is being configured to display on the console |

**tag**

| Field Name | Type | Description|
| --- | --- | --- |
| tagId | Number | Tag ID |
| name | String | Tag Name |



**Example: **

Request URL
```
https://api.mediatek.com/mcs/v2/devices/d1234567890

https://api.mediatek.com/mcs/v2/devices/d1234567890,d1234567891
```


Response Body

```
{
  "apiVersion": "0.0.1",
  "code": 200,
  "message": "Request has succeeded",
 "results": [
    {
      "deviceId": "DTRL0Knx",
      "deviceKey": "Xcwe9T82ehPSN6dv",
      "deviceName": "aa",
      "deviceDescription": "aaa",
      "trustIpRange": null,
      "lastIp": "127.0.0.1",
      "deviceImageURL": null,
      "isVerified": true,
      "isActive": true,
      "isTest": true,
      "activatedAt": "2015-03-02T18:43:17.587Z",
      "deactivatedAt": null,
      "privilege": "owner",
      "product": {
        "prodId": "PydFXsArwtru",
        "name": "11",
        "description": "",
        "displayConfigs": [
          {
            "format": {
              "lowerbound": "1",
              "upperbound": "5",
              "unitTypes": 20
            },
            "displayType": 14,
            "displayOrder": 1,
            "streamTypeId": 1,
            "dataChnIds": [
              "aa"
            ],
            "showHistory": false,
            "configs": {
              "format": {
                "lowerbound": "integer",
                "upperbound": "integer",
                "unitTypes": "category-units"
              }
            }
          },
          {
            "format": {
              "lowerbound": "1",
              "upperbound": "20",
              "unitTypes": 17
            },
            "displayType": 14,
            "displayOrder": 2,
            "streamTypeId": 1,
            "dataChnIds": [
              "11"
            ],
            "showHistory": false
          }
        ],
        "chip": "LinkIt One (MT2502)",
        "version": "111",
        "privilege": "owner"
      },
      "fw": {
        "fwId": "FvMNKIXNKbox",
        "name": "Default Firmware",
        "description": "Default Firmware",
        "version": "0.0"
      },
      "dataChannels": [
        {
          "dataChnId": "aa",
          "name": "aa",
          "description": "aa",
          "channelType": {
            "dataChnTypeId": 1,
            "name": "Integer"
          },
          "format": {
            "lowerbound": "1",
            "upperbound": "5",
            "unitTypes": 20
          },
          "isHidden": false,
          "isControllable": true,
          "unitType": {
            "unitTypeId": null,
            "name": null
          }
        },
        {
          "dataChnId": "11",
          "name": "11111",
          "description": "111",
          "channelType": {
            "dataChnTypeId": 1,
            "name": "Integer"
          },
          "format": {
            "lowerbound": "1",
            "upperbound": "20",
            "unitTypes": 17
          },
          "isHidden": false,
          "isControllable": true,
          "unitType": {
            "unitTypeId": null,
            "name": null
          }
        }
      ]
    }
  ]
}
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
  "results": {
    "code": 1002,
    "url": "http://mcs.mediatek.com/api_errorcode?code=1002",
    "description": "You do not have access right to this API"
  },
  statusCode: 401,
  options: { }
}
```
