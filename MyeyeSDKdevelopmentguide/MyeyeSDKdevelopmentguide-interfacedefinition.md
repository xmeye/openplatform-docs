## SDK初始化

```
typedef void (CALLBACK pfmessageCallBack)(
    enum_P_Client_Msg enumType,
    int nType2, char szDeviceID,
    int channel, int nParam1,
    char pParam1,
    long dwUser);
```

1.P_CLIENT_API int CALL_METHOD P_Client_Init(pfmessageCallBack callback, long dwUser);

    函数说明：初始化SDK, 在所有的SDK函数之前调用
    参数说明：
	    callback信息回调函数， 
	    [in]dwUser 用户数据
	    回调函数参数说明：
	       enumType 
	       enum_P_Client_Msg
	       nType2 子类型，状态
	    szDeviceID 设备ID
	    Channel通道号
	    nParam1保留  nType为预览，回放，对讲等请求时候，这里存在的就是请求的ID
	    pParam1保留, 可代表设备ID
	    dwUser用户数据，就是上面输入的用户数据
    返回值：成功返回0
    相关函数：P_Client_ClearUp
    
2.P_CLIENT_API int CALL_METHOD P_Client_ClearUp ();

    函数说明：清空SDK, 释放占用的资源，在所有的SDK函数之后调用。
    参数：无
    返回值：无
    相关函数：P_Client_Init
    典型应用：在应用程序关闭时调用

## 报警状态获取

typedef void (CALLBACK *pAlarmMessageCallBack)(enum_P_Client_AlarmMsg enumType, char *szDeviceID, int channel, int nStatus, int nParam1, long dwUser);

3.P_CLIENT_API int CALL_METHOD P_Client_SetAlarmCallBack(pAlarmMessageCallBack callback, long dwUser)

    函数说明：设置报警信息回调
    参数说明：
	    callback 消息回调函数，当设置为0时表示禁止回调
	    [in] dwUser用户数据
	    回调函数参数说明:
	    enumType 具体类型见 enum_P_Client_AlarmMsg
        szDeviceID设备ID
        Channel 通道号
        nStatus状态 0 消失  1 产生报警
	    nParam1   保留
	    dwUser    回调的用户数据，就是上面输入的用户数据
	返回值：0 
	
## 平台注册

4.P_CLIENT_API int CALL_METHOD P_Client_LoginServer(char *ip, int port, char* user, char* password, int waittime = 5000)

    函数说明：注册用户到平台， 
    参数说明：
	    [in] ip 平台服务IP
	    [in] port 服务端口
	    [in] user 用户名
	    [in] password 用户密码
	    [in] waittime 超时时间
	返回值：失败返回<0， 
    相关函数：

## 设置访问模式

5.P_CLIENT_API int CALL_METHOD P_Client_SetVisitType(int nType)

    函数说明：设置操作的访问模式 
    参数说明：
    	[in] nType 访问模式，参见enum_P_Visit_Type

## 获取设备信息

6.P_CLIENT_API int CALL_METHOD P_Client_GetDevicesLen();

    函数说明：获取设备列表需要的缓冲长度 
    参数说明：
	返回值：>0 成功，返回缓冲长度 
	相关函数：P_Client_GetDevices
	
7.P_CLIENT_API int CALL_METHOD P_Client_GetDevices(char *pBuf, int nLen);

    函数说明：获取设备信息 
    参数说明：
	    pBuf  接收数据内存地址， 返回的数据通过GroupXmlParser来一个个解析，参考demo
	    Len  内存长度
	返回值：>0 成功，返回缓冲长度 
    相关函数：P_Client_GetDevicesLen

## 实时监视

8.P_CLIENT_API int CALL_METHOD P_Client_ConnectRealPlay(P_Client_RealInfo *pRealInfo) 

    函数说明：启动实时监视
    参数说明：
	    [in] pRealInfo 实时监视参数
    返回值：失败返回<0，成功返回实时监视ID(实时监视句柄)，将作为相关函数的参数。
    相关函数：P_Client_StopRealPlay

9.P_CLIENT_API int CALL_METHOD P_Client_StopRealPlay(int realHandle); 

    函数说明：停止实时监视
    参数说明：
	    [in] realHandle
	    P_Client_ConnectRealPlay的返回值
	返回值：成功返回0，失败返回<0
    相关函数：P_Client_ConnectRealPlay
    典型应用：关闭实时监视

## 回放和下载

10.P_CLIENT_API int CALL_METHOD P_Client_QueryRecord(P_Client_QueryRecInfo* pInfo) 

    函数说明：查询录像文件
    参数说明：
	    [in] pInfo 查询条件P_Client_QueryRecInfo
	返回值：成功返回0，失败返回<0
    相关函数：P_Client_GetNextRecord, P_Client_CloseQueryRecord

11.P_CLIENT_API int CALL_METHOD P_Client_GetNextRecord(int nQueryHandle, P_Client_RecordInfo* pRecInfo)

    函数说明：获取下一条录像信息
    参数说明：
	    [in] nQueryHandle
	    P_Client_QueryRecord 的返回值
	    [out] pRecInfo 接收录像信息地址
	返回值：成功返回0，失败返回《0

