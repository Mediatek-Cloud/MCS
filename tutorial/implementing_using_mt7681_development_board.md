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

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/7681CreateProduct.jpg)


Step 1.4 Now we're going to add some controllers. Click "Detail" button of the product we just created.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/ProductDetail.JPG)


Step 1.5 Click the "Add" button.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/AddDataChannel.JPG)



Step 1.6 Select "Controller" in Data Channel type by clicking the "Add" button in the Controller box.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/7681DataChannelType.jpg)


Step 1.7 Enter the Data Channel name, Id, description and select Data type. In the case of 7681, the Data Channel Id is predefined. Enter "GPIO_01" in the Data Channel Id field and select "ON/OFF" in the Data Channel Type. Click the "Save" button to create the Data Channel.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/addGPIO.jpg)


Step 1.8 To add more GPIO controllers, repeat Step 5 to 7 and change the Data Channel Id to GPIO_0x where x can be any integer between 1 and 5

Step 1.9 Now let's add some PWM controllers. Repeat Step 5 and 6 to open the Add Data Channel popup. Enter "PWM_01" in the Data Channel Id and select PWM in the Data Channel Type. Click the "Save" button to create the Data Channel.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/addPWM.jpg)


Step 1.10 The first PWM Data Channel has been created. To add more PWM controllers, repeat Step 9 and change the Data Channel Id to PWM_0x where x ranges from 1 to 5.

Step 1.11 The last data channel type that 7681 supports is UART. To add an UART data channel, open the Add Data Channel popup as described in Step 4 and 5 then enter "UART" in the Data Channel Id and select String or Hex in the Data Channel type depends on your needs. Click the "Save" button to create the Data Channel.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/addUART.jpg)


Congratulations! Now you have created all the Data Channels that 7681 supports. Please continue to Step 2 to obtain your product info from MCS.

####Step 2. Obtain product info
Step 2.1 Click "Development" in the navigation bar to the left and click the "Details" button under the product you'd like to use.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/ProductDetail.JPG)


Step 2.2 You can obtain the Product Id and Product Key under the description of your product.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/obtainProductInfo.jpg)

Product ID and product key is essential for activating your 7681 devices. Please proceed to Step 3 

####Step 3. Obtain Device ID, Device Key, Data Channel ID
[steps to be filled in]

####Step 4. Code the development board
[steps to be filled in]

####Step 5. Turn on the board and see it in action!
[steps to be filled in]

Full C source code:

```
[to be filled in here]
