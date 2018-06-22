## 集成准备

### 获得uuid/AppKey/AppSecret/moveCard

   在"控制台"中找到您的应用，可以查看uuid、AppKey、AppSecret和moveCard四个值。如果您还未创建应用，请查看"开发者必读"->"<a href="http://open.xmeye.net/resource.do?cid=ec799b013aec4a589357b644630fd4d2&rid=69896d3a5962401dbd5db30988e67a56#undefined">新手指南</a>"。

### 下载SDK

SDK及Demo 在 资源中心->下载中心->FunSDK下载 中，请选择对应的平台进行下载。

### 导入SDK

#### 1.SDK文件说明

FunSDK.framework

#### 2.使用XCode导入SDK

将 FunSDK.framework 加入到链接库列表
除了 <lable style="color:red">FunSDK.framework </lable>之外， 还需要加入  <lable style="color:red"> OpenAL.framework, libresolv,libiconv,libbz2,libz</lable>这几个系统自带的framework/库。

#### 3、bulid settings配置：
1、Build Active Architure Only :YES \n
2、Enable Bitode :NO
3、Enable Testability:NO
4、Other Linker Flags :-ObjC
5、C Language Dialect : Compiler Default
6、C++ Language Dialect :Compiler Default
7、C++ Standard Library : Compiler Default
8、Preprocessor Macros : Debug:DEBUG=1 OS_IOS=1 FORMAL=1
                                     Release :OS_IOS=1 FORMAL=1


## 基本功能集成

### FunSDK初始化

FunSDK的初始化，建议再AppDelegate的 <lable style="color:red">(BOOL)</lable>application:(<lable style="color:#5500ff">UIApplication </lable>*)application didFinishLaunchingWithOptions:(<lable style="color:#5500ff">NSDictionary </lable>*)launchOptions中执行，通过以下几个步骤进行：

```
   a> 库初始化1 : Fun_Init();
   b> 库初始化2: Fun_InitNetSDK();
   c> 设置App文件存储路径 :

   //设置配置文件存储目录
   FUN_SetFunStrAttr(EFUN_ATTR_CONFIG_PATH,...);
   //设置升级文件存储目录
   FUN_SetFunStrAttr(EFUN_ATTR_UPDATE_FILE_PATH,...);
   //设置临时文件存储目录
   FUN_SetFunStrAttr(EFUN_ATTR_TEMP_FILES_PATH,...);

   d> 设置本地登录, AP模式登录及P2P模式登录的参数

   //设置本地登录设备相关信息保存文件的位置
   FUN_SysInit();
   //设置AP模式(app直连设备热点)下设置设备信息保存文件位置
   FUN_SysInitAsAPModel();
   //设置云服务
   FUN_SysInit();
```

初始化过程可参考FunSDKDemo for iOS中的接口实现:

```
+(int)initSDK{
    SInitParam pa;
    pa.nAppType = H264_DVR_LOGIN_TYPE_MOBILE;
    FUN_Init(0, &pa);
    //注册api
    NSString* strAppKey = @"6356f3673b134e53983798cfb7a0adf3";
    NSDictionary *infoDictionary = [[NSBundle mainBundle]infoDictionary];
    NSString *strUuid = [infoDictionary objectForKey:@"CFBundleIdentifier"];
    FUN_RegistAPI([strAppKey UTF8String], [strUuid UTF8String]);
    FUN_InitNetSDK();
    //设置用于存储设备信息等的数据配置文件
    NSArray *pathArray = NSSearchPathForDirectoriesInDomains(
    NSCachesDirectory, NSUserDomainMask, YES
    );
    NSString *path = [pathArray lastObject];
    //设置配置文件存储目录
    FUN_SetFunStrAttr(
    EFUN_ATTR_CONFIG_PATH, [[path stringByAppendingString:@"/Configs/"] UTF8String]
    );
    //设置升级文件存储目录
    FUN_SetFunStrAttr(
    EFUN_ATTR_UPDATE_FILE_PATH,[[path stringByAppendingString:@"/Updates/"] UTF8String]
    );
    //设置临时文件存储目录
    FUN_SetFunStrAttr(
    EFUN_ATTR_TEMP_FILES_PATH,[[path stringByAppendingString:@"/Temps/"] UTF8String]
    );
    //设置本地登录设备相关信息保存文件的位置
    FUN_SysInit(
    [[path stringByAppendingString:@"/LocalDevs.db"] UTF8String]
    );
    //设置AP模式(app直连设备热点)下设置设备信息保存文件位置
    FUN_SysInitAsAPModel(
    [[path stringByAppendingString:@"/APDevs.db"] UTF8String]
    );
    //设置云服务
    FUN_SysInit(constStrServerAddrs, constIntServerPort);
    return 0;
}
```

