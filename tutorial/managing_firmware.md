# Managing Firmware

MediaTek Clous Sandbox(MCS) enables the user to manage the firmware and provides firmware Over-The-Air (FOTA) update to the device.

To use the Firmware service, go to the **Firmware tab** in the Prototype detail page. You can see there is a Default Firmware indicating your current firmware and you can set it as other uploaded firmwares' prerequisite to be upraded.

Click **Add firmware** to first upload a new firmware,

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/firmware/fw01.jpg)

Enter the Firmware name, version, and select a firmware file to upload and click the Upload button.

Next, select the compatible firmware of the fimrware you just uploaded.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/firmware/fw02.jpg)

Choose the prerequisite firmware that are compatible for this firmware you've uploaded.

The default option is all firmware selected or you can specify your own selection by click on the limited firmware. Only the firmware listed in the prerequisite list can be upgraded using the firmware you've uploaded.

If you do not want to further proceed to directly pushing the firmware upgrade to test devices, you can stop here by clikc on the Done button, or to click on the Next button to push the firmware to devices.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/firmware/fw03.jpg)

After selecting the devices you would like to upgrade, click the Push botton. You can also do this step by click on the first icon next to the firmware.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/firmware/fw04.JPG)

The user can also upgrade the firmware of a device in the Device detail page. In the Device detail page, click on the frimware tab, and you will see the current using firmware and the firmware that the device can be upgraded to.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/firmware/fw05.JPG)

Click on the **Upgrade** button next to the firmware that you want the device to be upgraded.


