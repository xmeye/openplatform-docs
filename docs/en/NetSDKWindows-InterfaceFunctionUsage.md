
<div style="text-align:center;font-size:25px;font-family:黑体"><b>Definition and usage of interface function    
</b></div>
1.1 SDK initialization                      
1.2 Alarm state acquisition                
1.3 Device registration                    
1.4 Real-time monitoring                   
1.5 Playback and download                 
1.6 Playback control                     
1.7 PTZ control                             
1.8 System configuration                     
1.9 Log management                      
1.10 Remote control                       
1.11 Voice intercom                        
1.12 Record mode settings                   
1.13 Set system time                      
1.14 Get set running status information       
1.15 Network keyboard                     
1.16 Network alarm                       
1.17 Alarm center                          
1.18 Disk management                        
1.19 Capture image                          
1.20 Transparent 232, 485                     
1.21 Get DDNS information                     
1.22 Support forced I-frames                    
1.23 Set timeout and attempt times of login device
1.24 Transparent serial port                    
1.25 DVR local
1.26 Client record                             
1.27 Open voice intercom (2)                    
1.28 Client audio                              
1.29Client capture image                       
1.30 Play location                            
1.31 Set information frame callback               
1.32 Client video color                         
1.33 Play client local file                      
1.34 Bind local IP                              
1.35 Set reported data callback                 
1.36 Support device active registration          
1.37 Set sub connection disconnect callback   
1.38 Set heartbeat packet time and disconnection time  
1.39 Search local area network device       
1.40 Get public IP                       
1.41 Get smart socket control commands   
1.42 Set smart socket control commands     
1.43 Smart socket control command parameters description    
1.44 Get set control commands           
1.45 Check whether the device is online   
<hr>

#### 1.1SDK initialization ####
<br/>

<table>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_GetLastError();</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Get error information</td></tr>
<tr><td style="background-color:#dedebe">Parameters description
</td><td style="background-color:#B9B973">None</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Query corresponding error code</td></tr>
</table>
<br/>

<table>
<tr><td style="background-color:#dedebe;width:30%;">Calling function
</td><td style="background-color:#B9B973">typedef void (CALL_METHOD *fDisConnect)(long lLoginID, char *pchDVRIP, long nDVRPort, unsigned long dwUser);
</td></tr>
<tr><td style="background-color:#dedebe">Calling function parameters description
</td><td style="background-color:#B9B973">lLoginID: the return value of H264_DVR_Login; pchDVRIP:   device IP; nDVRPort: port number; dwUser: user data is the   second parameter of H264_DVR_Init () function </td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return TRUE, fail return FALSE
</td></tr>
</table>
<br/>

<table>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_Init(fDisConnect cbDisConnect, unsigned long dwUser);</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Initialize SDK, calling before all the SDK functions
</td></tr>
<tr><td style="background-color:#dedebe">Parameters description
</td><td style="background-color:#B9B973">cbDisConnect: disconnection callback function, callback the device whosecurrent network has been   disconnected. Do not callback this device that call H264_DVR_Logout()   function to automatically disconnect; when set to zero,   the callback is prohibited. dwUser: user data, can be NULL.</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return   TRUE, fail return FALSE
</td></tr>
</table>
<br/>


<table>
<tr><td style="background-color:#dedebe;width:30%;">Correlation function
</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_Cleanup();</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">empty   SDK; release the occupied resources, calling after all the SDK functions.</td></tr>
<tr><td style="background-color:#dedebe">Parameters description
</td><td style="background-color:#B9B973">None</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">None</td></tr>
</table>
<br/>


#### 1.2 Alarm state acquisition ####
<br/>

<table>
<tr><td style="background-color:#dedebe;width:30%;">Calling function
</td><td style="background-color:#B9B973">typedef bool (CALL_METHOD *fMessCallBack)(long lLoginID, char *pBuf, unsigned long dwBufLen, long dwUser);
</td></tr>
<tr><td style="background-color:#dedebe">  Calling function  parameters   description
</td><td style="background-color:#B9B973">lLoginID: the return value of   H264_DVR_Login; pBuf: details see enumeration SDK_AlarmInfo (alarm) or H264_DVR_ACTIVEREG_INFO   (active register DAS);dwUser is the last parameter for the   following interface function.
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return   TRUE, fail return FALSE
</td></tr>
</table>
<br/>

<table>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_SetDVRMessCallBack(fMessCallBack cbAlarmcallback, unsigned long lUser);</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973"> Set the message   callback function, to get the current state information of device which has   nothing to do with the calling sequence. SDK default not   callback, this callback function is valid   if it firstly calls the alarm message subscription interface   H264_DVR_SetupAlarmChan.    At the same time, the alarm which required   description and aimed at current definition is the current alarm information   per second callback device.</td></tr>
<tr><td style="background-color:#dedebe">Parameters description
</td><td style="background-color:#B9B973">cbAlarmcallback: message callback   function, you can callback the state of the device, for example the alarm   state can be obtained by this callback.  When set to zero, the callback is prohibited.   lUser: user data
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">TRUE is that callback function   executes correctly, FALSE is execution error
</td></tr>
</table>
<br/>


<table>
<tr><td style="background-color:#dedebe;width:30%;">Correlation function
</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_SetupAlarmChan(long lLoginID); and H264_DVR_API bool CALL_METHOD H264_DVR_CloseAlarmChan(long lLoginID);(turn off alarm reporting)</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Start a   subscription of a device, which is used to set up whether need to callback   the device message, obtained message callback from the set value of   H264_DVR_SetDVRMessCallBack()</td></tr>
<tr><td style="background-color:#dedebe">Parameters description
</td><td style="background-color:#B9B973">lLoginID; the return value of H264_DVR_Login
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return   TRUE, fail return FALSE
</td></tr>
</table>
<br/>

#### 1.3Device registration ####

