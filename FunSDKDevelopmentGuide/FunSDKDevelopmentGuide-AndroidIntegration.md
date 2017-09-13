## 集成准备

Android最低版本要求：4.0.3

### 获得(uuid/AppKey/AppSecret/moveCard)

在"控制台"中找到您的应用，可以查看uuid、AppKey、AppSecret和moveCard四个值。如果您还未创建应用，请查看"<a href="http://open.xmeye.net/resource.do?cid=ec799b013aec4a589357b644630fd4d2&rid=69896d3a5962401dbd5db30988e67a56#undefined">[开发者必读]"->"新手指南</a>"。

### 下载SDK

SDK及Demo 在 <a href="https://open.xmeye.net/resource.do?cid=b2a64dde3b254ca3a2aab6b39e7222ad&rid=355ed2dde82a43939e71e6277e51543e">[下载中心]->[FunSDK下载] </a>中，请选择对应的平台进行下载。

### 导入SDK

#### 1 SDK文件说明

libs/LibFunSDK.jar
libs/Core.jar
libs/dewarp.jar
libs/armeabi/libFunSDK.so
libs/armeabi/libh264tomp4.so
libs/armeabi/libvrsoft.so
libs/armeabi/libfisheye.so

#### 2 使用Eclipse (ADT) 导入SDK

将LibFunSDK.jar,Core.jar,dewarp.jar放在libs目录下；
将所有的.so文件放在libs/armeabi目录下；

<img src="http://open.xmeye.net/upload/image/20160516/1463375322540086037.png">

#### 3 使用Android Studio导入SDK

将LibFunSDK.jar,Core.jar,dewarp.jar放在libs目录下；
将所有的.so文件放在src/main/jniLib/armeabi目录下；

<img src="http://open.xmeye.net/upload/image/20160516/1463375420439072097.png">

并在项目的 build.gradle 文件中写入对的LibFunSDK.jar依赖

<img src="http://open.xmeye.net/upload/image/20160516/1463375425418033557.png">

### 配置manifest和APP证书

#### 1 manifest权限说明

(暂略)

#### 2 填写APP证书(uuid/AppKey/AppSecret/moveCard)

```mr
完整的APP证书包括uuid/AppKey/AppSecret/moveCard四个部分，在FunSDK初始化之后，设置开发平台的APP证书
例如：
uuid ：e0534f3240274897821a126be19b6d46
App Key ：0621ef206a1d4cafbe0c5545c3882ea8
App Secret ：90f8bc17be2a425db6068c749dee4f5d
moveCard ：2
(暂不支持在manifest里面配置，以代码调用传入的为准）
```
<img src="http://open.xmeye.net/upload/image/20160516/1463375970123072470.png">

## 基本功能集成

### FunSDK初始化

FunSDK的初始化，建议在Application的onCreate()中执行，通过以下几个步骤进行：
```mr
 a> 库初始化1: FunSDK.Init();
 b> 库初始化2: FunSDK.MyInitNetSDK();
 c> 设置App临时文件存储路径 :FunSDK.SetFunStrAttr(EFUN_ATTR.APP_PATH, ...);
 d> 选择是互联网使用还是直连设备方式访问: FunSDK.SysInitNet()或者FunSDK.SysInitAsAPModle();
 e> 设置APP证书：FunSDK.XMCloudPlatformInit(...)；
```

初始化过程可参考FunSDKDemo for Android中的FunSupport.init()接口实现：

<img src="http://open.xmeye.net/upload/image/20160516/1463375480321031106.png">

### 几种常用的设备访问方式

目前，FunSDK在不同的使用场景下，以不同的方式访问设备时，需要调用不同的SysInit初始化接口，除此之外，设备访问及其他设备操作接口完全统一，并且在使用过程中可以相互切换；在使用中可以参考Demo里面FunSupport.setLoginType()的使用，具体说明如下

#### 1 AP模式：以AP直连设备

需要调用：FunSDK.SysInitAsAPModle()；
模式说明：故名思议，就是设备中的AP热点打开，手机连接到设备的AP热点，这样达到近距离移动客户端与设备交互的目的；
参考例子：Demo参考"2.设备相关"->"2.2 连接设备(附近AP直连)"

#### 2 本地模式：通过设备序列号访问

需要调用：FunSDK.SysInitLocal()；
模式说明：输入设备序列号或者IP+PORT，直接访问设备；可以访问远程的设备，也可以访问同一局域网内的设备（以IP+PORT作为序列号）；不需要注册用户，设备列表可以在本地管理；
参考例子：Demo参考"2.设备相关"->"2.1 连接设备(通过序列号连接)"

#### 3 用户模式：互联网方式(推荐)

需要调用：FunSDK.SysInitNet()；
模式说明：需要先注册用户，然后在用户下添加设备；用户使用不同的手机，只需要登录同一个账号，就可以获取到自己的设备列表；
参考例子：Demo参考"2.设备相关"->"2.6 连接设备(通过序列号连接)"

### 功能接口使用前准备

异步消息的方式返回结果到调用者界面线程，接口说明如下：
功能接口使用者调用SDK.RegUser(this)方法,参数this即为希望接收回调的类，接口回调进入该类的OnFunSDKResult(Message msg, XMSG ex)中，完成消息接收者的注册，该类需要实现接口 "OnFunSDKResult(Message msg, XMSG ex)"，完成消息接收函数的处理。移除注册使用 “SDK.UnRegUser()”。注册后，消息接收者会被分配到一个唯一的接收者ID（一个int 值），使用相应的功能接口时，此值做为结果接收者标识传到接口中（一般是第一个参数）。

