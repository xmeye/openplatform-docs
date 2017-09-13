<pre>
<h1> 1 接口定义</h1>
<div style="font-size:18px;">
<b>1.1 SDK初始化</b>
</div>
 <label style="color:blue;">typedef</label> void (CALLBACK *pfmessageCallBack)(enum_P_Client_Msg enumType, int nType2, <label style="color:blue;"><label style="color:blue;">char</label> *szDeviceID, <lable style="color:blue;">int</label> channel, <label style="color:blue;">int</label> nParam1, <label style="color:blue;">char</label>* pParam1, <label style="color:blue;">long</label> dwUser);
</div>

1.P_CLIENT_API int CALL_METHOD P_Client_Init(pfmessageCallBack callback, long dwUser);
    Function description: SDK initialization, calling before all the SDK functions
    Parameters description:
		callback Information callback function，
		[in]dwUser User data
		Callback function parameters description:
			enumType 
			enum_P_Client_Msg
			nType2  Sub type, state
		szDeviceID Device ID 
		Channel Channel number
		nParam1 Remain, when nType is the request of preview, playback and intercom,
                here is the requested ID
		pParam1 Remain, can represent device ID
		dwUser User data that is the user data inputed above
    Return value: success return 0
    Correlation function:P_Client_ClearUp

 

2.P_CLIENT_API int CALL_METHOD P_Client_ClearUp ();
    Function description: empty SDK; release the occupied resources, calling after all
                          the SDK functions.
    Parameters: None
    Return value: None
    Correlation function: P_Client_Init
    Typical applications: calling when the application is closed

 
<div style="margin-left:30px;font-size:18px;">
<b>1.2 Alarm state acquisition</b>
</div>

typedef void (CALLBACK *pAlarmMessageCallBack)(enum_P_Client_AlarmMsg enumType, char *szDeviceID, int channel, int nStatus, int nParam1, long dwUser);

4.P_CLIENT_API int CALL_METHOD P_Client_SetAlarmCallBack(pAlarmMessageCallBack callback, long dwUser)
    Function description: set alarm information callback
    Parameters description:
		callback  Message callback function, when set to 0, it means that prohibit callback
		[in] dwUser User data
   		Callback function parameters description:
		enumType Specific types seeenum_P_Client_AlarmMsg
        szDeviceID Device ID
        Channel    Channel              
        nStatus   Status 0 disappear 1 generate alarm
		nParam1   Remain
		dwUser   Callback user data that is the user data inputed above
  		Return value:0


<div style="margin-left:30px;font-size:18px;">
<b>1.3 Platform registration</b>
</div>

5.P_CLIENT_API int CALL_METHOD P_Client_LoginServer(char *ip, int port, char* user, char* password, int waittime = 5000)
    Function description: register users to the platform
    Parameters description:
		[in] ip Platform service IP
		[in] port Service port
		[in] user Username
		[in] password User password
		[in] waittime Timeout 
   Return value: fail return <0，
   Correlation function:

 
<div style="margin-left:30px;font-size:18px;">
<b>1.4 Set visiting mode</b>
</div>

6.P_CLIENT_API int CALL_METHOD P_Client_SetVisitType(int nType)
    Function description: set the visiting mode of the operation
	Parameters description:
		[in] nType  Visiting mode, see enum_P_Visit_Type

 
<div style="margin-left:30px;font-size:18px;">
<b>1.5 Get device information</b>
</div>

7.P_CLIENT_API int CALL_METHOD P_Client_GetDevicesLen();
    Function description: get the buffering length needed by device list
    Parameters description:
    Return value: >0 success, return buffering length
    Correlation function:P_Client_GetDevices

8.P_CLIENT_API int CALL_METHOD P_Client_GetDevices(char *pBuf, int nLen);
    Function description: get device information
    Parameters description:
        pBuf Receive data memory address, the returned data is parsed one by one 
             via GroupXmlParser, refer to demo
        Len nLen Memory length
    Return value: >0 success, return buffering length
    Correlation function:P_Client_GetDevicesLen

 
