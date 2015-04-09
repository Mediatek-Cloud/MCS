# Connect device


To connect the device:

Call the RESTful API: GET https://api.mediatek.com/mcs/v2/devices/{deviceId}/connections to obtain the response value for Socket Server IP and Port.
Command server respond format:

```
{
    "ip": "ServerIp",
    "port": "serverPort"
}

```
Open a tcp connection to the given ip and port and send a heartbeat message.

Heartbeat format:

```
    deviceId, deviceKey, timestamp

```
After the TCP long connecion is built, the user can give command to the device via the MSC platform.

The command Format:
```
    deviceId, deviceKey, timestamp, dataChnId, commandValue

```

You can refer to the command server format in the API reference page to find more detail for the formats for each kind of data channel types.