<table>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_Login(char *sDVRIP, unsigned short wDVRPort, char *sUserName, char *sPassword, LPH264_DVR_DEVICEINFO lpDeviceInfo, int *error,int socketType DEF_PARAM(0));</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Register users to the device, when   the device is set to the user to reuse  (device default user such as admin, cannot   be set to reuse), you can use the account to register multiple times.
</td></tr>
<tr><td style="background-color:#dedebe">Parameters description
</td><td style="background-color:#B9B973">sDVRIP: device IP   wDVRPort: device port number  sUserName:   username     sPassword: user password lpDeviceInfo:device   information, output parameter error: return the login error code (can refer   to error code) socketTyle: login type (see: SocketStyle)
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973"> Fail return zero; success   return device ID. After logging in, the operation of the device can be   corresponding to the appropriate device via the value (device handle).
</td></tr>
<tr><td style="background-color:#eff">Extended interface function
</td><td style="background-color:#cff">H264_DVR_API long CALL_METHOD H264_DVR_LoginEx(char *sDVRIP, unsigned short wDVRPort, char *sUserName, char *sPassword, LPH264_DVR_DEVICEINFO lpDeviceInfo, int nType, int *error);
</td></tr>
<tr><td style="background-color:#eff">Function description
</td><td style="background-color:#cff">Register users to the device's extended interface to support a user to   specify login client type
</td></tr>
<tr><td style="background-color:#eff">Parameters description
</td><td style="background-color:#cff"> nType: capability supported by device, when the value is two, indicates   the user login in active listening mode-see   enumeration 
<a href="http://open.xmeye.net/zh/#LoginType">SDK_LoginType</a>
</td></tr>
<tr><td style="background-color:#eff">Return value
</td><td style="background-color:#cff"> Fail return zero; success   return device ID, After logging in, the operation of the device can be   corresponding to the appropriate device via the value (device handle).</td></tr>
<tr><td colspan="2" style="background-color:#666">&#160</td></tr>
<tr><td style="background-color:#eff">Extend V2 interface function
</td><td style="background-color:#cff">H264_DVR_API long CALL_METHOD H264_DVR_LoginEx_V2(char *sDVRIP, unsigned short wDVRPort, char *sUserName, char *sPassword, LPH264_DVR_DEVICEINFO lpDevieInfo, int nType, int *error,int socketType);</td></tr>
<tr><td style="background-color:#eff">Function description
</td><td style="background-color:#cff">Register users to the device's extended V2 interface to support a user   to specify login client type
</td></tr>
<tr><td style="background-color:#eff">Parameters description
</td><td style="background-color:#cff"> nType: login type- see enumeration SDK_LoginType  socketType: login ways- see enumeration SocketStyle (if socketType is 1, then sDVRIP should fill in the device's cloud   serial number)
</td></tr>
<tr><td style="background-color:#eff">Return value
</td><td style="background-color:#cff"> Fail return   zero; success return device ID, After logging in, the operation of the device   can be corresponding to the appropriate device via the value (device handle).</td></tr>
<tr><td colspan="2" style="background-color:#666">&#160</td></tr>
<tr><td style="background-color:#eff">Customer cloud login interface function
</td><td style="background-color:#cff">H264_DVR_API long CALL_METHOD H264_DVR_Login_Cloud(char *sDVRIP, unsigned short wDVRPort, char *sUserName, char*sPassword, LPH264_DVR_DEVICEINFO lpDeviceInfo, int *error,char* uuid);</td></tr>
<tr><td style="background-color:#eff">Function description
</td><td style="background-color:#cff">Customer cloud login interface, it needs to register on our company's   server, then can be used
</td></tr>
<tr><td style="background-color:#eff">Parameters description
</td><td style="background-color:#cff">sDVRIP: device serial number 
</td></tr>
<tr><td style="background-color:#eff">Return value
</td><td style="background-color:#cff"> Fail return   zero; success return device ID, After logging in, the operation of the device   can be corresponding to the appropriate device via the value (device handle).</td></tr>
<tr><td colspan="2" style="background-color:#000">&#160</td></tr>
<tr><td style="background-color:#eff">Correlation function
</td><td style="background-color:#cff">H264_DVR_API long CALL_METHOD H264_DVR_Logout(long lLoginID);</td></tr>
<tr><td style="background-color:#eff">Function description
</td><td style="background-color:#cff">To cancel the device, logout device user
</td></tr>
<tr><td style="background-color:#eff">Parameters description
</td><td style="background-color:#cff">lLoginID：the return value of <a href="http://open.xmeye.net/zh/#Login">H264_DVR_Login</a> function</td></tr>
<tr><td style="background-color:#eff">Return value
</td><td style="background-color:#cff">Success return 1, fail return 0</td></tr>
</table>
<br/>

#### 1.4Real-time monitoring ####
<br/>

<table>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_RealPlay(long lLoginID, LPH264_DVR_CLIENTINFO lpClientInfo);</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Open real-time monitor (preview video)
</td></tr>
<tr><td style="background-color:#dedebe">Parameters description
</td><td style="background-color:#B9B973">lLoginID：the return value of <a href="http://open.xmeye.net/zh/#Login">H264_DVR_Login</a>function  lpClientInfo: real-time   monitoring parameters-refer to H264_DVR_CLIENTINFO structure
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Fail return<=0, <0 can use<a href="http://open.xmeye.net/zh/#GetLastError">H264_DVR_GetLastError</a>function get partial error code   analysis; success return to play handle
</td></tr>
<tr><td colspan="2" style="background-color:#000">&#160</td></tr>
<tr><td style="background-color:#9cf;width:30%;">Correlation function
</td><td style="background-color:#69c">H264_DVR_API bool CALL_METHOD H264_DVR_StopRealPlay(long lRealHandle,void*hWnd DEF_PARAM(0));</td></tr>
<tr><td style="background-color:#9cf">Function description
</td><td style="background-color:#69c">Stop real-time monitoring</td></tr>
<tr><td style="background-color:#9cf">Parameters description
</td><td style="background-color:#69c">lRealHandle：the return value of <a href="http://open.xmeye.net/zh/#RealPlay">H264_DVR_RealPlay</a>hWnd: used to stop the decoding play of the   corresponding window  (the default   value of NULL to stop all the windows of the decoding play)</td></tr>
<tr><td style="background-color:#9cf">Return value
</td><td style="background-color:#69c">Success return   TRUE, fail return FALSE
</td></tr>
<tr><td colspan="2" style="background-color:#666">&#160</td></tr>
<tr><td style="background-color:#9cf;width:30%;">Correlation function
</td><td style="background-color:#69c">H264_DVR_API long CALL_METHOD H264_DVR_PauseRealPlay(long lRealHandle, bool bPause);</td></tr>
<tr><td style="background-color:#9cf">Function description
</td><td style="background-color:#69c">Pause / continue to real-time monitor</td></tr>
<tr><td style="background-color:#9cf">Parameters description
</td><td style="background-color:#69c">lRealHandle： the return value   of <a href="http://open.xmeye.net/zh/#RealPlay">H264_DVR_RealPlay</a>bPause: pause   enable, 0 represents continue, 1 represents pause</td></tr>
<tr><td style="background-color:#9cf">Return value
</td><td style="background-color:#69c">Success return   TRUE, fail return FALSE
</td></tr>
<tr><td colspan="2" style="background-color:#666">&#160</td></tr>
<tr><td style="background-color:#dedebe;width:30%;">Callback function
</td><td style="background-color:#B9B973">typedef int(CALL_METHOD *fRealDataCallBack) (long lRealHandle, long dwDataType, unsigned char *pBuffer,long lbufsize,long dwUser);</td></tr>
<tr><td style="background-color:#dedebe">Callback function parameters description
</td><td style="background-color:#B9B973"></td></tr>
<tr><td style="background-color:#9cf;width:30%;">Correlation function
</td><td style="background-color:#69c">H264_DVR_API bool CALL_METHOD H264_DVR_SetRealDataCallBack(long lRealHandle,fRealDataCallBack cbRealData, long dwUser);</td></tr>
<tr><td style="background-color:#9cf">Function description
</td><td style="background-color:#69c">Set data callback</td></tr>
<tr><td style="background-color:#9cf">Parameters description
</td><td style="background-color:#69c">lRealHandle：the return value of <a href="http://open.xmeye.net/zh/#RealPlay">H264_DVR_RealPlay</a>cbRealData: real-time   data callback  dwUser: callback function parameters
</td></tr>
<tr><td style="background-color:#9cf">Return value
</td><td style="background-color:#69c">Success return   TRUE, fail return FALSE
<tr><td colspan="2" style="background-color:#666">&#160</td></tr>
<tr><td style="background-color:#dedebe;width:30%;">V2 Callback function
</td><td style="background-color:#B9B973">typedef int(CALL_METHOD *fRealDataCallBack_V2) (long lRealHandle, const PACKET_INFO_EX *pFrame, unsigned int dwUser);</td></tr>
<tr><td style="background-color:#dedebe"> Callback function parameters description
</td><td style="background-color:#B9B973"></td></tr>
<tr><td style="background-color:#9cf;width:30%;">Correlation function
</td><td style="background-color:#69c">H264_DVR_API bool CALL_METHOD H264_DVR_SetRealDataCallBack_V2(long lRealHandle,fRealDataCallBack_V2 cbRealData, long dwUser);</td></tr>
<tr><td style="background-color:#9cf">Function description
</td><td style="background-color:#69c"> Data is analyzed by stream and have the specific information of the   frame, others are same as H264_DVR_SetRealDataCallBack</td></tr>
<tr><td style="background-color:#9cf">Parameters description
</td><td style="background-color:#69c">lRealHandle：the return value of<a href="http://open.xmeye.net/zh/#RealPlay">H264_DVR_RealPlay</a>cbRealData: real-time data callback  dwUser: callback function   parameters
</td></tr>
<tr><td style="background-color:#9cf">Return value
</td><td style="background-color:#69c">Success return   TRUE, fail return FALSE
<tr><td colspan="2" style="background-color:#666">&#160</td></tr>
<tr><td style="background-color:#9cf;width:30%;">Correlation function
</td><td style="background-color:#69c">H264_DVR_API bool CALL_METHOD H264_DVR_DelRealDataCallBack(long lRealHandle,fRealDataCallBack cbRealData, long dwUser);</td></tr>
<tr><td style="background-color:#9cf">Function description
</td><td style="background-color:#69c"> Clear callback function,   this function need to call before H264_DVR_StopRealPlay</td></tr>
<tr><td style="background-color:#9cf">Parameters description
</td><td style="background-color:#69c">lRealHandle：the return value of <a href="http://open.xmeye.net/zh/#RealPlay">H264_DVR_RealPlay</a>cbRealData: real-time data callback  dwUser: callback function   parameters
</td></tr>
<tr><td style="background-color:#9cf">Return value
</td><td style="background-color:#69c">Success return   TRUE, fail return FALSE
<tr><td colspan="2" style="background-color:#666">&#160</td></tr>
<tr><td style="background-color:#9cf;width:30%;">Correlation function
</td><td style="background-color:#69c">H264_DVR_API bool CALL_METHOD H264_DVR_DelRealDataCallBack_V2(long lRealHandle,fRealDataCallBack_V2 cbRealData, long dwUser);</td></tr>
<tr><td style="background-color:#9cf">Function description
</td><td style="background-color:#69c">Clear callback <a href="http://open.xmeye.net/zh/#SetRealDataCallBack_V2">H264_DVR_SetRealDataCallBack_V2</a> function V2   version, this function need to call before<a href="http://open.xmeye.net/zh/#StopRealPlay">H264_DVR_StopRealPlay</a></td></tr>
<tr><td style="background-color:#9cf">Function description
</td><td style="background-color:#69c">lRealHandle：the return value of <a href="http://open.xmeye.net/zh/#RealPlay">H264_DVR_RealPlay</a>cbRealData: real-time data callback  dwUser: callback function   parameters
</td></tr>
<tr><td style="background-color:#9cf">Return value
</td><td style="background-color:#69c">Success return   TRUE, fail return FALSE
</table>

<div style="background-color:#c66;width:120px;">
Partial error code analysis:   
</div>
<br/>

<table>
<tr style="background-color:#c66"><td>1.Return value=-11202：Set video sub connection failed,   the device may not be online or in the restart process. Treatment methods:   after received disconnection callback, logout and then login again.</td><tr>
<tr style="background-color:#c66" ><td>2.Return value=-11203：(1) Local area   network access: sub-connect communication failed, that is sub connection set   up success, but the communication failed. The device has been disconnected   after the sub connection is set up successfully. Treatment method:   once again call the H264_DVR_RealPlay function will appear the return value   -11202.                           (2) Active   registration access: the main connecion communication failed, device is   disconnected, sdk interior has not received disconnection callback. Treatment   method: after received the disconnection callback, then logout.</td><tr>
<tr style="background-color:#c66"><td>3.Return value=-11206：Illegal error,   the main connection has been disconnected. The device has been disconnected and   then restarts success, but has not received disconnection callback which   still uses the previous login handle at this time.   Treatment method: after received the   disconnection callback, then logout.
</td><tr>
</table>
<br/>
<div style="font-size:20px;">
<b>1.5Playback and download</b>
</div>
<br/>

<table>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_FindFile(long lLoginID, H264_DVR_FINDINFO* lpFindInfo, H264_DVR_FILE_DATA *lpFileData, int lMaxCount, int *findcount, int waittime DEF_PARAM(5000));</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Query video file by file name
</td></tr>
<tr><td style="background-color:#dedebe">Function parameters

</td><td style="background-color:#B9B973;text-align:left;">lLoginID: login handle<br/>
lpFindInfo:query condition-view H264_DVR_FINDINFO structure<br/>
lpFileData:query result-view H264_DVR_FILE_DATA   structure<br/>
lMaxCount:queried maximum   number of videos(unit byte, recommended between 100-200*sizeof   (H264_DVR_FILE_DATA)<br/>
findcount:queried maximum number of   videos, which is the maximum output parameters that can only   check the recording of the full buffer<br/>
waittime:wait time<br/>
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return   TRUE, fail return FALSE
</td></tr>
<tr><td colspan="2" style="background-color:#ccc">&#160</td></tr>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_FindFileByTime(long lLoginID, SDK_SearchByTime* lpFindInfo, SDK_SearchByTimeResult *lpFileData, int waittime DEF_PARAM(10000));
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Query video file by time
</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left;">lLoginID: login handle<br/>
lpFindInfo:query   condition-view SDK_SearchByTime structure<br/>
lpFileData: returned video file information, is a SDK_SearchByTimeResult structure array, external open memory <br/>
waittime: wait time, unit ms
<br/>
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return   TRUE, fail return FALSE
</td></tr>
</table>
<br/>

####  1.5.2Replay video file ####
<br/>
<table>
<tr><td style="background-color:#cfc;width:30%;">Callback function
</td><td style="background-color:#9c6">typedef void(CALL_METHOD *fDownLoadPosCallBack) (long lPlayHandle, long lTotalSize, long lDownLoadSize, long dwUser);</td></tr>
<tr><td style="background-color:#cfc">Callback function description
</td><td style="background-color:#9c6">Video playback progress callback   prototype (if customers want to display real-time schedule, they should get time from the stream to calculate, network section does not analyze the stream. If   according to the current received data size / total size to calculate the   progress is not very accurate, should be based on the current time, and   according to the start time and end time to calculate progress).
</td></tr>
<tr><td colspan="2" style="background-color:#ccc">&#160</td></tr>
<tr><td style="background-color:#cfc;width:30%;">Callback function
</td><td style="background-color:#9c6">typedef int(CALL_METHOD *fRealDataCallBack) (long lRealHandle, long dwDataType, unsigned char *pBuffer,long lbufsize,long dwUser);</td></tr>
<tr><td style="background-color:#cfc"> Callback function description
</td><td style="background-color:#9c6">Original data callback prototype
</td></tr>
<tr><td colspan="2" style="background-color:#ccc">&#160</td></tr>
<tr><td style="background-color:#cfc;width:30%;">Callback function
</td><td style="background-color:#9c6">typedef int(CALL_METHOD *fRealDataCallBack_V2) (long lRealHandle, const PACKET_INFO_EX *pFrame, unsigned int dwUser);</td></tr>
<tr><td style="background-color:#cfc"> Callback function description
</td><td style="background-color:#9c6">Original data callback prototype
</td></tr>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_PlayBackByName(long lLoginID, H264_DVR_FILE_DATA *sPlayBackFile, fDownLoadPosCallBack cbDownLoadPos, fRealDataCallBack fDownLoadDataCallBack, long dwDataUser);
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Playback video file by file name
</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left;">lLoginID: login handle <br/>
sPlayBackFile:  playback file parameters<br/>
cbDownLoadPos:progress   callback, user notify that whether the user device has been sent  the data completely.   lDownLoadSize=-1 in callback,   represents data is sent completed.<br/>
fDownLoadDataCallBack:playback data callback<br/>
dwDataUser:data callback parameters<br/>
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return   network playback ID, fail return 0
</td></tr>
<tr><td colspan="2" style="background-color:#ccc">&#160</td></tr>
<tr><td style="background-color:#dedebe;width:30%;">V2Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_PlayBackByName_V2(long lLoginID, H264_DVR_FILE_DATA *sPlayBackFile, fDownLoadPosCallBack cbDownLoadPos, fRealDataCallBack_V2 fDownLoadDataCallBack, long dwDataUser);
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Playback video file   by file name
</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left;">lLoginID: login handle <br/>
sPlayBackFile: playback file   parameters<br/>
cbDownLoadPos: progress   callback, user notify that whether the user device has been sent  the data completely.   lDownLoadSize=-1 in callback, represents   data is sent completed.
<br/>
fDownLoadDataCallBack:playback data callback <br/>
dwDataUser:data callback   parameters<br/>
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return   network playback ID, fail return 0
</td></tr>
<tr><td colspan="2" style="background-color:#ccc">&#160</td></tr>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_PlayBackByTime(long lLoginID, H264_DVR_FINDINFO* lpFindInfo, fDownLoadPosCallBack cbDownLoadPos, fRealDataCallBack fDownLoadDataCallBack, long dwDataUser);
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Playback video file   by time
</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left;">lLoginID: login handle <br/>
sPlayBackFile: playback file   parameters<br/>
cbDownLoadPos: progress   callback, user notify that whether the user device has been sent  the data completely.   lDownLoadSize=-1 in callback, represents   data is sent completed.
<br/>
fDownLoadDataCallBack:playback data callback <br/>
dwDataUser:data callback   parameters<br/>
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return   network playback ID, fail return 0
</td></tr>
<tr><td colspan="2" style="background-color:#ccc">&#160</td></tr>
<tr><td style="background-color:#dedebe;width:30%;"> Extended interface function
</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_PlayBackByTimeEx(long lLoginID, H264_DVR_FINDINFO* lpFindInfo,fRealDataCallBack fDownLoadDataCallBack, long dwDataUser, fDownLoadPosCallBack cbDownLoadPos, long dwPosUser);
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Playback video Ex by time, progress   callback and data callback use different callback parameters, the other is   the same with H264_DVR_PlayBackByTime.
</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left;">dwDataUser：the parameters of   fDownLoadDataCallBack progress callback function<br/>
cbDownLoadPos：currently only used to play the end   callback (get the location, please call H264_DVR_GetPlayPos <a href="http://open.xmeye.net/zh #GetPlayPos">
H264_DVR_GetPlayPosinterface)</a><br/>
dwPosUser：the parameters of cbDownLoadPos   data callback function<br/>
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return   network playback ID, fail return 0
</td></tr>
<tr><td colspan="2" style="background-color:#ccc">&#160</td></tr>
<tr><td style="background-color:#dedebe;width:30%;">V2Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_PlayBackByTime_V2(long lLoginID, H264_DVR_FINDINFO* lpFindInfo,fRealDataCallBack_V2 fDownLoadDataCallBack, long dwDataUser, fDownLoadPosCallBack cbDownLoadPos, long dwPosUser);
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973"> The data stream callback from the fDownLoadDataCallBack   data has been analyzed，the other is same   with H264_DVR_PlayBackByTimeEx
</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left;">dwDataUser：the parameters of   fDownLoadDataCallBack progress callback function<br/>
cbDownLoadPos：currently only used to play the end   callback (get the location, please call H264_DVR_GetPlayPos <a href="http://open.xmeye.net/zh #GetPlayPos">
H264_DVR_GetPlayPosinterface)</a><br/>
dwPosUser：the parameters of cbDownLoadPos   data callback function<br/>
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return   network playback ID, fail return 0
</td></tr>
<tr><td colspan="2" style="background-color:#000">&#160</td></tr>
<tr><td style="background-color:#9cf;width:30%;">Correlation function
</td><td style="background-color:#69c">H264_DVR_API bool CALL_METHOD H264_DVR_StopPlayBack(long lPlayHandle);</td></tr>
<tr><td style="background-color:#9cf">Function description
</td><td style="background-color:#69c">Stop video playback
</td></tr>
<tr><td style="background-color:#9cf">Function description
</td><td style="background-color:#69c">lPlayHandle[in]:  the handle returned by the playback   function.
</td></tr>
<tr><td style="background-color:#9cf">Return value
</td><td style="background-color:#69c">Success return   TRUE, fail return FALSE
</table>
<br/>

#### 1.5.3Download video file ####
<br/>

<table>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_GetFileByName(long lLoginID,H264_DVR_FILE_DATA *sPlayBackFile,char *sSavedFileName, fDownLoadPosCallBack cbDownLoadPos DEF_0_PARAM, long dwDataUser DEF_0_PARAM,fRealDataCallBack fDownLoadDataCallBack DEF_0_PARAM);
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">  Download by file name, user cannot use callback and get progress via H264_DVR_GetDownloadPos</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left;">lLoginID[in]: login handle<br/>
sPlayBackFile[in]:downloaded video   information<br/>
sSavedFileName[in]:saved file path,   the full path<br/>
cbDownLoadPos[out]:download progress   callback fDownLoadPosCallBack function, can be empty, user call   H264_DVR_GetDownloadPos to get progress<br/>
dwDataUser[in]:callback function parameters<br/>
fDownLoadDataCallBack[out]:data callback fRealDataCallBack <a href="http://open.xmeye.net/zh/#fRealDataCallBack">fRealDataCallBack</a>function<br/>
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return   TRUE, fail return FALSE
</td></tr>
<tr><td colspan="2" style="background-color:#ccc">&#160</td></tr>
<tr><td style="background-color:#dedebe;width:30%;">V2Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_GetFileByName_V2(long lLoginID,H264_DVR_FILE_DATA *sPlayBackFile,char *sSavedFileName, fDownLoadPosCallBack cbDownLoadPos DEF_0_PARAM, long dwDataUser DEF_0_PARAM,fRealDataCallBack_V2 fDownLoadDataCallBack_V2 DEF_0_PARAM);
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973"> Download V2 version by file name, data callback is analyzed by stream,   the other is same with H264_DVR_GetFileByName
</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left;">lLoginID[in]: login handle<br/>
sPlayBackFile[in]:downloaded video   information<br/>
sSavedFileName[in]:saved file path,   the full path<br/>
cbDownLoadPos[out]:download progress   callback fDownLoadPosCallBack function, can be empty, user call   H264_DVR_GetDownloadPos to get progress<br/>
dwDataUser[in]:callback function parameters<br/>
fDownLoadDataCallBack[out]:data callback fRealDataCallBack <a href="http://open.xmeye.net/zh/#fRealDataCallBack">fRealDataCallBack</a>function<br/>
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return   TRUE, fail return FALSE
</td></tr>
<tr><td colspan="2" style="background-color:#ccc">&#160</td></tr>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_GetFileByTime(long lLoginID, H264_DVR_FINDINFO* lpFindInfo, char *sSavedFileDIR, bool bMerge DEF_PARAM(0), fDownLoadPosCallBack cbDownLoadPos DEF_0_PARAM, long dwDataUser DEF_0_PARAM,fRealDataCallBack fDownLoadDataCallBack DEF_0_PARAM);
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Download video file by time
</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left;">lLoginID[in]: login handle<br/>
sPlayBackFile[in]:downloaded video   information<br/>
sSavedFileName[in]:saved file path,   the full path<br/>
cbDownLoadPos[out]:download progress   callback fDownLoadPosCallBack function, can be empty, user call   H264_DVR_GetDownloadPos to get progress<br/>
dwDataUser[in]:callback function parameters<br/>
fDownLoadDataCallBack[out]:data callback fRealDataCallBack <a href="http://open.xmeye.net/zh/#fRealDataCallBack">fRealDataCallBack</a>function<br/>
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return   TRUE, fail return FALSE
</td></tr>
<tr><td colspan="2" style="background-color:#ccc">&#160</td></tr>
<tr><td style="background-color:#dedebe;width:30%;">V2Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_GetFileByTime_V2(long lLoginID, H264_DVR_FINDINFO* lpFindInfo, char *sSavedFileDIR, bool bMerge, DownLoadPosCallBack cbDownLoadPos DEF_0_PARAM,long dwDataUser DEF_0_PARAM,fRealDataCallBack_V2 fDownLoadDataCallBack_V2 DEF_0_PARAM);
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">The data stream callback from the   fDownLoadDataCallBack data has been analyzed，the other is same with H264_DVR_GetFileByTime
</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left;">lLoginID[in]: login handle<br/>
sPlayBackFile[in]:downloaded video   information<br/>
sSavedFileName[in]:saved file path,   the full path<br/>
cbDownLoadPos[out]:download progress   callback fDownLoadPosCallBack function, can be empty, user call   H264_DVR_GetDownloadPos to get progress<br/>
dwDataUser[in]:callback function parameters<br/>
fDownLoadDataCallBack[out]:data callback fRealDataCallBack <a href="http://open.xmeye.net/zh/#fRealDataCallBack">fRealDataCallBack</a>function<br/>
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return   TRUE, fail return FALSE
</td></tr>
<tr><td colspan="2" style="background-color:#000">&#160</td></tr>
<tr><td style="background-color:#9cf;width:30%;">Correlation function
</td><td style="background-color:#69c">H264_DVR_API int CALL_METHOD H264_DVR_GetDownloadPos(long lFileHandle);</td></tr>
<tr><td style="background-color:#9cf">Function description
</td><td style="background-color:#69c">Get the current location of the download video, can use   to the interface which does not need to real-time display the download progress   and is similar to the function of downloading callback function.
</td></tr>
<tr><td style="background-color:#9cf">Function parameters
</td><td style="background-color:#69c">lFileHandle[in]:download handle
</td></tr>
<tr><td style="background-color:#9cf">Return value
</td><td style="background-color:#69c">>= 0 for download progress   (percentage), < 0 for fail
</table>
<br/>

#### 1.6Playback control ####
<br/>

<table>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_PlayBackControl(long lPlayHandle, long lControlCode,long lCtrlValue);
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Network playback pause and recovery   and schedule control
</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left;">lPlayHandle[in]:playback handle
<br/>
lControlCode[in]:control command, see enum <a href="http://open.xmeye.net/zh/#PlayBackAction">SDK_PlayBackAction</a><br/>
lCtrlValue[in]:control value<br/>
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return   TRUE, fail return FALSE
</td></tr>
</table>
<br/>

#### 1.7PTZ control ####
<br/>

<table>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_PTZControl(long lLoginID,int nChannelNo, long lPTZCommand, bool bStop  DEF_PARAM(0), long lSpeed DEF_PARAM(4));
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">PTZ control
</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left;">lLoginID[in]:	  login handle
<br/>
nChannelNo[in]:	channel number<br/>
lPTZCommand[in]:control command,   see enum<a herf="http://open.xmeye.net/zh/#ControlType">enum PTZ_ControlType</a><br/>
bStop[in]:    whether it is pause<br/>
lSpeed[in]:   speed<br/>
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return   TRUE, fail return FALSE
</td></tr>
<tr><td colspan="2" style="background-color:#ccc">&#160</td></tr>
<tr><td style="background-color:#dedebe;width:30%;"> Extended interface function
</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_PTZControlEx(long lLoginID,int nChannelNo, long lPTZCommand, long lParam1, long lParam2, long lParam3, bool bStop DEF_0_PARAM);
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">   Expand PTZ settings, including preset   point setting, the cruise route, rapid positioning, etc.
</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left;">lLoginID[in]:login handle<br/>
nChannelNo[in]:	channel   number<br/>
lPTZCommand[in]:control command,   see enum  <a herf="http://open.xmeye.net/zh/#ControlType">enum PTZ_ControlType</a><br/>
lParam1[in]，lParam2[in]，lParam3[in]:<br/>
 1、Set up, delete, and turn to the preset point:   lParam1 is preset point value.<br/>
 2、Add the preset point to the cruise; delete the   preset point in the cruise:  lParam1 is   the value of the cruise route, lParam2 is preset point value, and lParam3 is   time interval.
<br/>
 3、Start cruising, stop cruising, and clear the cruise   routes: lParam1 is the value of the cruise line.<br/>
 4、PTZ direction setting: lParam1 is horizontal step length,   lParam2 is vertical step length.<br/>
 5、 PTZ preset point cruise: lParam3 is time interval. bStop[in]: whether it is pause<br/>
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return   TRUE, fail return FALSE
</td></tr>
</table>
<br/>

#### 1.8System configuration ####
<br/>

<table>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API long  CALL_METHOD H264_DVR_GetDevConfig(long lLoginID, unsigned long dwCommand, int nChannelNO, char * lpOutBuffer, unsigned long dwOutBufferSize, unsigned long* lpBytesReturned,int waittime DEF_PARAM(1000));
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Remote setting configuration   parameters
</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left;">lLoginID[in]: login handle<br/>
dwCommand[in]: control command, see enum   SDK_CONFIG_TYPE<br/>
nChannelNO[in]:	-1 represents the full   channel, 0-n represents single channel<br/>
lpOutBuffer[out]:receive buffer, store buffer which input parameters. According   to different types, output different configuration structure, for details,   see configuration structure in the data structure definition.<br/>
dwOutBufferSize[in]:receive buffer size (unit byte)<br/>
lpBytesReturned[out]: the actual returned buffer size, corresponding to the   size of the configuration structure (unit byte)<br/>
waittime[in]: wait time<br/>
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">= 0: success, <   0: fail
</td></tr>
<tr><td colspan="2" style="background-color:#ccc">&#160</td></tr>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API long  CALL_METHOD H264_DVR_SetDevConfig(long lLoginID, unsigned long dwCommand, int nChannelNO, char * lpInBuffer, unsigned long dwInBufferSize, int waittime DEF_PARAM(1000));
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Remote setting configuration   parameters
</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left;">lLoginID[in]: login handle<br/>
dwCommand[in]: control command, see enum   SDK_CONFIG_TYPE<br/>
nChannelNO[in]:	-1 represents the full   channel, 0-n represents single channel<br/>
lpOutBuffer[out]:receive buffer, store buffer which input parameters. According   to different types, output different configuration structure, for details,   see configuration structure in the data structure definition.<br/>
dwOutBufferSize[in]:receive buffer size (unit byte)<br/>
lpBytesReturned[out]: the actual returned buffer size, corresponding to the   size of the configuration structure (unit byte)<br/>
waittime[in]: wait time<br/>
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">= 0: success, <   0: fail
</td></tr>
<tr><td colspan="2" style="background-color:#ccc">&#160</td></tr>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_SetConfigOverNet(unsigned long dwCommand, int nChannelNO, char * lpInBuffer, unsigned long dwInBufferSize, int waittime DEF_PARAM(1000));
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973"> Cross network setting device configuration,   currently only supports the network configuration settings
</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left;">dwCommand[in]:configuration   type, E_SDK_CONFIG_SYSNET<br/>
nChannelNO[in]:configure   channel number, 1 temporary storage, the other for the permanent preservation<br/>
lpInBuffer[in]:	store buffer which input parameters, SDK_CONFIG_NET_COMMON_V3   structure address<br/>
dwInBufferSize[in]:input buffer size   sizeof (SDK_CONFIG_NET_COMMON_V3) unit byte<br/>
waittime[in]:wait time<br/>
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">= 0: success, <   0: fail
</td></tr>
</table>
<br/>

#### 1.9 Log management ####
<br/>

<table>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_FindDVRLog(long lLoginID, SDK_LogSearchCondition *pFindParam, SDK_LogList *pRetBuffer, long lBufSize, int waittime DEF_PARAM(2000));
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Log query
</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left;">lLoginID[in]:login handle<br/>
pFindParam[in]:query condition<br/>
pRetBuffer[out]:log return   information<br/>
lBufSize[in]:receive log information   size<br/>
waittime:wait time<br/>
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return   TRUE, fail return FALSE
</td></tr>
</table>
<br/>

#### 1.10Remote control ####
<br/>

<table>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_ControlDVR(long lLoginID, int type, int waittime DEF_PARAM(2000));
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Device control
</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left;">lLoginID[in]:login handle<br/>
type[in]:	control type, 0.Reset   device, 1.Clear log 2.Shutdown 3. Recover record   log 4.Stop record log<br/>
waittime[in]: wait time
<br/>
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return   TRUE, fail return FALSE
</td></tr>
</table>
<br/>

#### 1.10.1Local upgrade ####
<br/>

<table>
<tr><td style="background-color:#cfc;width:30%;">Callback function
</td><td style="background-color:#9c6">typedef void(CALL_METHOD *fUpgradeCallBack) (long lLoginID, long lUpgradechannel,int nTotalSize, int nSendSize, long dwUser);</td></tr>
<tr><td style="background-color:#cfc">Callback function description
</td><td style="background-color:#9c6;text-align:left">lUpgradechannel, the returned handle for updrading <a href="http://open.xmeye.net/zh/#Upgrade">H264_DVR_Upgrade</a>function<br/>
nSendSize = -1 upgrade completed  <br/>
nSendSize = -2 upgrade error<br/>
nTotalSize = -1, nSendSize:1-99return upgrade   progress <br/>
nTotalSize =0,nSendSize = H264_DVR_NOENOUGH_MEMORY-H264_DVR_INVALID_WIFI_DRIVE upgrade error specific   code<br/>
Other is to send progress<br/>
Cloud upgrade add this step:nTotalSize=-2, nSendSize:0   - 100=download progress, no send progress<br/>
</td></tr>
<tr><td colspan="2" style="background-color:#ccc">&#160</td></tr>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_Upgrade(long lLoginID, char *sFileName, int nType DEF_0_PARAM, fUpgradeCallBack cbUpgrade = NULL, long dwUser = 0);
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Set up upgrade program for the front   end device network</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left;">lLoginID[in]: login handle<br/>
sFileName[in]:upgrade file path<br/>
nType[in]:upgrade type, 1-start   to upgrade  0-stop upgrading<br/>
cbUpgrade[in]:upgrade progress   callback<br/>
dwUser[in]:callback function parameters<br/>
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return upgrade handle ID, fail   return 0
</td></tr>
<tr><td style="background-color:#9cf;width:30%;">Correlation function
</td><td style="background-color:#69c">H264_DVR_API int CALL_METHOD H264_DVR_GetUpgradeState(long lUpgradeHandle);</td></tr>
<tr><td style="background-color:#9cf">Function description
</td><td style="background-color:#69c">Get upgrade status
</td></tr>
<tr><td style="background-color:#9cf">Function parameters
</td><td style="background-color:#69c">lUpgradechannel, the returned handle for updrading <a href="http://open.xmeye.net/zh/#Upgrade">H264_DVR_Upgrade</a>function</td></tr>
<tr><td style="background-color:#9cf">Return value
</td><td style="background-color:#69c">Success return 1, upgrading return 2,   fail return 3
<tr><td colspan="2" style="background-color:#ccc">&#160</td></tr>
<tr><td style="background-color:#9cf;width:30%;">Correlation function
</td><td style="background-color:#69c">H264_DVR_API long CALL_METHOD H264_DVR_CloseUpgradeHandle(long lUpgradeHandle);</td></tr>
<tr><td style="background-color:#9cf">Function description
</td><td style="background-color:#69c">Stop upgrade, release the upgrade   handle
</td></tr>
<tr><td style="background-color:#9cf">Function parameters
</td><td style="background-color:#69c">lUpgradechannel, the returned handle for updrading <a href="http://open.xmeye.net/zh/#Upgrade">H264_DVR_Upgrade</a>function</td></tr>
<tr><td style="background-color:#9cf">Return value
</td><td style="background-color:#69c">Success return 1, fail return 0
</table>
<br/>

#### 1.10.2Cloud upgrade  ####
<br/>

<table>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_Upgrade_Cloud(long lLoginID, SDK_CloudUpgradeVersion *sUpgradeVer, int nType DEF_0_PARAM, fUpgradeCallBack cbUpgrade DEF_0_PARAM, long dwUser DEF_0_PARAM);
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Start cloud upgrade
</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left;">lLoginID[in]: login handle      sUpgradeVer[in]:upgraded file information</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return 0, fail return <0
</td></tr>
<tr><td colspan="2" style="background-color:#ccc">&#160</td></tr>
<tr><td style="background-color:#dedebe;width:30%;">V2Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_Upgrade_Cloud_V2(long lLoginID, SDK_CloudUpgradeStartReq *sUpgradeVer, int nType DEF_0_PARAM, fUpgradeCallBack cbUpgrade DEF_0_PARAM, long dwUser DEF_0_PARAM);
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">New cloud upgrade
</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left;">lLoginID[in]:login   handle    sUpgradeVer[in]:upgraded file information</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return 0, fail return <0
</td></tr>
<tr><td style="background-color:#9cf;width:30%;">Correlation function
</td><td style="background-color:#69c">H264_DVR_API long CALL_METHOD H264_DVR_StopUpgrade_Cloud(long lHandle);</td></tr>
<tr><td style="background-color:#9cf">Function description
</td><td style="background-color:#69c">Stop cloud upgrade
</td></tr>
<tr><td style="background-color:#9cf">Function parameters
</td><td style="background-color:#69c">lHandle[in]:cloud upgrade <a href="http://open.xmeye.net/zh/#Upgrade_Cloud">H264_DVR_Upgrade_Cloud</a>function returned value handle 
</td></tr>
<tr><td style="background-color:#9cf">Return value
</td><td style="background-color:#69c">Success return 0, fail return <0
</table>
<br/>

#### 1.10.3Search device information ####
<br/>

<table>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_SearchDevice(char* szBuf, int nBufLen, int* pRetLen, int nSearchTime);
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Search local area network device
</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left;">szBuf[out]:	 receive buffer<br/>
nBufLen[in]:	receive   buffer size, sizeof(<a href="http://open.xmeye.net/zh/#NET_COMMON_V2">SDK_CONFIG_NET_COMMON_V2</a>)*n<br/>
pRetLen[in]:	returned   size<br/>
nSearchTime[in]:wait time<br/>
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return   TRUE, fail return FALSE
</td></tr>
<tr><td colspan="2" style="background-color:#ccc">&#160</td></tr>
<tr><td style="background-color:#cfc;width:30%;">Callback function
</td><td style="background-color:#9c6">typedef  void ( CALL_METHOD *pfSearchDeviceCallBack)(SDK_CONFIG_NET_COMMON_V2  *pNetCom , unsigned long userData);</td></tr>
<tr><td style="background-color:#cfc">  Callback function description
</td><td style="background-color:#9c6">Custom callback function to obtain   device information
</td></tr>
<tr><td style="background-color:#dedebe;width:30%;">V2Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_SearchDevice_V2(pfSearchDeviceCallBack pfNetCom,unsigned long userData, int nSearchTime);
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">   Search device in the local area network, search device V2 version in   the local area network
</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left;">pfNetCom[out]:callback function
<br/>
userData[in]:	callback parameters <br/>
nSearchTime[in]:wait time<br/>
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return   TRUE, fail return FALSE
<tr><td style="background-color:#dedebe;width:30%;">  Extended interface function
</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_SearchDevice_IPV6(char* szBuf, int nBufLen, int* pRetLen, int nSearchTime, int ntype);
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Search IPV6 device   in the local area network
</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left;">szBuf[out]:	receive buffer 
<br/>
nBufLen[in]:	 receive buffer size, sizeof(<a href="http://open.xmeye.net/zh/#NET_COMMON_V2">SDK_CONFIG_NET_COMMON_V2</a>))*n<br/>
pRetLen[in]:	returned size<br/>
nSearchTime[in]:wait time<br/>
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return   TRUE, fail return FALSE
</td></tr>
</table>
<br/>

#### 1.11Voice intercom ####
<br/>


<table>
<tr><td style="background-color:#cfc;width:30%;">Callback function
</td><td style="background-color:#9c6">typedef void (CALL_METHOD *pfAudioDataCallBack)(long lVoiceHandle, char *pDataBuf, long dwBufSize, char byAudioFlag, long dwUser);</td></tr>
<tr><td style="background-color:#cfc"> Callback function description
</td><td style="background-color:#9c6;">The audio data callback function   prototype of voice intercom</td></tr>
<tr><td colspan="2" style="background-color:#ccc">&#160</td></tr>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_StartVoiceCom_MR(long lLoginID, pfAudioDataCallBack pVcb, long dwDataUser);
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Start voice intercom
</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left;">lLoginID[in]:  login handle<br/>
pVcb[out]:	receive intercom data callback<br/>
dwDataUser[in]:callback function parameters<br/>
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">> 0 intercom   handle, <= 0 fail
</td></tr>
<tr><td style="background-color:#9cf;width:30%;">Correlation function
</td><td style="background-color:#69c">H264_DVR_API bool CALL_METHOD H264_DVR_VoiceComSendData(long lVoiceHandle, char *pSendBuf, long lBufSize);</td></tr>
<tr><td style="background-color:#9cf">Function description
</td><td style="background-color:#69c">Send intercom data, forwarding voice   intercom data collected by PC</td></tr>
<tr><td style="background-color:#9cf">Function parameters
</td><td style="background-color:#69c">lVoiceHandle[in]:the return value handle of <a href="http://open.xmeye.net/zh/#StartVoiceCom_MR">H264_DVR_StartVoiceCom_MR</a>fucntion
<br/>
pSendBuf[in]:	 intercom data<br/>
lBufSize[in]:	intercom   data size<br/>
</td></tr>
<tr><td style="background-color:#9cf">Return value
</td><td style="background-color:#69c">Success return   TRUE, fail return FALSE
<tr><td colspan="2" style="background-color:#ccc">&#160</td></tr>
<tr><td style="background-color:#9cf;width:30%;">Correlation function
</td><td style="background-color:#69c">H264_DVR_API bool CALL_METHOD H264_DVR_StopVoiceCom(long lVoiceHandle);</td></tr>
<tr><td style="background-color:#9cf">Function description
</td><td style="background-color:#69c">Stop intercom
</td></tr>
<tr><td style="background-color:#9cf">Function parameters
</td><td style="background-color:#69c">lVoiceHandle[in]:the return value handle of   <a href="http://open.xmeye.net/zh/#StartVoiceCom_MR">H264_DVR_StartVoiceCom_MR</a> function
</td></tr>
<tr><td style="background-color:#9cf">Return value
</td><td style="background-color:#69c">Success return   TRUE, fail return FALSE
<tr><td colspan="2" style="background-color:#ccc">&#160</td></tr>
<tr><td style="background-color:#9cf;width:30%;">Correlation function
</td><td style="background-color:#69c">H264_DVR_API bool CALL_METHOD H264_DVR_SetTalkMode(long lLoginID, SDK_AudioInFormatConfig* pTalkMode);</td></tr>
<tr><td style="background-color:#9cf">Function description
</td><td style="background-color:#69c">Set intercom audio encoding mode, user   cannot set, default G711A code</td></tr>
<tr><td style="background-color:#9cf">Function parameters
</td><td style="background-color:#69c">lLoginID[in]: login handle
pTalkMode[in]: intercom   mode structure see: SDK_AudioInFormatConfig channel number, -1 represents the full   channel, 0-n represents a single channel</td></tr>
<tr><td style="background-color:#9cf">Return value
</td><td style="background-color:#69c">Success return   TRUE, fail return FALSE
</table>
</table>
<br/>

#### 1.12Record mode settings ####
<br/>

<table>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_StartDVRRecord(long lLoginID, int nChannelNo ,long lRecordType);
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Set record mode
</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left;">lLoginID[in]:login handle<br/>
nChannelNo[in]:channel number, -1   represents the full channel, 0-n represents a single channel<br/>
lRecordType[in]:record mode, see enum<a href="http://open.xmeye.net/zh/#RecordModeTypes">SDK_RecordModeTypes</a><br/>
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return   TRUE, fail return FALSE
</td></tr>
<tr><td style="background-color:#9cf;width:30%;">Correlation function
</td><td style="background-color:#69c">H264_DVR_API bool CALL_METHOD H264_DVR_StopDVRRecord(long lLoginID, int nChannelNo);
</td></tr>
<tr><td style="background-color:#9cf">Function description
</td><td style="background-color:#69c">Close record
</td></tr>
<tr><td style="background-color:#9cf">Function parameters
</td><td style="background-color:#69c">lLoginID[in]: login handle<br/>
nChannelNo[in]: -1   represents the full channel, 0-n represents a single channel<br/>
</td></tr>
<tr><td style="background-color:#9cf">Return value
</td><td style="background-color:#69c">Success return   TRUE, fail return FALSE
</table>
<br/>

#### 1.13Set system time ####
<br/>

<table>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_SetSystemDateTime(long lLoginID, SDK_SYSTEM_TIME *pSysTime);
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Set system time
</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left;">lLoginID[in]:login handle<br/>
pSysTime[in]: time-see enumeration <a href="http://open.xmeye.net/zh/#SYSTEM_TIME">SDK_SYSTEM_TIME</a><br/>
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return   TRUE, fail return FALSE
</td></tr>
</table>
<br/>

#### 1.14Get set running status information ####
<br/>

<table>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_GetDVRWorkState(long lLoginID, SDK_DVR_WORKSTATE *pWorkState);
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Get device working status information 
</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left;">lLoginID[in]: login handle<br/>
pWorkState[out]:device working   status-see<a href="http://open.xmeye.net/zh/#WORKSTATE">SDK_DVR_WORKSTATE</a>structure<br/></td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return   TRUE, fail return FALSE
</td></tr>
</table>
<br/>

#### 1.15Network keyboard ####
<br/>

<table>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_ClickKey(long lLoginID, SDK_NetKeyBoardData *pKeyBoardData);
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Send network keyboard key messages
</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left;">lLoginID[in]: login handle<br/>
pKeyBoardData[in]:network keyboard parameters-see <a href="http://open.xmeye.net/zh/#NetKeyBoardData">SDK_NetKeyBoardData<a>
<br/></td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return   TRUE, fail return FALSE
</td></tr>
</table>
<br/>

#### 1.16Network alarm ####
<br/>

<table>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_SendNetAlarmMsg(long lLoginID, SDK_NetAlarmInfo *pAlarmInfo);
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Send network alarm information
</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left;">lLoginID[in]:login handle<br/>
pAlarmInfo[in]:network alarm parameters-see <a href="http://open.xmeye.net/zh/#NetAlarmInfo">SDK_NetAlarmInfo</a>
<br/></td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return   TRUE, fail return FALSE
</td></tr>
</table>
<br/>

#### 1.17Alarm center  ####
<br/>

<table>
<tr><td style="background-color:#cfc;width:30%;">Callback funtion
</td><td style="background-color:#9c6">typedef bool (CALL_METHOD *fMessCallBack)(long lLoginID, char *pBuf, unsigned long dwBufLen, long dwUser);</td></tr>
<tr><td style="background-color:#cfc"> Callback funtion description
</td><td style="background-color:#9c6;text-align:left">Message (alarm, active registration) callback prototype<br/>
1.Alarm, pBuf description,,SDK_AlarmInfo alarmInfo;memcpy ( &alarmInfo, pBuf, dwBufLen );<br/>
2.Active registration, pBuf description,H264_DVR_ACTIVEREG_INFO activeInfo;memcpy ( &alarmInfo, pBuf, dwBufLen );<br/>
</td></tr>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_StartAlarmCenterListen(int nPort, fMessCallBack cbAlarmCenter, unsigned long dwDataUser);
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Start alarm center monitor</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left;">nPort[in]:port number<br/>
cbAlarmCenter[out]:data callback <a href="http://open.xmeye.net/zh/#fMessCallBack">fMessCallBack</a>function<br/>
dwDataUser[in]:callback function   parameters<br/>
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return   TRUE, fail return FALSE
</td></tr>
<tr><td style="background-color:#9cf;width:30%;">Correlation function
</td><td style="background-color:#69c">H264_DVR_API bool CALL_METHOD H264_DVR_StopAlarmCenterListen();
</td></tr>
<tr><td style="background-color:#9cf">Function description
</td><td style="background-color:#69c">Close alarm center monitor</td></tr>
<tr><td style="background-color:#9cf">Function parameters
</td><td style="background-color:#69c">Null</td></tr>
<tr><td style="background-color:#9cf">Return value
</td><td style="background-color:#69c">Success return   TRUE, fail return FALSE
</td></tr>
</table>
<br/>

#### 1.18Disk management  ####
<br/>

<table>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API int CALL_METHOD H264_DVR_StorageManage(long lLoginID, SDK_StorageDeviceControl *pStorageCtl);
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Partition and format the hard disk,   and so on
</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;">lLoginID[in]: login handle  pStorageCtl[in]: operating   parameters-see<a href="http://open.xmeye.net/zh/#StorageDeviceControl">SDK_StorageDeviceControl</a>
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">> 0 success，<=0   fail
</td></tr>
</table>
<br/>

#### 1.19Capture image ####
<br/>

<table>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_CatchPic(long lLoginID, int nChannel, char *sFileName);
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973;text-align:left">Device capture image that is capture the   memory buf of an instant picture sent by device, external generates files.<br/>
1.This interface is effective when it   has screenshot configuration option in the device configuration.<br/>
2.If meet 1, the   default resolution is D1. If you want to capture the same resolution video   images, we need to modify the screenshot resolution in the encoding setting.  (If there is no screenshot resolution option   in the    encoding setting, you need to   customize the program which supports this option).<br/>
</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left">lLoginID[in]:  login handle<br/>
nChannel[in]: channel number<br/>
sFileName[in]:saved path<br/>
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return   TRUE, fail return FALSE
（view the specific error values via   <a href="http://open.xmeye.net/zh/#GetLastError">H264_DVR_GetLastError</a>）
</td></tr>
<tr><td colspan="2" style="background-color:#ccc">&#160</td></tr>
<tr><td style="background-color:#dedebe;width:30%;">  Extended interface function
</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_CatchPicInBuffer(long lLoginID, int nChannel, char *pBuffer, int nBufLen, int *pPicLen);
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973;text-align:left">Device capture image that is capture the   memory buf of an instant picture sent by device, external generates files.<br/>
1.This interface is effective when it   has screenshot configuration option in the device configuration.<br/>
2.If meet 1, the   default resolution is D1. If you want to capture the same resolution video   images, we need to modify the screenshot resolution in the encoding setting.  (If there is no screenshot resolution option   in the    encoding setting, you need to   customize the program which supports this option).<br/>
</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left">lLoginID[in]:  login handle <br/>
nChannel[in]: channel number <br/>
pBuffer[out]:receive buffer<br/>
nBufLen[in]:receive buffer   size<br/>
pPicLen[in]:actual returned size<br/>
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return   TRUE, fail return FALSE
（view the specific error values via <a href="http://open.xmeye.net/zh/#GetLastError">H264_DVR_GetLastError</a>）
</td></tr>
</table>
<br/>

#### 1.20Transparent 232, 485 ####
<br/>

<table>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_SerialWrite(long lLoginID, SERIAL_TYPE nType, char *pBuffer, int nBufLen);
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Write data to the device via the   serial port
</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left;">lLoginID[in]:login handle<br/>
nType[in]:serial port   type-see enumeration <a href="http://open.xmeye.net/zh/#SERIAL_TYPE">SERIAL_TYPE</a><br/>
pBuffer[in]: data<br/>
nBufLen[in]: data length<br/>
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return   TRUE, fail return FALSE
</td></tr>
<tr><td style="background-color:#9cf;width:30%;">Correlation function
</td><td style="background-color:#69c">H264_DVR_API bool CALL_METHOD H264_DVR_SerialRead(long lLoginID, SERIAL_TYPE nType, char *pBuffer, int nBufLen, int *pReadLen);
</td></tr>
<tr><td style="background-color:#9cf">Function description
</td><td style="background-color:#69c">Read data from the device via the   serial port
</td></tr>
<tr><td style="background-color:#9cf">Function parameters
</td><td style="background-color:#69c;text-align:left;">lLoginID[in]: login handle<br/>
nType[in]: serial port type-see enumeration<a href="http://open.xmeye.net/zh/#SERIAL_TYPE">SERIAL_TYPE</a><br/>
pBuffer[out]: receive data<br/>
nBufLen[in]: receive data length<br/>
pReadLen[out]:received data   length<br/>
</td></tr>
<tr><td style="background-color:#9cf">Return value
</td><td style="background-color:#69c">Success return   TRUE, fail return FALSE
</td></tr>
</table>
<br/>

#### 1.21Get DDNS information ####
<br/>

<table>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API int CALL_METHOD H264_DVR_GetDDNSInfo(SearchMode &searchmode, DDNS_INFO *pDevicInfo, int maxDeviceNum, int &nretNum);
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Get DDNS information
</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left">searchmode[in]:search information
<br/>
pDevicInfo[out]:DDNS information<br/>
maxDeviceNum[in]:maximum number of   devices<br/>
nretNum[out]:obtained number of devices<br/>
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">>= 0 success, <   0 fail</td></tr>
</table>
<br/>

#### 1.22Support forced I-frames ####
<br/>

<table>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_MakeKeyFrame(long lLoginID, int nChannel, int nStream);
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">forced I-frames
</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left">lLoginID[in]:login handle<br/>
nChannel[in]:channel number<br/>
nStream[in]:the code stream type, 0 represents the main stream, and 1   represents the sub stream.<br/>
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return   TRUE, fail return FALSE
</td></tr>
</table>
<br/>

#### 1.23Set timeout and attempt times of login device ####
<br/>

<table>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_SetConnectTime(long nWaitTime, long nTryTimes);
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Set timeout and attempt times of login   device
</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left">nWaitTime[in]: when the unit ms is not   set, default 5000ms<br/>
nTryTimes[in]:when the number of   times do not set, default 3 times<br/>
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return   TRUE, fail return FALSE
</td></tr>
</table>
<br/>

#### 1.24Transparent serial port   ####
<br/>

<table>
<tr><td style="background-color:#cfc;width:30%;">Callback funtion
</td><td style="background-color:#9c6">typedef void (CALL_METHOD *fTransComCallBack) (long lLoginID, long lTransComType, char *pBuffer, unsigned long dwBufSize, unsigned long dwUser);</td></tr>
<tr><td style="background-color:#cfc"> Callback funtion description
</td><td style="background-color:#9c6;">Transparent serial port   callback function prototype
</td></tr>
<tr><td style="background-color:#cfc">Callback parameters
</td><td style="background-color:#9c6;">lTransComType：lTransComType: serial   port type, see enumeration<a href="http://open.xmeye.net/zh/#SERIAL_TYPE">SERIAL_TYPE</a>
</td></tr>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_OpenTransComChannel(long lLoginID, TransComChannel *TransInfo, fTransComCallBack cbTransCom, unsigned long lUser);
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Create the transparent serial port   channel
</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left;">lLoginID[in]:login handle<br/>
TransInfo[in]:	transparent   serial port parameters<br/>
cbTransCom[out]: device data callback <a href="http://open.xmeye.net/zh/#fTransComCallBack">fTransComCallBack</a>function<br/>
lUser[in]:  callback function parameters<br/>
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return   TRUE, fail return FALSE
</td></tr>
<tr><td style="background-color:#9cf;width:30%;">Correlation function
</td><td style="background-color:#69c">H264_DVR_API bool CALL_METHOD H264_DVR_CloseTransComChannel(long lLoginID, SERIAL_TYPE nType);</td></tr>
<tr><td style="background-color:#9cf">Function description
</td><td style="background-color:#69c">Close the transparent serial port channel
</td></tr>
<tr><td style="background-color:#9cf">Function parameters
</td><td style="background-color:#69c;text-align:left;">lLoginID[in]:login handle <br/>
nType[in]: transparent   serial port type, see enumeration <a href="http://open.xmeye.net/zh/#SERIAL_TYPE">SERIAL_TYPE</a><br/>
</td></tr>
<tr><td style="background-color:#9cf">Return value
</td><td style="background-color:#69c">Success return   TRUE, fail return FALSE
</td></tr>
<tr><td style="background-color:#9cf;width:30%;">Correlation function
</td><td style="background-color:#69c">H264_DVR_API bool CALL_METHOD H264_DVR_GetDeviceState(long lLoginID, SDK_State_Type type, char *pState)</td></tr>
<tr><td style="background-color:#9cf">Function description
</td><td style="background-color:#69c">Get status information
</td></tr>
<tr><td style="background-color:#9cf">Function parameters
</td><td style="background-color:#69c;text-align:left;">lLoginID[in]:device login handle
<br/>
nType[in]:for details, see <a href="http://open.xmeye.net/zh/#State_Type">SDK_State_Type</a><br/>
pState[in]:data return<br/>
</td></tr>
<tr><td style="background-color:#9cf">Return value
</td><td style="background-color:#69c">Success return   TRUE, fail return FALSE
</td></tr>
</table>
<br/>

#### 1.25DVR local user operation interface screenshot ####
<br/>

<table>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_CatchPicUI(long lLoginID,char *saveFileName,int type DEF_PARAM(1));</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Get DVR local user operation interface   screenshot
</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left">lLoginID[in]:login handle<br/>
saveFileName[in]:image saved path<br/>
type[in]: saved picture type, 1: the   whole picture, 2: activity area picture.<br/>
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return   TRUE, fail return FALSE
</td></tr>
</table>
<br/>


#### 1.26Client record ####
<br/>

<table>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_StartLocalRecord(long lRealHandle,char*szSaveFileName,long type=0);</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Start local record</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left">lRealHandle[in]:play handle the return value of <a href="http://open.xmeye.net/zh/#RealPlay">H264_DVR_RealPlay</a>function
<br/>
szSaveFileName[in]:record path <br/>
type[in]: record type (0: file name suffix is .h264; 2:   file name suffix is .avi), default is 0<br/>
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return   TRUE, fail return FALSE
</td></tr>
<tr><td style="background-color:#9cf;width:30%;">Correlation function
</td><td style="background-color:#69c">H264_DVR_API bool CALL_METHOD H264_DVR_StopLocalRecord(long lRealHandle);</td></tr>
<tr><td style="background-color:#9cf">Function description
</td><td style="background-color:#69c">Close local record</td></tr>
<tr><td style="background-color:#9cf">Function parameters
</td><td style="background-color:#69c;">lRealHandle[in]:play handle the return value of <a href="http://open.xmeye.net/zh/#RealPlay">H264_DVR_RealPlay</a>function
</td></tr>
<tr><td style="background-color:#9cf">Return value
</td><td style="background-color:#69c">Success return   TRUE, fail return FALSE
</td></tr>
</table>
<br/>

#### 1.27Open voice intercom (2)   ####
<br/>

<table>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_StartLocalVoiceCom(long lLoginID);
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Open voice intercom
</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;">lLoginID[in]:login handle the   return value of <a href="http://open.xmeye.net/zh/#Login">H264_DVR_Login</a> function
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return   TRUE, fail return FALSE
</td></tr>
</table>
<br/>


#### 1.28Client audio   ####
<br/>

<table>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_OpenSound(long lHandle);
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Open channel audio, preview / playback   / local play a function</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;">lRealHandle[in]:play handle the return value of <a href="http://open.xmeye.net/zh/#RealPlay">H264_DVR_RealPlay</a> function</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return   TRUE, fail return FALSE
</td></tr>
<tr><td style="background-color:#9cf;width:30%;">Correlation function
</td><td style="background-color:#69c">H264_DVR_API bool CALL_METHOD H264_DVR_CloseSound(long lHandle);</td></tr>
<tr><td style="background-color:#9cf">Function description
</td><td style="background-color:#69c">Close channel audio, preview /   playback / local play a function</td></tr>
<tr><td style="background-color:#9cf">Function parameters
</td><td style="background-color:#69c;text-align:left">lRealHandle[in]: play handle, the return value of<a href="http://open.xmeye.net/zh/#RealPlay">H264_DVR_RealPlay</a>function or H264_DVR_PlayBackByName function or H264_DVR_StartLocalPlay   function or H264_DVR_PlayBackByTimeEx function</td></tr>
<tr><td style="background-color:#9cf">Return value
</td><td style="background-color:#69c">Success return   TRUE, fail return FALSE
</td></tr>
</table>
<br/>


#### 1.29Client capture image ####
<br/>

<table>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_LocalCatchPic(long lHandle,char*szSaveFileName);
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Capture local picture, preview /   playback / local play a function</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left">lRealHandle[in]: play handle, the   return value of H264_DVR_RealPlay functionor H264_DVR_PlayBackByName function   or H264_DVR_StartLocalPlay function or H264_DVR_PlayBackByTimeEx function</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return   TRUE, fail return FALSE
</td></tr>
</table>
<br/>


#### 1.30Play location  ####
<br/>

<table>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API float CALL_METHOD H264_DVR_GetPlayPos(long lPlayHandle);
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Gets the play position (percentage), for playback and   local play, the interface is valid when the playback and pass window handle
</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left">lRealHandle[in]: play handle the   return value of H264_DVR_PlayBackByName function or H264_DVR_StartLocalPlay function or H264_DVR_PlayBackByTimeEx function</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Return play progress   (percentage)</td></tr>
<tr><td style="background-color:#9cf;width:30%;">Correlation function
</td><td style="background-color:#69c">H264_DVR_API bool CALL_METHOD H264_DVR_SetPlayPos(long lPlayHandle,float fRelativPos);
</td></tr>
<tr><td style="background-color:#9cf">Function description
</td><td style="background-color:#69c">Set the play position (percentage),   for playback and local play, the interface is valid when the playback and   pass window handle</td></tr>
<tr><td style="background-color:#9cf">Function parameters
</td><td style="background-color:#69c;text-align:left">lRealHandle[in]: play handle, the   return value of H264_DVR_PlayBackByName function or H264_DVR_StartLocalPlay function or H264_DVR_PlayBackByTimeEx function</td></tr>
<tr><td style="background-color:#9cf">Return value
</td><td style="background-color:#69c">Success return   TRUE, fail return FALSE
</td></tr>
</table>
<br/>

#### 1.31Set information frame callback ####
<br/>

<table>
<tr><td style="background-color:#cfc;width:30%;">Callback function
</td><td style="background-color:#9c6">typedef void (CALL_METHOD  *InfoFramCallBack)(long lPlayHand, long nType, LPCSTR pBuf,long nSize, long nUser);</td></tr>
<tr><td style="background-color:#cfc">Callback function description
</td><td style="background-color:#9c6;"> Information frame callback setting   nType: (0x03 represents gprs information frame)</td></tr>
<tr><td style="background-color:#dedebe;width:30%;">Interface function
</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_SetInfoFrameCallBack(long lPlayHandle,InfoFramCallBack callback,long user);
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Set information frame callback
</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left">lRealHandle[in]:play handle, the return value of <a href="http://open.xmeye.net/zh/#RealPlay">H264_DVR_RealPlay</a>function or<a href="http://open.xmeye.net/zh/#PlayBackByName">H264_DVR_PlayBackByName</a>function or<a href="http://open.xmeye.net/zh/#StartLocalPlay">H264_DVR_StartLocalPlay</a>function or<a href="http://open.xmeye.net/zh/#PlayBackByTimeEx">H264_DVR_PlayBackByTimeEx</a>function<br/>
callback[out]:	 information frame   callback <br/>
user[in]:Callback function   parameters<br/>
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return   TRUE, fail return FALSE
</td></tr>
</td></tr>
</table>
<br/>



#### 1.32Client video color ####
<br/>

<table>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_LocalGetColor(long lHandle, DWORD nRegionNum, LONG *pBrightness, LONG *pContrast, LONG *pSaturation, LONG *pHue)
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Get play video color information, preview / playback / local play a function</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left">lHandle[in]:real-time play handle or playback handle   or local play handl, thereturn value of <a href="http://open.xmeye.net/zh/#RealPlay">H264_DVR_RealPlay</a> function or <a href="http://open.xmeye.net/zh/#PlayBackByName">H264_DVR_PlayBackByName</a> function or <a href="http://open.xmeye.net/zh/#StartLocalPlay">H264_DVR_StartLocalPlay</a> function or <a href="http://open.xmeye.net/zh/#PlayBackByTimeEx">H264_DVR_PlayBackByTimeEx</a>function<br/>
nRegionNum[in]:display area, if   only one display area (usually) is set to 0<br/>
pBrightness[out]:brightness  <br/>	 
pContrast[out]:	contrast<br/>
pSaturation[out]:saturation<br/>
pHue[out]:hue<br/>
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return   TRUE, fail return FALSE
</td></tr>
<tr><td colspan="2" style="background-color:#ccc">&#160</td></tr>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_LocalSetColor(long lHandle, DWORD nRegionNum, LONG nBrightness, LONG nContrast, LONG nSaturation, LONG nHue);
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Set play video color information, preview / playback / local play a function</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left">lHandle[in]:real-time play handle or playback handle   or local play handl, thereturn value of <a href="http://open.xmeye.net/zh/#RealPlay">H264_DVR_RealPlay</a> function or <a href="http://open.xmeye.net/zh/#PlayBackByName">H264_DVR_PlayBackByName</a> function or <a href="http://open.xmeye.net/zh/#StartLocalPlay">H264_DVR_StartLocalPlay</a> function or <a href="http://open.xmeye.net/zh/#PlayBackByTimeEx">H264_DVR_PlayBackByTimeEx</a>function<br/>
nRegionNum[in]:display area, if   only one display area (usually) is set to 0<br/>
pBrightness[out]:brightness  <br/>	 
pContrast[out]:	contrast<br/>
pSaturation[out]:saturation<br/>
pHue[out]:hue<br/>
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return   TRUE, fail return FALSE
</td></tr>
</table>
<br/>


#### 1.33Play client local file ####
<br/>

<table>
<tr><td style="background-color:#cfc;width:30%;">Callback function
</td><td style="background-color:#9c6">typedef void (CALL_METHOD * fPlayDrawCallBack)(long lPlayHand,HDC hDc,long nUser);</td></tr>
<tr><td style="background-color:#cfc">Callback function description
</td><td style="background-color:#9c6;">RigisterDraw callback prototype
</td></tr>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_StartLocalPlay(char*pFileName,void* hWnd,fPlayDrawCallBack drawCallBack=0,long user=0)
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Play local. h.264 video file
</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left">pFileName[in]:video file path
<br/>
hWnd[in]:Play window   handle<br/>
drawCallBack[out]:superpose drawing callback function (do not use can set   to NULL)<br/>
user[in]:callback function   parameters<br/>
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Fail return 0, success return play ID   (local play handle)</td></tr>
<tr><td style="background-color:#9cf;width:30%;">Correlation function
</td><td style="background-color:#69c">H264_DVR_API bool CALL_METHOD H264_DVR_StopLocalPlay(long lPlayHandle);
</td></tr>
<tr><td style="background-color:#9cf">Function description
</td><td style="background-color:#69c">Close local play</td></tr>
<tr><td style="background-color:#9cf">Function parameters
</td><td style="background-color:#69c;">lPlayHandle[in]:local play handle,   the return value of <a href="http://open.xmeye.net/zh/#StartLocalPlay">H264_DVR_StartLocalPlay</a>function
</td></tr>
<tr><td style="background-color:#9cf">Return value
</td><td style="background-color:#69c">Success return   TRUE, fail return FALSE
</td></tr>
<tr><td colspan="2" style="background-color:#ccc">&#160</td></tr>
<tr><td style="background-color:#cfc;width:30%;">Callback function
</td><td style="background-color:#9c6">typedef void (CALL_METHOD * fLocalPlayFileCallBack)(long lPlayHand, long nUser);</td></tr>
<tr><td style="background-color:#cfc"> Callback function description
</td><td style="background-color:#9c6;">Local play end callback prototype
</td></tr>
<tr><td style="background-color:#9cf;width:30%;">Correlation   function
</td><td style="background-color:#69c">H264_DVR_API bool CALL_METHOD H264_DVR_SetFileEndCallBack(long lPlayHandle,fLocalPlayFileCallBack callBack,long user)
</td></tr>
<tr><td style="background-color:#9cf">Function description
</td><td style="background-color:#69c">Local file play end callback
</td></tr>
<tr><td style="background-color:#9cf">Function parameters
</td><td style="background-color:#69c;text-align:left">lPlayHandle[in]:callback handle or   local play handle, the return value of <a href="http://open.xmeye.net/zh/#StartLocalPlay">H264_DVR_StartLocalPlay</a>function<br/>
callBack[out]:play end callback<br/>
user[in]:callback function parameters<br/>
</td></tr>
<tr><td style="background-color:#9cf">Return value
</td><td style="background-color:#69c">Success return   TRUE, fail return FALSE
</td></tr>
<tr><td colspan="2" style="background-color:#ccc">&#160</td></tr>
<tr><td style="background-color:#9cf;width:30%;">Correlation   function
</td><td style="background-color:#69c">H264_DVR_API bool CALL_METHOD H264_DVR_LocalPlayCtrl(long lPlayHandle,SDK_LoalPlayAction action,long lCtrlValue)
</td></tr>
<tr><td style="background-color:#9cf">Function description
</td><td style="background-color:#69c">Pc file play control (play, pause,   recover, fast-forward, slow motion)</td></tr>
<tr><td style="background-color:#9cf">Function parameters
</td><td style="background-color:#69c;text-align:left">lPlayHandle[in]:playback handle or local   play handle, the return value of  <a href="http://open.xmeye.net/zh/#StartLocalPlay">H264_DVR_StartLocalPlay</a>function<br/>
action[in]:play control type <a href="http://open.xmeye.net/zh/#LoalPlayAction">SDK_LoalPlayAction</a><br/>
lCtrlValue[in]: control speed fast-forward (1,2,3,4   level), and slow motion (1,2,3,4 level)<br/>
</td></tr>
<tr><td style="background-color:#9cf">Return value
</td><td style="background-color:#69c">Success return   TRUE, fail return FALSE
</td></tr>
</table>
<br/>


#### 1.34Bind local IP ####
<br/>

<table>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_SetLocalBindAddress(char*szIP);
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">  Set the local IP, socket communication socket binding IP (in the   multi-network card,you can specify the binding IP address)</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;">szIP[in]: binding IP address</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return   TRUE, fail return FALSE
</td></tr>
</table>
<br/>

#### 1.35Set reported data callback  ####
<br/>

<table>
<tr><td style="background-color:#cfc;width:30%;">Callback function
</td><td style="background-color:#9c6">typedef void (CALL_METHOD *fUploadDataCallBack) (long lLoginID, long UploadType, char *pBuffer, unsigned long dwBufSize, unsigned long dwUser)</td></tr>
<tr><td style="background-color:#cfc">Callback function description
</td><td style="background-color:#9c6;">Data upload channel callback function   prototype
</td></tr>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_StartUploadData(long lLoginID,UploadDataType upLoadType,fUploadDataCallBack callBack,long lUser);
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Open the data report, currently only   have vehicle-borne data upload</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left">lLoginID[in]:login handle<br/>
upLoadType[in]:report data type<br/>
callBack[out]:report data callback<br/>
lUser[in]:callback function parameters<br/>
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return   TRUE, fail return FALSE
</td></tr>
<tr><td style="background-color:#9cf;width:30%;">Correlation function
</td><td style="background-color:#69c">H264_DVR_API bool CALL_METHOD H264_DVR_StopUploadData(long lLoginID,UploadDataType upLoadType)
</td></tr>
<tr><td style="background-color:#9cf">Function description
</td><td style="background-color:#69c">Stop reporting data</td></tr>
<tr><td style="background-color:#9cf">Function parameters
</td><td style="background-color:#69c;">lLoginID[in]: login handle       upLoadType[in]: report data type</td></tr>
<tr><td style="background-color:#9cf">Return value
</td><td style="background-color:#69c">Success return   TRUE, fail return FALSE
</td></tr>
</table>
<br/>

#### 1.36Support device active registration ####
<br/>

<table>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_StartActiveRigister(int nPort, fMessCallBack cbFunc, unsigned long dwDataUser);
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Start active registration
</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left">nPort[in]:listen the port number,0<=nPort<=65535<br/>
cbFunc[out]:  register on-line callback   function <a href="http://open.xmeye.net/zh/#fMessCallBack">fMessCallBack</a><br/>
dwDataUser[in]:callback function   parameters<br/>
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return   TRUE, fail return FALSE
</td></tr>
<tr><td style="background-color:#9cf;width:30%;">Correlation function
</td><td style="background-color:#69c">H264_DVR_API bool CALL_METHOD H264_DVR_StopActiveRigister();
</td></tr>
<tr><td style="background-color:#9cf">Function description
</td><td style="background-color:#69c">Close active registration
</td></tr>
<tr><td style="background-color:#9cf">Function parameters
</td><td style="background-color:#69c;">None
</td></tr>
<tr><td style="background-color:#9cf">Return value
</td><td style="background-color:#69c">Success return   TRUE, fail return FALSE
</td></tr>
</table>
<br/>

#### 1.37Set sub connection disconnect callback ####
<br/>

<table>
<tr><td style="background-color:#cfc;width:30%;">Callback function
</td><td style="background-color:#9c6">typedef void (CALL_METHOD *fSubDisConnectCallBack)(long lLoginID, SubConnType type, long nChannel, long dwUser);</td></tr>
<tr><td style="background-color:#cfc">   Callback function description
</td><td style="background-color:#9c6;">Sub connection disconnection callback
</td></tr>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_SetSubDisconnectCallBack(fSubDisConnectCallBack callBack,DWORD userData);</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Detect sub connection abnormal   disconnection
</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left">callBack[out]:sub connection   disconnect callback <a href="http://open.xmeye.net/zh/#fSubDisConnectCallBack">fSubDisConnectCallBack</a><br/>
userData[in]: callback function   parameters<br/>
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return   TRUE, fail return FALSE
</td></tr>
</table>
<br/>

#### 1.38Set heartbeat packet time and break time ####
<br/>

<table>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_SetKeepLifeTime(long lLoginID,unsigned int perKeeplifeTime,unsigned int detectDisconTime);</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Set keep-alive time, perKeeplifeTime   (heartbeat interval): default 10 seconds, detectDisconTime (disconnection   detection time): default 60 seconds</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left">lLoginID[in]:login handle<br/>
perKeeplifeTime[in]:  keep-alive time (unit seconds)<br/>
detectDisconTime[in]: disconnection   detection time (unit seconds)<br/>
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return   TRUE, fail return FALSE
</td></tr>
</table>
<br/>

#### 1.39Search local area network device ####
<br/>

<table>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_SearchDeviceEX(long lLoginID,SDK_NetDevList *pDevlist,SDK_TransferProtocol_V2 transferProtocol DEF_PARAM(SDK_TRANSFER_PROTOCOL_NETIP),int waittime DEF_PARAM(15000));</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">The device which is searched by   device, the device is in the same local area network with device, deviec to   search, and then return the results             (H264_DVR_SearchDevice this   interface is searched by sdk itself, the resultsof both return is consistent)</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left">lLoginID[in]: login handle<br/>
pDevlist[out]:device list<br/>
transferProtocol[in]:transmission   protocol, see enum  <a href="http://open.xmeye.net/zh/#TransferProtocol_V2">SDK_TransferProtocol_V2</a><br/>
waittime[in]:wait time<br/>
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return   TRUE, fail return FALSE
</td></tr>
</table>
<br/>

#### 1.40Get public IP ####
<br/>

<table>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_Get_OutNet_IP(const char *uuid, char* ip);
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Query a device extranet IP
</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;">uuid[in]:device serial number  ip[out]: extranet ip</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return TRUE, fail return <=   0
</td></tr>
</table>
<br/>

#### 1.41Get smart socket control commands ####
<br/>

<table>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_GetDevConfig_Json(long lLoginID, const char* dwCommand, int nChannelNO,char * lpOutBuffer,unsigned long dwOutBufferSize,unsigned long* lpBytesReturned,int waittime DEF_PARAM(1000));
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Get smart socket configuration
</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left">lLoginID[in]: login handle
<br/>dwCommand[in]:json name<br/>
nChannelNO[in]:channel number, -1:   get the full channel configuration, 0-n: get a single channel configuration,   starting from 0<br/>
lpOutBuffer[out]:receive json buffer<br/>
dwOutBufferSize[in]:receive buffer   size<br/>
lpBytesReturned[out]:obtained buffer   size (byte)<br/>
waittime[in]: wait time<br/>
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success >0, fail <= 0
</td></tr>
</table>
<br/>

#### 1.42Set smart socket control commands ####
<br/>

<table>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_SetDevConfig_Json(long lLoginID,const char* dwCommand, int nChannelNO, char * lpInBuffer,int waittime DEF_PARAM(1000));
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Set smart socket configuration
</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left">lLoginID[in]: login handle
<br/>dwCommand[in]:json name<br/>
nChannelNO[in]:channel number, -1:   get the full channel configuration, 0-n: get a single channel configuration,   starting from 0<br/>
lpOutBuffer[out]:receive json buffer<br/>
dwOutBufferSize[in]:receive buffer   size<br/>
lpBytesReturned[out]:obtained buffer   size (byte)<br/>
waittime[in]: wait time<br/>
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return 1, fail <=0
</td></tr>
</table>
<br/>

#### 1.43Smart socket control command parameters description ####
<br/>

<table>
<tr><td style="width:33%;background-color:#fcc">Enum value
</td><td style="width:33%;background-color:#fc9">name</td><td style="width:33%;background-color:#f93">Code style</td></tr>
<tr><td style="width:33%;background-color:#fcc">E_SDK_CFG_POWER_SOCKET_SET</td><td style="width:33%;background-color:#fc9">"OPPowerSocketGet"</td><td style="width:33%;background-color:#f93"></td></tr>
<tr><td style="width:33%;background-color:#fcc">E_SDK_CFG_AUTO_SWITCH</td><td style="width:33%;background-color:#fc9">"PowerSocket.AutoArm"</td><td style="width:33%;background-color:#f93"></td></tr>
<tr><td style="width:33%;background-color:#fcc">E_SDK_CFG_AUTO_ARM</td><td style="width:33%;background-color:#fc9">"PowerSocket.AutoArm"</td><td style="width:33%;background-color:#f93"></td></tr>
<tr><td style="width:33%;background-color:#fcc">E_SDK_CFG_CIENT_INFO</td><td style="width:33%;background-color:#fc9">"PowerSocket.ClientInfo"</td><td style="width:33%;background-color:#f93"></td></tr>
<tr><td style="width:33%;background-color:#fcc">E_SDK_CFG_ATHORITY</td><td style="width:33%;background-color:#fc9">"PowerSocket.Arm"</td><td style="width:33%;background-color:#f93"></td></tr>
<tr><td style="width:33%;background-color:#fcc">E_SDK_CFG_ARM</td><td style="width:33%;background-color:#fc9">"PowerSocket.Arm"</td><td style="width:33%;background-color:#f93"></td></tr>
<tr><td style="width:33%;background-color:#fcc">E_SDK_CFG_AUTOLIGHT</td><td style="width:33%;background-color:#fc9">"PowerSocket.AutoLight"</td><td style="width:33%;background-color:#f93"></td></tr>
<tr><td style="width:33%;background-color:#fcc">E_SDK_CFG_LIGHT</td><td style="width:33%;background-color:#fc9">"PowerSocket.Light"
</td><td style="width:33%;background-color:#f93"></td></tr>
<tr><td style="width:33%;background-color:#fcc">E_SDK_CFG_WORKRECORD</td><td style="width:33%;background-color:#fc9">"PowerSocket.WorkRecord"</td><td style="width:33%;background-color:#f93"></td></tr>
<tr><td style="width:33%;background-color:#fcc">E_SDK_CFG_SYSTEMTIME</td><td style="width:33%;background-color:#fc9">"System.Time"</td><td style="width:33%;background-color:#f93"></td></tr>
<tr><td style="width:33%;background-color:#fcc">E_SDK_CFG_WECHATACCOUNT</td><td style="width:33%;background-color:#fc9">"PowerSocket.WechatAccount"</td><td style="width:33%;background-color:#f93"></td></tr>
<tr><td style="width:33%;background-color:#fcc">E_SDK_CFG_WECHATRENEW</td><td style="width:33%;background-color:#fc9">"PowerSocket.WechatRenew"</td><td style="width:33%;background-color:#f93"></td></tr>
<tr><td style="width:33%;background-color:#fcc">E_SDK_CFG_POWERSOCKET_WIFI</td><td style="width:33%;background-color:#fc9">"PowerSocket.WiFi"</td><td style="width:33%;background-color:#f93"></td></tr>
</table>
<br/>

#### 1.44Get set control commands (mainly used in the company's internal mobile terminal command control) ####
<br/>

<table>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_CmdGeneral(long lLoginID, int nCmdReq, const char *szCmd, void *lpOutBuffer, unsigned long dwOutBufferSize, unsigned long* lpBytesReturned, int nTimeout, char *pInParam DEF_PARAM(0), int nInParamLen DEF_PARAM(0), int nCmdRes DEF_PARAM(-1));
</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Not only can get but also can   configure the device parameters</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left">lLoginID[in]: login handle<br/>
nCmdReq[in]: request command<br/>
szCmd[in]:json name<br/>
lpOutBuffer[out]:receive json buffer<br/>
dwOutBufferSize[in]: receive buffer   size (byte)<br/>
lpBytesReturned[out]:received json   size<br/>
nTimeout[in]:wait time<br/>
pInParam[in]:requested command send   to device json string<br/>
nInParamLen[in]:requested command send to device json size (byte)<br/>
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return 0, fail return < 0</td></tr>
</table>
<br/>

#### 1.45Check whether the device is online  ####
<br/>

<table>
<tr><td style="background-color:#cfc;width:30%;">Callback function
</td><td style="background-color:#9c6">typedef int (*OnFoundDevCB)(char * uuid,int state,int userData);</td></tr>
<tr><td style="background-color:#cfc"> Callback function parameters
</td><td style="background-color:#9c6;"> </td></tr>
<tr><td style="background-color:#dedebe;width:30%;">Interface   function
</td><td style="background-color:#B9B973">H264_DVR_API int CALL_METHOD H264_DVR_Check_Device_Exist_V2(SDK_SDevicesState *pStates, int nTimeout,OnFoundDevCB decCb,int userData);</td></tr>
<tr><td style="background-color:#dedebe">Function description
</td><td style="background-color:#B9B973">Check whether multiple devices are   online V2 version</td></tr>
<tr><td style="background-color:#dedebe">Function parameters
</td><td style="background-color:#B9B973;text-align:left">pStates[out]: a number of device   information needed to query SDK_SDevicesState, will return the device status<br/>
nTimeout[in]: wait time<br/>
decCb[out]:  the callback of device   online or not <br/>
userData[out]:callback parameters<br/>
</td></tr>
<tr><td style="background-color:#dedebe">Return value
</td><td style="background-color:#B9B973">Success return 0, fail return < 0
</td></tr>
</table>
<br/>