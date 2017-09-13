## SDK初始化

<style>
	table{
		border-collapse:collapse;
		width:100%;
		text-align:center;
		margin-left:20px;
	}
	table tr td{
		border:1px solid #fff;
	}
</style>
<table>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_GetLastError();</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">获取错误信息</td></tr>
<tr><td style="background-color:#dedebe">参数说明
</td><td style="background-color:#B9B973">无</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">查询对应错误码</td></tr>
</table>


<table>
<tr><td style="background-color:#dedebe;width:30%;">回调函数</td><td style="background-color:#B9B973">typedef void (CALL_METHOD *fDisConnect)(long lLoginID, char *pchDVRIP, long nDVRPort, unsigned long dwUser);
</td></tr>
<tr><td style="background-color:#dedebe">回调函数参数说明
</td><td style="background-color:#B9B973">lLoginID：<a href="http://open.xmeye.net/zh/#Login">H264_DVR_Login</a>的返回值； pchDVRIP:设备IP； nDVRPort:端口号； dwUser:用户数据即为H264_DVR_Init()函数的第二个参数</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回TRUE，失败返回FALSE
</td></tr>
</table>


<table>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_Init(fDisConnect cbDisConnect, unsigned long dwUser);</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">初始化SDK，在所有的SDK函数之前调用
</td></tr>
<tr><td style="background-color:#dedebe">参数说明
</td><td style="background-color:#B9B973">cbDisConnect:为断线回调函数，回调出当前网络已经断开的设备，对调用H264_DVR_Logout()函数主动断开的设备不回调；设置为0时，禁止回调dwUser:用户数据，可为NULL。</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回TRUE，失败返回FALSE
</td></tr>
</table>



<table>
<tr><td style="background-color:#dedebe;width:30%;">相关函数</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_Cleanup();</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">清空SDK，释放占用的资源，在所有的SDK函数之后调用</td></tr>
<tr><td style="background-color:#dedebe">参数说明
</td><td style="background-color:#B9B973">无</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">无
</td></tr>
</table>

## 报警状态获取

<table>
<tr><td style="background-color:#dedebe;width:30%;">回调函数</td><td style="background-color:#B9B973">typedef bool (CALL_METHOD *fMessCallBack)(long lLoginID, char *pBuf, unsigned long dwBufLen, long dwUser);
</td></tr>
<tr><td style="background-color:#dedebe">回调函数参数说明
</td><td style="background-color:#B9B973">lLoginID：H264_DVR_Login的返回值；pBuf:具体见枚举<a href="http://open.xmeye.net/zh/#Alarm"Info>SDK_AlarmInfo</a>(报警)或者H264_DVR_ACTIVEREG_INFO(主动注册DAS)；dwUser即为下面接口函数的最后一个参数。</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回TRUE，失败返回FALSE
</td></tr>
</table>


<table>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_SetDVRMessCallBack(fMessCallBack cbAlarmcallback, unsigned long lUser);</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">设置设备消息回调函数，用来得到设备当前状态信息，与调用顺序无关，SDK默认不回调，此回调函数必须先调用报警消息订阅接口H264_DVR_SetupAlarmChan才有效，同时需要说明的针对目前定义的报警，是每秒回调设备当前的报警信息。
</td></tr>
<tr><td style="background-color:#dedebe">参数说明
</td><td style="background-color:#B9B973">cbAlarmcallback:消息回调函数，可以回调设备的状态，如报警状态可以通过此回调获取当设置为0时表示禁止回调lUser:用户数据。
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">TRUE回调函数执行正确，FALSE执行错误
</td></tr>
</table>



<table>
<tr><td style="background-color:#dedebe;width:30%;">相关函数</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_SetupAlarmChan(long lLoginID); 和 H264_DVR_API bool CALL_METHOD H264_DVR_CloseAlarmChan(long lLoginID);(关闭报警上报)</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">开始对某个设备订阅消息，用来设置是否需要对设备消息回调，得到的消息从H264_DVR_SetDVRMessCallBack()函数的设置值回调出来</td></tr>
<tr><td style="background-color:#dedebe">参数说明
</td><td style="background-color:#B9B973">lLoginID;<a href="http://open.xmeye.net/zh/#Login">H264_DVR_Login</a>的返回值</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返TRUE，失败返回FALSE
</td></tr>
</table>

## 设备注册

<table>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_Login(char *sDVRIP, unsigned short wDVRPort, char *sUserName, char *sPassword, LPH264_DVR_DEVICEINFO lpDeviceInfo, int *error,int socketType DEF_PARAM(0));</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">注册用户到设备，当设备端把用户设置为复用(设备默认的用户如admin，不能设置为复用)，则使用该账户可以多次向设备注册。
</td></tr>
<tr><td style="background-color:#dedebe">参数说明
</td><td style="background-color:#B9B973">sDVRIP：设备IP wDVRPort：设备端口 sUserName：用户名 sPassword：用户密码 lpDeviceInfo：设备信息，属于输出参数 error：返回登陆错误码(可参考错误码中) socketTyle：登陆类型(参见：SocketStyle)
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">失败返回0；成功返回设备ID。登录成功后对设备的操作都可以通过此值(设备句柄)对应到相应的设备
</td></tr>
<tr><td style="background-color:#eff">扩展接口函数
</td><td style="background-color:#cff">H264_DVR_API long CALL_METHOD H264_DVR_LoginEx(char *sDVRIP, unsigned short wDVRPort, char *sUserName, char *sPassword, LPH264_DVR_DEVICEINFO lpDeviceInfo, int nType, int *error);
</td></tr>
<tr><td style="background-color:#eff">函数说明
</td><td style="background-color:#cff">注册用户到设备的扩展接口，支持一个用户指定登陆的客户端类型
</td></tr>
<tr><td style="background-color:#eff">参数说明
</td><td style="background-color:#cff">nType：设备支持的能力，值为2表示主动侦听模式下的用户登陆-见枚举<a href="http://open.xmeye.net/zh/#LoginType">SDK_LoginType</a>
</td></tr>
<tr><td style="background-color:#eff">返回值
</td><td style="background-color:#cff">失败返回0，成功返回设备ID，登录成功后对设备的操作都可以通过此值(设备句柄)对应到相应的设备</td></tr>
<tr><td colspan="2" style="background-color:#666">&#160</td></tr>
<tr><td style="background-color:#eff">扩展V2接口函数
</td><td style="background-color:#cff">H264_DVR_API long CALL_METHOD H264_DVR_LoginEx_V2(char *sDVRIP, unsigned short wDVRPort, char *sUserName, char *sPassword, LPH264_DVR_DEVICEINFO lpDevieInfo, int nType, int *error,int socketType);</td></tr>
<tr><td style="background-color:#eff">函数说明
</td><td style="background-color:#cff">注册用户到设备的扩展V2接口，支持一个用户指定登录类型
</td></tr>
<tr><td style="background-color:#eff">参数说明
</td><td style="background-color:#cff">nType：登录类型-见枚举<a href="http://open.xmeye.net/zh/#LoginType">SDK_LoginType</a>  socketType：登录方式-见枚举<a href="http://open.xmeye.net/zh/#SocketStyle">SocketStyle</a>（如果socketType为1，则sDVRIP应填写设备的云序列号）
</td></tr>
<tr><td style="background-color:#eff">返回值
</td><td style="background-color:#cff">失败返回0，成功返回设备ID，登录成功后对设备的操作都可以通过此值(设备句柄)对应到相应的设备</td></tr>
<tr><td colspan="2" style="background-color:#666">&#160</td></tr>
<tr><td style="background-color:#eff">客户云登陆接口函数
</td><td style="background-color:#cff">H264_DVR_API long CALL_METHOD H264_DVR_Login_Cloud(char *sDVRIP, unsigned short wDVRPort, char *sUserName, char*sPassword, LPH264_DVR_DEVICEINFO lpDeviceInfo, int *error,char* uuid);</td></tr>
<tr><td style="background-color:#eff">函数说明
</td><td style="background-color:#cff">客户云登陆接口，需在我司服务器上注册方可使用
</td></tr>
<tr><td style="background-color:#eff">参数说明
</td><td style="background-color:#cff">sDVRIP：为设备的序列号
</td></tr>
<tr><td style="background-color:#eff">返回值
</td><td style="background-color:#cff">失败返回0，成功返回设备ID，登录成功后对设备的操作都可以通过此值(设备句柄)对应到相应的设备</td></tr>
<tr><td colspan="2" style="background-color:#000">&#160</td></tr>
<tr><td style="background-color:#eff">相关函数
</td><td style="background-color:#cff">H264_DVR_API long CALL_METHOD H264_DVR_Logout(long lLoginID);</td></tr>
<tr><td style="background-color:#eff">函数说明
</td><td style="background-color:#cff">向设备注销，登出设备用户
</td></tr>
<tr><td style="background-color:#eff">参数说明
</td><td style="background-color:#cff">lLoginID：<a href="http://open.xmeye.net/zh/#Login">H264_DVR_Login</a>函数的返回值</td></tr>
<tr><td style="background-color:#eff">返回值
</td><td style="background-color:#cff">成功返回1，失败返回0</td></tr>
</table>

## 实时监视

