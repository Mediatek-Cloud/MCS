# Retrieve device criterion

Use **HTTPs GET** to retrieve device criterion

### Request URL

```
https://api.mediatek.com/mcs/v2/devices/:deviceId/criterions

```

### Action

HTTPs GET

### Parameters

:deviceId

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

*** Data Format: JSON ***

**Example:**

Request URL

```
https://api.mediatek.com/mcs/v2/devices/DkjNRTKG/criterions
```

Request Body

NULL

Response Body

```
{
  apiVersion: '0.0.1',
  code: 200,
  message: 'Request has succeeded',
  deviceNtfCritGrps:
   [ { ntfCritGrpId: 1726,
       prodId: 'PAGw6rxY1f8X',
       name: 'Vickie Dooley',
       isProdActivated: true,
       isDeviceActivated: null,
       ntfcrits: [Object],
       ntfmths: [Object] } ]
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

device not found:

```
{ errors: [ { code: 404, message: '404 Not Found' } ],
  message: 'device not found',
  statusCode: 404,
  options: {} }
```