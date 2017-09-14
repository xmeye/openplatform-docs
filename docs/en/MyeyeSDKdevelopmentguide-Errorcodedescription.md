# Typical calling order #
<pre>
A.Initialization:                        
    SDK Initialization         P_Client_Init ()
B.SDK function information acquisition:                      
    Set alarm message callback    P_Client_SetAlarmCallBack ()
C.Login server:
    Login device        P_Client_LoginServer()
D.Get device information                  
    Get device information data length    P_Client_GetDevicesLen() 
    Get device information    P_Client_GetDevices()
E.Real-time monitoring channel:
    Open monitoring channel     P_Client_ConnectRealPlay ()
 				P_Client_StopRealPlay ()
F.Playback:
    Query video    P_Client_QueryRecord ()
                   P_Client_GetNextRecord
                   P_Client_CloseQueryRecord
    Playback       P_Client_PlaybackByFile
                   P_Client_PlaybackByTime ()
G.Release SDK resources:
    SDK exit     P_Client_ClearUp ()
</pre>

# Error code

    
<pre>
<label style="color:blue">#define</label> P_CLIENT_UNKNOW_ERROR             			-1   <label style="color:green">//Unknown error</label>
<label style="color:blue">#define</label> P_CLIENT_LOGIN_TIMEOUT            			-2   <label style="color:green">//Login timeout</label>
<label style="color:blue">#define</label> P_CLIENT_NO_USER                  			-3   <label style="color:green">//No current user</label>
<label style="color:blue">#define</label> P_CLIENT_PWD_ERROR                			-4   <label style="color:green">//Password error</label>
<label style="color:blue">#define</label> P_CLIENT_HAS_LOGIN                			-5   <label style="color:green">//Users have been logged in other places</label>
<label style="color:blue">#define</label> P_CLIENT_CONNECT_ERROR            			-6   <label style="color:green">//Connect server failed</label>
<label style="color:blue">#define</label> P_CLIENT_GET_GROUP_TIMEOUT        			-7   <label style="color:green">//Get permission group list timeout</label>
<label style="color:blue">#define</label> P_CLIENT_GET_ORG_TIMEOUT     					-8   <label style="color:green">//Get permission group information timeout</label>
<label style="color:blue">#define</label> P_CLIENT_PARSE_ERROR              			-9   <label style="color:green">//File parses error, perhaps the client and server version does not match</label>
<label style="color:blue">#define</label> P_CLIENT_NO_GROUP                 			-10  <label style="color:green">//The current user does not have any rights</label>
<label style="color:blue">#define</label> P_CLIENT_INVALID_USERID           			-11  <label style="color:green">//Invalid user ID, an exception information</label>
<label style="color:blue">#define</label> P_CLIENT_NO_SESSION              				-12  <label style="color:green">//User connection does not exist, an exception information</label>
<label style="color:blue">#define</label> P_CLIENT_USER_LOCKED              			-13  <label style="color:green">//User is locked </label>

 

<label style="color:blue">#define</label> P_CLIENT_NO_INIT                  			-50  <label style="color:green">//No initialization</label>
<label style="color:blue">#define</label> P_CLIENT_NO_LOGIN                             -51  <label style="color:green">//Not logged in</label>
<label style="color:blue">#define</label> P_CLIENT_INPUT_PARAM_ERROR                    -52  <label style="color:green">//Invalid parameters  </label>

 