<table>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_RealPlay(long lLoginID, LPH264_DVR_CLIENTINFO lpClientInfo);</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">打开实时监视（预览视频）
</td></tr>
<tr><td style="background-color:#dedebe">参数说明
</td><td style="background-color:#B9B973">lLoginID：<a href="http://open.xmeye.net/zh/#Login">H264_DVR_Login</a>函数的返回值  lpClientInfo：实时监视参数-可参考H264_DVR_CLIENTINFO结构体
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">失败返回小于等于0，小于0时可用<a href="http://open.xmeye.net/zh/#GetLastError">H264_DVR_GetLastError</a>函数获得<a href="http://open.xmeye.net/zh/#1.41">部分错误码分析</a>；成功返回播放句柄
</td></tr>
<tr><td colspan="2" style="background-color:#000">&#160</td></tr>
<tr><td style="background-color:#9cf;width:30%;">相关函数</td><td style="background-color:#69c">H264_DVR_API bool CALL_METHOD H264_DVR_StopRealPlay(long lRealHandle,void*hWnd DEF_PARAM(0));</td></tr>
<tr><td style="background-color:#9cf">函数说明
</td><td style="background-color:#69c">停止实时监视</td></tr>
<tr><td style="background-color:#9cf">参数说明
</td><td style="background-color:#69c">lRealHandle：<a href="http://open.xmeye.net/zh/#RealPlay">H264_DVR_RealPlay</a>的返回值；hWnd：用于停止相应窗口的解码播放（默认值NULL停止所有窗口的解码播放）</td></tr>
<tr><td style="background-color:#9cf">返回值
</td><td style="background-color:#69c">成功返TRUE，失败返回FALSE
</td></tr>
<tr><td colspan="2" style="background-color:#666">&#160</td></tr>
<tr><td style="background-color:#9cf;width:30%;">相关函数</td><td style="background-color:#69c">H264_DVR_API long CALL_METHOD H264_DVR_PauseRealPlay(long lRealHandle, bool bPause);</td></tr>
<tr><td style="background-color:#9cf">函数说明
</td><td style="background-color:#69c">暂停/继续实时监视</td></tr>
<tr><td style="background-color:#9cf">参数说明
</td><td style="background-color:#69c">lRealHandle：<a href="http://open.xmeye.net/zh/#RealPlay">H264_DVR_RealPlay</a>的返回值；bPause：暂停使能，其中0表示继续，1表示暂停</td></tr>
<tr><td style="background-color:#9cf">返回值
</td><td style="background-color:#69c">成功返TRUE，失败返回FALSE
</td></tr>
<tr><td colspan="2" style="background-color:#666">&#160</td></tr>
<tr><td style="background-color:#dedebe;width:30%;">回调函数</td><td style="background-color:#B9B973">typedef int(CALL_METHOD *fRealDataCallBack) (long lRealHandle, long dwDataType, unsigned char *pBuffer,long lbufsize,long dwUser);</td></tr>
<tr><td style="background-color:#dedebe">回调函数参数说明
</td><td style="background-color:#B9B973"></td></tr>
<tr><td style="background-color:#9cf;width:30%;">相关函数</td><td style="background-color:#69c">H264_DVR_API bool CALL_METHOD H264_DVR_SetRealDataCallBack(long lRealHandle,fRealDataCallBack cbRealData, long dwUser);</td></tr>
<tr><td style="background-color:#9cf">函数说明
</td><td style="background-color:#69c">设置数据回调</td></tr>
<tr><td style="background-color:#9cf">参数说明
</td><td style="background-color:#69c">lRealHandle：<a href="http://open.xmeye.net/zh/#RealPlay">H264_DVR_RealPlay</a>的返回值；cbRealData：实时数据回调  dwUser：回调函数参数
</td></tr>
<tr><td style="background-color:#9cf">返回值
</td><td style="background-color:#69c">成功返TRUE，失败返回FALSE
<tr><td colspan="2" style="background-color:#666">&#160</td></tr>
<tr><td style="background-color:#dedebe;width:30%;">V2回调函数</td><td style="background-color:#B9B973">typedef int(CALL_METHOD *fRealDataCallBack_V2) (long lRealHandle, const PACKET_INFO_EX *pFrame, unsigned int dwUser);</td></tr>
<tr><td style="background-color:#dedebe">回调函数参数说明
</td><td style="background-color:#B9B973"></td></tr>
<tr><td style="background-color:#9cf;width:30%;">相关函数</td><td style="background-color:#69c">H264_DVR_API bool CALL_METHOD H264_DVR_SetRealDataCallBack_V2(long lRealHandle,fRealDataCallBack_V2 cbRealData, long dwUser);</td></tr>
<tr><td style="background-color:#9cf">函数说明
</td><td style="background-color:#69c">数据经过码流分析过，带有帧的具体信息，其他与H264_DVR_SetRealDataCallBack相同</td></tr>
<tr><td style="background-color:#9cf">参数说明
</td><td style="background-color:#69c">lRealHandle：<a href="http://open.xmeye.net/zh/#RealPlay">H264_DVR_RealPlay</a>的返回值；cbRealData：实时数据回调  dwUser：回调函数参数
</td></tr>
<tr><td style="background-color:#9cf">返回值
</td><td style="background-color:#69c">成功返TRUE，失败返回FALSE
<tr><td colspan="2" style="background-color:#666">&#160</td></tr>
<tr><td style="background-color:#9cf;width:30%;">相关函数</td><td style="background-color:#69c">H264_DVR_API bool CALL_METHOD H264_DVR_DelRealDataCallBack(long lRealHandle,fRealDataCallBack cbRealData, long dwUser);</td></tr>
<tr><td style="background-color:#9cf">函数说明
</td><td style="background-color:#69c">清除回调函数,该函数需要在H264_DVR_StopRealPlay前调用</td></tr>
<tr><td style="background-color:#9cf">参数说明
</td><td style="background-color:#69c">lRealHandle：<a href="http://open.xmeye.net/zh/#RealPlay">H264_DVR_RealPlay</a>的返回值；cbRealData：实时数据回调  dwUser：回调函数参数
</td></tr>
<tr><td style="background-color:#9cf">返回值
</td><td style="background-color:#69c">成功返TRUE，失败返回FALSE
<tr><td colspan="2" style="background-color:#666">&#160</td></tr>
<tr><td style="background-color:#9cf;width:30%;">相关函数</td><td style="background-color:#69c">H264_DVR_API bool CALL_METHOD H264_DVR_DelRealDataCallBack_V2(long lRealHandle,fRealDataCallBack_V2 cbRealData, long dwUser);</td></tr>
<tr><td style="background-color:#9cf">函数说明
</td><td style="background-color:#69c">清除回调<a href="http://open.xmeye.net/zh/#SetRealDataCallBack_V2">H264_DVR_SetRealDataCallBack_V2</a>函数V2版本,该函数需要在<a href="http://open.xmeye.net/zh/#StopRealPlay">H264_DVR_StopRealPlay</a>前调用</td></tr>
<tr><td style="background-color:#9cf">参数说明
</td><td style="background-color:#69c">lRealHandle：<a href="http://open.xmeye.net/zh/#RealPlay">H264_DVR_RealPlay</a>的返回值；cbRealData：实时数据回调  dwUser：回调函数参数
</td></tr>
<tr><td style="background-color:#9cf">返回值
</td><td style="background-color:#69c">成功返TRUE，失败返回FALSE
</table>

<div style="width:120px;">
部分错误码分析：
</div>


<table>
<tr style="background-color:#c66"><td>1.返回值=-11202：建立视屏子连接失败，设备可能不在线或者在重启过程中。处理方法：收到断线回调后登出再登录。</td><tr>
<tr style="background-color:#c66" ><td>2.返回值=-11203：（1）局域网访问：子连接通讯失败，即子连接建立成功了，但是通讯失败了，设备在子连接建立成功后设备断开了。处理方法：再次调用H264_DVR_RealPlay函数会出现的返回值-11202。（2）主动注册访问：主连接通讯失败,设备断线了,sdk内部还没有收到断线回调.处理方法:等收到了断线回调再登出即可。</td><tr>
<tr style="background-color:#c66"><td>3.返回值=-11206：非法错误，主连接已断开，设备已断开过，然后重启成功了，但是还没收到断线回调，这个时候还在使用之前的登录句柄。收到断线回调后登出再登录设备。
</td><tr>
</table>

## 回放和下载

### 查询录像文件

<table>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_FindFile(long lLoginID, H264_DVR_FINDINFO* lpFindInfo, H264_DVR_FILE_DATA *lpFileData, int lMaxCount, int *findcount, int waittime DEF_PARAM(5000));</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">按文件名查询录像文件
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left;">lLoginID:登陆句柄
lpFindInfo:查询条件-查看H264_DVR_FINDINFO结构体
lpFileData:查询结果-查看H264_DVR_FILE_DATA结构体
lMaxCount:查询的最大录像数量（单位字节，建议在100-200*sizeof(H264_DVR_FILE_DATA)之间）
findcount:查询到的录像数量，属于输出参数最大只能查到缓冲满为止的录像记录
waittime:等待时间
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回TRUE,失败返回FALSE
</td></tr>
<tr><td colspan="2" style="background-color:#ccc">&#160</td></tr>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_FindFileByTime(long lLoginID, SDK_SearchByTime* lpFindInfo, SDK_SearchByTimeResult *lpFileData, int waittime DEF_PARAM(10000));
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">按时间查询录像文件
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left;">lLoginID:登陆句柄lpFindInfo:查询条件-查看SDK_SearchByTime结构体
lpFileData:返回的录像文件信息，是一个SDK_SearchByTimeResult结构体数组，外部开内存waittime:等待时间，单位ms
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回TRUE,失败返回FALSE
</td></tr>
</table>

### 回放录像文件

