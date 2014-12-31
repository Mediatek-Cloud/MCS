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
   "results":[
      {
         "deviceId":"d1234567890",
         "deviceKey":"1234567890d",
         "deviceName":"My 1st device",
         "deviceDescription":"Livingroom Smart Plug 1",
         "product":{
            "prodId":"a1234567890",
            "prodVersion":"1",
            "name":"MediaTek Smart Plug",
            "description":"Monitors Power Usag",
            "displayConfigs":[
               {
                  "displayType":2,
                  "displayOrder":1,
                  "dataChnIds":[
                     100004,
                     100006
                  ]
               },
               {
                  "displayType":1,
                  "displayOrder":2,
                  "dataChnIds":[
                     100009
                  ]
               }
            ],
            "chip":"MT7688"
         },
         "dataChannels":[
            {
               "dataChnId":10001,
               "isAvailable":true,
               "name":"My 1st Data Channel",
               "channelType":{
                  "dataChnTypeId":1,
                  "name":"float"
               },
               "isHidden":false,
               "isControllable":false,
               "description":"My first data channel on MCS 2.0",
               "unitType":{
                  "unitTypeId":2,
                  "name":"°C"
               },
               "format":{
                  "lowerbound":0.0,
                  "upperbound":100.0,
                  "interval":0.5,
                  "defaultValue":5.0
               },
               "comps":[
                  {
                     "compId":1,
                     "name":"MTK Camera"
                  },
                  {
                     "compId":2,
                     "name":"MTK Thermometer"
                  }
               ]
            },
            {
               "dataChnId":10002,
               "isAvailable":true,
               "name":"My 2nd Data Channel",
               "channelType":{
                  "dataChnTypeId":2,
                  "name":"swtich"
               },
               "isHidden":false,
               "isControllable":true,
               "description":"My second data channel on MCS 2.0",
               "format":{
                  "options":[
                     {
                        "name":"low",
                        "value":"1"
                     },
                     {
                        "name":"medium",
                        "value":"2"
                     },
                     {
                        "name":"high",
                        "value":"3"
                     }
                  ]
               }
            }
         ],
         "fw":{
            "fwId":"f1234567890",
            "name":"Appliance Firmware 2.0",
            "description":"",
            "version":0.5
         },
         "trustIpRange":[
            "*.*.*.*"
         ],
         "lastIp":"140.112.106.1",
         "deviceImageURL":"http://img.mediatek.com/img003.jpg",
         "isHeartbeating":true,
         "isVerified":true,
         "isActive":true,
         "isTest":false,
         "activatedAt":946684800,
         "deactivatedAt":0,
         "tags":[
            {
               "tagId":20,
               "name":"Smart Home"
            },
            {
               "tagId":59,
               "name":"Energy"
            }
         ],
         "deviceNtCritGrps":[
            {
               "ntfCritGrpId":1,
               "name":"Continuous Operating Time"
               "ntfMthTypeId":1,
               "ntfMthTypeName":"email"
            }
         ],
         "privilege":"Owner"
      },
      {
         "deviceId":"d1234567891",
         "deviceKey":"1987654321d",
         "name":"My 2nd device",
         "description":"Livningroom Smart Plug 2",
         "product":{
            "prodId":"a1234567890",
            "name":"MediaTek Smart Plug",
            "description":"Monitors Power Usage",
            "displayConfigs":[
               {
                  "displayType":2,
                  "displayOrder":1,
                  "dataChnIds":[
                     100004,
                     100006
                  ]
               },
               {
                  "displayType":1,
                  "displayOrder":2,
                  "dataChnIds":[
                     100009
                  ]
               }
            ],
            "chip":"MT7688"
         },
         "dataChannels":[
            {
               "dataChnId":10001,
               "isAvailable":true,
               "name":"My 1st Data Channel",
               "channelType":{
                  "dataChnTypeId":1,
                  "name":"float"
               },
               "isHidden":false,
               "isControllable":false,
               "description":"My first data channel on MCS 2.0",
               "unitType":{
                  "unitTypeId":2,
                  "name":"°C"
               },
               "format":{
                  "lowerbound":0.0,
                  "upperbound":100.0,
                  "interval":0.5,
                  "defaultValue":5.0
               },
               "comps":[
                  {
                     "compId":1,
                     "name":"MTK Camera"
                  },
                  {
                     "compId":2,
                     "name":"MTK Thermometer"
                  }
               ]
            },
            {
               "dataChnId":10002,
               "isAvailable":true,
               "name":"My 2nd Data Channel",
               "channelType":{
                  "dataChnTypeId":2,
                  "name":"swtich"
               },
               "isHidden":false,
               "isControllable":true,
               "description":"My second data channel on MCS 2.0",
               "format":{
                  "options":[
                     {
                        "name":"low",
                        "value":"1"
                     },
                     {
                        "name":"medium",
                        "value":"2"
                     },
                     {
                        "name":"high",
                        "value":"3"
                     }
                  ]
               }
            }
         ],
         "fw":{
            "fwId":"f1234567890",
            "name":"Appliance Firmware 2.0",
            "description":"",
            "version":0.3
         },
         "trustIpRange":[
            "*.*.*.*"
         ],
         "lastIp":"140.112.106.2",
         "deviceImageURL":"http://img.mediatek.com/img003.jpg",
         "isHeartbeating":false,
         "isVerified":true,
         "isActive":true,
         "isTest":false,
         "activatedAt":946684800,
         "deactivatedAt":0,
         "tags":[
            {
               "tagId":20,
               "name":"Smart Home"
            },
            {
               "tagId":59,
               "name":"Energy"
            }
         ],
         "privilege":"Viewer"
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
  "results": {
    "code": 1002,
    "url": "http://mcs.mediatek.com/api_errorcode?code=1002",
    "description": "You do not have access right to this API"
  }
}
```
