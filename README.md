# MediaTek Cloud Sandbox API

* * *

MediaTek Cloud Sandbox is an external Cloud Services to support LinkIt ONE development IoT devices to:
- Push DataPoints from device to Cloud - eg. geo-location, temperature, humidity, switch-state...etc.
- Pull DataPoints from Cloud to device - eg. simple switching, remote control..etc.
- Manage for device and sensor profiles
- Quick view on the DataPoint value over time chart for trends

MediaTek Cloud Sandbox exposes its services as RESTful API. LinkIt ONE and other devices capable of making RESTful API call can interact with MediaTek Cloud Sandbox

MediaTek Cloud Sandbox defines Product, Device, Sensor and DataPoint Model, all models created under the ownership of a single user (as a representation to a unique apiKey). Take a weather staion device as an example, the model hierarchy can be designed as below:

![](https://raw.githubusercontent.com/Mediatek-Cloud/api-reference/master/graphics/data-hirachy.JPG)

The sequence of creating a weather station device is to:

1. Define a **PRODUCT** namely "Weather Station Model 01".
2. Once the PROUDCT is created, we can create **DEVICE** within this specific PRODUCT, the relationship between PRODUCT and DEVICE is one to many.
3. Once a DEVICE is created, we can create **SENSOR** within this specific DEVICE, the relationship between DEVICE and SENSOR is one to many.
4. For this specific example, we create four SENSORS with this device, SENSOR is the placeholder for **DATAPOINTS** which represents the actual data we wish to store or retrieve.

The actions interacting to each model:

| Object| API| Management Console
| --- | --- |
| PRODUCT| Currently not supported | Create / Delete / Edit / List / View |
| DEVICE | Delete / Edit / View |  Create / Delete / Edit / List / View |
| SENSOR | Create / Delete / Edit / List / View | Create / Delete / Edit / List / View |
| DATAPOINT | Create / Delete / Edit / List / History View | Create / List / History View |

### Prerequisites for Use

1. Users must be a MediaTek Development Network registered user.
2. A registered and logged in user can have access to MediaTek Cloud Sandbox management console to obtain apikey for RESTful API call.