<table>
<tr><td style="background-color:#cfc;width:30%;">回调函数</td><td style="background-color:#9c6">typedef void(CALL_METHOD *fDownLoadPosCallBack) (long lPlayHandle, long lTotalSize, long lDownLoadSize, long dwUser);</td></tr>
<tr><td style="background-color:#cfc">回调函数参数说明
</td><td style="background-color:#9c6">回放录像进度回调原形（客户如果想实时显示进度，应该从码流里面获取时间来计算网络部分不分析码流，如果以当前接收数据大小/总大小来计算进度的话不是很准，应该以当前时间，根据开始时间和结束时间来计算进度）
</td></tr>
<tr><td colspan="2" style="background-color:#ccc">&#160</td></tr>
<tr><td style="background-color:#cfc;width:30%;">回调函数</td><td style="background-color:#9c6">typedef int(CALL_METHOD *fRealDataCallBack) (long lRealHandle, long dwDataType, unsigned char *pBuffer,long lbufsize,long dwUser);</td></tr>
<tr><td style="background-color:#cfc">回调函数参数说明
</td><td style="background-color:#9c6">原始数据回调原形
</td></tr>
<tr><td colspan="2" style="background-color:#ccc">&#160</td></tr>
<tr><td style="background-color:#cfc;width:30%;">回调函数</td><td style="background-color:#9c6">typedef int(CALL_METHOD *fRealDataCallBack_V2) (long lRealHandle, const PACKET_INFO_EX *pFrame, unsigned int dwUser);</td></tr>
<tr><td style="background-color:#cfc">回调函数参数说明
</td><td style="background-color:#9c6">原始数据回调原形
</td></tr>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_PlayBackByName(long lLoginID, H264_DVR_FILE_DATA *sPlayBackFile, fDownLoadPosCallBack cbDownLoadPos, fRealDataCallBack fDownLoadDataCallBack, long dwDataUser);
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">按文件名回放录像文件
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left;">lLoginID:登陆句柄
sPlayBackFile: 回放的文件参数
cbDownLoadPos:进度回调，用户通知用户设备是否已经将数据发送完毕，回调中的lDownLoadSize=-1代表数据发送完毕
fDownLoadDataCallBack:回放数据回调
dwDataUser:数据回调参数
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回网络回放ID，失败返回0
</td></tr>
<tr><td colspan="2" style="background-color:#ccc">&#160</td></tr>
<tr><td style="background-color:#dedebe;width:30%;">V2接口函数</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_PlayBackByName_V2(long lLoginID, H264_DVR_FILE_DATA *sPlayBackFile, fDownLoadPosCallBack cbDownLoadPos, fRealDataCallBack_V2 fDownLoadDataCallBack, long dwDataUser);
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">按文件名回放录像文件
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left;">lLoginID:登陆句柄
sPlayBackFile: 回放的文件参数
cbDownLoadPos:进度回调，用户通知用户设备是否已经将数据发送完毕，回调中的lDownLoadSize=-1代表数据发送完毕
fDownLoadDataCallBack:回放数据回调
dwDataUser:数据回调参数
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回网络回放ID，失败返回0
</td></tr>
<tr><td colspan="2" style="background-color:#ccc">&#160</td></tr>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_PlayBackByTime(long lLoginID, H264_DVR_FINDINFO* lpFindInfo, fDownLoadPosCallBack cbDownLoadPos, fRealDataCallBack fDownLoadDataCallBack, long dwDataUser);
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">按时间回放录像文件
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left;">lLoginID:登陆句柄
sPlayBackFile: 回放的文件参数
cbDownLoadPos:进度回调，用户通知用户设备是否已经将数据发送完毕，回调中的lDownLoadSize=-1代表数据发送完毕
fDownLoadDataCallBack:回放数据回调
dwDataUser:数据回调参数
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回网络回放ID，失败返回0
</td></tr>
<tr><td colspan="2" style="background-color:#ccc">&#160</td></tr>
<tr><td style="background-color:#dedebe;width:30%;">扩展接口函数</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_PlayBackByTimeEx(long lLoginID, H264_DVR_FINDINFO* lpFindInfo,fRealDataCallBack fDownLoadDataCallBack, long dwDataUser, fDownLoadPosCallBack cbDownLoadPos, long dwPosUser);
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">按时间回放录像Ex,进度回调和数据回调用不同的回调参数,其他与H264_DVR_PlayBackByTime相同
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left;">dwDataUser：为fDownLoadDataCallBack进度回调函数的参数
cbDownLoadPos：目前只用于播放结束回调（获取位置请调用<a href="http://open.xmeye.net/zh/#GetPlayPos">H264_DVR_GetPlayPos接口）</a>
dwPosUser：为cbDownLoadPos数据回调函数的参数
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回网络回放ID，失败返回0
</td></tr>
<tr><td colspan="2" style="background-color:#ccc">&#160</td></tr>
<tr><td style="background-color:#dedebe;width:30%;">V2接口函数</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_PlayBackByTime_V2(long lLoginID, H264_DVR_FINDINFO* lpFindInfo,fRealDataCallBack_V2 fDownLoadDataCallBack, long dwDataUser, fDownLoadPosCallBack cbDownLoadPos, long dwPosUser);
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">fDownLoadDataCallBack数据回调出来的数据的码流分析过，其他与H264_DVR_PlayBackByTimeEx相同
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left;">dwDataUser：为fDownLoadDataCallBack进度回调函数的参数
cbDownLoadPos：目前只用于播放结束回调（获取位置请调用<a href="http://open.xmeye.net/zh/#GetPlayPos">H264_DVR_GetPlayPos接口）</a>
dwPosUser：为cbDownLoadPos数据回调函数的参数
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回网络回放ID，失败返回0
</td></tr>
<tr><td colspan="2" style="background-color:#000">&#160</td></tr>
<tr><td style="background-color:#9cf;width:30%;">相关函数</td><td style="background-color:#69c">H264_DVR_API bool CALL_METHOD H264_DVR_StopPlayBack(long lPlayHandle);</td></tr>
<tr><td style="background-color:#9cf">函数说明
</td><td style="background-color:#69c">停止录像回放
</td></tr>
<tr><td style="background-color:#9cf">参数说明
</td><td style="background-color:#69c">lPlayHandle[in]:<a href="http://open.xmeye.net/zh/#PlayBack">回放播放函数</a>返回的句柄
</td></tr>
<tr><td style="background-color:#9cf">返回值
</td><td style="background-color:#69c">成功返TRUE，失败返回FALSE
</table>

### 下载录像文件

<table>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_GetFileByName(long lLoginID,H264_DVR_FILE_DATA *sPlayBackFile,char *sSavedFileName, fDownLoadPosCallBack cbDownLoadPos DEF_0_PARAM, long dwDataUser DEF_0_PARAM,fRealDataCallBack fDownLoadDataCallBack DEF_0_PARAM);
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">按文件名下载,用户可以不使用回调，自己通过H264_DVR_GetDownloadPos获取进度
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left;">lLoginID[in]:登陆句柄
sPlayBackFile[in]:下载的录像信息
sSavedFileName[in]:保存的文件路径,全路径
cbDownLoadPos[out]:下载进度回调<a href="http://open.xmeye.net/zh/#fDownLoadPosCallBack">fDownLoadPosCallBack</a>函数，可以为空，用户自己调用<a  href="http://open.xmeye.net/zh/#GetDownloadPos">H264_DVR_GetDownloadPos</a>得到进度
dwDataUser[in]:回调函数参数
fDownLoadDataCallBack[out]:数据回调<a href="http://open.xmeye.net/zh/#fRealDataCallBack">fRealDataCallBack</a>函数
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回TRUE，失败返回FALSE
</td></tr>
<tr><td colspan="2" style="background-color:#ccc">&#160</td></tr>
<tr><td style="background-color:#dedebe;width:30%;">V2接口函数</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_GetFileByName_V2(long lLoginID,H264_DVR_FILE_DATA *sPlayBackFile,char *sSavedFileName, fDownLoadPosCallBack cbDownLoadPos DEF_0_PARAM, long dwDataUser DEF_0_PARAM,fRealDataCallBack_V2 fDownLoadDataCallBack_V2 DEF_0_PARAM);
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">按文件名下载V2版本,数据回调是经过码流分析过,其他与H264_DVR_GetFileByName相同
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left;">lLoginID[in]:登陆句柄
sPlayBackFile[in]:下载的录像信息
sSavedFileName[in]:保存的文件路径,全路径
cbDownLoadPos[out]:下载进度回调<a href="http://open.xmeye.net/zh/#fDownLoadPosCallBack">fDownLoadPosCallBack</a>函数，可以为空，用户自己调用<a  href="http://open.xmeye.net/zh/#GetDownloadPos">H264_DVR_GetDownloadPos</a>得到进度
dwDataUser[in]:回调函数参数
fDownLoadDataCallBack[out]:数据回调<a href="http://open.xmeye.net/zh/#fRealDataCallBack">fRealDataCallBack</a>函数
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回TRUE，失败返回FALSE
</td></tr>
<tr><td colspan="2" style="background-color:#ccc">&#160</td></tr>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_GetFileByTime(long lLoginID, H264_DVR_FINDINFO* lpFindInfo, char *sSavedFileDIR, bool bMerge DEF_PARAM(0), fDownLoadPosCallBack cbDownLoadPos DEF_0_PARAM, long dwDataUser DEF_0_PARAM,fRealDataCallBack fDownLoadDataCallBack DEF_0_PARAM);
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">按时间下载录像文件
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left;">lLoginID[in]:登陆句柄
sPlayBackFile[in]:下载的录像信息
sSavedFileName[in]:保存的文件路径,全路径
cbDownLoadPos[out]:下载进度回调<a href="http://open.xmeye.net/zh/#fDownLoadPosCallBack">fDownLoadPosCallBack</a>函数，可以为空，用户自己调用<a  href="http://open.xmeye.net/zh/#GetDownloadPos">H264_DVR_GetDownloadPos</a>得到进度
dwDataUser[in]:回调函数参数
fDownLoadDataCallBack[out]:数据回调<a href="http://open.xmeye.net/zh/#fRealDataCallBack">fRealDataCallBack</a>函数
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回TRUE，失败返回FALSE
</td></tr>
<tr><td colspan="2" style="background-color:#ccc">&#160</td></tr>
<tr><td style="background-color:#dedebe;width:30%;">V2接口函数</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_GetFileByTime_V2(long lLoginID, H264_DVR_FINDINFO* lpFindInfo, char *sSavedFileDIR, bool bMerge, DownLoadPosCallBack cbDownLoadPos DEF_0_PARAM,long dwDataUser DEF_0_PARAM,fRealDataCallBack_V2 fDownLoadDataCallBack_V2 DEF_0_PARAM);
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">数据回调出来的数据的码流分析过,其他与H264_DVR_GetFileByTime相同
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left;">lLoginID[in]:登陆句柄
sPlayBackFile[in]:下载的录像信息
sSavedFileName[in]:保存的文件路径,全路径
cbDownLoadPos[out]:下载进度回调<a href="http://open.xmeye.net/zh/#fDownLoadPosCallBack">fDownLoadPosCallBack</a>函数，可以为空，用户自己调用<a  href="http://open.xmeye.net/zh/#GetDownloadPos">H264_DVR_GetDownloadPos</a>得到进度
dwDataUser[in]:回调函数参数
fDownLoadDataCallBack[out]:数据回调<a href="http://open.xmeye.net/zh/#fRealDataCallBack">fRealDataCallBack</a>函数
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回TRUE，失败返回FALSE
</td></tr>
<tr><td colspan="2" style="background-color:#000">&#160</td></tr>
<tr><td style="background-color:#9cf;width:30%;">相关函数</td><td style="background-color:#69c">H264_DVR_API int CALL_METHOD H264_DVR_GetDownloadPos(long lFileHandle);</td></tr>
<tr><td style="background-color:#9cf">函数说明
</td><td style="background-color:#69c">获得下载录像的当前位置,可以用于不需要实时显示下载进度的接口,与下载回调函数的功能类似
</td></tr>
<tr><td style="background-color:#9cf">函数参数
</td><td style="background-color:#69c">lFileHandle[in]:下载句柄
</td></tr>
<tr><td style="background-color:#9cf">返回值
</td><td style="background-color:#69c">>= 0为下载进度（百分比），< 0为失败
</table>

## 回放控制