12.P_CLIENT_API int CALL_METHOD P_Client_CloseQueryRecord(int nQueryHandle)

    函数说明：关闭查询
    参数说明：
	    [in] nQueryHandle
	    P_Client_QueryRecord的返回值
	返回值：成功返回0，失败返回《0

13.P_CLIENT_API int CALL_METHOD P_Client_PlaybackByFile(P_Client_PlaybackInfo* pPlayInfo, P_Client_RecordInfo* pRecInfo , pPlayEndCallBack endCallback, long lUser);

    函数说明：按文件回放
    参数说明：
	    [in] pPlayInfo 回放信息
	    [in] pRecInfo  录像文件信息，由P_Client_GetNextRecord返回
	    [in] endCallback 回放结束回调
	    [in] lUser 回放结束回调用户参数
	返回值：成功返回网络回放ID，失败返回<=0
    相关函数： 

14.P_CLIENT_API int CALL_METHOD P_Client_StopPlaybackByFile(int nHandle)

    函数说明：按文件回放
    参数说明：
	    [in] nHandle
	    P_Client_PlaybackByFile 返回值
	返回值：成功返回0，失败返回<0
    相关函数：

15.P_CLIENT_API int CALL_METHOD P_Client_PlaybackByTime(P_Client_PlayByTimeInfo* pPlayInfo, pPlayEndCallBack endCallback, long lUser);

    函数说明：按时间进行录像回放
    参数说明：
	    [in] pPlayInfo 回放信息
	    [in] endCallback 回放结束回调
	    [in] lUser 回放结束回调用户参数
	返回值：成功返回网络回放ID，失败返回《=0

16.P_CLIENT_API int CALL_METHOD P_Client_StopPlaybackByTime(int nHandle)

    a) 函数说明：停止按时间回放
    b) 参数说明：
       [in] nHandle
        P_Client_PlaybackByTime的返回值
    c) 返回值：成功返回0，失败返回《0

17.P_CLIENT_API int CALL_METHOD P_Client_PlaybackControl(int nHandle, enum_P_Playback_Control control ) 

    函数说明：网络回放暂停与恢复以及进度控制
    参数说明：
	   [in] nHandle 回放句柄,如P_Client_PlaybackByTime, P_Client_PlaybackByFile的返回值
	   [in] lControlCode 见 enum_P_Playback_Control
	返回值：成功返回0，失败返回《0

18.P_CLIENT_API int CALL_METHOD P_Client_SetPlayTimePos(int nHandle, int nTime)

     函数说明：时间偏移
     参数说明：
	     [in] nHandle 回放句柄,如P_Client_PlaybackByTime, P_Client_PlaybackByFile的返回值
	     [in] nTime 从开始的偏移量，秒为单位
	 返回值：成功返回0，失败返回《0

## 云台控制

19.P_CLIENT_API int CALL_METHOD P_Client_PTZControl(char *szCameraId, int nCmd, int nParam1, int nParam2, int nParam3, bool bStop); 

    函数说明：云台控制
    参数说明:
		szCameraId 通道ID
	    [out] nCmd 控制类型。P_CLIENT_PTZCommand
	    [in] nParam1 步长
		[in] nParam2
		[in] nParam3
	    [in] bStop 是否是停止
	返回值:成功返回0，失败返回<0。
    相关函数：

## 系统配置

20.P_CLIENT_API int CALL_METHOD P_Client_GetDeviceConfig(int nType, char* szDeviceID, int nChannelNo, char *pConfigBuf, int nLen, int &nRetLen);

    函数说明: 获取设备配置。
    参数说明 :
	    [in] nType 配置类型 enum_P_Device_Config_Type
	    [in]szDeviceID 设备ID
	    [in] nChannelNo 配置通道号，-1表示所有通道
		[out] lpOutBuffer 存放输出参数的缓冲区, 根据不同的类型, 输出不同的配置结构, 具体见数据结构定义中各配置结构  
	    [in] nLen 输入缓冲区的大小, (单位字节). 
	    [out] nRetLen 实际返回的缓冲区大小,对应配置结构的大小, (单位字节).
	返回值：0表示成功，《0表示失败。 

21.P_CLIENT_API int CALL_METHOD P_Client_SetDeviceConfig(int nType, char* szDeviceID, int nChannelNo, char *pConfigBuf, int nLen);

    函数说明: 设置设备配置。
    参数说明 :
	    [in] nType 配置类型 enum_P_Device_Config_Type
	    [in]szDeviceID 设备ID
	    [in]nChannelNO 配置通道号，-1表示所有通道
		[in] pConfigBuf 存放输入参数的缓冲区, 根据不同的类型, 输入不同的配置结构, 具体见数据结构定义中各配置结构  
	 	[in] nLen 输入缓冲区的大小, (单位字节). 
	返回值：0表示成功，《0表示失败。

## 语音对讲

