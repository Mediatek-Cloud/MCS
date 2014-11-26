# uploadImage

### Description

Use **HTTPs POST** to upload images

### Request URL

```
https://api.mediatek.com/mcs/v2/images?type=:type_name

```

### Action
HTTPs POST

### Parameters

#### Header

Authorization: Bearer '{token}'

### Query String
| Field Name | Type |Description|
| --- | --- | --- |
| type_name | String | Image Type ( Only allows: product, avatar, device ) |

#### Body

The request body should be structured in form-data with the following fields:

| Field Name | Type |Description|
| --- | --- | --- |
| File | Bytes | Image File Content |




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
| name | String | Hashed file name on the server |


**Example: **

Request URL
```
https://api.mediatek.com/mcs/v2/images?type=product
```

Request Body

```
----WebKitFormBoundaryE19zNvXGzXaLvS5C
Content-Disposition: form-data; name="image"; filename="photo.jpg"
Content-Type: image/jpeg


```

Response Body

```
{
    "name":"product/ajfie86zvj10f.jpg"
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




