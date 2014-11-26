# retrieveDeviceInfo

### Description

Use **HTTPs GET** to retrieve devices

### Request URL

```
https://api.mediatek.com/mcs/v2/devices/:device_id

```

### Action
HTTPs GET

### Parameters

#### Header

Authorization: Bearer '{token}'


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
| deviceId | String | Device ID |
| deviceKey | String | Device Key |
| product | Object | Product Info |
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
| tags | String Array | Tags of the device |
| privilege | String | User's privilege on the device |

**Detailed Object Fields**

**product**

| Field Name | Type |Description|
| --- | --- | --- |
| prodId | String | Product ID |
| name | String | Product Name |
| description | String | Product Description |
| displayConfigs | Object Array | A JSON format object indicatig how each data channel will be displayed |
| chip | String | Product Chip |

**fw**

| Field Name | Type |Description|
| --- | --- | --- |
| fwId | String | Firmware ID |
| name | String | Frimware Name |
| description | String | Firmware Description |

**displayConfig**

| Field Name | Type |Description|
| --- | --- | --- |
| displayType | Number  | How to display |
| displayOrder | Number | The order of displaying the component |
| dataChnIds | Number Array | ID of data channel that is being configured to display on the console |


**Example: **

Request URL
```
https://api.mediatek.com/mcs/v2/devices/d1234567890

https://api.mediatek.com/mcs/v2/devices/d1234567890,d1234567891
```


Response Body

```
{
   "devices":[
      {
         "deviceId":"d1234567890",
         "deviceKey":"1234567890d",
         "product":{
            "prodId":"a1234567890",
            "name":"MediaTek Smart Plug",
            "description":"Monitors Power Usage in kitchen",
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
         "fw":{
            "fwId":"f1234567890",
            "name":"Appliance Firmware 2.0",
            "description":""
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
            "Test",
            "Mediatek"
         ],
         "privilege":"Owner"
      },
      {
         "deviceId":"d1234567891",
         "deviceKey":"1987654321d",
         "product":{
            "prodId":"a1234567890",
            "name":"MediaTek Smart Plug",
            "description":"Monitors Power Usage in kitchen",
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
         "fw":{
            "fwId":"f1234567890",
            "name":"Appliance Firmware 2.0",
            "description":""
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
            "MCS"
         ],
         "privilege":"Viewer"
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





