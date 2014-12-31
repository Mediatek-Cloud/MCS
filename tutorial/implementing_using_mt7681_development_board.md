# Implementing using LinkIt Connect 7681 development board

This is a guide to setting up your LinkIt Connect 7681 development board to connect to MediaTek Cloud Sandbox (MCS).

## Scenario
The scenario for this setup is to enable your LinkIt Connect 7681 development board to connect to MCS and receive remote control commands from the MCS console.


## Setup requirement:

To complete this setup, you’ll need:

1. USB power source connect to the development board
2. A Wi-Fi connection made available to the development board
3. MCS mobile app. It’s currently available for Android. Please scan the following QR code to download the APK:

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/MT7681-tutorial/apkQrCode.png)

No additional components need to be connected to the development board.

## MT7681 controllers list and their corresponding MCS data channel IDs
The MT7681 chipset provides 5 GPIO pins that can implement PWM and 1 UART port. Below is a list of the pins and their corresponding data channel IDs to use on MCS.

|  | GPIO | PWM | UART |
| -- | -- | -- | -- |
| 00 | GPIO_00 | PWM_00 | UART |
| 01 | GPIO_01 | PWM_01 |
| 02 | GPIO_02 | PWM_02 |
| 03 | GPIO_03 | PWM_03 |
| 04 | GPIO_04 | PWM_04 |

## Step-by-step

### Step 1. Create a LinkIt Connect 7681 Product with GPIO, PWM and UART data channels

Step 1.1 Click **Development** on the left hand navigator.

Step 1.2 Click **Create**, on the right, to create a new product.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/CreateProduct.JPG)


Step 1.3 Enter the product name, product version, and select your industry. Select **MT7681** in the **Chip** dropdown box and click **Save**. Your Product is created.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/MT7681-tutorial/7681CreateProduct.jpg)


Step 1.4 Now you're going to add GPIO controllers to your product. Click **Detail** for the product you created.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/ProductDetail.JPG)


Step 1.5 Click **Add**.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/AddDataChannel.JPG)




Step 1.6 To add a controller, in the **Add Data Channel** page click **Add** under the **Controller** data channel.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/MT7681-tutorial/7681DataChannelType.jpg)


Step 1.7 For MT7681 products, the Data Channel Id are already defined, in this case you will use "GPIO_01". Enter the Data Channel name ("GPIO_01"), Id ("GPIO_01") and description then select **GPIO** as the Data type. Click **Save** to create the Data Channel.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/MT7681-tutorial/addGPIO.jpg)



Step 1.8 To add more GPIO pin controllers, repeat Step 1.5 to 1.7 and change the Data Channel Id to GPIO_0x where x is the integer between 0 and 4 corresponding to the pin number.

Step 1.9 Now add PWM controllers. Repeat Step 1.5 and 1.6 to open the **Add Data Channel** popup. Enter "PWM_01" as the Data Channel Id and select **PWM** in **Data Channel Type**. Click **Save** to create the Data Channel.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/MT7681-tutorial/addPWM.jpg)


Step 1.10 To add more PWM controllers, repeat Step 1.9 and change the Data Channel Id to PWM_0x where x ranges from 0 to 4 corresponding to the GPIO pin number.

Step 1.11 Another data channel type that MT7681 Products supports is UART. To add a UART data channel, open the **Add Data Channel** popup as described in Step 1.4 and 1.5 then enter "UART" as the Data Channel Id and select **String** or **Hex** in the **Data Channel type** depends on your needs. Click **Save** to create the Data Channel.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/MT7681-tutorial/addUART.jpg)


You have created all the controller Data Channel types that LinkIt Connect 7681 products support. Please continue to Step 2 to obtain your product Id and Key from MCS.

### Step 2. Obtain product Id and Key
Step 2.1 Click **Development** in the navigation bar on the left and click **Details** under the product you created for this tutorial.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/ProductDetail.JPG)


Step 2.2 You can see the Product Id and Product Key under the description of the product.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/MT7681-tutorial/obtainProductInfo.jpg)

Product ID and Product Key are essential for activating your MediaTek LinkIt Connect 7681 devices. Please proceed to Step 3 to flash the Product Id and Key to your device.


### Step 3. Flashing Product Id and Key to your device
Step 3.1 Connect your LinkIt Connect 7681 development board to a PC and open a terminal application (such as Terminal on Linux or Command Prompt on Windows). If you’ve not setup this terminal, please refer to the MediaTek LinkIt Connect 7681 Developer’s Guide for detailed set up steps. In the terminal console, enter the following command to flash the Product Id to your board:

