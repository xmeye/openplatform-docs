## Integrated preparation

### btain uuid/AppKey/AppSecret/moveCard

<div style="margin-left:40px;">
   Find your application in “Console”, and view uuid, AppKey, AppSecret and moveCard these four values.
   If you haven't created an application, please see “Developers Must Read”- > "<a href="http://open.xmeye.net/resource.do?cid=ec799b013aec4a589357b644630fd4d2&rid=69896d3a5962401dbd5db30988e67a56#undefined">“Newbie guide”.</a>"。
</div>

###  Download SDK

<div style="margin-left:40px;">  SDK and Demo are in “Resource Center - > Download Center>FunSDK, please select the corresponding platform to download.</div>

### Import SDK

<div name="zhunbei31" id="zhunbei31" style="margin-left:40px;font-size:15px;line-height:60px;">1.3.1 SDK document description</div>
<div style="margin-left:80px;"> FunSDK.framework</div>
<div name="zhunbei32" id="zhunbei32" style="margin-left:40px;font-size:15px;line-height:60px;"> 1.3.2 Use Xcode to import SDK </div>
<div style="margin-left:80px;font-size:15px;">Add FunSDK.framework.to the link library list; <br/>
In addition to  <lable style="color:red">FunSDK.framework </lable>， it also needs to add  <lable style="color:red"> OpenAL.framework, libresolv,libiconv,libbz2,libz</lable>these system framework/ library.
</div>

## Basic function integration

### FunSDK initialization

<div>
The initialization of FunSDK could be executed in -<lable style="color:red">(BOOL)</lable>application:(<lable style="color:#5500ff">UIApplication </lable>*)application didFinishLaunchingWithOptions:(<lable style="color:#5500ff">NSDictionary </lable>*)launchOptionsof AppDelegate, through the following steps:
</div>

   a>  Library initialization 1: Fun_Init();<br/>
   b> Library initialization 2: Fun_InitNetSDK();<br/>
   c> Set App file storage path;<br/>
   
```
   //Set configuration file storage directory
   FUN_SetFunStrAttr(EFUN_ATTR_CONFIG_PATH,...);
   //Set upgrade file storage directory
   FUN_SetFunStrAttr(EFUN_ATTR_UPDATE_FILE_PATH,...);
   //Set temporary file storage directory
   FUN_SetFunStrAttr(EFUN_ATTR_TEMP_FILES_PATH,...);
```

d> Set the parameters of local login, AP mode login and P2P mode login
   
```
   //Set the location of relevant information preservation when local login device.
   FUN_SysInit();
   //Set the location of device information file preservation in AP mode (app directly connect to device hotspot)
   FUN_SysInitAsAPModel();
   //Set cloud service
   FUN_SysInit();
```

The initialization process can refer to the interface realization in FunSDKDemo for iOS

```
	 +(int)initSDK{
    	SInitParam pa;
	    pa.nAppType = H264_DVR_LOGIN_TYPE_MOBILE;
	    FUN_Init(0, &pa);
	    //Register api
	    NSString* strAppKey = @"6356f3673b134e53983798cfb7a0adf3";
	    NSDictionary *infoDictionary = [[NSBundle mainBundle]infoDictionary];
	    NSString *strUuid = [infoDictionary objectForKey:@"CFBundleIdentifier"];	    
	    FUN_RegistAPI([strAppKey UTF8String], [strUuid UTF8String]);	    
	    FUN_InitNetSDK();	
	    //Set the data configuration files for storing device information
	    NSArray *pathArray = NSSearchPathForDirectoriesInDomains(NSCachesDirectory, NSUserDomainMask, YES);
	    NSString *path = [pathArray lastObject];	    
	    //Set configuration file storage directory
	    FUN_SetFunStrAttr(EFUN_ATTR_CONFIG_PATH, [[path stringByAppendingString:@"/Configs/"] UTF8String]);
	    //Set upgrade file storage directory
	    FUN_SetFunStrAttr(EFUN_ATTR_UPDATE_FILE_PATH,[[path stringByAppendingString:@"/Updates/"] UTF8String]);
	    //Set temporary file storage directory
	    FUN_SetFunStrAttr(EFUN_ATTR_TEMP_FILES_PATH,[[path stringByAppendingString:@"/Temps/"] UTF8String]);	    
	    //Set the location of relevant information preservation when local login device.
	    FUN_SysInit([[path stringByAppendingString:@"/LocalDevs.db"] UTF8String]);	    
	    //Set the location of device information file preservation in AP mode (app directly connect to device hotspot)
	    FUN_SysInitAsAPModel([[path stringByAppendingString:@"/APDevs.db"] UTF8String]);	    
	    //Set cloud service
	    FUN_SysInit(constStrServerAddrs, constIntServerPort);	
	    return 0;
}
```

