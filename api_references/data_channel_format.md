# Data channel format

The API format of each data type is defined here. It is the format that the device report data to the command server.


**The timestamp is using the UNIX timestamp format, and it is not a required field. You can leave it blank, and the system will give the timestamp automatically as the server recorded time.

MCS supports both json and csv formats.

## Switch

For json:
```
 "datapoints":[
      {
         "dataChnId":"dataChanId",
         "values":{
            "value":"{0 or 1}"
         }
      }
   ]
}

```


For csv:
```
dataChannelId,timestamp,{0 or 1}

```
0 stands for OFF, and 1 stands for ON.

For example:

switch01,, 1

To turn the switch01 to on state, and do not give the timestamp.

## Category

For json:
```
 "datapoints":[
      {
         "dataChnId":"dataChanId",
         "values":{
            "value":"{Key value}"
         }
      }
   ]
}

```


For csv:
```
dataChannelId,timestamp,{Key Value}
```
The Key value will correspond to the Key name that you’ve set.

## Integer

For json:
```
 "datapoints":[
      {
         "dataChnId":"dataChanId",
         "values":{
            "value":"{Integer value}"
         }
      }
   ]
}

```


For csv:
```
dataChannelId,timestamp,{Integer}
```

## Float

For json:
```
 "datapoints":[
      {
         "dataChnId":"dataChanId",
         "values":{
            "value":"{Float value}"
         }
      }
   ]
}

```


For csv:
```
dataChannelId,timestamp,{Float}
```

## Hex

For json:
```
 "datapoints":[
      {
         "dataChnId":"dataChanId",
         "values":{
            "value":"{HEX value}"
         }
      }
   ]
}

```


For csv:
```
dataChannelId,timestamp,{Hex value}
```
Hex is referred to hexadecimal value which only takes value from A-D and 0-9.

## String

For json:
```
 "datapoints":[
      {
         "dataChnId":"dataChanId",
         "values":{
            "value":"{string value}"
         }
      }
   ]
}

```


For csv:
```
dataChannelId,timestamp,{string}
```

## GPS
For json:
```
 "datapoints":[
       {
         "dataChnId":"dataChnId",
         "values":{
            "latitude":"{latitude value}",
            "longitude":"{longitude value}",
            "altitude":"{altitude value}"
         }
      }
   ]
}

```


For csv:

```
dataChannelId,timestamp,{latitude},{longitude},{altitude}
```

The range of latitude is from -90 to 90. 0 to 90 stands for North and 0 to -90 stands for South.

The range of longitude is from -180 to 180. 0 to 180 stands for East and 0 to -180 stands for West.

The range of altitude is from 0 to 20000 in meter.

## GPIO

For json:
```
 "datapoints":[
      {
         "dataChnId":"dataChanId",
         "values":{
            "value":"{0 or 1}"
         }
      }
   ]
}

```


For csv:
```
dataChannelId,timestamp,{0 ot 1}
```
0 stands for Low, and 1 stands for High.

## PWM
For json:
```
 "datapoints":[
      {
         "dataChnId":"dataChanId",
         "values":{
            "value":"{value}",
            "period":"{period value}"
         }
      }
   ]
}

```


For csv:
```
dataChannelId,timestamp,{Value},{Period}
```
