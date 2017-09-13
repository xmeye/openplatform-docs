<label style="color:#000044;font-size:20px;"><b>Summary of common problems in FunSDK development</b></label>

<label style="color:#c30"><b> Q： What are APP certificates?</b></label><br>
A：Xiongmai APP certificates refer to the platform access certificates issued uniformly by the platform when applying for registration application in XM open platform. Including uuid/App Key/App Secret/moveCard four parts; UUID is the unique identifier of the customer, App Key is the unique identifier of App, Secret App and moveCard are used for content protection; APP certificate is the legal basis for visiting platform, so for the safety of the platform and the user, try not to leak or use by the third party. Our company reserves the right that abolishes the certificates which are used illegally.


<label style="color:#c30"><b> Q： Does the new version FunSDK only support registered users?</b></label><br>
A： The current version of FunSDK, in addition to the use of registered users, it still retains the local login function. You can directly log in device via device number/ device login name/ device login password; please refer to: Android integration ->2.2 Several frequently-used methods of device visiting; but the device alarm function must firstly register an account, this platform only provides the alarm function to the registered user;

<label style="color:#c30"><b> Q：  Why is it strongly recommended using the user system of this platform?</b></label><br>
A： Although the new version remains that directly log in device in the case of no user login, it is still recommended to register the user in this platform. Because some of the new features still need to be supported by users: server device alarm push, DSS forwarding, etc.;



<label style="color:#c30"><b> Q： Why does the device state query fail?</b></label><br>
A： Firstly confirm the mobile phone network connection is normal; secondly confirm whether it is properly initialized according to the device. If it is the local mode, directly query the device status via the serial number, ensure that FunSDK.SysInitLocal () has been executed. If it is the user mode, ensure that FunSDK.SysInitNet () has been executed, and ServerIP is available;




<label style="color:#c30"><b> Q： Users cannot login, user registration fails, and user interface cannot be used?</b></label><br>
A：Ensure thatFunSDK.XMCloudPlatformInit(uuid, AppKey, AppSecret, moveCard)has been called correctly, while confirming the correctness of the APP certificate;


<label style="color:#c30"><b>Q：  After the device is powered down, the device status in the device list is still in the online state, how to deal with it？</b></label><br>
A： After the device is powered down, if the device status updates for "offline" within three minutes, it is normal; if it still displays online status after more than three minutes,please confirm that APP has timely refresh the device status. If you have refreshed the device list/device status, it still displays an online state, please contact the salesman or customer service staff in time;

