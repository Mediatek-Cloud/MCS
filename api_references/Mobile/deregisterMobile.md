# deregister Mobile

Use **HTTPs DELETE** to deregister mobile device

### Request URL

```
https://api.mediatek.com/mcs/v2/mobiles/:mobileId
```

### Action

HTTPs DELETE

### Parameters

`:deviceId`: Device unique ID.

#### Header

Authorization: Bearer '{token}'

#### Body

json example:

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
https://api.mediatek.com/mcs/v2/mobiles/MTG2FTZyG6Ap
```

Request Body

NULL

Response Body

```
{
  apiVersion: '0.0.1',
  code: 200,
  message: 'Request has succeeded',
  affectedRows: 1
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

missing mobile required property:

```
{
  errors: [ { code: 400, message: '400 Bad Request' } ],
  message: 'missing required property ids',
  statusCode: 400,
  options: {}
}
```