```
AT#FLASH -s0x18133 -c[productId]
```
For example, if the product Id is ABCDEFG12345 then you should enter *AT#FLASH -s0x18101 -cABCDEFG12345*.

In response, you should see something like this on your terminal:
```
[WTask]45072
[0x18101]=ABCDEFG12345
[WTask]50073
```

Step 3.2 At the terminal, enter the following command to flash the Product Key to your board:
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
The flashing of Product Id and Key has completed. You must reboot the development board to make the new details effective:
```
AT#Reboot
```
Next you’ll see how to setup the Wi-Fi on 7681 with MediaTek Smart Connection.

### Step 4. Smart Connection
Step 4.1 Open the MCS mobile app, sign in with your account and select the product you created in step 1.. Please make sure that you’ve completed step 3.

Step 4.2 After signing in, tap the add icon (on the bottom right of the screen).

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/MT7681-tutorial/deviceList.png)

Step 4.3 Click **Smart Connection**, at the bottom of the screen.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/MT7681-tutorial/addDevice.png)

Step 4.4 Enter the SSID and password of the Wi-Fi AP and click **Start**. The SSID should be automatically populated with the Wi-Fi access points the smartphone is connected to.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/MT7681-tutorial/smartConnection.png)

Step 4.5 Wait for a few seconds, if Smart Connection was successfully, you should see your device on the list.

Tap **Cancel** to exit the add smart connection pop-up.

Now you can choose to register the device using the MCS mobile app (Step 5A) or to create a test device using the web console to complete the registration. (Step 5B).


### Step 5A. Activate a LinkIt Connect 7681 device from the MCS mobile app

Step 5A.1 Open the MCS mobile app and sign in. After signing in, tap the add icon (on the bottom right of the screen).

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/MT7681-tutorial/deviceList.png)


Step 5A.2 If your device has got the smart connection successfully, it should be shown on the list. Click on the add icon to the right of the device you'd like to register.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/MT7681-tutorial/addDevice2.png)

Step 5A.3 You can edit the Product ID, Serial Number and the Hardware ID in the pop-up window. In most cases you can just use the default value, and here, we are going to use the default value as well. The default value of Product ID should be what you already flashed into 7681 in step 3. Click "Save" to go to the next step.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/MT7681-tutorial/addDevice3.png)

Step 5A.4 Enter the device name and description and click "Save".

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/MT7681-tutorial/editDevice.png)


You will be brought back to the device list after the device has been activated. Your device should be now shown on the list.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/MT7681-tutorial/deviceList2.png)

### Step 5B. Create a test device on the web console
Step 5B.1 In the MCS web console, click the "Development" in the navigation bar on the left and then click the "Details" button under the product which you'd like to register.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/MT7681-tutorial/addTestDevice1.jpg)


Step 5B.2 Click "Create Test Device" button to the top right.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/MT7681-tutorial/addTestDevice2.jpg)

Step 5B.3 A pop-up will show after your test device has been successfully created. Click "OK" to exit the pop-up.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/MT7681-tutorial/addTestDevice3.jpg)

Step 5B.4 Go to "My Devices" by clicking on the navigation bar on the left and click on the "Details" button under the device which has just been created. It should have the same name as the product.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/MT7681-tutorial/addTestDevice4.jpg)

Step 5B.5 You should be able to find the deviceId and deviceKey of the test device you just created.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/MT7681-tutorial/addTestDevice5.jpg)


Step 5B.6 Now we have to manually flash the id and key into 7681. Open the terminal that is connected to 7681 board and enter the following command:

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

### Step 6 Control your devices

**From the MCS web platform**

Go to "My Devices" by clicking on the navigation bar on the left and click on the "Details" button under the device which has just been created and registered.
![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/MT7681-tutorial/addTestDevice4.jpg)

Now you can see the data channels and control their states using the MCS platform. Our control panel is straightforward for you to turn between different states by dragging the control bar.


![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/MT7681-tutorial/RemoteControlWeb.jpg)


**From Mobile App**

Open MCS mobile app and log in. Click on the device you'd like to control.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/MT7681-tutorial/apkControlDevice.png)


You will see a list of controllers which were added in the previous steps. Try switching the GPIO controller from high to low. The LED on 7681 development board should be turned on. **Please note that when GPIO is set to high, the LED is turned off; when the GPIO is set to low, the LED is turned on**.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/MT7681-tutorial/apiControlDevice2.png)