<div style="margin-left:30px;font-size:18px;">
<b>1.6 Real-time monitoring</b>
</div>

9.P_CLIENT_API int CALL_METHOD P_Client_ConnectRealPlay(P_Client_RealInfo *pRealInfo) 
    Function description: start real time monitoring
    Parameters description:
    	[in] pRealInfo Real-time monitoring parameters
    Return value: fail return <0, return to real time monitoring ID success
                  (real-time monitoring handle), it will be used as parameters 
                  of correlation function.
    Correlation function:P_Client_StopRealPlay

 

10.P_CLIENT_API int CALL_METHOD P_Client_StopRealPlay(int realHandle); 
    Function description: stop real time monitoring
    Parameters description:
		[in] realHandle The return value of P_Client_ConnectRealPlay
    Return value: success return 0, fail return <0
    Correlation function:P_Client_ConnectRealPlay
    Typical application: turn off real-time monitoring

<div style="margin-left:30px;font-size:18px;">
<b>1.7 Playback and download</b>
</div>

10.P_CLIENT_API int CALL_METHOD P_Client_QueryRecord(P_Client_QueryRecInfo* pInfo) 
    Function description: query video file
    Parameters description:
    	[in] pInfo Query criteriaP_Client_QueryRecInfo
    Return value: success return 0, fail return <0
    Correlation function:P_Client_GetNextRecord, P_Client_CloseQueryRecord

11.P_CLIENT_API int CALL_METHOD P_Client_GetNextRecord(int nQueryHandle, P_Client_RecordInfo* pRecInfo)
    Function description:  Get the next video information
    Parameters description:
    	[in] nQueryHandle  The return value of P_Client_QueryRecord
		[out] pRecInfo  Receive video information address
    Return value: success return 0, fail return <0

 

12.P_CLIENT_API int CALL_METHOD P_Client_CloseQueryRecord(int nQueryHandle)
    Function description: close query
    Parameters description:
    	[in] nQueryHandle  The return value of P_Client_QueryRecord
    Return value: success return 0, fail return <0

 
13.P_CLIENT_API int CALL_METHOD P_Client_PlaybackByFile(P_Client_PlaybackInfo* pPlayInfo, P_Client_RecordInfo* pRecInfo , pPlayEndCallBack endCallback, long lUser);
    Function description: playback by file
    Parameters description:
		[in] pPlayInfo  Playback information 
		[in] pRecInfo   Video file information, return by P_Client_GetNextRecord
		[in] endCallback  Playback end callback
		[in] lUser  Playback end, callback user parameters 
    Return value: success return network playback ID, fail return <=0
    Correlation function:



14.P_CLIENT_API int CALL_METHOD P_Client_StopPlaybackByFile(int nHandle)
    Function description: playback by file
    Parameters description:
		[in] nHandle The return value of P_Client_PlaybackByFile
    Return value: success return 0, fail return <0
    Correlation function:

15.P_CLIENT_API int CALL_METHOD P_Client_PlaybackByTime(P_Client_PlayByTimeInfo* pPlayInfo, pPlayEndCallBack endCallback, long lUser);
    Function description: video playback by time
    Parameters description:
    	[in] pPlayInfo Playback information
		[in] endCallback Playback end callback
		[in] lUser  Playback end, callback user parameters
    Return value: success return network playback ID, fail return <=0

 

16.P_CLIENT_API int CALL_METHOD P_Client_StopPlaybackByTime(int nHandle)
	a)Function description: stop playback by time
	b)Parameters description:
	[in] nHandle  The return value of P_Client_PlaybackByTime
	c)Return value: success return 0, fail return <0

 
17.P_CLIENT_API int CALL_METHOD P_Client_PlaybackControl(int nHandle, enum_P_Playback_Control control ) 
    Function description: network playback pause and recovery and progress control
    Parameters description: 
		[in] nHandle
        Playback handle, such as the return value of P_Client_PlaybackByTime, P_Client_PlaybackByFile
		[in] lControlCode  see enum_P_Playback_Control
    Return value: success return 0, fail return <0

 

