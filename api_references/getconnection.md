# getConnection


## Description

Use **HTTPs GET** to  set up connections between device and command server.


## Request URL

To set up connections between device and command server:

```
https://api.mediatek.com/mcs/v2/devices/:deviceId/connections

```

To set up TCP long connection between the device and the command server, the device will need to first send a REST API `getConnection` to request a set of ip and port to build a TCP connection. The MCS will respond with its IP address and a port to the device.

Command server respond format:

```
{
    "ip": "ServerIp",
    "port": "serverPort"
}

```

Once get the server ip and port to connect, the device need to send a heartbeat to the command server to be identified. The device also need to sent heartbeats to the server every 120 seconds to stay connected, or the server will disconnect the device.

Heartbeat format:

```
    deviceId, deviceKey, timestamp

```

After the TCP long connecion is built, the user can give command to the device via the MSC platform.

The command Format:
```
{
    deviceId, deviceKey, timestamp, dataChnId, commandValue
}

```

## Action
HTTPs GET


## Parameters
### Header


Content-Type:`application/json` or `text/csv`


deviceKey: `device_key_here`


### Return format
The return format can be in either JSON or CSV format

JSON:

when the request for resource ends with *connections*


CSV:

when the reqeust for resouce ends with *connections.csv*


## Response

### Response Code
200

### Response Header
For JSON response:
```
Content-Type:`application/json`
```
For CSV response:
```
Content-Type: `text/csvt`
```

### Response Body

***Data Format: JSON***

The response body will construct in JSON format with the following fields:

| Field Name | Type | Description|
| --- | --- | --- | --- |
| ip | array | the command server ip |
|port|Integer|the command server port for the device to connect|


**Example:**

Request URL
```
https://api.mediatek.com/mcs/v2/devices/a1234567890/connections
```

Response Body

```
{
   "ip": xxx.xxx.xxx.xxx,
   "port":443

}
```


## Error Response

When error is incurred, the response code will be non-200 and the response body will construct in JSON format with the following fields:

| Field Name | Type |Description|
| --- | --- | --- |
| code | Integer | Error Code |
| description | String | Error Description |

**Example:**

```
{
  "results": {
    "code": 1002,
    "description": "You dont have permission"
  }
}
```