语音对讲的音频数据回调函数原形

typedef void (CALLBACK *pfTalkDataCallBack)(char *pBuffer, long dwBufSize, long dwUser);

22.P_CLIENT_API int CALL_METHOD P_Client_StartTalk(char *szDeviceID, pfTalkDataCallBack dataCallback, int nUser)

    函数说明：开启语音对讲
    参数说明：
		[in] szDeviceID     设备ID
		[in] dataCallback 从设备接收到的语音对讲数据回调
		[in] nUser 接收数据对象
	返回值：> 0 对讲句柄   <= 0 失败
    相关函数:P_Client_StopTalk

23.P_CLIENT_API int CALL_METHOD P_Client_StopTalk(int handle)

	函数说明：停止语音对讲
	参数说明：
    	[in] handle     对讲句柄：P_Client_StartTalk返回值
    返回值：0 成功   《0 失败
	相关函数：P_Client_StartTalk

## 透明串口
                
24  P_CLIENT_API int CALL_METHOD P_Client_OpenTransport(char* szDeviceID, int nType, int nBaudrate, int nDatabits, int nStopbits, int nParity );

	函数说明：开启透明通道
	参数说明：
		[in] szDeviceID     设备id
		[in] nType            串口类型，0=232， 1=485
		[in]nBaudrate     波特率
		[in] nDatabits   数据位
		[in] nStopbits   停止位
		[in] nParity      校验位
	返回值：0 成功   《0 失败
	相关函数：P_Client_CloseTransport

25.P_CLIENT_API int CALL_METHOD P_Client_CloseTransport(char* szDeviceID, int nType);

	函数说明：关闭透明通道
	参数说明：
		[in] szDeviceID     设备id
		[in] nType            串口类型，0=232， 1=485
	返回值：0 成功   《0 失败
	相关函数：P_Client_OpenTransport

26.P_CLIENT_API int CALL_METHOD P_Client_WriteTransportData(char* szDeviceID, int nType, char *pbuf, int nLen)

	函数说明：写入透明通道
	参数说明：
		[in] szDeviceID     设备id
		[in] nType            串口类型，0=232， 1=485
		[in] pbuf             需要写入的数据，注意，长度不能超过255
		[in] nLen             写入数据的长度
	返回值：0 成功   《0 失败

## 手动中心录像

27.P_CLIENT_API int CALL_METHOD P_Client_StartCenterRecord(char* szCamereID)

	函数说明：开启手动录像
	参数说明：
		[in] szCamereID     通道id
    返回值：0 成功   《0 失败
	相关函数：P_Client_StopCenterRecord

28  P_CLIENT_API int CALL_METHOD P_Client_StopCenterRecord(char* szCamereID)

	函数说明：停止手动录像
	参数说明：
		[in] szCamereID  通道id
	返回值：0 成功   《0 失败
	相关函数：P_Client_StartCenterRecord

## 手动控制

29  P_CLIENT_API int CALL_METHOD P_Client_Capture(int nHandle, char* pFile)

	函数说明：抓图
	参数说明：
		[in] nHandle    预览或者回放返回的id
		[in] pFile      图片文件全路径，目前只有bmp格式
	返回值：0 成功   《0 失败
	相关函数：
		P_Client_ConnectRealPlay，P_Client_PlaybackByFile，P_Client_PlaybackByTime

30.P_CLIENT_API int CALL_METHOD P_Client_OpenSound(int nHandle)

	函数说明：打开声音
	参数说明：
		[in] nHandle 预览或者回放返回的id
	返回值：0 成功   《0 失败
    相关函数：P_Client_CloseSound

31.P_CLIENT_API int CALL_METHOD P_Client_CloseSound(int nHandle)

	函数说明：关闭声音
	参数说明：
		[in] nHandle 预览或者回放返回的id
	返回值：0 成功   《0 失败
    相关函数：P_Client_OpenSound

32.P_CLIENT_API int CALL_METHOD P_Client_StartLocalRecord(int nHandle, char* pFile)

	函数说明：开启手动录像
	参数说明：
		[in] nHandle 预览或者回放返回的id
		[in] pFile  文件文件全路径
	返回值：0 成功   《0 失败
    相关函数：P_Client_StopLocalRecord

33.P_CLIENT_API int CALL_METHOD P_Client_StopLocalRecord(int nHandle)

	函数说明：停止手动录像
	参数说明：
		[in] nHandle 预览或者回放返回的id
	返回值：0 成功   《0 失败
    相关函数：P_Client_StartLocalRecord

34.P_CLIENT_API int CALL_METHOD P_Client_SetVideoWnd(int nType, int nWndNum, HWND* pWnd)

	函数说明：设置窗口资源， 这个必须在初始化后就调用，否则无法做任何视频操作
	参数说明：
		[in] nType  窗口类型，0 实时窗口  1 回放窗口
		[in] nWndNum 窗口数量
		[in] pWnd    窗口句柄
    返回值：0 成功   《0 失败

## 示例功能实现
请参看ClientDemo程序和” DEMO说明.doc。