18.P_CLIENT_API int CALL_METHOD P_Client_SetPlayTimePos(int nHandle, int nTime)
    Function description: time offset
    Parameters description:
		[in] nHandle  Playback handle, such as the return value of 
                      P_Client_PlaybackByTime,  P_Client_PlaybackByFile

		[in] nTime  From the started offset, second for the unit
    Return value: success return 0, fail return <0

<div style="margin-left:30px;font-size:18px;">
<b>1.8 PTZ control</b>
</div>


19.P_CLIENT_API int CALL_METHOD P_Client_PTZControl(char *szCameraId, int nCmd, int nParam1, int nParam2, int nParam3, bool bStop); 
    Function description: PTZ control
    Parameters description:
		szCameraId  Channel ID
		[out] nCmd  Control type P_CLIENT_PTZCommand
		[in] nParam1  Step length
		[in] nParam2
		[in] nParam3
    	[in] bStop  Whether to stop
    Return value: success return 0, fail return <0
    Correlation function:

<div style="margin-left:30px;font-size:18px;">
<b>1.9 System configuration</b>
</div>

20.P_CLIENT_API int CALL_METHOD P_Client_GetDeviceConfig(int nType, char* szDeviceID, int nChannelNo, char *pConfigBuf, int nLen, int &nRetLen);
    Function description: get device configuration
    Parameters description:
    	[in] nType  Configuration typeenum_P_Device_Config_Type
        [in]szDeviceID   Device ID
        [in] nChannelNo  Channel number, -1 means all the channels
		[out] lpOutBuffer Store the buffer of output parameters, according to different 
                          types to output different configuration structure. For details, 
                          see configuration structure in data structure definition.  
        [in] nLen  Input the size of the buffer (unit byte).
		[out] nRetLen The actual return buffer size, corresponding to the size of 
                      the configuration structure (unit byte).
        Return value: 0 means success, <0 means fail

 

21.P_CLIENT_API int CALL_METHOD P_Client_SetDeviceConfig(int nType, char* szDeviceID, int nChannelNo, char *pConfigBuf, int nLen);
    Function description: set device configuratio
    Parameters description:
		[in] nType  Configuration typeenum_P_Device_Config_Type
		[in]szDeviceID                Device ID
        [in]nChannelNO  Channel number, -1 means all the channels
		[in]pConfigBuf Store the buffer of input parameters, according to different types 
                       to input different configuration structure. For details, see 
                       configuration structure in data structure definition.
		[in] nLen  Input the size of the buffer (unit byte).
	Return value: 0 means success, <0 means fail



<div style="margin-left:30px;font-size:18px;">
<b>1.10 Voice intercom</b>
</div>

// The audio data of voice intercom callback functions prototype

typedef void (CALLBACK *pfTalkDataCallBack)(char *pBuffer, long dwBufSize, long dwUser);

22.P_CLIENT_API int CALL_METHOD P_Client_StartTalk(char *szDeviceID, pfTalkDataCallBack dataCallback, int nUser)
	Function description: turn on voice intercom
    Parameters description:
		[in] szDeviceID      Device ID
		[in] dataCallback  Voice intercom data callback received from the device
		[in] nUser  Receive data object
    Return value: >0 intercom handle <= 0 fail
    Correlation function: P_Client_StopTalk

 

23.P_CLIENT_API int CALL_METHOD P_Client_StopTalk(int handle)
	Function description: stop voice intercom
	Parameters description:
		[in] handle   Intercom handle: P_Client_StartTalk return value
	Return value: 0 success <0 fail
	Correlation function:P_Client_StartTalk


<div style="margin-left:30px;font-size:18px;">
<b>3.10Transparent serial port </b>
</div>
                  
