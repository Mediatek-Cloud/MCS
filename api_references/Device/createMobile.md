# Create Mobile

Use **HTTPs POST** to create mobile device

### Request URL

```
https://api.mediatek.com/mcs/v2/mobiles/:deviceId/mobiles/:mobileId

```

### Action

HTTPs POST

### Parameters

:deviceId
:mobileId

#### Header

Authorization: Bearer '{token}'

#### Body

NULL

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
| created | boolean | create or update |
| status | boolean | enable or disable |


**Example:**

Request URL

```
https://api.mediatek.com/mcs/v2/devices/DYlPUvjQ/mobiles/MAPJMomc2w62
```

Request Body

NULL

Response Body

```
{
  apiVersion: '0.0.1',
  code: 200,
  message: 'Request has succeeded',
  created: true,
  status: true
}
```

### Error Response

token is incorrect:

```
{
  errors: [ { code: 4001, message: 'token is incorrect' } ],
  statusCode: 401,
  options: {}
}
```

403 forbidden:

```
{ errors: [ { code: 403, message: '403 Forbidden' } ],
  statusCode: 403,
  options: {} }
```
