# retrieveProductApplicationType

### Description

Use **HTTP GET** to request for product application type category creation

### Request URL

```
http://api.mediatek.com/mcs/v2/productapplicationtypes?prodIndTypeId=1
```

### Action
HTTP GET

### Parameters

#### Header

Authorization:Bearer `TOKEN_HERE`

Content-Type:application/json

#### Body

There is no body


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
| prodAppTypeId | int | Id Product Application Type|
| name | String | name of the Application Type |



**Example: **

Request URL
```
http://api.mediatek.com/mcs/v2/productapplicationtypes?prodIndTypeId=1
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
        "prodAppTypeId": 1,
        "name": "Home Automation"
    },
    {
        "prodAppTypeId": 2,
        "name": "Smart Controller"
    }]
}
```

### Error Response

When error is incurred, the response code will be non-200 and the response body will construct in JSON format with the following fields:

| Field Name | Type |Description|
| --- | --- | --- |
| code | int | Error Code |
| url | string | url to API Error detail page |
| description | String | Error Description |

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