24.P_CLIENT_API int CALL_METHOD P_Client_OpenTransport(char* szDeviceID, int nType, int nBaudrate, int nDatabits, int nStopbits, int nParity);
	Function description: open transparent channel
	Parameters description:
		[in] szDeviceID    Device ID
		[in] nType           Serial port type，0=232， 1=485
		[in]nBaudrate     Baud rate
		[in] nDatabits  Data bits
		[in] nStopbits  Stop bits
		[in] nParity     Parity
	Return value: 0 success <0 fail
	Correlation function:P_Client_CloseTransport

25.P_CLIENT_API int CALL_METHOD P_Client_CloseTransport(char* szDeviceID, int nType);
	Function description: close transparent channel
	Parameters description:
		[in] szDeviceID    Device ID
		[in] nType           Serial port type，0=232， 1=485
	Return value: 0 success <0 fail
	Correlation function:P_Client_OpenTransport

 

26.P_CLIENT_API int CALL_METHOD P_Client_WriteTransportData(char* szDeviceID, int nType, char *pbuf, int nLen)
	Function description: write in transparent channel
	Parameters description:
		[in] szDeviceID    Device ID
		[in] nType           Serial port type，0=232， 1=485
		[in] pbuf  Data needed to be written, pay attention that length cannot exceed 255
		[in] nLen            The length of the data written in
	Return value: 0 success <0 fail


<div style="margin-left:30px;font-size:18px;">
<b>3.11 Manual center recording </b>
</div>

27.P_CLIENT_API int CALL_METHOD P_Client_StartCenterRecord(char* szCamereID)
	Function description: open manual recording
	Parameters description:
		[in] szCamereID    Channel ID
	Return value: 0 success <0 fail
	Correlation function: P_Client_StopCenterRecord

28.P_CLIENT_API int CALL_METHOD P_Client_StopCenterRecord(char* szCamereID)
	Function description: stop manual recording
	Parameters description:
		[in] szCamereID Channel ID
	Return value: 0 success <0 fail
	Correlation function:P_Client_StartCenterRecord

 
<div style="margin-left:30px;font-size:18px;">
<b>3.12 Manual control </b>
</div>


29.P_CLIENT_API int CALL_METHOD P_Client_Capture(int nHandle, char* pFile)
	Function description: capture image
	Parameters description: 
		[in] nHandle   Returned ID of preview or playback
		[in] pFile   Image file full path, currently only BMP format
	Return value: 0 success <0 fail
	Correlation function:P_Client_ConnectRealPlay，P_Client_PlaybackByFile，
	                     P_Client_PlaybackByTime

30.P_CLIENT_API int CALL_METHOD P_Client_OpenSound(int nHandle)
	Function description: open sound
	Parameters description:
		[in] nHandleReturned ID of preview or playback
	Return value: 0 success <0 fail
	Correlation function：P_Client_CloseSound

31.P_CLIENT_API int CALL_METHOD P_Client_CloseSound(int nHandle)
	Function description: close sound
	Parameters description:
		[in] nHandleReturned ID of preview or playback
	Return value: 0 success <0 fail
	Correlation function:P_Client_OpenSound

32.P_CLIENT_API int CALL_METHOD P_Client_StartLocalRecord(int nHandle, char* pFile)
	Function description: open manual recording
	Parameters description:
		[in] nHandleReturned ID of preview or playback
		[in] pFile File full path
	Return value: 0 success <0 fail
	Correlation function:P_Client_StopLocalRecord

33.P_CLIENT_API int CALL_METHOD P_Client_StopLocalRecord(int nHandle)
	Function description: stop manual recording
	Parameters description:
		[in] nHandleReturned ID of preview or playback
	Return value: 0 success <0 fail
	Correlation function：P_Client_StartLocalRecord

34  P_CLIENT_API int CALL_METHOD P_Client_SetVideoWnd(int nType, int nWndNum, HWND* pWnd)
	Function description: set the window resources, this must be called after 
                          the initialization, otherwise unable to do any video operation
	Parameters description:
		[in] nType Window type, 0 real-time window, 1 playback window
		[in] nWndNumNumber of windows
		[in] pWnd   Window handle
	Return value: 0 success <0 fail

# 2   Examples function implementation #
Please see ClientDemo program and DEMO description.Doc.
</pre>
