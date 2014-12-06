# Key Concept

There are key components that make up a thing in MediaTek Cloud Sandbox. The key components are defined across two phases:

## Development Phase


At Development Phase, a developer is able to create a **Product**.
A **Product** is like a blueprint of your final device you would imagine the end user will end up using. Within the product you are able to define the following:

### Data Channel

The data channel a logical placeholder in the cloud for data generated either coming from a specific component of a physical device, or a command coming from the cloud intended to push into a specific component of the connected physical device. Simply put, data channel is designed for one-way or two-way communications between the cloud and the connected physical device.

We have further elaberate this one-way and two-way communications into three types of data channel that mimics for common use cases:

#### Data Channel Type


**Display**

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/datachannel_type_display.JPG)

Use this data channel when the data is only generated from a specific component of a connected physical device, such as a temperature sensor constantly generating temperature data and push into the cloud over time.


**Controller**

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/datachannel_type_controller.JPG)

Use this data channel type when the data flow is initiated from the cloud and transfer into the connected physical device example such as command sending to device.


**Hybrid**

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/datachannel_type_hybrid.JPG)

Use this data channel is a fast setup for one Display plus one Controller data channel in one setup. The templates under the Hybrid controller integrates both channel and make it a logical and common use cases.

[describe data types of channel - ON/OFF, Category, int, float, string, HEX, gps]

Data channel is established to place holding data.
There are 7 pre-defined data types:

####Data Type

**ON/OFF** - this data type support a status switch allows the user to activate or deactivate a device. eg, turn on or turn off light.

**Category** - this data type carries user defined category. eg, weekday and month.

**int** - this data type carries integer. eg, number.

**float** - this data type carries float. eg, temperature.

**string** - this data type carries strings. eg, message.

**HEX** - This data type carries hexadecimal value using character A-F and 0-9. It it useful for some electronical device development.

**GPS** - this data type carries the GPS location information inclusing longitude, latitude and elevation.


### Notification

In the developement stage, the developer can use notification to set alert for specific data channel data value. The developer can set a notification to remind the user when a data channel is sending back a value that is greater than or lower than a pre-defined specific value.

The notification can not only be used for sensor push back value which is out of our limitation but also when other privileged user is giving command to change the status of device. The developer can set the related subscriber and the owner to get the notification.

The current means of notification is email.


### Firmware

[explain firmware can be updated after the product is released]

After the product is released and got several connected and activated devices, whenever there is a new version of the firmware, the system will start to detect all competible devices and allow the user to update the firmware over the air.

### Manufacturing Info

[This is where you are able to further describe your product and will be visible at end user's "My Devices" page]

During the process of you development, you are able to create a Test Device from the current Product you are working on, which the system will create a Test Device that comes with defined **Device ID** and **Device Key** and is readiy visible in your **Management** workbench and **My Devices** Page.

### Product Release

After a final product is developed and be tested using the test devices, the developer can release the product for deployment which transfer the product from the development state to the release state. After release, the end user is able to create devices out of this released product in the **Management** workbench.


## Management Phase

After the release of the Product, you can create devices from the released product, considered as you have completed and tested you prototype phased into mass production of the product. The management phase is the management of the mass produced devices. Starting from creating each individual devices a placeholder for data interactions. The first step to so create a placeholder for each device for their initial "registration" step. The management of the devices from develper's perspective is under the Management workbench.

### Batch Create with Key




### Batch Create without Key
[describe how it works]

### Device Registration

[describe Devices can be registered and de-registered using the following two APIs:
regsiterDevices
deregisterDevices
]

## My Devices

[Describes My Devices Page, this is the end-user's page for devices they own or have right for access, within this page the end user can see the exact Data Channel configurations as defined in Product  last datapoints pushed for the Data Channel as well as historical chart for time-series based data. For Data Channel defined as GPS Data Channel the geolocation will be represented in a map, for]
