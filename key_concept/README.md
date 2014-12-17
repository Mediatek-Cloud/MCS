# Key Concept

There are key components that make up a thing in MediaTek Cloud Sandbox. The key components are defined across two phases:

## Development Phase

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/product-structure.JPG)

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


####Data Type

Data channel is established to place holding data.
There are 7 pre-defined data types:

**ON/OFF** - this data type support a status switch allows the user to activate or deactivate a device. eg, turn on or turn off light.

**Category** - this data type carries user defined category. eg, weekday and month.

**int** - this data type carries integer. eg, number.

**float** - this data type carries float. eg, temperature.

**string** - this data type carries strings. eg, message.

**HEX** - This data type carries hexadecimal value using character A-F and 0-9. It it useful for some electronical device development.

**GPS** - this data type carries the GPS location information inclusing longitude, latitude and elevation.

**GPIO** - this data type supports MT7681 development to carry digital signal. eg, CPU signal.

**PWM** - this data type supports MT7681 development to carry digital signal. eg, pulsing signal.



### Notification

In the developement stage, the developer can use notification to set alert for specific data channel data value. The developer can set a notification to remind the user when a data channel is sending back a value that is greater than or lower than a pre-defined specific value.

The notification can not only be used for sensor push back value which is out of our limitation but also when other privileged user is giving command to change the status of device. The developer can set the related subscriber and the owner to get the notification.

The current means of notification is email.


### Firmware

After the product is released and got several connected and activated devices, whenever there is a new version of the firmware, the system will start to detect all competible devices and allow the user to update the firmware over the air.

### Manufacturing Info

This is where you are able to further describe your product and will be visible at end user's "My Devices" page.

### Create Test Device ###

During the process of you development, you are able to create a Test Device from the current Product you are working on, which the system will create a Test Device that comes with defined **Device ID** and **Device Key** and is readiy visible in your **Management** workbench and **My Devices** Page.

### Product Release

After a final product is developed and be tested using the test devices, the developer can release the product for deployment which transfer the product from the development state to the release state. After release, the end user is able to create devices out of this released product in the **Management** workbench.


## Management Phase

After the release of the Product, you can create devices from the released product, considered as you have completed and tested you prototype phased into mass production of the product. The management phase is the management of the mass produced devices. Starting from creating each individual devices a placeholder for data interactions. The first step to so create a placeholder for each device for their initial "registration" step. The management of the devices from develper's perspective is under the Management workbench.

### Batch Create with Key

The serial number is a unique key assigned to each device which will be accessible while the device registration. The device will need to this key to be able to registered. The unique key can be generated by uploading a CSV file which has one device serial number per line or by entering the serial numbers manually.



### Batch Create without Key

When each device does not need a unique key to be registered, you can then create the devices without key.



### Device Registration

After a device is created, it can be registered or de-registered in the management page. While a device is registered, it is ready to be used. The user can register or de-register the device using the registerDevices and deregisterDevices. You can find the API information in the API reference page.



## My Devices


The end user can use the **My Devices** to manage the devices they own or have the access. In this page, the end user can see the exact Data Channel configurations as defined in the product. Although the end user cannot change the Data Channel configuration, the end user can do other settings base on preference. The end user can view the time-series based data in a historical visualization chart and GPS geolocation data in a map.

Apart from viewing the data channel information, the user can set notification alet, set user privileges and get the firmware update directly here in My Devices page.

Also, the end user can get manufacturer information and report any error in My device page as well.

