# deleteProductDataChannel


### Description

Use **HTTPs DELETE** to request to remove data channels from a product

### Request URL

```
https://api.mediatek.com/mcs/v2/products/:product_id/datachannels/:datachannel_id
```

### Action
HTTPs DELETE

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
| prodId | Int | Product ID |
| dataChannelId | Int | Data Channel ID |


**Example:**

Request URL
```
https://api.mediatek.com/mcs/v2/products/a1234567890/datachannels/10001
```


Response Body

```
{
    "prodId":"a1234567890",
    "dataChnId":10001
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

