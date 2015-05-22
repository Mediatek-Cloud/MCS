# Update product device criterion

Use **HTTPs PUT** to update product device criterion

### Request URL

```
https://api.mediatek.com/mcs/v2/devices/:deviceId/product/criterions/:criterionId

```

### Action

HTTPs PUT

### Parameters

`:deviceId`: Device unique ID.
`:criterionId`: Criterion unique ID.

#### Header

Authorization: Bearer `{token}`

#### Body

```
{
  "isActivated": true,
  "ntfcrits":[{
    "ntfCritId": 1,
    "streamId": 2,
    "thresholdValue": 1234
  }, {
    "ntfCritId": 2,
    "streamId": 2,
    "thresholdValue": 5678
  }]
}
```

### Response

```
{
  apiVersion: '0.0.1',
  code: 200,
  message: 'Request has succeeded'
}
```

#### Response Code

200

#### Response Header

Content-Type:`application/json`

#### Response Body

***Data Format: JSON***

**Example:**

Request URL

```
https://api.mediatek.com/mcs/v2/devices/DwW0TyjI/product/criterions/1727
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

device not found:

```
{ errors: [ { code: 404, message: '404 Not Found' } ],
  message: 'device not found',
  statusCode: 404,
  options: {} }
```

Missing required property: thresholdValue

```
{ errors:
   [ { [ValidationError: Missing required property: thresholdValue]
       message: 'Missing required property: thresholdValue',
       params: 'ntfcrits/0',
       code: 302,
       subErrors: null } ],
  missing: [],
  valid: false,
  statusCode: 400,
  options: {} }
```