<label style="color:blue">#define</label> P_CLIENT_REAL_RTSP_ERROR                        -100 <label style="color:green">//Connect streaming media failed</label>
<label style="color:blue">#define</label> P_CLIENT_REAL_LOGIN_DEVICE_ERROR                -101 <label style="color:green">//Streaming media connect to device failed</label>
<label style="color:blue">#define</label> P_CLIENT_REAL_OPENVIDEO_ERROR                   -102 <label style="color:green">//Streaming media connect to video failed</label>
<label style="color:blue">#define</label> P_CLIENT_REAL_RTP_LISTEN_ERROR                  -103 <label style="color:green">//pc listen rtp failed</label>
<label style="color:blue">#define</label> P_CLIENT_REAL_RTP_CONNECT_ERROR                 -104 <label style="color:green">//pc connect to streaming media video port failed</label>
<label style="color:blue">#define</label> P_CLIENT_REAL_PORT_ERROR                        -105 <label style="color:green">//pc decode port failed, may be over range</label>
<label style="color:blue">#define</label> P_CLIENT_REAL_MTS_EXCEPTION                     -106 <label style="color:green">//MTS abnormal disconnection</label>
<label style="color:blue">#define</label> P_CLIENT_REAL_TIME_OUT                          -107 <label style="color:green">//Wait timeout</label>
<label style="color:blue">#define</label> P_CLIENT_REAL_NOT_FOUND                         -108 <label style="color:green">//Do not find the channel, or the device is not login successfully, or the server does not add device</label>
<label style="color:blue">#define</label> P_CLIENT_REAL_INVALID_PROTOCOL                  -109 <label style="color:green">//Wrong protocol type, currently only tcp and udp</label>
<label style="color:blue">#define</label> P_CLIENT_REAL_OPENREAL_ERROR                    -110 <label style="color:green">//Open video failed</label>
<label style="color:blue">#define</label> P_CLIENT_REAL_NOT_FOUND_VIDEO                   -111 <label style="color:green">//No current video found</label>
<label style="color:blue">#define</label> P_CLIENT_REAL_RTP_EXCEPTION                     -112 <label style="color:green">//Connection exception, may be the streaming media has been deleted the current video channel</label>
<label style="color:blue">#define</label> P_CLIENT_REAL_NO_RIGHT                          -113 <label style="color:green">//No preview permissions</label>
<label style="color:blue">#define</label> P_CLIENT_REAL_DEV_OFFLINE                       -114 <label style="color:green">//Device is not online</label>
<label style="color:blue">#define</label> P_CLIENT_REAL_LOGINDEV_FAILED                   -115 <label style="color:green">//Device login failed，</label>
 

 

<label style="color:blue">#define</label> P_CLIENT_PLAYBACK_INVLAID_TIME                  -200 <label style="color:green">//Invalid time</label>
<label style="color:blue">#define</label> P_CLIENT_PLAYBACK_INVLAID_SOURCE                -201 <label style="color:green">//Invalid source</label>
<label style="color:blue">#define</label> P_CLIENT_PLAYBACK_INVLAID_TYPE                  -202 <label style="color:green">//Invalid type</label>
<label style="color:blue">#define</label> P_CLIENT_PLAYBACK_INVALID_PARAM                 -203 <label style="color:green">//Invalid parameters</label>
<label style="color:blue">#define</label> P_CLIENT_PLAYBACK_NO_CAMERA                     -204 <label style="color:green">//Camera does not exist</label>
<label style="color:blue">#define</label> P_CLIENT_PLAYBACK_NO_RIGHT                      -205 <label style="color:green">//No permissions</label>
<label style="color:blue">#define</label> P_CLIENT_PLAYBACK_TIME_OUT                      -206 <label style="color:green">//Timeout</label>
<label style="color:blue">#define</label> P_CLIENT_PLAYBACK_LOGIN_FAILED                  -207 <label style="color:green">//Login device failed</label>
<label style="color:blue">#define</label> P_CLIENT_PLAYBACK_QUERY_FAILED                  -208 <label style="color:green">//Searched failed</label>
<label style="color:blue">#define</label> P_CLIENT_PLAYBACK_NO_VOD                        -209 <label style="color:green">//No vod server</label>
<label style="color:blue">#define</label> P_CLIENT_PLAYBACK_NO_RECORD                     -210 <label style="color:green">//No video file</label>
<label style="color:blue">#define</label> P_CLIENT_PLAYBACK_SS_EXCEPTION                  -211 <label style="color:green">//Playback service abnormal disconnection</label>
<label style="color:blue">#define</label> P_CLIENT_PLAYBACK_OPENFILE_ERRPR                -212 <label style="color:green">//Open file failed</label>
<label style="color:blue">#define</label> P_CLIENT_PLAYBACK_WRITEFILE_ERRPR               -213 <label style="color:green">//Writing file failed</label>
<label style="color:blue">#define</label> P_CLIENT_PLAYBACK_EXCEPTION                     -214 <label style="color:green">//Playback abnormal disconnection</label>
<label style="color:blue">#define</label> P_CLIENT_PLAYBACK_CONNECT_ERROR                 -215 <label style="color:green">//Connect playback service failed</label>
<label style="color:blue">#define</label> P_CLIENT_PLAYBACK_SERVER_ACK_ERROR              -216 <label style="color:green">//Service response failed, may be connected to the device error</label>
<label style="color:blue">#define</label> P_CLIENT_PLAYBACK_CONNECT_RTP_ERROR             -217 <label style="color:green">//Connect to media channel failed</label>
<label style="color:blue">#define</label> P_CLIENT_PLAYBACK_HAS_OPEND                     -218 <label style="color:green">//Already in playback status</label>
<label style="color:blue">#define</label> P_CLIENT_PLAYBACK_NO_DEVICE                     -219 <label style="color:green">//Device not found</label>
<label style="color:blue">#define</label> P_CLIENT_PLAYBACK_LIMIT_DEV                     -220 <label style="color:green">//Reach the device playback limit</label>
<label style="color:blue">#define</label> P_CLIENT_PLAYBACK_LIMIT_SYS                     -221 <label style="color:green">//Reach the system playback limit</label>
<label style="color:blue">#define</label> P_CLIENT_PLAYBACK_HAS_OPENED_OTHER              -222 <label style="color:green">//The current channel is occupied by other clients</label>
<label style="color:blue">#define</label> P_CLIENT_PLAYBACK_FAILED_DEV                    -223 <label style="color:green">//Playback failed, SDK return </label>


 