<table>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_PlayBackControl(long lPlayHandle, long lControlCode,long lCtrlValue);
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">网络回放暂停与恢复以及进度控制
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left;">lPlayHandle[in]:回放句柄
lControlCode[in]:控制命令,见enum <a href="http://open.xmeye.net/zh/#PlayBackAction">SDK_PlayBackAction</a>
lCtrlValue[in]:控制值
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回TRUE，失败返回FALSE
</td></tr>
</table>

## 云台控制

<table>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_PTZControl(long lLoginID,int nChannelNo, long lPTZCommand, bool bStop  DEF_PARAM(0), long lSpeed DEF_PARAM(4));
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">云台控制
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left;">lLoginID[in]:	登陆句柄
nChannelNo[in]:	通道号
lPTZCommand[in]:控制命令，见<a herf="http://open.xmeye.net/zh/#ControlType">enum PTZ_ControlType</a>
bStop[in]:    是否是停止
lSpeed[in]:   速度
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回TRUE，失败返回FALSE
</td></tr>
<tr><td colspan="2" style="background-color:#ccc">&#160</td></tr>
<tr><td style="background-color:#dedebe;width:30%;">扩展接口函数</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_PTZControlEx(long lLoginID,int nChannelNo, long lPTZCommand, long lParam1, long lParam2, long lParam3, bool bStop DEF_0_PARAM);
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">扩展云台设置，包括预置点设置，巡航路线，快速定位等
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left;">lLoginID[in]:	登陆句柄
nChannelNo[in]:	通道号
lPTZCommand[in]:控制命令，见enum <a herf="http://open.xmeye.net/zh/#ControlType">enum PTZ_ControlType</a>
lParam1[in]，lParam2[in]，lParam3[in]:</br>
 1、设置，删除，转到预置点时：lParam1为预置点值</br>
 2、加入预置点到巡航，删除巡航中预置点时：lParam1为巡航线路值，lParam2为预置点值,lParam3为时间间隔</br>
 3、开始巡航，停止巡航，清除巡航线路时：lParam1为巡航线路值</br>
 4、云台方向设置时：lParam1为水平步长，lParam2为垂直步长</br>
 5、云台预置点巡航时lParam3为时间间隔</br>

bStop[in]:	是否是停止
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回TRUE，失败返回FALSE
</td></tr>
</table>

## 系统配置

<table>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API long  CALL_METHOD H264_DVR_GetDevConfig(long lLoginID, unsigned long dwCommand, int nChannelNO, char * lpOutBuffer, unsigned long dwOutBufferSize, unsigned long* lpBytesReturned,int waittime DEF_PARAM(1000));
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">远程获取配置参数
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left;">lLoginID[in]:登陆句柄
dwCommand[in]:控制命令,见enum SDK_CONFIG_TYPE
nChannelNO[in]:	-1代表全通道,0-n代表单个通道
lpOutBuffer[out]:接收缓冲，存放输出参数的缓冲区, 根据不同的类型, 输出不同的配置结构, 具体见数据结构定义中各配置结构
dwOutBufferSize[in]:接收缓冲大小（单位字节）
lpBytesReturned[out]:实际返回的缓冲区大小,对应配置结构的大小, (单位字节)
waittime[in]:等待时间
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">= 0:成功，< 0:失败
</td></tr>
<tr><td colspan="2" style="background-color:#ccc">&#160</td></tr>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API long  CALL_METHOD H264_DVR_SetDevConfig(long lLoginID, unsigned long dwCommand, int nChannelNO, char * lpInBuffer, unsigned long dwInBufferSize, int waittime DEF_PARAM(1000));
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">远程设置配置参数
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left;">lLoginID[in]:登陆句柄
dwCommand[in]:控制命令,见enum SDK_CONFIG_TYPE
nChannelNO[in]:	-1代表全通道,0-n代表单个通道
lpOutBuffer[out]:接收缓冲，存放输出参数的缓冲区, 根据不同的类型, 输出不同的配置结构, 具体见数据结构定义中各配置结构
dwOutBufferSize[in]:接收缓冲大小（单位字节）
lpBytesReturned[out]:实际返回的缓冲区大小,对应配置结构的大小, (单位字节)
waittime[in]:等待时间
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">= 0:成功，< 0:失败
</td></tr>
<tr><td colspan="2" style="background-color:#ccc">&#160</td></tr>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_SetConfigOverNet(unsigned long dwCommand, int nChannelNO, char * lpInBuffer, unsigned long dwInBufferSize, int waittime DEF_PARAM(1000));
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">跨网段设置设备配置，目前只支持对网络配置进行设置
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left;">dwCommand[in]:配置类型，E_SDK_CONFIG_SYSNET
nChannelNO[in]:配置通道号，1临时保存,其他为永久保存
lpInBuffer[in]:	存放输入参数的缓冲去，SDK_CONFIG_NET_COMMON_V3结构体地址
dwInBufferSize[in]:输入缓冲区的大小sizeof(SDK_CONFIG_NET_COMMON_V3)单位字节
waittime[in]:等待时间
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">= 0:成功，< 0:失败
</td></tr>
</table>

## 日志管理

<table>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_FindDVRLog(long lLoginID, SDK_LogSearchCondition *pFindParam, SDK_LogList *pRetBuffer, long lBufSize, int waittime DEF_PARAM(2000));
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">日志查询
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left;">lLoginID[in]:登陆句柄
pFindParam[in]:查询条件
pRetBuffer[out]:日志返回信息
lBufSize[in]:接收日志信息大小
waittime:等待时间
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回TRUE，失败返回FALSE
</td></tr>
</table>

## 远程控制

<table>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_ControlDVR(long lLoginID, int type, int waittime DEF_PARAM(2000));
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">设备控制
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left;">lLoginID[in]:登陆句柄
type[in]:	控制类型,0 重启设备，1 清除日志 2 关机 3.恢复记录日志 4.停止记录日志
waittime[in]:等待时间
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回TRUE，失败返回FALSE
</td></tr>
</table>

### 本地升级

<table>
<tr><td style="background-color:#cfc;width:30%;">回调函数</td><td style="background-color:#9c6">typedef void(CALL_METHOD *fUpgradeCallBack) (long lLoginID, long lUpgradechannel,int nTotalSize, int nSendSize, long dwUser);</td></tr>
<tr><td style="background-color:#cfc">回调函数参数说明
</td><td style="background-color:#9c6;text-align:left">lUpgradechannel为升级<a href="http://open.xmeye.net/zh/#Upgrade">H264_DVR_Upgrade</a>函数的返回句柄
nSendSize = -1 说明升级完成  
nSendSize = -2 说明升级出错
nTotalSize = -1时, nSendSize:1-99返回升级进度 
nTotalSize =0时,nSendSize = H264_DVR_NOENOUGH_MEMORY-H264_DVR_INVALID_WIFI_DRIVE 升级错误具体码
其他就是发送进度
云升级增加了这一步:nTotalSize=-2时，nSendSize:0 - 100=下载进度,没有发送进度
</td></tr>
<tr><td colspan="2" style="background-color:#ccc">&#160</td></tr>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_Upgrade(long lLoginID, char *sFileName, int nType DEF_0_PARAM, fUpgradeCallBack cbUpgrade = NULL, long dwUser = 0);
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">设置对前端设备网络升级程序
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left;">lLoginID[in]: 登陆句柄
sFileName[in]:升级文件路径
nType[in]:升级类型,1-开始升级 0-终止升级
cbUpgrade[in]:升级进度回调
dwUser[in]:回调函数参数
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回升级句柄ID，失败返回0
</td></tr>
<tr><td style="background-color:#9cf;width:30%;">相关函数</td><td style="background-color:#69c">H264_DVR_API int CALL_METHOD H264_DVR_GetUpgradeState(long lUpgradeHandle);</td></tr>
<tr><td style="background-color:#9cf">函数说明
</td><td style="background-color:#69c">获取升级状态
</td></tr>
<tr><td style="background-color:#9cf">函数参数
</td><td style="background-color:#69c">lUpgradechannel为升级<a href="http://open.xmeye.net/zh/#Upgrade">H264_DVR_Upgrade</a>函数的返回句柄
</td></tr>
<tr><td style="background-color:#9cf">返回值
</td><td style="background-color:#69c">成功返回1，正在升级返回2，失败返回3
<tr><td colspan="2" style="background-color:#ccc">&#160</td></tr>
<tr><td style="background-color:#9cf;width:30%;">相关函数</td><td style="background-color:#69c">H264_DVR_API long CALL_METHOD H264_DVR_CloseUpgradeHandle(long lUpgradeHandle);</td></tr>
<tr><td style="background-color:#9cf">函数说明
</td><td style="background-color:#69c">停止升级，释放升级句柄
</td></tr>
<tr><td style="background-color:#9cf">函数参数
</td><td style="background-color:#69c">lUpgradechannel为升级<a href="http://open.xmeye.net/zh/#Upgrade">H264_DVR_Upgrade</a>函数的返回句柄
</td></tr>
<tr><td style="background-color:#9cf">返回值
</td><td style="background-color:#69c">成功返回1，失败返回0
</table>

### 云升级

<table>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_Upgrade_Cloud(long lLoginID, SDK_CloudUpgradeVersion *sUpgradeVer, int nType DEF_0_PARAM, fUpgradeCallBack cbUpgrade DEF_0_PARAM, long dwUser DEF_0_PARAM);
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">开始云升级
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left;">lLoginID[in]:登陆句柄  sUpgradeVer[in]:升级的文件信息</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回0，失败返回<0
</td></tr>
<tr><td colspan="2" style="background-color:#ccc">&#160</td></tr>
<tr><td style="background-color:#dedebe;width:30%;">V2接口函数</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_Upgrade_Cloud_V2(long lLoginID, SDK_CloudUpgradeStartReq *sUpgradeVer, int nType DEF_0_PARAM, fUpgradeCallBack cbUpgrade DEF_0_PARAM, long dwUser DEF_0_PARAM);
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">新的云升级
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left;">lLoginID[in]:登陆句柄  sUpgradeVer[in]:升级的文件信息</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回0，失败返回<0
</td></tr>
<tr><td style="background-color:#9cf;width:30%;">相关函数</td><td style="background-color:#69c">H264_DVR_API long CALL_METHOD H264_DVR_StopUpgrade_Cloud(long lHandle);</td></tr>
<tr><td style="background-color:#9cf">函数说明
</td><td style="background-color:#69c">停止云升级
</td></tr>
<tr><td style="background-color:#9cf">函数参数
</td><td style="background-color:#69c">lHandle[in]:云升级<a href="http://open.xmeye.net/zh/#Upgrade_Cloud">H264_DVR_Upgrade_Cloud</a>函数返回值句柄
</td></tr>
<tr><td style="background-color:#9cf">返回值
</td><td style="background-color:#69c">成功返回0，失败返回<0
</table>

