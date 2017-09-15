## 典型调用顺序

```
A.初始化 ：       
    SDK初始化             P_Client_Init ()
B.SDK功能信息获取： 
    设置报警消息回调     P_Client_SetAlarmCallBack ()

C.登录服务器  ：  
    登入设备            P_Client_LoginServer()
D.获取设备信息 ： 
    获取设备信息数据长度  P_Client_GetDevicesLen() 
    获取设备信息         P_Client_GetDevices()
E.实时监视通道 ：
    打开监视通道         P_Client_ConnectRealPlay ()
     P_Client_StopRealPlay ()
F.回放：
    查询录像            P_Client_QueryRecord ()
                        P_Client_GetNextRecord
                        P_Client_CloseQueryRecord
    回放                P_Client_PlaybackByFile
                       P_Client_PlaybackByTime ()
G.释放SDK资源：
    SDK退出            P_Client_ClearUp ()
```

## 错误码

<label style="color:blue">#define</label> P_CLIENT_UNKNOW_ERROR    			-1   <label style="color:green">//未知错误</label>
<label style="color:blue">#define</label> P_CLIENT_LOGIN_TIMEOUT   			-2   <label style="color:green">//登陆超时</label>
<label style="color:blue">#define</label> P_CLIENT_NO_USER			-3   <label style="color:green">//没有当前用户</label>
<label style="color:blue">#define</label> P_CLIENT_PWD_ERROR       			-4   <label style="color:green">//密码错误</label>
<label style="color:blue">#define</label> P_CLIENT_HAS_LOGIN       			-5   <label style="color:green">//用户已被其他地方登陆</label>
<label style="color:blue">#define</label> P_CLIENT_CONNECT_ERROR   			-6   <label style="color:green">//连接服务器失败</label>
<label style="color:blue">#define</label> P_CLIENT_GET_GROUP_TIMEOUT        			-7   <label style="color:green">//获取权限组列表超时</label>
<label style="color:blue">#define</label> P_CLIENT_GET_ORG_TIMEOUT     					-8   <label style="color:green">//获取权限组信息超时</label>
<label style="color:blue">#define</label> P_CLIENT_PARSE_ERROR     			-9   <label style="color:green">//文件解析出错，或许是客户端和服务器版本不匹配</label>
<label style="color:blue">#define</label> P_CLIENT_NO_GROUP        			-10  <label style="color:green">//当前用户没有任何的权限</label>
<label style="color:blue">#define</label> P_CLIENT_INVALID_USERID  			-11  <label style="color:green">//无效用户id，属于异常信息</label>
<label style="color:blue">#define</label> P_CLIENT_NO_SESSION     				-12  <label style="color:green">//用户连接不存在，属于异常信息</label>
<label style="color:blue">#define</label> P_CLIENT_USER_LOCKED     			-13  <label style="color:green">//用户被锁定</label>

 

<label style="color:blue">#define</label> P_CLIENT_NO_INIT			-50  <label style="color:green">//没有初始化</label>
<label style="color:blue">#define</label> P_CLIENT_NO_LOGIN  -51  <label style="color:green">//未登陆</label>
<label style="color:blue">#define</label> P_CLIENT_INPUT_PARAM_ERROR  -52  <label style="color:green">//无效的参数</label>

 

