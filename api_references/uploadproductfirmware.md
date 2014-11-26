# uploadProductFirmware

### Description

Use **HTTP POST** to request for Product Firmware upload

### Request URL

```
http://api.mediatek.com/mcs/v2/products/:product_id/firmware
```

### Action
HTTP POST

### Parameters

#### Header

Authorization:Bearer `TOKEN_HERE`

Content-Type:application/json

#### Body

The body will construct in JSON format with the following fields:

| Field Name | Mandatory | Type |Description|
| --- | --- | --- | --- |
| version | Yes | Float | version of the firmware |
| name | Yes | String | name of the firmware |
| description | Yes |String | description of the firmware |
| candidatefwId | No |String Array | candidate Firmware version for upgrade |
| defaultprodfw | Yes | Bool | set as default product firmware |
| url | Yes | String | URL for the location of firmware file uploaded |
| checksum | No | String | checksum for the file uploaded |


### Response

#### Response Code
200

#### Response Header

Content-Type:`application/json`
#### Response Body

***Data Format: JSON***

The response body will construct in JSON format with the following fields:

| Field Name | Mandatory | Type |Description|
| --- | --- | --- | --- | --- |
| fwId | Yes |String | FirewareId Created |



**Example: **

Request URL
```
http://api.mediatek.com/mcs/v2/products/12345678901/firmware
```

Request Header

```
Authorization:Bearer 32fff343frg45434

Content-Type:application/json
```

Request Body

```
{
  "version": "2.0",
  "name" : "Fireware 2.0 for SmartKattle",
  "description" : "Firmware 2.0 which fixes issue with connectivities ",
  "candidatefwId" : ["23412553223", "34523356423"],
  "defaultprodfw" : true,
  "url" : "https://cdn.mediatek.com/mcs/fw/998235333323/9332395283.xx",
  "checksum" : "332efew343feff"
}
```

Response Body

```
{
  "fwId" : "1234567890"
}

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