###  Device login

No matter what kind of mode (local, AP, or P2P) you use, it all uses the same set of login and logout interface, and just the devid parameters are different if using different login methods to login device. 

DevId are filled in the “ip:port” format, whether it is local login or AP login. For example, the device IP address is 192.168.1.12, the device tcp port is set to 34567 (the default value of common device), then the devid is “192.168.1.12:34567”. AP mode, because the device is a gateway, so devid generally fill in for the "192.168.10.1:34567" format.

In P2P mode, devid is the serial number of the device;
Other interfaces that need to use devid parameters are also like this;

<div style="line-height:40px;">Firstly call the device login interface before visiting to the device:<br></div>

int FUN_DevLogin(UI_HANDLE hUser, const char *szDevId, const char *szUser, const char *szPwd, int nSeq);<br/>

</div>

Result message id is  EMSG_DEV_LOGIN

Login process can refer to the realization in Demo:


```
	#pragma mark - login
	- (IBAction)login:(id)sender {
    if ( self.isLogined ) {
        return;
    }
    if (self.ipText.text.length == 0 || self.userText.text.length == 0 || self.portText.text.length == 0){
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
    //The format that using ip (domain name) mode to visit devId is ip (domain name): port
    //The format that using sn mode to visit devId is sn
    self.devId = [NSString stringWithFormat:@"%s:%s", sIP, sPort];
    int nSeq = 123;  //The serial number, when the message is received, it will return as the original value
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
                //Login success
                self.isLogined = YES; 
                //After login, you can get the system information or other information
                FUN_DevGetConfig_Json(SelfMsgHandler, [self.devId UTF8String], systemInfo.Name(), 0);      
                //After getting the system information, you can set the system time for the device (time synchronization)
                NSString* date;
                NSDateFormatter* formatter = [[NSDateFormatter alloc]init];
                [formatter setDateFormat:@"YYYY-MM-dd hh:mm:ss"];
                date = [formatter stringFromDate:[NSDate date]];
                FUN_DevSetConfig_Json(SelfMsgHandler, [self.devId UTF8String], "OPTimeSetting", [date UTF8String], date.length+1);
            }
        }
        break;
	}
```

When the device no longer needs to be visited, you can log out the device:

int FUN_DevLogout(UI_HANDLE hUser, const char *szDevId);

### Monitoring device video play

 Several frequently-used functions of device video playing are:

a> Device play real-time video:

int MediaRealPlay(int hUser, String devId, int  nChnIndex, int  nStreamType, Object hWnd, int  nSeq)；

b> Video play stop：

int MediaStop(int hPlayer, int  nSeq = 0);

 Brief description: 
 
1.MediaRealPlay() parameter 1 hUser is the recipient of the result returned message that interface calls. Parameter 2 devId is the device id (same with login and logout). Parameter 3 nChnIndex is channel number, start from 0. Parameter 4 nStreamType is stream type, 0- main stream (high resolution), 1- sub stream (low resolution). Parameter 5 hWnd is video display view pointer. The return value is the player handle hPlayer;

2. MediaStop() parameter 1 fill in MediaRealPlay, the returned player handle hPlayer;

3. Other interfaces can refer to the description of FunSDK interface;

### Device alarm message

## More functions

</div>
<div style="margin-left:30">(Please refer to API description for more functions)
</div>