<label style="color:blue">#define</label> P_CLIENT_REAL_RTSP_ERROR      -100 <label style="color:green">//连接流媒体失败</label>
<label style="color:blue">#define</label> P_CLIENT_REAL_LOGIN_DEVICE_ERROR       -101 <label style="color:green">//流媒体连接设备失败</label>
<label style="color:blue">#define</label> P_CLIENT_REAL_OPENVIDEO_ERROR -102 <label style="color:green">//流媒体连接视频失败</label>
<label style="color:blue">#define</label> P_CLIENT_REAL_RTP_LISTEN_ERROR-103 <label style="color:green">//pc侦听rtp失败</label>
<label style="color:blue">#define</label> P_CLIENT_REAL_RTP_CONNECT_ERROR        -104 <label style="color:green">//pc连接流媒体视频端口失败</label>
<label style="color:blue">#define</label> P_CLIENT_REAL_PORT_ERROR      -105 <label style="color:green">//pc解码端口失败，可能是超过范围</label>
<label style="color:blue">#define</label> P_CLIENT_REAL_MTS_EXCEPTION   -106 <label style="color:green">//MTS异常断线</label>
<label style="color:blue">#define</label> P_CLIENT_REAL_TIME_OUT        -107 <label style="color:green">//等待超时</label>
<label style="color:blue">#define</label> P_CLIENT_REAL_NOT_FOUND       -108 <label style="color:green">//没找到通道，或许是设备没有登录成功，或许服务器没添加设备</label>
<label style="color:blue">#define</label> P_CLIENT_REAL_INVALID_PROTOCOL-109 <label style="color:green">//错误的协议类型，目前只有tcp和udp</label>
<label style="color:blue">#define</label> P_CLIENT_REAL_OPENREAL_ERROR  -110 <label style="color:green">//打开视频失败</label>
<label style="color:blue">#define</label> P_CLIENT_REAL_NOT_FOUND_VIDEO -111 <label style="color:green">//没有发现当前视频</label>
<label style="color:blue">#define</label> P_CLIENT_REAL_RTP_EXCEPTION   -112 <label style="color:green">//连接异常，可能是流媒体已经删除了当前视频通道</label>
<label style="color:blue">#define</label> P_CLIENT_REAL_NO_RIGHT        -113 <label style="color:green">//没有预览权限</label>
<label style="color:blue">#define</label> P_CLIENT_REAL_DEV_OFFLINE     -114 <label style="color:green">//设备不在线</label>
<label style="color:blue">#define</label> P_CLIENT_REAL_LOGINDEV_FAILED -115 <label style="color:green">//设备登陆失败，</label>
 

 

<label style="color:blue">#define</label> P_CLIENT_PLAYBACK_INVLAID_TIME-200 <label style="color:green">//无效的时间</label>
<label style="color:blue">#define</label> P_CLIENT_PLAYBACK_INVLAID_SOURCE       -201 <label style="color:green">//无效的来源</label>
<label style="color:blue">#define</label> P_CLIENT_PLAYBACK_INVLAID_TYPE-202 <label style="color:green">//无效的类型</label>
<label style="color:blue">#define</label> P_CLIENT_PLAYBACK_INVALID_PARAM        -203 <label style="color:green">//无效参数</label>
<label style="color:blue">#define</label> P_CLIENT_PLAYBACK_NO_CAMERA   -204 <label style="color:green">//摄像头不存在</label>
<label style="color:blue">#define</label> P_CLIENT_PLAYBACK_NO_RIGHT    -205 <label style="color:green">//没有权限</label>
<label style="color:blue">#define</label> P_CLIENT_PLAYBACK_TIME_OUT    -206 <label style="color:green">//超时</label>
<label style="color:blue">#define</label> P_CLIENT_PLAYBACK_LOGIN_FAILED-207 <label style="color:green">//登陆设备失败</label>
<label style="color:blue">#define</label> P_CLIENT_PLAYBACK_QUERY_FAILED-208 <label style="color:green">//查询失败</label>
<label style="color:blue">#define</label> P_CLIENT_PLAYBACK_NO_VOD      -209 <label style="color:green">//没有点播服务</label>
<label style="color:blue">#define</label> P_CLIENT_PLAYBACK_NO_RECORD   -210 <label style="color:green">//没有录像文件</label>
<label style="color:blue">#define</label> P_CLIENT_PLAYBACK_SS_EXCEPTION-211 <label style="color:green">//回放服务异常断线</label>
<label style="color:blue">#define</label> P_CLIENT_PLAYBACK_OPENFILE_ERRPR       -212 <label style="color:green">//打开文件失败</label>
<label style="color:blue">#define</label> P_CLIENT_PLAYBACK_WRITEFILE_ERRPR      -213 <label style="color:green">//写文件失败</label>
<label style="color:blue">#define</label> P_CLIENT_PLAYBACK_EXCEPTION   -214 <label style="color:green">//回放异常断线</label>
<label style="color:blue">#define</label> P_CLIENT_PLAYBACK_CONNECT_ERROR        -215 <label style="color:green">//连接回放服务失败</label>
<label style="color:blue">#define</label> P_CLIENT_PLAYBACK_SERVER_ACK_ERROR     -216 <label style="color:green">//服务应答失败，可能是连接设备错误</label>
<label style="color:blue">#define</label> P_CLIENT_PLAYBACK_CONNECT_RTP_ERROR    -217 <label style="color:green">//连接媒体通道失败</label>
<label style="color:blue">#define</label> P_CLIENT_PLAYBACK_HAS_OPEND   -218 <label style="color:green">//已经处于回放状态</label>
<label style="color:blue">#define</label> P_CLIENT_PLAYBACK_NO_DEVICE   -219 <label style="color:green">//找不到设备</label>
<label style="color:blue">#define</label> P_CLIENT_PLAYBACK_LIMIT_DEV   -220 <label style="color:green">//到达设备回放上限</label>
<label style="color:blue">#define</label> P_CLIENT_PLAYBACK_LIMIT_SYS   -221 <label style="color:green">//到达系统回放上限</label>
<label style="color:blue">#define</label> P_CLIENT_PLAYBACK_HAS_OPENED_OTHER     -222 <label style="color:green">//当前通道被其他客户端占用</label>
<label style="color:blue">#define</label> P_CLIENT_PLAYBACK_FAILED_DEV  -223 <label style="color:green">//回放失败，SDK返回</label>

