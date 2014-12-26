# Implementing using MT7681 Development Board

This is a simple guide to setup your MT7681 development board to connect to MediaTek Cloud Sandbox.

##Scenario
The scenario for this setup is to allow your MT7681 development board to connect to MCS and be able to accept remote control command from MCS console.


##Setup requirement:

To complete this test setup, you will need:

1. Battery Pack to power up the micro-USB of the development board
2. A Wifi access point made available to the development board

There is no additional electrical component required to connect to the development board.


####Step 1. Create Product with Switch data channel

Step 1.1 Click Development on the left hand side navigator.

Step 2. Click Create button on the right to create a new product.


![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/CreateProduct.JPG)



Step 3. Enter the Product name, version, and select '7681' in the chip type dropdown box, industry and Click Create button. Your Product is created.


![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/CreateProductPage.JPG)


Step 4. Click Detail button of the product just created.


![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/ProductDetail.JPG)


Step 5. Click Add in the product just created.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/AddDataChannel.JPG)



Step 6. Select the Data Channel type. eg, Controller, Display, or Hybrid. And Click Add button.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/DataChannel.JPG)


Step 7. Enter the Data Channel name, Id, description and select Data type.


Step 8. Click Save button. And now you can start create your test device for the product!


![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/AddDataChannelPage.JPG)



For more Data Channel and Data Type information and concept, please refer to the Key concept section for more detail.


####Step 2. Create Test Device
[steps to be filled in]

####Step 3. Obtain Device ID, Device Key, Data Channel ID
[steps to be filled in]

####Step 4. Code the development board
[steps to be filled in]

####Step 5. Turn on the board and see it in action!
[steps to be filled in]

Full C source code:

```
[to be filled in here]
