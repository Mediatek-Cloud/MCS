# Key Concept

There are key components that make up a thing in MediaTek Cloud Sandbox. The key components are defined across two phases:

## Development Phase


At Development Phase, a developer is able to create a **Product**.
A **Product** is like a blueprint of your final device you would imagine the end user will end up using. Within the product you are able to define the following:

### Data Channel

[describe channel mechansim]

The data chennel is where the data is transfer between the sensor and the cloud and the cloud and the mobile.

[describe types of channel - Controller, display]

There are three types of data channel:

**Controller** - Use this data channel type when the data is transfer from the management console or the remote control mobile to the sensor.

**Display** - Use this data channel when the data is only transfer from the sensor to the cloud.

**Hybrid** - Use this data channel when you need both display and control mechanisms which allows two way data transaction.

[describe data types of channel - ON/OFF, Category, int, float, string, HEX, gps]

There are 7 type of data types of channel:

**ON/OFF** - this data type support a status switch allows the user to activate or deactivate a device. eg, turn on or turn off light.

**Category** - this data type carries user defined category. eg, weekday and month.

**int** - this data type carries integer. eg, number.

**float** - this data type carries float. eg, temperature.

**string** - this data type carries strings. eg, message.

**HEX** - This data type carries hexadecimal value using character A-F and 0-9. It it useful for some electronical device development.

**GPS** - this data type carries the GPS location information inclusing longitude and latitude.


### Notification

[explain how notification works]

In the developement stage, the developer can use notification to set alert for specific data channel. The developer can set a notification to remind the user when a data channel is sending back a value that is greater than or lower than a pre-defined specific value.


The notification can not only be used for sensor push bcak value which is out of our limitation but also when other privileged user is giving command to change the status of device. The developer can set the related subscriber and the owner to get the notification.



### Firmware

[explain how firmware works]

[explain firmware can be updated after the product is released]

After the product is released and got several connected and activated devices, whenever there is a new version of the firmware, the system will start to detect all competible devices and allow the user to update the firmware over the air.

### Manufacturing Info

[This is where you are able to further describe your product and will be visible at end user's "My Devices" page]

During the process of you development, you are able to create a Test Device from the current Product you are working on, which the system will create a Test Device that comes with defined **Device ID** and **Device Key** and is readiy visible in your **Management** workbench and **My Devices** Page.

### Product Release

After a product is developed and tested, the developer can release the product for deployment.

## Management Phase

After the release of the Product, you are able to create devices at the **Management** workbench

### Batch Create with Key
[describe how it works]

### Batch Create without Key
[describe how it works]

What you can see in ### Management
 workbench




Product

with in the Product the developer can define the following:

Data Channel

Data Channel Mechanism








Management Phase

Product

Data Channel












Devices

