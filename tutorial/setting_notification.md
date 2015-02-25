# Using Notification

The user can set the notification for a data channel when its value pass the limit of the defined range. The user will get email notification and the GCM notification using the mobile application. Please be noted that MCS currently only support notification for integer and float data channel type.


On the Prototype detail page, click on the **Notification** tab.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/notification/not01.JPG)

CLick on the **Add notification** to enter the notification name and select the data channel you would like to set alert for. The rules include greater than, lower then, and equal to.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/notification/not02.JPG)

Click Add button to save.

To have more than one data channel rules in a notification rule, all data channel rules need to be satisfied to trigger the notification(AND logic). The user can create separate notification rules to have the OR loigic.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/notification/not03.JPG)

The test device will inherit all the notification rules from its parent prototype. The notification in the device cannot be editted and it will by default in on state.