做完以上准备工作，既可以直接以FunSDK.ABC（）的方式调用接口ABC了

<div style="color:red;background-color:yellow">
<b>Action：接口说明/开发指南中描述的hUser，就是指SDK.RegUser()返回的操作句柄。</b>
</div>

### 设备登录

在访问设备（操作）接口之前（互联网连接和直连设备都一样），要先登录设备，接口如下：
int DevLogin(int hUser, String szDevId, String loginName, String loginPasswd, int seq);

在退出设备访问时，需要调用设备登出接口：
int DevLogout(int hUser, String szDevId, int nSeq);

接口说明可以参考“FunSDK接口说明”->“设备功能方法”相关说明。
Demo示例中，参考以下两个函数的调用：

<img src="http://open.xmeye.net/upload/image/20160516/1463375561625045214.png">

### 设备状态查询

在获取到设备列表(不论是本地模式还是用户模式），都需要查询设备的状态(在线/离线)，接口如下：
```mr
int  SysGetDevState(int hUser, String devIds, int nSeq);

参数说明：devIds支持多个序列号同时查询，不同序列号以分号";"隔开即可。
使用说明：获取设备状态只需要知道设备序列号就可以查询，不需要先调用登录设备（DevLogin()）。
```

### 设备视频播放

设备视频播放常用的几个函数为：

a> 设备播放实时视频：
int MediaRealPlay(int hUser, String devId, int  nChnIndex, int  nStreamType, Object hWnd, int  nSeq)；

b> 视频播放停止：
int MediaStop(int hPlayer, int  nSeq = 0);

简要说明：
```mr
1.MediaRealPlay()返回一个播放句柄hPlayer，即MediaStop中传入的第一个参数"hPlayer"；
2.MediaRealPlay()中的第二个参数devId，如果是AP方式与设备直连，那么devId传设备IP地址+端口；
  如果是互联网方式连接，那么传设备的MAC；
3.其他接口可以参考FunSDK接口说明；
```

Demo中封装了一个类似VideoView的<a href="http://open.xmeye.net/zh/#4.2"><b>FunVideoView</b></a>类，可以以标准Android控件的形式使用，但是设置播放地址接口FunVideoView.setVideoPath()与标准VideoView接口略有不同，地址格式需要满足上述说明2中的描述。

### 设备报警

#### 1 报警推送开关

报警推送开关是指设备报警消息是否推送到报警服务器；

#### 2 报警通知（Notification）开关

报警通知开关是指报警通知是否需要在手机Notification中显示，区别于“报警推送开关”，只要报警推送开关打开，即使关闭了报警通知开关，报警消息也会推送到服务器，用户依然可以在历史报警信息中查看，但是手机Notification不会实时通知；

#### 3 历史报警信息

## 更多功能

(更多功能请参考API说明)

## 关于com.lib.funsdk.support

com.lib.funsdk.support本身不是FunSDK的一部分，是为了方便移植和理解FunSDK接口调用，更适合Android/Java的开发习惯而提供的参考代码，开放源码，在我司授权下可以免费使用；可以在此基础上再次开发，如果有修改，还请同步给我们。
com.lib.funsdk.support存在的目的是为了移植FunSDK更简单。

### FunSupport

FunSupport封装了大部分的FunSDK接口，并实现了IFunSDKResult.OnFunSDKResult()，大部分的结果处理可以参考此处的代码；FunSupport中在处理完IFunSDKResult.OnFunSDKResult()之后会以相应Listener的方式回调，使用时可以先注册Listener，主要有以下几种：

1.OnFunLoginListener
用户登录/登出结果监听
2.OnFunDeviceListener
设备列表变化，设备状态更新等监听
3.OnFunDeviceOptListener
设备登录，获取/设置设备配置信息等监听；
4.OnFunDeviceFileListener
设备文件下载监听；
5.其他

<lable style="color:red">注</lable>：如果不用FunSupport也是完全可以的，参考<a href="https://open.xmeye.net/resource.do?cid=91631cce47184420ae06a71b23cb5554&rid=c60af28a1b5246edbcb00def7878a993">FunSDK接口说明</a>即可；FunSupport里面也是直接调用的FunSDK接口；无论是否使用FunSupport中的代码，还请仔细阅读<a href="https://open.xmeye.net/resource.do?cid=91631cce47184420ae06a71b23cb5554&rid=c60af28a1b5246edbcb00def7878a993">FunSDK接口说明</a>。

### FunVideoView

FunVideoView封装了部分的媒体功能方法（FunSDK.Media*），从类名可以看出，期望以一个标准控件的方式提供视频播放的功能（类似VideoView）；
可以在布局文件（layout.xml）中直接使用（参考./res/layout/activity_device_camera.xml）：

<img src="http://open.xmeye.net/upload/image/20160516/1463375583707004130.png">

几个特殊的接口说明：
1.FunVideoView.setRealDevice(String devSn); 
设置需要播放视频的设备序列号，如果是AP方式连接，那么是IP:PORT的格式；
2.FunVideoView.setStreamType(FunStreamType streamType);
设置码流类型，主/辅码流（如果设备不支持，设置无效）；
