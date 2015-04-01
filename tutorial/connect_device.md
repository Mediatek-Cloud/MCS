# Connect device

Connect the development board to Wi-Fi first, and then download the MCS mobile app and log in as an authorized user to access the device. Use the smart connection function build in to the mobile app to connect to the device and register the device to be active.

To connect the device:
1.	Make sure Wireless Access Point is made available to the device and the device is connected
2.	Then enter the following commands to set the status to activated:
AT#FLASH –s0x18101 –v1
AT#FLAST –s0x18102 –v0
Download the Mobile app and use the smart connection to get the connected device, and you are able to get the data from and control the device.
