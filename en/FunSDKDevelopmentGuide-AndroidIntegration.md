
<div name="zhunbei" id="zhunbei" style="font-size:20px;line-height:60px;"><b>1.Integration preparation</b></div>
<div style="margin-left:40px;">Android minimum version requirements: 4.0.3

</div>
<div name="zhunbei1" id="zhunbei1" style="margin-left:20px;font-size:15;line-height:60px;">
<b>1.1Get certificates (uuid/AppKey/AppSecret/moveCard)</b>
</div>
<div style="margin-left:40px;">
   Find your application in “Console”, and view uuid, AppKey, AppSecret and moveCard these four values. If you haven't created an application, please see "<a href="http://open.xmeye.net/resource.do?cid=ec799b013aec4a589357b644630fd4d2&rid=69896d3a5962401dbd5db30988e67a56#undefined">“Developers Must Read”- > “Newbie guide”.</a>"。
</div>
<div name="zhunbei2" id="zhunbei2" style="margin-left:20px;font-size:15px;line-height:60px;"><b>1.2 Download SDK</b></div>
<div style="margin-left:40px;">SDK and Demo are in <a href="https://open.xmeye.net/resource.do?cid=b2a64dde3b254ca3a2aab6b39e7222ad&rid=355ed2dde82a43939e71e6277e51543e">“Download Center - > FunSDK Download, </a>please select the corresponding platform to download.


</div>
<div name="zhunbei3" id="zhunbei3" style="margin-left:20px;font-size:15px;line-height:60px;"><b>1.3 Import SDK</b></div>
<div name="zhunbei31" id="zhunbei31" style="margin-left:40px;font-size:15px;line-height:60px;"><b>1.3.1 SDK document description</b></div>
<div style="margin-left:80px;">  
libs/LibFunSDK.jar
libs/Core.jar<br/>
libs/dewarp.jar<br/>
libs/armeabi/libFunSDK.so<br/>
libs/armeabi/libh264tomp4.so<br/>
libs/armeabi/libvrsoft.so<br/>
libs/armeabi/libfisheye.so<br/>
</div>
<div name="zhunbei32" id="zhunbei32" style="margin-left:40px;font-size:15px;line-height:60px;"> <b>1.3.2 Use Eclipse (ADT) to import SDK
</b> </div>
<div style="margin-left:80px;font-size:15px;">
 Put LibFunSDK.jar under libs directory；<br/>
Put all so files under libs/armeabi directory;<br/>
</div>
<label style="margin-left:100px;">
<img src="http://open.xmeye.net/upload/image/20160516/1463375322540086037.png">
</label>
<div name="zhunbei33" id="zhunbei33" style="margin-left:40px;font-size:15px;line-height:60px;"> <b>1.3.3 Use Android Studio to import SDK
</b> </div>
<div style="margin-left:80px;font-size:15px;">
 Put LibFunSDK.jar under libs directory;<br/>
   Put all so files under src/main/jniLib/armeabi directory; 
<br/>
</div>
<label style="margin-left:100px;">
<img src="http://open.xmeye.net/upload/image/20160516/1463375420439072097.png">
</label>
<div style="margin-left:80px;font-size:15px;">
 And write the correct LibFunSDK.jar dependencies in the build.gradle file of the project<br/>
<br/>
</div>
<label style="margin-left:100px;">
<img src="http://open.xmeye.net/upload/image/20160516/1463375425418033557.png">
</label>
<div name="zhunbei4" id="zhunbei4" style="margin-left:20px;font-size:15px;line-height:60px;"><b>1.4  Configure manifest and APP certificates

</b></div>
<div name="zhunbei41" id="zhunbei41" style="margin-left:40px;font-size:15px;line-height:60px;"><b>1.4.1 Manifest permissions description</b></div>
<div style="margin-left:100px;">  
(omit)
</div>
<div name="zhunbei42" id="zhunbei42" style="margin-left:40px;font-size:15px;line-height:60px;"> <b>1.4.2 Fill in the APP certificates (uuid/AppKey/AppSecret/moveCard) </b> </div>
<div style="margin-left:80px;font-size:15px;">
The Complete APP certificates include uuid/AppKey/AppSecret/moveCard four parts. After the initialization of FunSDK, set the APP certificates for the development platform, for example:
<div style="margin-left:30px;">
&#160&#160&#160&#160&#160&#160&#160&#160&#160&#160&#160uuid ：<label style="background-color:#fc6">e0534f3240274897821a126be19b6d46</label><br/>
&#160&#160&#160&#160App Key ：<label style="background-color:#fc6">0621ef206a1d4cafbe0c5545c3882ea8</label><br/>
App Secret ：<label style="background-color:#fc6">90f8bc17be2a425db6068c749dee4f5d</label><br/>
  &#160moveCard ：<label style="background-color:#fc6">2</label><br/>