### 搜索设备信息

<table>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_SearchDevice(char* szBuf, int nBufLen, int* pRetLen, int nSearchTime);
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">搜索局域网内的设备
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left;">szBuf[out]:	接收缓冲
nBufLen[in]:	接收缓冲大小,sizeof(<a href="http://open.xmeye.net/zh/#NET_COMMON_V2">SDK_CONFIG_NET_COMMON_V2</a>)*n
pRetLen[in]:	返回的大小
nSearchTime[in]:等待时间
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回TRUE，失败返回FALSE
</td></tr>
<tr><td colspan="2" style="background-color:#ccc">&#160</td></tr>
<tr><td style="background-color:#cfc;width:30%;">回调函数</td><td style="background-color:#9c6">typedef  void ( CALL_METHOD *pfSearchDeviceCallBack)(SDK_CONFIG_NET_COMMON_V2  *pNetCom , unsigned long userData);</td></tr>
<tr><td style="background-color:#cfc">回调函数参数说明
</td><td style="background-color:#9c6">自定义回调函数获取设备信息
</td></tr>
<tr><td style="background-color:#dedebe;width:30%;">V2接口函数</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_SearchDevice_V2(pfSearchDeviceCallBack pfNetCom,unsigned long userData, int nSearchTime);
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">搜索局域网内的设备，搜索局域网内的设备V2版本
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left;">pfNetCom[out]:	回调函数
userData[in]:	回调参数
nSearchTime[in]:等待时间
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回TRUE，失败返回FALSE
<tr><td style="background-color:#dedebe;width:30%;">扩展接口函数</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_SearchDevice_IPV6(char* szBuf, int nBufLen, int* pRetLen, int nSearchTime, int ntype);
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">搜索局域网内IPV6的设备
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left;">szBuf[out]:	接收缓冲
nBufLen[in]:	接收缓冲大小,sizeof(<a href="http://open.xmeye.net/zh/#NET_COMMON_V2">SDK_CONFIG_NET_COMMON_V2</a>))*n
pRetLen[in]:	返回的大小
nSearchTime[in]:等待时间
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回TRUE，失败返回FALSE
</td></tr>
</table>

## 语音对讲

<table>
<tr><td style="background-color:#cfc;width:30%;">回调函数</td><td style="background-color:#9c6">typedef void (CALL_METHOD *pfAudioDataCallBack)(long lVoiceHandle, char *pDataBuf, long dwBufSize, char byAudioFlag, long dwUser);</td></tr>
<tr><td style="background-color:#cfc">回调函数参数说明
</td><td style="background-color:#9c6;">语音对讲的音频数据回调函数原形
</td></tr>
<tr><td colspan="2" style="background-color:#ccc">&#160</td></tr>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_StartVoiceCom_MR(long lLoginID, pfAudioDataCallBack pVcb, long dwDataUser);
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">开始对讲
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left;">lLoginID[in]:  登陆句柄
pVcb[out]:	接收对讲数据回调	
dwDataUser[in]:回调函数参数
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">> 0为对讲句柄，<= 0为失败
</td></tr>
<tr><td style="background-color:#9cf;width:30%;">相关函数</td><td style="background-color:#69c">H264_DVR_API bool CALL_METHOD H264_DVR_VoiceComSendData(long lVoiceHandle, char *pSendBuf, long lBufSize);</td></tr>
<tr><td style="background-color:#9cf">函数说明
</td><td style="background-color:#69c">发送对讲数据，转发PC采集到的语音对讲数据
</td></tr>
<tr><td style="background-color:#9cf">函数参数
</td><td style="background-color:#69c">lVoiceHandle[in]:<a href="http://open.xmeye.net/zh/#StartVoiceCom_MR">H264_DVR_StartVoiceCom_MR</a>函数的返回值句柄
pSendBuf[in]:	对讲数据
lBufSize[in]:	对讲数据大小
</td></tr>
<tr><td style="background-color:#9cf">返回值
</td><td style="background-color:#69c">成功返回TRUE，失败返回FALSE
<tr><td colspan="2" style="background-color:#ccc">&#160</td></tr>
<tr><td style="background-color:#9cf;width:30%;">相关函数</td><td style="background-color:#69c">H264_DVR_API bool CALL_METHOD H264_DVR_StopVoiceCom(long lVoiceHandle);</td></tr>
<tr><td style="background-color:#9cf">函数说明
</td><td style="background-color:#69c">停止对讲
</td></tr>
<tr><td style="background-color:#9cf">函数参数
</td><td style="background-color:#69c">lVoiceHandle[in]:<a href="http://open.xmeye.net/zh/#StartVoiceCom_MR">H264_DVR_StartVoiceCom_MR</a>函数的返回值句柄
</td></tr>
<tr><td style="background-color:#9cf">返回值
</td><td style="background-color:#69c">成功返回TRUE，失败返回FALSE
<tr><td colspan="2" style="background-color:#ccc">&#160</td></tr>
<tr><td style="background-color:#9cf;width:30%;">相关函数</td><td style="background-color:#69c">H264_DVR_API bool CALL_METHOD H264_DVR_SetTalkMode(long lLoginID, SDK_AudioInFormatConfig* pTalkMode);</td></tr>
<tr><td style="background-color:#9cf">函数说明
</td><td style="background-color:#69c">设置对讲音频编码方式，用户可以不设置，默认为G711A编码
</td></tr>
<tr><td style="background-color:#9cf">函数参数
</td><td style="background-color:#69c">lLoginID[in]: 登陆句柄
pTalkMode[in]: 对讲模式结构体 参见:<a href="http://open.xmeye.net/zh/#AudioInFormatConfig">SDK_AudioInFormatConfig</a>通道号,-1代表全通道，0-n代表单个通道
</td></tr>
<tr><td style="background-color:#9cf">返回值
</td><td style="background-color:#69c">成功返回TRUE，失败返回FALSE
</table>
</table>

## 录像模式设置

<table>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_StartDVRRecord(long lLoginID, int nChannelNo ,long lRecordType);
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">设置录像模式
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left;">lLoginID[in]:  登陆句柄
nChannelNo[in]: 通道号,-1代表全通道，0-n代表单个通道
lRecordType[in]:录像模式,见枚举enum <a href="http://open.xmeye.net/zh/#RecordModeTypes">SDK_RecordModeTypes</a>
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回TURE，失败返回FALSE
</td></tr>
<tr><td style="background-color:#9cf;width:30%;">相关函数</td><td style="background-color:#69c">H264_DVR_API bool CALL_METHOD H264_DVR_StopDVRRecord(long lLoginID, int nChannelNo);
</td></tr>
<tr><td style="background-color:#9cf">函数说明
</td><td style="background-color:#69c">关闭录像
</td></tr>
<tr><td style="background-color:#9cf">函数参数
</td><td style="background-color:#69c">lLoginID[in]: 登陆句柄
nChannelNo[in]: 通道号,-1代表全通道，0-n代表单个通道
</td></tr>
<tr><td style="background-color:#9cf">返回值
</td><td style="background-color:#69c">成功返回TRUE，失败返回FALSE
</table>

## 设置系统时间

<table>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_SetSystemDateTime(long lLoginID, SDK_SYSTEM_TIME *pSysTime);
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">设置系统时间
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left;">lLoginID[in]:登陆句柄
pSysTime[in]:时间-参见枚举<a href="http://open.xmeye.net/zh/#SYSTEM_TIME">SDK_SYSTEM_TIME</a>
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回TURE，失败返回FALSE
</td></tr>
</table>

## 获取设置运行状态信息

<table>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_GetDVRWorkState(long lLoginID, SDK_DVR_WORKSTATE *pWorkState);
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">获取设备工作状态信息
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left;">lLoginID[in]: 登陆句柄
pWorkState[out]:设备的工作状态-参见<a href="http://open.xmeye.net/zh/#WORKSTATE">SDK_DVR_WORKSTATE</a>结构体</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回TURE，失败返回FALSE
</td></tr>
</table>

## 网络键盘

<table>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_ClickKey(long lLoginID, SDK_NetKeyBoardData *pKeyBoardData);
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">发送网络键盘按键消息
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left;">lLoginID[in]: 登陆句柄
pKeyBoardData[in]:网络键盘参数-参见<a href="http://open.xmeye.net/zh/#NetKeyBoardData">SDK_NetKeyBoardData<a>
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回TURE，失败返回FALSE
</td></tr>
</table>

## 网络报警

<table>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_SendNetAlarmMsg(long lLoginID, SDK_NetAlarmInfo *pAlarmInfo);
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">发送网络报警信息
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left;">lLoginID[in]: 登陆句柄
pAlarmInfo[in]:网络报警参数-参见<a href="http://open.xmeye.net/zh/#NetAlarmInfo">SDK_NetAlarmInfo</a>
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回TURE，失败返回FALSE
</td></tr>
</table>

## 报警中心

<table>
<tr><td style="background-color:#cfc;width:30%;">回调函数</td><td style="background-color:#9c6">typedef bool (CALL_METHOD *fMessCallBack)(long lLoginID, char *pBuf, unsigned long dwBufLen, long dwUser);</td></tr>
<tr><td style="background-color:#cfc">回调函数参数说明
</td><td style="background-color:#9c6;text-align:left">消息（报警,主动注册）回调原形
1.报警,pBuf说明,SDK_AlarmInfo alarmInfo;memcpy ( &alarmInfo, pBuf, dwBufLen );
2.主动注册,pBuf说明,H264_DVR_ACTIVEREG_INFO activeInfo;memcpy ( &alarmInfo, pBuf, dwBufLen );
</td></tr>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_StartAlarmCenterListen(int nPort, fMessCallBack cbAlarmCenter, unsigned long dwDataUser);
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">启动报警中心监听
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left;">nPort[in]:监听端口号
cbAlarmCenter[out]:数据回调<a href="http://open.xmeye.net/zh/#fMessCallBack">fMessCallBack</a>函数
dwDataUser[in]:回调函数参数
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回TURE，失败返回FALSE
</td></tr>
<tr><td style="background-color:#9cf;width:30%;">相关函数</td><td style="background-color:#69c">H264_DVR_API bool CALL_METHOD H264_DVR_StopAlarmCenterListen();
</td></tr>
<tr><td style="background-color:#9cf">函数说明
</td><td style="background-color:#69c">关闭报警中心监听
</td></tr>
<tr><td style="background-color:#9cf">函数参数
</td><td style="background-color:#69c">无</td></tr>
<tr><td style="background-color:#9cf">返回值
</td><td style="background-color:#69c">成功返回TURE，失败返回FALSE
</td></tr>
</table>

