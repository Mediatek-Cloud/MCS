# Implementing using MT7681 Development Board

This is a simple guide to setup your MT7681 development board to connect to MediaTek Cloud Sandbox.

##Scenario
The scenario for this setup is to allow your MT7681 development board to connect to MCS and be able to accept remote control command from MCS console.


##Setup requirement:

To complete this test setup, you will need:

1. Battery Pack to power up the micro-USB of the development board
2. A Wifi access point made available to the development board

There is no additional electrical component required to connect to the development board.


####Step 1. Create a 7681 Product with GPIO, PWM and UART data channels

Step 1.1 Click Development on the left hand side navigator.

Step 1.2 Click Create button on the right to create a new product.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/CreateProduct.JPG)


Step 1.3 Enter the Product name, Product version, and select your industry. Select 'MT7681' in the Chip dropdown box and click Save button. Now your Product is created.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/MT7681-tutorial/7681CreateProduct.jpg)


Step 1.4 Now we're going to add some controllers for your 7681 device. Click "Detail" button of the product we just created.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/ProductDetail.JPG)


Step 1.5 Click the "Add" button.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/AddDataChannel.JPG)



Step 1.6 Select "Controller" in Data Channel type by clicking the "Add" button in the Controller box.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/MT7681-tutorial/7681DataChannelType.jpg)


Step 1.7 Enter the Data Channel name, Id, description and select Data type. In the case of 7681, the Data Channel Id is predefined. Enter "GPIO_01" in the Data Channel Id field and select "GPIO" in the Data Channel Type. Click the "Save" button to create the Data Channel.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/MT7681-tutorial/addGPIO.jpg)


Step 1.8 To add more GPIO controllers, repeat Step 5 to 7 and change the Data Channel Id to GPIO_0x where x can be any integer between 1 and 5

Step 1.9 Now let's add some PWM controllers. Repeat Step 5 and 6 to open the Add Data Channel popup. Enter "PWM_01" in the Data Channel Id and select PWM in the Data Channel Type. Click the "Save" button to create the Data Channel.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/MT7681-tutorial/addPWM.jpg)


Step 1.10 The first PWM Data Channel has been created. To add more PWM controllers, repeat Step 9 and change the Data Channel Id to PWM_0x where x ranges from 1 to 5.

Step 1.11 The last data channel type that 7681 supports is UART. To add an UART data channel, open the Add Data Channel popup as described in Step 4 and 5 then enter "UART" in the Data Channel Id and select String or Hex in the Data Channel type depends on your needs. Click the "Save" button to create the Data Channel.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/MT7681-tutorial/addUART.jpg)


Congratulations! Now you have created all the Data Channel types that 7681 supports. Please continue to Step 2 to obtain your product info from MCS.

####Step 2. Obtain product info
Step 2.1 Click "Development" in the navigation bar to the left and click the "Details" button under the product you'd like to use.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/ProductDetail.JPG)


Step 2.2 You can obtain the Product Id and Product Key under the description of your product.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/MT7681-tutorial/obtainProductInfo.jpg)

Product ID and product key is essential for activating your 7681 devices. Please proceed to Step 3 to flash the product info on 7681.

####Step 3. Flashing product info on 7681
Step 3.1 Connect the 7681 development board to a PC and open the terminal. If you have not setup Please refernce to the MT7681 development guide for a detailed guide. In the terminal console, enter the following command to flash the product id on 7681:
```
AT#FLASH -s0x18133 -c[productId]
```
For example, the product Id is ABCDEFG12345 then you should enter AT#FLASH -s0x18101 -cABCDEFG12345

You should be able to see something like this on your terminal:
```
[WTask]45072
[0x18101]=ABCDEFG12345
[WTask]50073
```

Step 3.2 At the terminal, enter the following command to flash the product key on 7681:
```
AT#FLASH -s0x18143 -c[prodyctKey]
```
For example, the product key is HIJKLMN6789 then you should enter AT#FLASH -s0x18111 -cHIJKLMN6789

You should be able to see something like this on your terminal:
```
[WTask]250419
[0x18111]=HIJKLMN6789
[WTask]255420
```
The flashing of product info has completed. You must reboot 7681 to make the new product info effective:
```
AT#Reboot
```
Next we will show you how to setup the wifi on 7681 with smart connection.

####Step 4. Smart Connection
Step 4.1 Open the MCS mobile app and login with your account with an appropriate product for 7681. Please make sure that you have completed step 3.

Step 4.2 After logged in, click on the orange circle with a white plus sign on the bottom right corner.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/MT7681-tutorial/deviceList.png)

Step 4.3 Click the "Smart Connection" button at the bottom of the screen

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/MT7681-tutorial/addDevice.png)

Step 4.4 Enter the ssid and password of the wifi AP and click "Start". The ssid should be automatically filled with the wifi which the smart phone is connected to.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/MT7681-tutorial/smartConnection.png)

Step 4.5 Wait for a few seconds and check if there're any devices appear on the list. If smart connection is success, you should be able to see it on the list. Now you can choose to activate the device by MCS mobile app (Step 5A) or to create a test device via the web console (Step 5B).


####Step 5A. Activate an MT7681 device by MCS mobile app

Step 5A.1 Open the MCS mobile app and logged in. After logged in, click on the orange circle with a white plus sign on the bottom right corner

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/MT7681-tutorial/deviceList.png)


Step 5A.2 If your device has successfully got the smart connection, it should be shown on the list. Click on the plus sign to the right of the device you'd like to activate

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/MT7681-tutorial/addDevice2.png)

Step 5A.3 You can edit the Product ID, Serial Number and the Hardware ID in the pop-up window. In most cases you can just use the default value. The default value of Product ID should be the one you flashed on 7681. Click "Save" to go to the next step.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/MT7681-tutorial/addDevice3.png)

Step 5A.4 Enter the device name and description and click "Save".

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/MT7681-tutorial/editDevice.png)


You will be brought back to the device list after the device has been activated. Your device should be now shown on the list.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/MT7681-tutorial/deviceList2.png)

####Step 5B. Create a test device on the web console
Step 5B.1 In the MCS web console, click the "Development" in the navigation bar to the left and then click the "Details" button on the product which you'd like to activate

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/MT7681-tutorial/addTestDevice1.jpg)


Step 5B.2 Click "Create Test Device" button to the top right.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/MT7681-tutorial/addTestDevice2.jpg)

Step 5B.3 A pop-up will show after your test device has been successfully created. Click "OK" to dismiss the pop-up.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/MT7681-tutorial/addTestDevice3.jpg)

Step 5B.4 Go to "My Devices" by clicking on the navigation bar to the left and click on the "Details" button on the device which has just been created. It should have the same name as the product.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/MT7681-tutorial/addTestDevice4.jpg)

Step 5B.5 In the middle of the page you could find the deviceId and deviceKey of the created test device.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/MT7681-tutorial/addTestDevice5.jpg)

Step 5B.6 Now we have to manually flash the id & key on 7681. Open the terminal that is connected to 7681 and enter the following command:
```
AT#FLASH -s0x180e9 -c[deviceId]
```
Then enter the following command to flash the deviceKey:
```
AT#FLASH -s0x180f1 -c[deviceKey]
```
Then enter the following commands to set the status to be activated:
```
AT#FLASH -s0x18101 –v1
AT#FLASH -s0x18102 –v0
```
Your device should now automatically connected to MCS.

####Step 6 Control your devices

