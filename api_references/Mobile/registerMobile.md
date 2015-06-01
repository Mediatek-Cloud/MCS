# Register Mobile

Use **HTTPs POST** to register mobile device

### Request URL

```
https://api.mediatek.com/mcs/v2/mobiles

```

### Action

HTTPs POST

### Parameters

#### Header

Authorization: Bearer '{token}'

#### Body

json example:

```
{
  name: 'Mediatek',
  regToken: 'xxxxx',
  mobileTypeId: "1",
  appKey: 'xxxxx',
  info: {
    os: 'android',
    name: 'android'
  }
}
```

> * `name`: device name
> * `regToken`: device register ID.
> * `mobileTypeId`: 1: Android, 2: iOS, 3: Windows
> * `appKey`: GCM Server key
> * `info`: Anything you want to save. Must be json object format


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
| mobileId | string | mobile unique id |


**Example:**

Request URL

```
https://api.mediatek.com/mcs/v2/mobiles
```

Request Body

```
{
  name: 'Mediatek',
  regToken: 'xxxxx',
  mobileTypeId: "1",
  appKey: 'xxxxx',
  info: {
    os: 'android',
    name: 'android'
  }
}
```

Response Body

```
{
  apiVersion: '0.0.1',
  code: 200,
  message: 'Request has succeeded',
  created: true,
  mobileId: 'M7Dxuj9T2Wkz'
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
  errors:
   [ { [ValidationError: Missing required property: regToken]
       message: 'Missing required property: regToken',
       params: 'regToken',
       code: 302,
       subErrors: null },
     { [ValidationError: Missing required property: appKey]
       message: 'Missing required property: appKey',
       params: 'appKey',
       code: 302,
       subErrors: null } ],
  missing: [],
  valid: false,
  statusCode: 400,
  options: {}
}
```