## 磁盘管理

<table>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API int CALL_METHOD H264_DVR_StorageManage(long lLoginID, SDK_StorageDeviceControl *pStorageCtl);
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">对硬盘进行分区,格式化等等操作
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;">lLoginID[in]: 登陆句柄  pStorageCtl[in]:操作参数-参见<a href="http://open.xmeye.net/zh/#StorageDeviceControl">SDK_StorageDeviceControl</a>
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">> 0为成功，<=0为失败
</td></tr>
</table>

## 抓图

<table>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_CatchPic(long lLoginID, int nChannel, char *sFileName);
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973;text-align:left">设备端抓图,即抓设备端发过来的即时的一张图片的内存buf</br>
1.需要设备配置里面有抓图配置选项该接口才有效</br>
2.如果满足1，默认抓出来的分辨率是D1，如果想抓跟视频分辨率一样的图片，就需要修改编码设置里的抓图分辨率，</br>
（如果编码设置没有抓图分辨率选项，则需要定制支持该项的程序）


</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left">lLoginID[in]: 登陆句柄
nChannel[in]: 通道号
sFileName[in]:保存路径
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回TURE，失败返回FALSE（通过<a href="http://open.xmeye.net/zh/#GetLastError">H264_DVR_GetLastError</a>可查看具体错误值）
</td></tr>
<tr><td colspan="2" style="background-color:#ccc">&#160</td></tr>
<tr><td style="background-color:#dedebe;width:30%;">扩展接口函数</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_CatchPicInBuffer(long lLoginID, int nChannel, char *pBuffer, int nBufLen, int *pPicLen);
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973;text-align:left">设备端抓图,即抓设备端发过来的即时的一张图片的内存buf
1.需要设备配置里面有抓图配置选项该接口才有效
2.如果满足1，默认抓出来的分辨率是D1，如果想抓跟视频分辨率一样的图片，就需要修改编码设置里的抓图分辨率，
（如果编码设置没有抓图分辨率选项，则需要定制支持该项的程序）
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left">lLoginID[in]: 登陆句柄
nChannel[in]: 通道号
pBuffer[out]:接收缓冲
nBufLen[in]:接收缓冲的大小
pPicLen[in]:实际返回的大小
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回TURE，失败返回FALSE（通过<a href="http://open.xmeye.net/zh/#GetLastError">H264_DVR_GetLastError</a>可查看具体错误值）
</td></tr>
</table>

## 透明232,485

<table>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_SerialWrite(long lLoginID, SERIAL_TYPE nType, char *pBuffer, int nBufLen);
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">通过串口向设备写数据
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left;">lLoginID[in]:登陆句柄
nType[in]:串口类型-参见枚举<a href="http://open.xmeye.net/zh/#SERIAL_TYPE">SERIAL_TYPE</a>
pBuffer[in]: 数据
nBufLen[in]: 数据长度
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回TURE，失败返回FALSE
</td></tr>
<tr><td style="background-color:#9cf;width:30%;">相关函数</td><td style="background-color:#69c">H264_DVR_API bool CALL_METHOD H264_DVR_SerialRead(long lLoginID, SERIAL_TYPE nType, char *pBuffer, int nBufLen, int *pReadLen);
</td></tr>
<tr><td style="background-color:#9cf">函数说明
</td><td style="background-color:#69c">通过串口从设备读数据
</td></tr>
<tr><td style="background-color:#9cf">函数参数
</td><td style="background-color:#69c;text-align:left;">lLoginID[in]: 登陆句柄
nType[in]: 串口类型-参见枚举<a href="http://open.xmeye.net/zh/#SERIAL_TYPE">SERIAL_TYPE</a>
pBuffer[out]: 接收数据
nBufLen[in]: 接收数据长度
pReadLen[out]:收到的数据长度
</td></tr>
<tr><td style="background-color:#9cf">返回值
</td><td style="background-color:#69c">成功返回TURE，失败返回FALSE
</td></tr>
</table>

## 获取DDNS信息

<table>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API int CALL_METHOD H264_DVR_GetDDNSInfo(SearchMode &searchmode, DDNS_INFO *pDevicInfo, int maxDeviceNum, int &nretNum);
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">获取DDNS信息
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left">searchmode[in]:搜索信息
pDevicInfo[out]:DDNS信息
maxDeviceNum[in]:最大设备数
nretNum[out]:得到的设备数
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">>= 0为成功，< 0为失败
</td></tr>
</table>

## 支持强迫I帧

<table>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_MakeKeyFrame(long lLoginID, int nChannel, int nStream);
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">强制I帧
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left">lLoginID[in]:登陆句柄
nChannel[in]:通道号
nStream[in]: 码流类型,0表示主码流，为1表示子码流
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回TURE，失败返回FALSE
</td></tr>
</table>

## 设置登录设备超时时间和尝试次数

<table>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_SetConnectTime(long nWaitTime, long nTryTimes);
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">设置登录设备超时时间和尝试次数
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left">nWaitTime[in]:单位ms不设置时默认5000ms,
nTryTimes[in]:次数,不设置时默认3次
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回TURE，失败返回FALSE
</td></tr>
</table>

## 透明串口

<table>
<tr><td style="background-color:#cfc;width:30%;">回调函数</td><td style="background-color:#9c6">typedef void (CALL_METHOD *fTransComCallBack) (long lLoginID, long lTransComType, char *pBuffer, unsigned long dwBufSize, unsigned long dwUser);</td></tr>
<tr><td style="background-color:#cfc">回调函数参数说明
</td><td style="background-color:#9c6;">透明串口回调函数原形
</td></tr>
<tr><td style="background-color:#cfc">回调参数
</td><td style="background-color:#9c6;">lTransComType：串口类型，参见枚举<a href="http://open.xmeye.net/zh/#SERIAL_TYPE">SERIAL_TYPE</a>
</td></tr>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_OpenTransComChannel(long lLoginID, TransComChannel *TransInfo, fTransComCallBack cbTransCom, unsigned long lUser);
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">创建透明串口通道
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left;">lLoginID[in]:	登陆句柄
TransInfo[in]:	透明串口参数
cbTransCom[out]: 设备数据回调<a href="http://open.xmeye.net/zh/#fTransComCallBack">fTransComCallBack</a>函数
lUser[in]:  回调函数参数
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回TURE，失败返回FALSE
</td></tr>
<tr><td style="background-color:#9cf;width:30%;">相关函数</td><td style="background-color:#69c">H264_DVR_API bool CALL_METHOD H264_DVR_CloseTransComChannel(long lLoginID, SERIAL_TYPE nType);</td></tr>
<tr><td style="background-color:#9cf">函数说明
</td><td style="background-color:#69c">关闭透明串口通道
</td></tr>
<tr><td style="background-color:#9cf">函数参数
</td><td style="background-color:#69c;text-align:left;">lLoginID[in]:登陆句柄
nType[in]:透明串口类型，参见枚举<a href="http://open.xmeye.net/zh/#SERIAL_TYPE">SERIAL_TYPE</a>
</td></tr>
<tr><td style="background-color:#9cf">返回值
</td><td style="background-color:#69c">成功返回TURE，失败返回FALSE
</td></tr>
<tr><td style="background-color:#9cf;width:30%;">相关函数</td><td style="background-color:#69c">H264_DVR_API bool CALL_METHOD H264_DVR_GetDeviceState(long lLoginID, SDK_State_Type type, char *pState)</td></tr>
<tr><td style="background-color:#9cf">函数说明
</td><td style="background-color:#69c">获取状态信息
</td></tr>
<tr><td style="background-color:#9cf">函数参数
</td><td style="background-color:#69c;text-align:left;">lLoginID[in]:设备登陆句柄
nType[in]:具体参考<a href="http://open.xmeye.net/zh/#State_Type">SDK_State_Type</a>
pState[in]:数据返回
</td></tr>
<tr><td style="background-color:#9cf">返回值
</td><td style="background-color:#69c">成功返回TURE，失败返回FALSE
</td></tr>
</table>

## DVR本地用户操作界面截图

<table>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_CatchPicUI(long lLoginID,char *saveFileName,int type DEF_PARAM(1));</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">获取DVR本地端用户操作界面截图
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left">lLoginID[in]:登陆句柄
saveFileName[in]:图片保存路径
type[in]:保存图片类型,1:为全图片 2:活动区域图片
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回TURE，失败返回FALSE
</td></tr>
</table>

## 客户端录像

<table>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_StartLocalRecord(long lRealHandle,char*szSaveFileName,long type=0);</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">开始本地录像
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left">lRealHandle[in]:播放句柄<a href="http://open.xmeye.net/zh/#RealPlay">H264_DVR_RealPlay</a>函数的返回值
szSaveFileName[in]:录像路径
type[in]:录像类型（0：文件名后缀为.h264；2：文件名后缀.avi），默认为0
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回TURE，失败返回FALSE
</td></tr>
<tr><td style="background-color:#9cf;width:30%;">相关函数</td><td style="background-color:#69c">H264_DVR_API bool CALL_METHOD H264_DVR_StopLocalRecord(long lRealHandle);</td></tr>
<tr><td style="background-color:#9cf">函数说明
</td><td style="background-color:#69c">关闭本地录像
</td></tr>
<tr><td style="background-color:#9cf">函数参数
</td><td style="background-color:#69c;">lRealHandle[in]:播放句柄<a href="http://open.xmeye.net/zh/#RealPlay">H264_DVR_RealPlay</a>函数的返回值
</td></tr>
<tr><td style="background-color:#9cf">返回值
</td><td style="background-color:#69c">成功返回TURE，失败返回FALSE
</td></tr>
</table>

## 打开语音对讲

<table>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_StartLocalVoiceCom(long lLoginID);
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">打开对讲
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;">lLoginID[in]:登陆句柄<a href="http://open.xmeye.net/zh/#Login">H264_DVR_Login</a>函数的返回值
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回TURE，失败返回FALSE
</td></tr>
</table>

## 客户端音频

