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

```
#define P_CLIENT_UNKNOW_ERROR    			-1   //未知错误
#define P_CLIENT_LOGIN_TIMEOUT   			-2   //登陆超时
#define P_CLIENT_NO_USER			-3   //没有当前用户
#define P_CLIENT_PWD_ERROR       			-4   //密码错误
#define P_CLIENT_HAS_LOGIN       			-5   //用户已被其他地方登陆
#define P_CLIENT_CONNECT_ERROR   			-6   //连接服务器失败
#define P_CLIENT_GET_GROUP_TIMEOUT        			-7   //获取权限组列表超时
#define P_CLIENT_GET_ORG_TIMEOUT     					-8   //获取权限组信息超时
#define P_CLIENT_PARSE_ERROR     			-9   //文件解析出错，或许是客户端和服务器版本不匹配
#define P_CLIENT_NO_GROUP        			-10  //当前用户没有任何的权限
#define P_CLIENT_INVALID_USERID  			-11  //无效用户id，属于异常信息
#define P_CLIENT_NO_SESSION     				-12  //用户连接不存在，属于异常信息
#define P_CLIENT_USER_LOCKED     			-13  //用户被锁定
#define P_CLIENT_NO_INIT			-50  //没有初始化
#define P_CLIENT_NO_LOGIN  -51  //未登陆
#define P_CLIENT_INPUT_PARAM_ERROR  -52  //无效的参数
#define P_CLIENT_REAL_RTSP_ERROR      -100 //连接流媒体失败
#define P_CLIENT_REAL_LOGIN_DEVICE_ERROR       -101 //流媒体连接设备失败
#define P_CLIENT_REAL_OPENVIDEO_ERROR -102 //流媒体连接视频失败
#define P_CLIENT_REAL_RTP_LISTEN_ERROR-103 //pc侦听rtp失败
#define P_CLIENT_REAL_RTP_CONNECT_ERROR        -104 //pc连接流媒体视频端口失败
#define P_CLIENT_REAL_PORT_ERROR      -105 //pc解码端口失败，可能是超过范围
#define P_CLIENT_REAL_MTS_EXCEPTION   -106 //MTS异常断线
#define P_CLIENT_REAL_TIME_OUT        -107 //等待超时
#define P_CLIENT_REAL_NOT_FOUND       -108 //没找到通道，或许是设备没有登录成功，或许服务器没添加设备
#define P_CLIENT_REAL_INVALID_PROTOCOL-109 //错误的协议类型，目前只有tcp和udp
#define P_CLIENT_REAL_OPENREAL_ERROR  -110 //打开视频失败
#define P_CLIENT_REAL_NOT_FOUND_VIDEO -111 //没有发现当前视频
#define P_CLIENT_REAL_RTP_EXCEPTION   -112 //连接异常，可能是流媒体已经删除了当前视频通道
#define P_CLIENT_REAL_NO_RIGHT        -113 //没有预览权限
#define P_CLIENT_REAL_DEV_OFFLINE     -114 //设备不在线
#define P_CLIENT_REAL_LOGINDEV_FAILED -115 //设备登陆失败，
#define P_CLIENT_PLAYBACK_INVLAID_TIME-200 //无效的时间
#define P_CLIENT_PLAYBACK_INVLAID_SOURCE       -201 //无效的来源
#define P_CLIENT_PLAYBACK_INVLAID_TYPE-202 //无效的类型
#define P_CLIENT_PLAYBACK_INVALID_PARAM        -203 //无效参数
#define P_CLIENT_PLAYBACK_NO_CAMERA   -204 //摄像头不存在
#define P_CLIENT_PLAYBACK_NO_RIGHT    -205 //没有权限
#define P_CLIENT_PLAYBACK_TIME_OUT    -206 //超时
#define P_CLIENT_PLAYBACK_LOGIN_FAILED-207 //登陆设备失败
#define P_CLIENT_PLAYBACK_QUERY_FAILED-208 //查询失败
#define P_CLIENT_PLAYBACK_NO_VOD      -209 //没有点播服务
#define P_CLIENT_PLAYBACK_NO_RECORD   -210 //没有录像文件
#define P_CLIENT_PLAYBACK_SS_EXCEPTION-211 //回放服务异常断线
#define P_CLIENT_PLAYBACK_OPENFILE_ERRPR       -212 //打开文件失败
#define P_CLIENT_PLAYBACK_WRITEFILE_ERRPR      -213 //写文件失败
#define P_CLIENT_PLAYBACK_EXCEPTION   -214 //回放异常断线
#define P_CLIENT_PLAYBACK_CONNECT_ERROR        -215 //连接回放服务失败
#define P_CLIENT_PLAYBACK_SERVER_ACK_ERROR     -216 //服务应答失败，可能是连接设备错误
#define P_CLIENT_PLAYBACK_CONNECT_RTP_ERROR    -217 //连接媒体通道失败
#define P_CLIENT_PLAYBACK_HAS_OPEND   -218 //已经处于回放状态
#define P_CLIENT_PLAYBACK_NO_DEVICE   -219 //找不到设备
#define P_CLIENT_PLAYBACK_LIMIT_DEV   -220 //到达设备回放上限
#define P_CLIENT_PLAYBACK_LIMIT_SYS   -221 //到达系统回放上限
#define P_CLIENT_PLAYBACK_HAS_OPENED_OTHER     -222 //当前通道被其他客户端占用
#define P_CLIENT_PLAYBACK_FAILED_DEV  -223 //回放失败，SDK返回
#define P_CLIENT_TALK_EXISIT -300 //已经有设备在对讲，请先关闭原先的
#define P_CLIENT_TALK_EXCEPTION       -301 //对讲异常，可能是设备已经被流媒体删除
#define P_CLIENT_TALK_NOT_FOUND       -302 //对讲不存在
#define P_CLIENT_TALK_NOT_DEVICE      -303 //服务器没有添加设备或者设备未登录
#define P_CLIENT_TALK_AUDIO_COLLECT_ERROR      -304 //对讲音频采集失败
#define P_CLIENT_TALK_OPEN_PORT_ERROR -305 //打开对讲解码端口失败
#define P_CLIENT_TALK_RTSP_ERROR      -306 //连接流媒体失败
#define F_CLIENT_TALK_LOGIN_FAILED    -307 //登陆设备失败，直连时候使用
#define P_CLIENT_PTZ_NOT_SUPPORT      -400 //不支持的命令
#define P_CLIENT_CFG_INVALID_PARAM    -401 //输入配置参数错误
#define P_CLIENT_CFG_NO_DMS  -402 //设备授权失败
#define P_CLIENT_CFG_TIMEOUT -403 //配置超时
#define P_CLIENT_CFG_NOT_MATCH        -404 //不匹配，一般是缓冲长度不够了
```