<label style="color:blue">#define</label> P_CLIENT_TALK_EXISIT                            -300 <label style="color:green">//There is a device in the intercom, please close the original</label>
<label style="color:blue">#define</label> P_CLIENT_TALK_EXCEPTION                         -301 <label style="color:green">//Abnormal intercom, may be the device has been deleted by streaming media</label>
<label style="color:blue">#define</label> P_CLIENT_TALK_NOT_FOUND                         -302 <label style="color:green">//Intercom does not exist</label>
<label style="color:blue">#define</label> P_CLIENT_TALK_NOT_DEVICE                        -303 <label style="color:green">//Server does not add device or device not logged in</label>
<label style="color:blue">#define</label> P_CLIENT_TALK_AUDIO_COLLECT_ERROR               -304 <label style="color:green">//Intercom audio acquisition failure</label>
<label style="color:blue">#define</label> P_CLIENT_TALK_OPEN_PORT_ERROR                   -305 <label style="color:green">//Open the intercom decoding port failed</label>
<label style="color:blue">#define</label> P_CLIENT_TALK_RTSP_ERROR                        -306 <label style="color:green">//Connect streaming media failed</label>
<label style="color:blue">#define</label> F_CLIENT_TALK_LOGIN_FAILED                      -307 <label style="color:green">//Login device failed, use in direct mode</label>

 

<label style="color:blue">#define</label> P_CLIENT_PTZ_NOT_SUPPORT                        -400 <label style="color:green">//Unsupported command</label>
<label style="color:blue">#define</label> P_CLIENT_CFG_INVALID_PARAM                      -401 <label style="color:green">//Input configuration parameters error</label>
<label style="color:blue">#define</label> P_CLIENT_CFG_NO_DMS                             -402 <label style="color:green">//Device authorization failed</label>
<label style="color:blue">#define</label> P_CLIENT_CFG_TIMEOUT                            -403 <label style="color:green">//Configuration timeout</label>
<label style="color:blue">#define</label> P_CLIENT_CFG_NOT_MATCH                          -404 <label style="color:green">//Does not match, generally the buffering length is not enough</label>

</pre>