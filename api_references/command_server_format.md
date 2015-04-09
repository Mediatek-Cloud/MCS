# Command server format
The command server format of each data type is defined here. It is the format that the command server sent to the device to process.

**The timestamp is using the UNIX timestamp format.

The device will get the data as the following format from the command server, and the user can write a parser in the device to parse the data needed.

Here is an example of how to parse and extract the datachannelId, value, and period of a PWM.

https://gist.github.com/iamblue/29705021bd77c9be6004


## Prerequsite
Before the device can get the command from command server, you need to first connect the device to MCS.

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


## Command formats for each data channel type


### Switch

```
deviceId,deviceKey,timestamp,dataChannelId,{0 or 1}

```
0 stands for OFF, and 1 stands for ON.

For example:

switch01,, 1

To turn the switch01 to on state, and do not give the timestamp.

### Category
```
deviceId,deviceKey,timestamp,dataChannelId,{Key Value}
```
The Key value will correspond to the Key name that you’ve set.

### Integer
```
deviceId,deviceKey,timestamp,dataChannelId,{Integer}
```

### Float
```
deviceId,deviceKey,timestamp,dataChannelId,{Float}
```

### Hex
```
deviceId,deviceKey,timestamp,dataChannelId,{Hex value}
```
Hex is referred to hexadecimal value which only takes value from A-D and 0-9.

### String
```
deviceId,deviceKey,timestamp,dataChannelId,{string}
```

### GPS
```
deviceId,deviceKey,timestamp,dataChannelId,{latitude},{longitude},{altitude}
```

The range of latitude is from -90 to 90. 0 to 90 stands for North and 0 to -90 stands for South.

The range of longitude is from -180 to 180. 0 to 180 stands for East and 0 to -180 stands for West.

The range of altitude is from 0 to 20000 in meter.

### GPIO
```
deviceId,deviceKey,timestamp,dataChannelId,{0 ot 1}
```
0 stands for Low, and 1 stands for High.

### PWM
```
deviceId,deviceKey,timestamp,dataChannelId,{value},{period}

```