### 设备登录

无论是哪种模式(本地，AP，还是P2P)登录登出均采用同一套登录登出接口，而不同登录方式登录登录设备只是devid参数不同；

本地登录与AP方式登录devId均填写 为 "ip:port" 的格式。例如设备ip地址为192.168.1.12 设备tcp端口设置为34567(普通设备默认值) 则devid为 "192.168.1.12:34567"。 AP模式，因为设备作为网关，所以devid 一般填写为 "192.168.10.1:34567"这种格式;

```
P2P方式devid 为设备的序列号;
其他需要用到devid参数的接口也是如此;
在访问设备之前要先调用设备登录接口：
int FUN_DevLogin(
UI_HANDLE hUser, const char *szDevId, const char *szUser, const char *szPwd, int nSeq
);
```

```
结果消息id为  EMSG_DEV_LOGIN
登录过程可以参考Demo中的实现:

	#pragma mark - 登陆
	- (IBAction)login:(id)sender {

    if ( self.isLogined ) {
        return;
    }

    if (self.ipText.text.length == 0 ||
        self.userText.text.length == 0 ||
        self.portText.text.length == 0){
        return;
    }

    NSUserDefaults *userDefault = [NSUserDefaults standardUserDefaults];
    [userDefault setObject:self.ipText.text forKey:@"devIP"];
    [userDefault setObject:self.portText.text forKey:@"devPort"];
    [userDefault setObject:self.userText.text forKey:@"devUser"];
    [userDefault setObject:self.passwordText.text forKey:@"devPwd"];

    char *sIP   = (char *)[self.ipText.text UTF8String];
    char *sPort = (char *)[self.portText.text UTF8String];
    char *sUser = (char *)[self.userText.text UTF8String];
    char *sPwd  = (char *)[self.passwordText.text UTF8String];

    //ip(域名)方式访问 devId格式为 ip(域名):port
    //sn方式访问 devId格式为 sn
    self.devId = [NSString stringWithFormat:@"%s:%s", sIP, sPort];

    int nSeq = 123;  //序号, 收到消息时会 原值返回
    FUN_DevLogin(SelfMsgHandler, [self.devId UTF8String], sUser, sPwd, nSeq);

	}
	 -(void)OnFunSDKResult:(NSNumber *) pParam{
      NSInteger nAddr = [pParam integerValue];
      MsgContent *msg = (MsgContent *)nAddr;

      switch ( msg->id ) {
        case EMSG_DEV_LOGIN:
        {
            int nReslut = msg->param1;
            NSLog(@"FunSDK Login Result [%d] DevId [%s]", nReslut, msg->szStr);
            if ( nReslut>=0 ) {
                //登录成功
                self.isLogined = YES;

                //登录成功后可以获取下 系统信息活着其他信息
                FUN_DevGetConfig_Json(
                SelfMsgHandler, [self.devId UTF8String], systemInfo.Name(), 0
                );


                //获取完系统信息可以给设备设置下系统时间（时间同步）
                NSString* date;
                NSDateFormatter* formatter = [[NSDateFormatter alloc]init];
                [formatter setDateFormat:@"YYYY-MM-dd hh:mm:ss"];
                date = [formatter stringFromDate:[NSDate date]];
                FUN_DevSetConfig_Json(
                SelfMsgHandler, [self.devId UTF8String], "OPTimeSetting",
                [date UTF8String], date.length+1
                );
            }
        }
        break;
	}
```

在设备不再需要继续访问时，可以登出该设备：

```
int FUN_DevLogout(UI_HANDLE hUser, const char *szDevId);
```

### 监控设备视频播放

设备视频播放常用的几个函数为：

```
a> 设备播放实时视频：
nt MediaRealPlay(
int hUser, String devId, int  nChnIndex, int  nStreamType, Object hWnd, int  nSeq
)；
b> 视频播放停止：
int MediaStop(int hPlayer, int  nSeq = 0);
```

简要说明:
1. MediaRealPlay() 参数1 hUser 为接口调用结果返回消息接收者，参数2 devId 为 设备id(同登录登出)。参数3 nChnIndex 为通道号，从0开始。 参数4 nStreamType 为码流类型 0-主码流（高分辨率）1-副码流(低分辨率)，参数5 hWnd 为视频显示view指针。  返回值为 播放器句柄hPlayer；
2. MediaStop() 参数1填写MediaRealPlay返回的播放器句柄hPlayer;
3. 其他接口可以参考FunSDK接口说明；


### 设备报警消息
开放平台登录后，进入控制台页面，IOS证书上传，请按照要求上传IOS的推送证书。后台会添加证书到服务器，然后按照demo集成接口就能实现报警推送功能。（没有上传证书，推送功能无效）
## 更多功能

(更多功能请参考API说明)