</div>
(Temporarily not support to configure in manifest, code calls incoming will prevail）
</div>
<lable style="margin-left:100px;">
<img src="http://open.xmeye.net/upload/image/20160516/1463375970123072470.png">
</lable>


<div name="jicheng" id="jicheng" style="font-size:20px;line-height:60px;"><b>2. Basic function integration
</b></div>
<div name="jicheng1" id="jicheng1" style="margin-left:20px;font-size:15px;line-height:60px;"><b>2.1 FunSDK initialization   </b></div>
<div style="margin-left:70px;">
The initialization of FunSDK could be executed in onCreate() of Application, through the following steps:<br/>
 a> Library initialization 1:: FunSDK.Init();<br/>
 b> Library initialization 2: FunSDK.MyInitNetSDK();<br/>
 c> Set App temporary file storage path:FunSDK.SetFunStrAttr(EFUN_ATTR.APP_PATH, ...);<br/>
 d> Select to use Internet or direct connection device to visit: FunSDK.SysInitNet() or FunSDK.SysInitAsAPModle();
 e>Set APP certificates: FunSDK.XMCloudPlatformInit(...)<br/>
 
</div>
<br/>
<div style="margin-left:70px;">
The initialization process can refer to the interface realization in FunSDKDemo for Android.
</div>
<label style="margin-left:100px;">
<img src="http://open.xmeye.net/upload/image/20160516/1463375480321031106.png">
</label>
<div name="jicheng2" id="jicheng2" style="margin-left:20px;font-size:15px;line-height:60px;"><b>2.2 Several frequently-used methods of device visiting</b></div>
<div>&#160&#160&#160&#160&#160&#160&#160&#160&#160&#160&#160&#160&#160&#160&#160&#160&#160&#160&#160&#160At present, FunSDK needs to call different SysInit initialization interface in different usage scenarios and in different ways to visit device. In addition, the interface of device visit and other device operation is completely unified, and can switch to each other in using process. When you use, you can refer to the usage of FunSupport.setLoginType() in Demo, the specific instructions as follows:</div>
<div name="jicheng21" id="jicheng21" style="margin-left:40px;font-size:15px;line-height:60px;"><b>2.2.1 AP mode: direct connect to device by AP</b></div>
<div style="margin-left:80px;">
 Need to call: FunSDK.SysInitAsAPModle()；<br/>
 Model Description: open AP hotspot in the device. Mobile phone connects to the device's AP hotspot, so as to achieve the interaction purpose of the mobile client and the device;<br/>
Examples: Demo reference “2.Device correlation” - > “2.2 Connect to device (Nearby AP direct connection)”
</div>
<div name="jicheng22" id="jicheng22" style="margin-left:40px;font-size:15px;line-height:60px;"><b>2.2.2 Local mode: visit by device serial number</b></div>
<div style="margin-left:80px;">
 Need to call:FunSDK.SysInitLocal()；<br/>
Model Description: input device serial number or IP+PORT to directly visit device; it can visit remote device and can also visit the device in same LAN (use IP+PORT as serial number); no need to register an account, the device list can be managed locally;<br/>
Examples: Demo reference “2.Device correlation” -> “2.2 Connect to device (connect by serial number)”
</div>
<div name="jicheng23" id="jicheng23" style="margin-left:40px;font-size:15px;line-height:60px;"><b>2.2.3 User mode: Internet mode (recommended)</b></div>
<div style="margin-left:80px;">
 Need to call:FunSDK.SysInitNet()；
Model Description: need to register an account firstly, and then add device under the user; users use different phones, only need to log in an account, and can get to the device list;
Examples: Demo reference “2.Device correlation” -> “2.6 Connect to device (connect by serial number)”
</div>
<div name="jicheng3" id="jicheng3" style="margin-left:20px;font-size:15px;line-height:60px;"><b>2.3 Preparation of functional interface before use</b></div>
<div style="margin-left:40px;">&#160&#160&#160&#160&#160&#160&#160&#160Use the asynchronous message way to return the result to the caller thread interface, interface descriptions are as follows:</div>
<div style="margin-left:40px;">&#160&#160&#160&#160&#160&#160&#160&#160 Functional interface user calls SDK.RegUser (this) method, complete the message receiver's registration, realize the interface “OnFunSDKResult (MSG Message, ex XMSG)”,
 and complete the processing of the message receiving functions. Remove the registration use “SDK.UnRegUser ()”. After registration, the message recipient is assigned to a unique recipient ID (an int value). When using the corresponding functional interface, this value, which is used as the result recipient identifier, is transferred to the interface.
</div>
<br/>
<br/>
<div style="margin-left:40px;color:red;background-color:yellow">
<b>Action: interface descriptions/ hUser described in Development Guide, refers to the operation handle returned by SDK.RegUser (). </b>
</div>
<div name="jicheng4" id="jicheng4" style="margin-left:20px;font-size:15px;line-height:60px;"><b>2.4 Device login </b></div>
<div style="margin-left:40px;">Before visiting the device (operate) interface (Internet connection and direct connection device are the same), firstly need to login device, the interface is as 
follows:<br>
int DevLogin(int hUser, String szDevId, String loginName, String loginPasswd, int seq);
</div>
<br/>
<div style="margin-left:40px;"> When exiting device visiting, need to call device logout interface:<br/>
int DevLogout(int hUser, String szDevId, int nSeq);
</div>
<br/>
<div style="margin-left:40px;">  Interface description can refer to the “FunSDK interface description” - > “device functional method” relevant instructions.<br/>
In Demo example, refer to the call of following two functions:
</div>
<label style="margin-left:100px;">
<img src="http://open.xmeye.net/upload/image/20160516/1463375561625045214.png">
</label>
<div name="jicheng5" id="jicheng5" style="margin-left:20px;font-size:15px;line-height:60px;"><b>2.5  Device status query  </b></div> 
<div style="margin-left:25px;">When get the device list (both the local mode and the user mode), need to query the status of the device (online/offline), the interface is as follows:<br/>
int  SysGetDevState(int hUser, String devIds, int nSeq);<br/>
Parameter description: devIds supports that multiple serial numbers can query at the same time, different serial numbers can be separated by “;”. <br/>
Instructions for use: only need to know the device serial number can query and get the device status, do not need to call the login device (DevLogin ()).
</div>
<br/>
<div name="jicheng6" id="jicheng6" style="margin-left:20px;font-size:15px;line-height:60px;"><b>2.6 Device video play</b></div> 
<div style="margin-left:25px;">
Several frequently-used functions of device video playing are:<br/>
<div style="margin-left:25px;">
a> Video play stop:
<div style="margin-left:25px;">
int MediaRealPlay(int hUser, String devId, int  nChnIndex, int  nStreamType, Object hWnd, int  nSeq)；
</div>
b> Device play real-time video:
<div style="margin-left:25px;">
int MediaStop(int hPlayer, int  nSeq = 0);
</div>
</div>
 Brief description:
<div style="margin-left:25px;">
1. MediaRealPlay()return a player handle hPlayer, that is the first parameter “hPlayer” passed from MediaStop<br/>
2. MediaRealPlay()The second parameter devId in MediaRealPlay(). If directly connect to device by AP mode, then devId upload device IP address + port; if connect by Internet mode,then upload the device MAC.<br/>
3. Other interfaces can refer to the description of FunSDK interface;   <br/>
</div>
<br>
Encapsulate a FunVideoView in Demo that is similar to VideoView. It can be used in a standard form of Android controls, but set the play address interface FunVideoView.setVideoPath () is slightly different from the standard VideoView interface, the address format needs to meet the description in instruction 2.
</div>
<div name="jicheng7" id="jicheng7" style="margin-left:20px;font-size:15px;line-height:60px;"><b>2.7 Device alarm</b></div>
<div name="jicheng71" id="jicheng71" style="margin-left:40px;font-size:15px;line-height:60px;"><b>2.7.1 Alarm push switch</b></div>
<div style="margin-left:80px;">
Alarm push switch refers to whether the device alarm message is sent to the alarm server;
</div>
<div name="jicheng72" id="jicheng72" style="margin-left:40px;font-size:15px;line-height:60px;"><b>2.7.2  Alarm notification switch</b></div>
<div style="margin-left:80px;">
 Alarm notification switch refers to whether the alarm notification needs to be displayed on a mobile phone Notification. Different from the “alarm push switch”, as long as the alarm push switch is turned on, even if the alarm switch is closed, the alarm message will be sent to the server, and user can still view in the history alarm information. However, the mobile phone Notification will not be notified in real time;
</div>
<div name="jicheng73" id="jicheng73" style="margin-left:40px;font-size:15px;line-height:60px;"><b>2.7.3 History alarm information</b></div>

<div name="gengduo" id="gengduo" style="font-size:20px;line-height:60px;"><b>3. More functions  
</b></div>
<div style="margin-left:40px;"> (Please refer to API description for more functions)</div>

<div name="guanyu" id="guanyu" style="font-size:20px;line-height:60px;"><b>4. About com.lib.funsdk.support</b></div>
<div>
&#160&#160&#160&#160&#160&#160&#160&#160&#160&#160Com.lib.funsdk.support is not a part of the FunSDK, but is a provided reference code that in order to facilitate the transplantation and understanding of the FunSDK interface calls and be more suitable for the development habits of Android/Java. Open source, it is free to use under the authorization of our company; it can be developed on this basis, if there are changes, please synchronize to us.  <br/>
</div>
<div style="margin-left:40px;">
The existing purpose of com.lib.funsdk.support is to transplant FunSDK more simple.
</div>
<div name="guanyu1" id="guanyu1" style="margin-left:20px;font-size:15px;line-height:60px;"><b>4.1 FunSupport</b></div>
<div>
&#160&#160&#160&#160&#160&#160&#160&#160&#160&#160FunSupport encapsulates most of the FunSDK interface and achieve IFunSDKResult.OnFunSDKResult().Most of the results processing can refer to the code here; in FunSupport, after processing IFunSDKResult.OnFunSDKResult(), it will callback in the corresponding way. When you use, you can firstly register Listener, there are several major kinds:
</div>
<div style="margin-left:40px;">
1. OnFunLoginListener<br/>
&#160&#160&#160&#160User login / logout results monitoring<br/>
2. OnFunDeviceListener<br/>
&#160&#160&#160&#160Device list changes, device status updates monitoring<br/>
3. OnFunDeviceOptListener<br/>
&#160&#160&#160&#160Device login, get / set up device configuration information monitoring;<br/>
4. OnFunDeviceFileListener<br/>
&#160&#160&#160&#160 Device file download monitoring;<br/>
5. Others   <br/>
</div>
<div>
 &#160&#160&#160&#160&#160&#160&#160&#160&#160&#160<lable style="color:red">Note:</lable>： It is completely possible if do not use FunSupport, you can refer to the FunSDK interface description; it is also a direct calling FunSDK interface in FunSupport; regardless of whether or not to use the code in the FunSupport, please read carefully the FunSDK interface description.    
</div>
<div name="guanyu2" id="guanyu2" style="margin-left:20px;font-size:15px;line-height:60px;"><b>4.2 FunVideoView</b></div>
<div style="margin-left:60px;">
FunSupport encapsulates part of the media function method (FunSDK.Media*). It can be seen from the class name that it is expected to provide video play functions as a standard control mode (similar to VideoView);  <br/>
It can be directly used in the layout file (layout.xml) (Reference./res/layout/activity_device_camera.xml):

</div>
<label style="margin-left:100px;">
<img src="http://open.xmeye.net/upload/image/20160516/1463375583707004130.png">
</label>
<div style="margin-left:60px;">
Several special interface instructions<br/>
1.FunVideoView.setRealDevice(String devSn); <br/>
&#160&#160&#160&#160Set the device serial number that need to play video. If the connection is AP mode, then it is the format of IP:PORT;<br/>
2.FunVideoView.setStreamType(FunStreamType streamType);<br/>
&#160&#160&#160&#160 Set the stream type, main /sub stream (if the device does not support, setup is invalid);<br/>
</div>

