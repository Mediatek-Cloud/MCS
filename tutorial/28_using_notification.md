# Setting User Privilege


MediaTek Cloud Sandbox(MCS) allows the user to configure the access level for different prototypes and test devices. The user can find this setting in the **User Privivlege** tab in the Prototype detail or the Device detail pages.


MCS provides three roles:

1. The **owner**, with the access to add, update, read, and delete a prototype or a test device.
2. The **administrator**, with the accesss right to add, update, and read a prototype or a test device.
2. The **viewer**, with only the access right to view a prototype or a test device.


As a prototype or device owner, or an administrator, you can add other registed MCS user to access the prototype or the test device by click on the privilege tab in the Prototype or Device detail pages.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/UP/up01.png)


Click Add user to add other MCS registered user to access the prototype.

![](https://raw.githubusercontent.com/Mediatek-Cloud/MCS/master/graphics/UP/up02.png)

Enter the user email and select the rols as administrator or viewer, and click Save button.



Please be noted that the test device will not inherit the user privilege setting from its parent prototype. The test device will take the users with the owner and administrator access to have the owner access to the test device. The owner can then modified the user privilege of the test device separately from the parent prototype.