<label style="color:blue">#define</label> P_CLIENT_TALK_EXISIT -300 <label style="color:green">//已经有设备在对讲，请先关闭原先的</label>
<label style="color:blue">#define</label> P_CLIENT_TALK_EXCEPTION       -301 <label style="color:green">//对讲异常，可能是设备已经被流媒体删除</label>
<label style="color:blue">#define</label> P_CLIENT_TALK_NOT_FOUND       -302 <label style="color:green">//对讲不存在</label>
<label style="color:blue">#define</label> P_CLIENT_TALK_NOT_DEVICE      -303 <label style="color:green">//服务器没有添加设备或者设备未登录</label>
<label style="color:blue">#define</label> P_CLIENT_TALK_AUDIO_COLLECT_ERROR      -304 <label style="color:green">//对讲音频采集失败</label>
<label style="color:blue">#define</label> P_CLIENT_TALK_OPEN_PORT_ERROR -305 <label style="color:green">//打开对讲解码端口失败</label>
<label style="color:blue">#define</label> P_CLIENT_TALK_RTSP_ERROR      -306 <label style="color:green">//连接流媒体失败</label>
<label style="color:blue">#define</label> F_CLIENT_TALK_LOGIN_FAILED    -307 <label style="color:green">//登陆设备失败，直连时候使用</label>

<label style="color:blue">#define</label> P_CLIENT_PTZ_NOT_SUPPORT      -400 <label style="color:green">//不支持的命令</label>
<label style="color:blue">#define</label> P_CLIENT_CFG_INVALID_PARAM    -401 <label style="color:green">//输入配置参数错误</label>
<label style="color:blue">#define</label> P_CLIENT_CFG_NO_DMS  -402 <label style="color:green">//设备授权失败</label>
<label style="color:blue">#define</label> P_CLIENT_CFG_TIMEOUT -403 <label style="color:green">//配置超时</label>
<label style="color:blue">#define</label> P_CLIENT_CFG_NOT_MATCH        -404 <label style="color:green">//不匹配，一般是缓冲长度不够了</label>
