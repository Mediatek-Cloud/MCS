# Key Concept

There are key components that make up a thing in MediaTek Cloud Sandbox. The key components are defined across two phases:

## Development Phase


At Development Phase, a developer is able to create a **Product**.
A **Product** is like a blueprint of your final device you would imagine the end user will end up using. Within the product you are able to define the following:

### Data Channel

[describe channel mechansim]
[describe types of channel - Controller, display]
[describe data types of channel - ON/OFF, Category, int, float, string, HEX, gps]


### Notification

[explain how notification works]

### Firmware

[explain how firmware works]
[explain firmware can be updated after the product is released]

### Manufacturing Info

[This is where you are able to further describe your product and will be visible at end user's "My Devices" page]

During the process of you development, you are able to create a Test Device from the current Product you are working on, which the system will create a Test Device that comes with defined **Device ID** and **Device Key** and is readiy visible in your **Management** workbench and **My Devices** Page.

### Product Release

[Describe how the final product can be shift from development state to release state and upon release of the product, user is able to create devaices out of this released product in Mangement workbench]


## Management Phase

After the release of the Product, you are able to create devices at the **Management** workbench

### Batch Create with Key
[describe how it works]

### Batch Create without Key
[describe how it works]

### Device Registration

[describe Devices can be registered and de-registered using the following two APIs:
regsiterDevices
deregisterDevices
]

## My Devices

[Describes My Devices Page, this is the end-user's page for devices they own or have right for access, within this page the end user can see the exact Data Channel configurations as defined in Product  last datapoints pushed for the Data Channel as well as historical chart for time-series based data. For Data Channel defined as GPS Data Channel the geolocation will be represented in a map, for]
