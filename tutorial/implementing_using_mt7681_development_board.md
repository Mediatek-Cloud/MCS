# Implementing using LinkIt Connect 7681 development board

This is a guide to setting up your LinkIt Connect 7681 development board to connect to MediaTek Cloud Sandbox (MCS).

## Scenario
The scenario for this setup is to enable your LinkIt Connect 7681 development board to connect to MCS and receive remote control commands from the MCS console or mobile app.


## Setup requirements

To complete this setup tutorial, you’ll need:

1. USB power source connected to the development board
2. A Wi-Fi connection available to the development board
3. MCS mobile app. It’s currently available for Android. Please scan the QR code below to download the APK:

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

Step 1.1 On the left hand navigator, click **Development**.

Step 1.2 In the **Prototype List**, click **Create**, to create a new prototype.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/screenshot/screen_shot-01.jpg)


Step 1.3 Enter the prototype name, prototype version, and select your industry. In the **Chip** dropdown box select **MT7681** and click **Save**. Your Prototype is created.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/screenshot/screen_shot-22.jpg)


Step 1.4 Now you're going to add GPIO controllers to your prototype. Below the listing of the prototype you created, click **Detail** .

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/screenshot/screen_shot-23.jpg)


Step 1.5 In **Data channel**, click **Add**.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/screenshot/screen_shot-03.jpg)




Step 1.6 To add a controller, in the **Add Data Channel** popup under the **Controller** data channel, click **Add**.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/screenshot/screen_shot-13.jpg)


Step 1.7 For MT7681 products, the Data Channel Ids follow a defined format — GPIO_nn, where nn is the pin number starting from 00. Create the channel for the first pin, using "GPIO_00". Enter the data channel name ("GPIO_00"), Id ("GPIO_00") and add a description, then select **GPIO** as the data type. Click **Save** to create the Data Channel.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/screenshot/screen_shot-24.jpg)



Step 1.8 To add more GPIO pin controllers, repeat Step 1.5 to 1.7 using the appropriate data channel Id for each pin (GPIO_01 to GPIO_04).

Step 1.9 Now add the PWM controllers. Repeat Step 1.5 and 1.6 to open the **Add Data Channel** popup. Enter "PWM_00" as the data channel Id and in **Data Channel Type** select **PWM**. Click **Save** to create the Data Channel.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/screenshot/screen_shot-25.jpg)


Step 1.10 To add more PWM controllers, repeat Step 1.9 using the appropriate data channel Id for each pin (PMW_01 to PMW_04).

Step 1.11 Another data channel type that MT7681 Products support is UART. To add a UART data channel, open the **Add Data Channel** popup as described in Step 1.4 and 1.5 and create a new Controller as described in step 1.6. Enter the Data Channel Id as "UART" and in the **Data Channel type** select **String** or **Hex** depending on your needs. Click **Save** to create the Data Channel.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/screenshot/screen_shot-26.jpg)


You’ve created all the controller Data Channel types that LinkIt Connect 7681 products support. Please continue to Step 2 to obtain your prototype Id and Key from MCS.


### Step 2. Connect your development board to Wi-Fi
Step 2.1 Open the MCS mobile app, sign in with your account and select the prototype you created in step 1.. Please make sure that you’ve completed step 3.

Step 2.2 After signing in, on the bottom right of the screen tap the add icon.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/MT7681-tutorial/deviceList.png)

Step 2.3 At the bottom of the screen, click **Smart Connection**. This provides an implementation of MediaTek Smart Connection, for more details see the MediaTek LinkIt Connect 7681 Developer’s Guide.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/MT7681-tutorial/addDevice.png)

Step 2.4 Enter the SSID and password of the Wi-Fi AP and click **Start**. The SSID should be automatically populated with the Wi-Fi access points the smartphone is connected to.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/MT7681-tutorial/smartConnection.png)

Step 2.5 Wait for a few seconds, if Smart Connection was successfully, you should see your device on the list.

Tap **Cancel** to exit the add Smart Connection pop-up.

Now you can choose to register the device using the MCS mobile app (Step 3A) or to create a test device using the web console to complete registration. (Step 3B).


### Step 3A. Activate a LinkIt Connect 7681 device from the MCS mobile app

Step 3A.1 Open the MCS mobile app and sign in. After signing in, on the bottom right of the screen, tap the add icon.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/MT7681-tutorial/deviceList.png)


Step 3A.2 If your device’s Wi-Fi settings were provisioned by Smart Connection successfully, it should be shown on the list. To the right of the device you'd like to register, tap the add icon.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/MT7681-tutorial/addDevice2.png)

Step 3A.3 A list of prototypes will be shown on the screen. Tap on the prototype you'd like to create to mark it and tap **Save** to go to the next step.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/MT7681-tutorial/addDevice3.png)

Step 3A.4 Enter the device name and description and tap **Save**.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/MT7681-tutorial/editDevice.png)


After the device has activated, the device list is redisplayed. Your device should now be on the list.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/4.png)

### Step 3B. Create a test device using the web console
Step 3B.1 In the MCS web console, in the navigation bar on the left, click **Development** and then under the prototype (the one you created in Step 1) that you'd like to register a device for click **Details**.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/screenshot/screen_shot-02.jpg)


Step 3B.2 To the top right of the page, click **Create Test Device**.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/screenshot/screen_shot-27.jpg)

Step 3B.3 A pop-up will display after your test device has been successfully created. Click **No Thanks** to exit the pop-up.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/screenshot/screen_shot-18.jpg)

Step 3B.4 On the navigation bar click **My Devices** then under the device that has just been created click **Details**. The device should have the same name as the prototype.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/screenshot/screen_shot-29.jpg)

Step 3B.5 You should be able to find the deviceId and deviceKey of the test device you just created.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/screenshot/screen_shot-28.jpg)


Step 3B.6 Now you have to manually flash the id and key into MT7681. Open a terminal that is connected to the development board and enter the following command:

```
AT#FLASH -s0x180e9 -c[deviceId]
```
Then enter the following command to flash the deviceKey:
```
AT#FLASH -s0x180f1 -c[deviceKey]
```
Then enter the following commands to set the status to activated:
```
AT#FLASH -s0x18101 –v1
AT#FLASH -s0x18102 –v0
```
Your device should now be automatically connected to MCS.

### Step 6A Control your device from the mobile app

Step 6A1 Open the MCS mobile app and sign in. Tap on the device you'd like to control.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/4.png)


Step6A.2 You’ll see a list of controllers that were added in step 1. Switch a GPIO controller from high to low: the LED on development board should turn on. **Please note that when GPIO is set to high, the LED is turned off; when the GPIO is set to low, the LED is turned on**.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/3.png)

### Step 6B Control your device from the MCS web console

Step BB.1 On the navigation bar click **My Devices**, then below the device that has just been created and registered click **Details**.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/screenshot/screen_shot-29.jpg)

Step 6B.2 Now you can see the device’s data channels and control their states using the MCS platform. To change the state for a particular data channel, drag that channel’s control bar. Switch a GPIO controller from high to low: the LED on development board should turn on. **Please note that when GPIO is set to high, the LED is turned off; when the GPIO is set to low, the LED is turned on**.


![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/screenshot/screen_shot-30.jpg)