<table>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_OpenSound(long lHandle);
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">打开通道音频,预览/回放/本地播放一个函数
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;">lRealHandle[in]:播放句柄<a href="http://open.xmeye.net/zh/#RealPlay">H264_DVR_RealPlay</a>函数的返回值
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回TURE，失败返回FALSE
</td></tr>
<tr><td style="background-color:#9cf;width:30%;">相关函数</td><td style="background-color:#69c">H264_DVR_API bool CALL_METHOD H264_DVR_CloseSound(long lHandle);</td></tr>
<tr><td style="background-color:#9cf">函数说明
</td><td style="background-color:#69c">关闭通道音频,预览/回放/本地播放一个函数
</td></tr>
<tr><td style="background-color:#9cf">函数参数
</td><td style="background-color:#69c;text-align:left">lRealHandle[in]:播放句柄<a href="http://open.xmeye.net/zh/#RealPlay">H264_DVR_RealPlay</a>函数或<a href="http://open.xmeye.net/zh/#PlayBackByName">H264_DVR_PlayBackByName</a>函数或<a href="http://open.xmeye.net/zh/#StartLocalPlay">H264_DVR_StartLocalPlay</a>函数或<a href="http://open.xmeye.net/zh/#PlayBackByTimeEx">H264_DVR_PlayBackByTimeEx</a>函数的返回值
</td></tr>
<tr><td style="background-color:#9cf">返回值
</td><td style="background-color:#69c">成功返回TURE，失败返回FALSE
</td></tr>
</table>

## 客户端抓图

<table>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_LocalCatchPic(long lHandle,char*szSaveFileName);
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">抓本地图片,预览/回放/本地播放一个函数
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left">lRealHandle[in]:播放句柄<a href="http://open.xmeye.net/zh/#RealPlay">H264_DVR_RealPlay</a>函数或<a href="http://open.xmeye.net/zh/#PlayBackByName">H264_DVR_PlayBackByName</a>函数或<a href="http://open.xmeye.net/zh/#StartLocalPlay">H264_DVR_StartLocalPlay</a>函数或<a href="http://open.xmeye.net/zh/#PlayBackByTimeEx">H264_DVR_PlayBackByTimeEx</a>函数的返回值
szSaveFileName[in]:保存图片的路径
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回TURE，失败返回FALSE
</td></tr>
</table>

## 播放定位

<table>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API float CALL_METHOD H264_DVR_GetPlayPos(long lPlayHandle);
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">获取播放位置（百分比），用于回放和本地播放,回放时传窗口句柄该接口才有效
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left">lRealHandle[in]:播放句柄<a href="http://open.xmeye.net/zh/#PlayBackByName">H264_DVR_PlayBackByName</a>函数或<a href="http://open.xmeye.net/zh/#StartLocalPlay">H264_DVR_StartLocalPlay</a>函数或<a href="http://open.xmeye.net/zh/#PlayBackByTimeEx">H264_DVR_PlayBackByTimeEx</a>函数的返回值
szSaveFileName[in]:保存图片的路径
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">返回播放进度（百分比）
</td></tr>
<tr><td style="background-color:#9cf;width:30%;">相关函数</td><td style="background-color:#69c">H264_DVR_API bool CALL_METHOD H264_DVR_SetPlayPos(long lPlayHandle,float fRelativPos);
</td></tr>
<tr><td style="background-color:#9cf">函数说明
</td><td style="background-color:#69c">设置播放位置（百分比）,用于回放，本地播放(本地回放时传窗口句柄该接口才有效)
</td></tr>
<tr><td style="background-color:#9cf">函数参数
</td><td style="background-color:#69c;text-align:left">lRealHandle[in]:播放句柄<a href="http://open.xmeye.net/zh/#PlayBackByName">H264_DVR_PlayBackByName</a>函数或<a href="http://open.xmeye.net/zh/#StartLocalPlay">H264_DVR_StartLocalPlay</a>函数或<a href="http://open.xmeye.net/zh/#PlayBackByTimeEx">H264_DVR_PlayBackByTimeEx</a>函数的返回值
</td></tr>
<tr><td style="background-color:#9cf">返回值
</td><td style="background-color:#69c">成功返回TURE，失败返回FALSE
</td></tr>
</table>

## 设置信息帧回调

<table>
<tr><td style="background-color:#cfc;width:30%;">回调函数</td><td style="background-color:#9c6">typedef void (CALL_METHOD  *InfoFramCallBack)(long lPlayHand, long nType, LPCSTR pBuf,long nSize, long nUser);</td></tr>
<tr><td style="background-color:#cfc">回调函数参数说明
</td><td style="background-color:#9c6;">信息帧回调设置 nType: （0x03 代表gprs信息帧）
</td></tr>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_SetInfoFrameCallBack(long lPlayHandle,InfoFramCallBack callback,long user);
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">设置信息帧回调
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left">lRealHandle[in]:播放句柄<a href="http://open.xmeye.net/zh/#RealPlay">H264_DVR_RealPlay</a>函数或<a href="http://open.xmeye.net/zh/#PlayBackByName">H264_DVR_PlayBackByName</a>函数或<a href="http://open.xmeye.net/zh/#StartLocalPlay">H264_DVR_StartLocalPlay</a>函数或<a href="http://open.xmeye.net/zh/#PlayBackByTimeEx">H264_DVR_PlayBackByTimeEx</a>函数的返回值
callback[out]:	信息帧回调
user[in]:回调函数参数
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回TURE，失败返回FALSE
</td></tr>
</td></tr>
</table>

## 客户端视频颜色

<table>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_LocalGetColor(long lHandle, DWORD nRegionNum, LONG *pBrightness, LONG *pContrast, LONG *pSaturation, LONG *pHue)
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">获取播放视频颜色信息，预览/回放/本地播放一个函数
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left">lHandle[in]:实时播放句柄或者回放句柄或本地播放句柄<a href="http://open.xmeye.net/zh/#RealPlay">H264_DVR_RealPlay</a>函数或<a href="http://open.xmeye.net/zh/#PlayBackByName">H264_DVR_PlayBackByName</a>函数或<a href="http://open.xmeye.net/zh/#StartLocalPlay">H264_DVR_StartLocalPlay</a>函数或<a href="http://open.xmeye.net/zh/#PlayBackByTimeEx">H264_DVR_PlayBackByTimeEx</a>函数的返回值
nRegionNum[in]:显示区域,如果只有一个显示区域(通常情况)设为0
pBrightness[out]:亮度	 
pContrast[out]:	对比度
pSaturation[out]:饱和度
pHue[out]:色调
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回TURE，失败返回FALSE
</td></tr>
<tr><td colspan="2" style="background-color:#ccc">&#160</td></tr>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_LocalSetColor(long lHandle, DWORD nRegionNum, LONG nBrightness, LONG nContrast, LONG nSaturation, LONG nHue);
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">设置播放视频颜色信息，预览/回放/本地播放一个函数
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left">lHandle[in]:实时播放句柄或者回放句柄或本地播放句柄<a href="http://open.xmeye.net/zh/#RealPlay">H264_DVR_RealPlay</a>函数或<a href="http://open.xmeye.net/zh/#PlayBackByName">H264_DVR_PlayBackByName</a>函数或<a href="http://open.xmeye.net/zh/#StartLocalPlay">H264_DVR_StartLocalPlay</a>函数或<a href="http://open.xmeye.net/zh/#PlayBackByTimeEx">H264_DVR_PlayBackByTimeEx</a>函数的返回值
nRegionNum[in]:显示区域,如果只有一个显示区域(通常情况)设为0
pBrightness[out]:亮度	 
pContrast[out]:	对比度
pSaturation[out]:饱和度
pHue[out]:色调
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回TURE，失败返回FALSE
</td></tr>
</table>

## 播放客户端本地文件

<table>
<tr><td style="background-color:#cfc;width:30%;">回调函数</td><td style="background-color:#9c6">typedef void (CALL_METHOD * fPlayDrawCallBack)(long lPlayHand,HDC hDc,long nUser);</td></tr>
<tr><td style="background-color:#cfc">回调函数参数说明
</td><td style="background-color:#9c6;">RigisterDraw回调原形
</td></tr>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_StartLocalPlay(char*pFileName,void* hWnd,fPlayDrawCallBack drawCallBack=0,long user=0)
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">播放本地.h264视频文件
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left">pFileName[in]:录像文件路径
hWnd[in]:播放窗口句柄
drawCallBack[out]:叠加绘制回调函数（不用可以设为NULL）
user[in]:回调函数参数
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">失败返回0，成功返回播放ID(本地播放句柄)
</td></tr>
<tr><td style="background-color:#9cf;width:30%;">相关函数</td><td style="background-color:#69c">H264_DVR_API bool CALL_METHOD H264_DVR_StopLocalPlay(long lPlayHandle);
</td></tr>
<tr><td style="background-color:#9cf">函数说明
</td><td style="background-color:#69c">关闭本地播放
</td></tr>
<tr><td style="background-color:#9cf">函数参数
</td><td style="background-color:#69c;">lPlayHandle[in]:本地播放句柄<a href="http://open.xmeye.net/zh/#StartLocalPlay">H264_DVR_StartLocalPlay</a>函数的返回值
</td></tr>
<tr><td style="background-color:#9cf">返回值
</td><td style="background-color:#69c">成功返回TURE，失败返回FALSE
</td></tr>
<tr><td colspan="2" style="background-color:#ccc">&#160</td></tr>
<tr><td style="background-color:#cfc;width:30%;">回调函数</td><td style="background-color:#9c6">typedef void (CALL_METHOD * fLocalPlayFileCallBack)(long lPlayHand, long nUser);</td></tr>
<tr><td style="background-color:#cfc">回调函数参数说明
</td><td style="background-color:#9c6;">本地播放结束回调原形
</td></tr>
<tr><td style="background-color:#9cf;width:30%;">相关函数</td><td style="background-color:#69c">H264_DVR_API bool CALL_METHOD H264_DVR_SetFileEndCallBack(long lPlayHandle,fLocalPlayFileCallBack callBack,long user)
</td></tr>
<tr><td style="background-color:#9cf">函数说明
</td><td style="background-color:#69c">本地文件播放结束回调
</td></tr>
<tr><td style="background-color:#9cf">函数参数
</td><td style="background-color:#69c;text-align:left">lPlayHandle[in]:回放句柄或本地播放句柄<a href="http://open.xmeye.net/zh/#StartLocalPlay">H264_DVR_StartLocalPlay</a>函数的返回值
callBack[out]:播放结束回调
user[in]:回调函数参数
</td></tr>
<tr><td style="background-color:#9cf">返回值
</td><td style="background-color:#69c">成功返回TURE，失败返回FALSE
</td></tr>
<tr><td colspan="2" style="background-color:#ccc">&#160</td></tr>
<tr><td style="background-color:#9cf;width:30%;">相关函数</td><td style="background-color:#69c">H264_DVR_API bool CALL_METHOD H264_DVR_LocalPlayCtrl(long lPlayHandle,SDK_LoalPlayAction action,long lCtrlValue)
</td></tr>
<tr><td style="background-color:#9cf">函数说明
</td><td style="background-color:#69c">pc端文件播放控制（播放，停止，恢复，快发，慢放）
</td></tr>
<tr><td style="background-color:#9cf">函数参数
</td><td style="background-color:#69c;text-align:left">lPlayHandle[in]:回放句柄或本地播放句柄<a href="http://open.xmeye.net/zh/#StartLocalPlay">H264_DVR_StartLocalPlay</a>函数的返回值
action[in]:播放控制类型<a href="http://open.xmeye.net/zh/#LoalPlayAction">SDK_LoalPlayAction</a>
lCtrlValue[in]: 控制速度快放（1,2,3,4级别），和慢放（1,2,3,4级别）
</td></tr>
<tr><td style="background-color:#9cf">返回值
</td><td style="background-color:#69c">成功返回TURE，失败返回FALSE
</td></tr>
</table>

