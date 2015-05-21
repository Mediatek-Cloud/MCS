# Create Mobile

Use **HTTPs DELETE** to create mobile device

### Request URL

```
https://api.mediatek.com/mcs/v2/mobiles/:deviceId/mobiles/:mobileId

```

### Action

HTTPs DELETE

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
  message: 'Request has succeeded'
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

input request is invaild:

```
{ errors: [ { code: 400, message: '400 Bad Request' } ],
  message: 'missing required property ids',
  statusCode: 400,
  options: {} }
```