## 绑定本地IP

<table>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_SetLocalBindAddress(char*szIP);
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">设置本地ip,socket通信套接字绑定的ip（在多网卡的时候，可以指定绑定的ip地址）</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;">szIP[in]:绑定的ip地址
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回TURE，失败返回FALSE
</td></tr>
</table>

## 设置上报数据回调

<table>
<tr><td style="background-color:#cfc;width:30%;">回调函数</td><td style="background-color:#9c6">typedef void (CALL_METHOD *fUploadDataCallBack) (long lLoginID, long UploadType, char *pBuffer, unsigned long dwBufSize, unsigned long dwUser)</td></tr>
<tr><td style="background-color:#cfc">回调函数参数说明
</td><td style="background-color:#9c6;">数据上传通道回调函数原型
</td></tr>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_StartUploadData(long lLoginID,UploadDataType upLoadType,fUploadDataCallBack callBack,long lUser);
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">打开数据上报，目前只有车载数据上传
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left">lLoginID[in]:登陆句柄
upLoadType[in]:上报数据类型
callBack[out]:上报数据回调
lUser[in]:回调函数参数
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回TURE，失败返回FALSE
</td></tr>
<tr><td style="background-color:#9cf;width:30%;">相关函数</td><td style="background-color:#69c">H264_DVR_API bool CALL_METHOD H264_DVR_StopUploadData(long lLoginID,UploadDataType upLoadType)
</td></tr>
<tr><td style="background-color:#9cf">函数说明
</td><td style="background-color:#69c">停止上报数据
</td></tr>
<tr><td style="background-color:#9cf">函数参数
</td><td style="background-color:#69c;">lLoginID[in]:登陆句柄      upLoadType[in]:上报数据类型
</td></tr>
<tr><td style="background-color:#9cf">返回值
</td><td style="background-color:#69c">成功返回TURE，失败返回FALSE
</td></tr>
</table>

## 支持设备主动注册

<table>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_StartActiveRigister(int nPort, fMessCallBack cbFunc, unsigned long dwDataUser);
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">开始主动注册
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left">nPort[in]:监听端口号,0<=nPort<=65535
cbFunc[out]: 注册上线回调函数<a href="http://open.xmeye.net/zh/#fMessCallBack">fMessCallBack</a>
dwDataUser[in]:回调函数参数
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回TURE，失败返回FALSE
</td></tr>
<tr><td style="background-color:#9cf;width:30%;">相关函数</td><td style="background-color:#69c">H264_DVR_API bool CALL_METHOD H264_DVR_StopActiveRigister();
</td></tr>
<tr><td style="background-color:#9cf">函数说明
</td><td style="background-color:#69c">关闭主动注册
</td></tr>
<tr><td style="background-color:#9cf">函数参数
</td><td style="background-color:#69c;">无
</td></tr>
<tr><td style="background-color:#9cf">返回值
</td><td style="background-color:#69c">成功返回TURE，失败返回FALSE
</td></tr>
</table>

## 设置子连接断开回调

<table>
<tr><td style="background-color:#cfc;width:30%;">回调函数</td><td style="background-color:#9c6">typedef void (CALL_METHOD *fSubDisConnectCallBack)(long lLoginID, SubConnType type, long nChannel, long dwUser);</td></tr>
<tr><td style="background-color:#cfc">回调函数参数说明
</td><td style="background-color:#9c6;">子连接断线回调
</td></tr>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_SetSubDisconnectCallBack(fSubDisConnectCallBack callBack,DWORD userData);</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">检测子连接异常断开
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left">callBack[out]:子连接断开回调<a href="http://open.xmeye.net/zh/#fSubDisConnectCallBack">fSubDisConnectCallBack</a>
userData[in]: 回调函数参数
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回TURE，失败返回FALSE
</td></tr>
</table>

## 设置心跳包时间以及断线时间

<table>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_SetKeepLifeTime(long lLoginID,unsigned int perKeeplifeTime,unsigned int detectDisconTime);</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">设置保活时间,perKeeplifeTime(心跳间隔):默认10秒,detectDisconTime(断线检测时间):默认60秒
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left">lLoginID[in]:登陆句柄
perKeeplifeTime[in]: 保活时间(单位秒)
detectDisconTime[in]:断线检测时间(单位秒)
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回TURE，失败返回FALSE
</td></tr>
</table>

## 搜索设备局域网设备

<table>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_SearchDeviceEX(long lLoginID,SDK_NetDevList *pDevlist,SDK_TransferProtocol_V2 transferProtocol DEF_PARAM(SDK_TRANSFER_PROTOCOL_NETIP),int waittime DEF_PARAM(15000));</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">设备搜索到的设备，与设备在同一个局域网的设备,设备去搜索，然后返回结果(H264_DVR_SearchDevice这个接口是sdk本身去搜索,两者返回的结果是一致的
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left">lLoginID[in]:登陆句柄
pDevlist[out]:设备列表
transferProtocol[in]:传输协议,见enum <a href="http://open.xmeye.net/zh/#TransferProtocol_V2">SDK_TransferProtocol_V2</a>
waittime[in]:等待时间
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回TURE，失败返回FALSE
</td></tr>
</table>

## 获取公网IP

<table>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API bool CALL_METHOD H264_DVR_Get_OutNet_IP(const char *uuid, char* ip);
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">查询某个设备的外网ip
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;">uuid[in]:设备序列号     ip[out]: 外网ip
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回TURE，失败返回<= 0
</td></tr>
</table>

## 获取智能插座控制命令

<table>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_GetDevConfig_Json(long lLoginID, const char* dwCommand, int nChannelNO,char * lpOutBuffer,unsigned long dwOutBufferSize,unsigned long* lpBytesReturned,int waittime DEF_PARAM(1000));
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">获取智能插座配置
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left">lLoginID[in]:登陆句柄dwCommand[in]:json名
nChannelNO[in]:通道号,-1:得到全通道配置,0-n:得到单个通道的配置,从0开始
lpOutBuffer[out]:接收json缓冲
dwOutBufferSize[in]:接收缓冲大小
lpBytesReturned[out]:得到的缓冲大小(字节)
waittime[in]:等待时间
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功大于0，失败小于等于0
</td></tr>
</table>

## 设置智能插座控制命令

<table>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_SetDevConfig_Json(long lLoginID,const char* dwCommand, int nChannelNO, char * lpInBuffer,int waittime DEF_PARAM(1000));
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">设置智能插座配置
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left">lLoginID[in]:登陆句柄dwCommand[in]:json名
nChannelNO[in]:通道号,-1:得到全通道配置,0-n:得到单个通道的配置,从0开始
lpOutBuffer[out]:设置的json字符串
waittime[in]:等待时间
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回1，失败小于等于0
</td></tr>
</table>

## 智能插座控制命令参数说明

<table>
<tr><td style="width:33%;background-color:#fcc">enum值</td><td style="width:33%;background-color:#fc9">name</td><td style="width:33%;background-color:#f93">代码样式</td></tr>
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

## 获取设置控制命令（主要用于公司内部移动端命令控制）

<table>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API long CALL_METHOD H264_DVR_CmdGeneral(long lLoginID, int nCmdReq, const char *szCmd, void *lpOutBuffer, unsigned long dwOutBufferSize, unsigned long* lpBytesReturned, int nTimeout, char *pInParam DEF_PARAM(0), int nInParamLen DEF_PARAM(0), int nCmdRes DEF_PARAM(-1));
</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">既可以获取也可以配置设备参数
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left">lLoginID[in]:登陆句柄
nCmdReq[in]:请求命令
szCmd[in]:json名称
lpOutBuffer[out]:接收json缓冲
dwOutBufferSize[in]: 接收缓冲大小(字节)
lpBytesReturned[out]:接收到的json大小
nTimeout[in]:等待时间
pInParam[in]:发给设备的请求命令json字符串
nInParamLen[in]:发给设备的请求命令json大小(字节)
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回0，失败返回小于0
</td></tr>
</table>

## 查询设备是否在线

<table>
<tr><td style="background-color:#cfc;width:30%;">回调函数</td><td style="background-color:#9c6">typedef int (*OnFoundDevCB)(char * uuid,int state,int userData);</td></tr>
<tr><td style="background-color:#cfc">回调函数参数说明
</td><td style="background-color:#9c6;"> </td></tr>
<tr><td style="background-color:#dedebe;width:30%;">接口函数</td><td style="background-color:#B9B973">H264_DVR_API int CALL_METHOD H264_DVR_Check_Device_Exist_V2(SDK_SDevicesState *pStates, int nTimeout,OnFoundDevCB decCb,int userData);</td></tr>
<tr><td style="background-color:#dedebe">函数说明
</td><td style="background-color:#B9B973">查询多个设备是否在线V2版本
</td></tr>
<tr><td style="background-color:#dedebe">函数参数
</td><td style="background-color:#B9B973;text-align:left">pStates[out]: 要查询的多个设备信息<a href="http://open.xmeye.net/zh/#SDevicesState">SDK_SDevicesState</a>,会返回设备状态
nTimeout[in]: 等待时间
decCb[out]:  设备在线与否的回调
userData[out]:回调参数
</td></tr>
<tr><td style="background-color:#dedebe">返回值
</td><td style="background-color:#B9B973">成功返回0，失败返回小于0
</td></tr>
</table>
