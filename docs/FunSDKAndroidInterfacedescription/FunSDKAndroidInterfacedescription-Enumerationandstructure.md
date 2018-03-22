## 消息<label style="color:Dodgerblue">MsgContent</label>类说明</b>

<div style="margin-left:20px;"><pre>
public class MsgContent {
 public int sender;   // 消息发送者
 public int arg3;	 // 消息返回值
 public String str;	 // 消息返回值
 public byte[] pData; // 消息返回值
 int seq;	 // 序列号
};
</pre></div>

## 消息<label style="color:Dodgerblue">EUIMSG</label>枚举值说明

<div style="margin-left:20px;"> <pre>
<label style="color:red">FUN_USER_MSG_BEGIN_1 = 500</label>
 

EMSG_APP_ON_CRASH = 119, 
 
EMSG_SYS_GET_DEV_INFO_BY_USER = FUN_USER_MSG_BEGIN_1, // 获取设备信息 
EMSG_SYS_USER_REGISTER,        // 注册用户 
EMSG_SYS_PSW_CHANGE = FUN_USER_MSG_BEGIN_1 + 3,        // 修改用户密码 
EMSG_SYS_ADD_DEVICE,        // 增加用户设备 
EMSG_SYS_CHANGEDEVINFO,        // 修改用户设备信息 
EMSG_SYS_DELETE_DEV,        // 删除设备 
EMSG_SYS_GET_DEV_STATE = FUN_USER_MSG_BEGIN_1 + 9,        // 获取设备状态 
 
EMSG_SYS_GET_PHONE_CHECK_CODE, // 获取手机验证码 
EMSG_SYS_REGISER_USER_XM,      // 用户注册 
EMSG_SYS_GET_DEV_INFO_BY_USER_XM, // 同步登录 
EMSG_SYS_EDIT_PWD_XM,      // 忘记用户登录密码 
EMSG_SYS_FORGET_PWD_XM,      // 忘记用户登录密码 
EMSG_SYS_REST_PWD_CHECK_XM,  // 验证验证码 
EMSG_SYS_RESET_PWD_XM,       // 重置用户登录密码 
EMSG_SYS_DEV_GET_PUBLIC,     // 获取用户公开设备列表 
EMSG_SYS_DEV_GET_SHARE,      // 获取用户共享设备列表 
EMSG_SYS_DEV_PUBLIC,         // 公开设备 
EMSG_SYS_DEV_SHARE,          // 分享设备(分享视频) 
EMSG_SYS_DEV_CANCEL_PUBLIC,  // 取消公开设备 
EMSG_SYS_DEV_CANCEL_SHARE,   // 取消分享设备 
EMSG_SYS_DEV_REGISTER,         // 设备注册 
EMSG_SYS_DEV_COMMENT,         // 发表评论 
EMSG_SYS_DEV_GET_COMMENT_LIST,//获取评论列表 
EMSG_SYS_DEV_GET_VIDEO_INFO,  //获取视频信息 
EMSG_SYS_DEV_UPLOAD_VIDEO,  // 上传本地视频 
EMSG_SYS_GET_USER_PHOTOS,   // 获取用户相册列表 
EMSG_SYS_CREATE_USER_PHOTOS,// 创建用户相册 
EMSG_SYS_UPLOAD_PHOTO,      // 上传图片 
EMSG_SYS_DEIT_PHOTO,        // 图片文件编辑 
EMSG_SYS_GET_VIDEO_LIST,    // 获取短片视频列表 
EMSG_SYS_DEV_EDIT_VIDEO,    // 短片视频编辑 
EMSG_SYS_GET_PHOTO_LIST,    // 图片文件列表 
EMSG_SYS_DEV_DELETE_VIDEO,  // 删除短片视频 
EMSG_SYS_DELETE_PHOTO,      // 删除图片 
EMSG_SYS_DELETE_PHOTOS,     // 删除相册 
 
EMSG_SYS_GETPWBYEMAIL,      // 通过邮箱找回密码 
EMSG_SYS_CHECK_PWD_STRENGTH, // 检测密码合法性及强度 
EMSG_SYS_CHECK_DEVIDE_REAL, // 检测产品正品否 
EMSG_SYS_SEND_EMAIL_CODE,     // 发送邮箱验证码 
EMSG_SYS_REGISTE_BY_EMAIL,  // 邮箱注册 
EMSG_SYS_SEND_EMAIL_FOR_CODE, // 发送邮箱验证码（修改密码、重置密码） 
EMSG_SYS_CHECK_CODE_FOR_EMAIL,// 验证邮箱验证码（修改密码、重置密码） 
EMSG_SYS_PSW_CHANGE_BY_EMAIL, // 通过邮箱修改密码（重置密码） 
EMSG_SYS_CHECK_USER_REGISTE, // 检测用户名是否已注册 
EMSG_SYS_LOGOUT, // 同步退出 
EMSG_SYS_NO_VALIDATED_REGISTER, // 无需验证注册 
EMSG_SYS_GET_USER_INFO, // 获取用户信息 
EMSG_SYS_SEND_BINDING_PHONE_CODE, // 绑定安全手机(1)—发送验证码 
EMSG_SYS_BINDING_PHONE, // 绑定安全手机(2)—验证code并绑定 
 
EMSG_SYS_CLOUDUPGRADE_CHECK, //5052  设备是否需要升级查询 
EMSG_SYS_CLOUDUPGRADE_DOWNLOAD, //设备云升级下载 
EMSG_SYS_SEND_BINDING_EMAIL_CODE = 5054, // 绑定安全邮箱(1)—发送验证码 
EMSG_SYS_BINDING_EMAIL, // 绑定安全邮箱(2)—验证code并绑定 
EMSG_SYS_REGISER_USER_XM_EXTEND,      // 用户注册(Extend) 
EMSG_SYS_REGISTE_BY_EMAIL_EXTEND,  // 邮箱注册(Extend) 
EMSG_SYS_NO_VALIDATED_REGISTER_EXTEND, // 无需验证注册(Extend) 
 
EMSG_SYS_STOP_CLOUDUPGRADE_DOWNLOAD, //停止下载 
EMSG_SYS_ADD_DEV_BY_FILE = 5060,            //5060 
EMSG_SYS_GET_DEV_INFO_BY_USER_INSIDE = 5061,  //内部获取设备列表，用于android报警推送 
EMSG_SYS_GET_DEVLOG = 5062,                    // 获取设备端日志，并上传到服务器 
EMSG_SYS_GET_DEVLOG_END = 5063,                // 获取设备端日志，并上传到服务器 
EMSG_SYS_WX_ALARM_LISTEN_OPEN = 5064,         // 开启微信报警监听 
EMSG_SYS_WX_ALARM_LISTEN_CLOSE = 5065,        // 关闭微信报警监听 
EMSG_SYS_WX_ALARM_WXPMSCHECK = 5066,          // 微信报警状态查询 
EMSG_SYS_CHECK_CS_STATUS     = 5067,          // 实时从服务器上查询云存储状态 
EMSG_SYS_DULIST     = 5068,                   // 获取设备所在的帐户信息 
EMSG_SYS_MDSETMA    = 5069,                   // 指定设备的主帐户 
EMSG_SYS_MODIFY_USERNAME = 5070,              // 修改登录用户名（只能修改微信等绑定帐户自动生成） 
EMSG_SYS_ON_DEV_STATE = 5071,                 // 设备状态变化通知 
EMSG_SYS_IS_MASTERMA = 5072,                  // 获取当前账号是否为该设备的主账号 
 
EMSG_XM030_VIDEO_LOGIN = 8601, //视频广场登入 
EMSG_XM030_VIDEO_LOGOUT = 8602, //视频广场登出 
 
EMSG_APP_ON_SEND_LOG_FILE  = 5098,    // 日志信息回调 
EMSG_APP_LOG_OUT  = 5098,    // 日志信息回调 
 
EMSG_DEV_GET_CHN_NAME = FUN_USER_MSG_BEGIN_1 + 100, 
EMSG_DEV_FIND_FILE = 5101, //录像查询 
EMSG_DEV_FIND_FILE_BY_TIME = 5102, //录像查询（按时间） 
EMSG_DEV_ON_DISCONNECT = 5103, //设备断开连接 
EMSG_DEV_ON_RECONNECT = 5104, //全部重连 
EMSG_DEV_PTZ_CONTROL = 5105, //云台控制 
EMSG_DEV_AP_CONFIG = 5106, //快速配置 
EMSG_DEV_GET_CONFIG = 5107, //获取设备配置	 
EMSG_DEV_SET_CONFIG = 5108, //设置设备配置 
EMSG_DEV_GET_ATTR = 5109,  //获取设备属性 
EMSG_DEV_SET_ATTR = 5110,  //设置设备属性 
EMSG_DEV_START_TALK = 5111, //开启语音对讲 
EMSG_DEV_SEND_MEDIA_DATA = 5112,//语音对讲-发送数据 
EMSG_DEV_STOP_TALK = 5113, //停止语言对讲 
EMSG_ON_DEV_DISCONNECT = 5114, 
EMSG_ON_REC_IMAGE_SYN = 5115, // 录像索引图片同步 param1 == 0：同步进度 总图片\已经同步图片 
// param1 == 1：param2 == 0  同步的数目 
EMSG_ON_FILE_DOWNLOAD = 5116, //文件下载 
EMSG_ON_FILE_DLD_COMPLETE = 5117, //文件下载完成 
EMSG_ON_FILE_DLD_POS = 5118, //文件下载进度 
EMSG_DEV_START_UPGRADE = 5119,       //设备升级 
EMSG_DEV_ON_UPGRADE_PROGRESS = 5120, //升级进度 
EMSG_DEV_STOP_UPGRADE = 5121, //停止设备升级 
EMSG_DEV_OPTION = 5122, //设备选项 
EMSG_DEV_START_SYN_IMAGE = 5123, 
EMSG_DEV_STOP_SYN_IMAGE = 5124, 
EMSG_DEV_CHECK_UPGRADE = 5125,     // 检查设备升级状态, 
EMSG_DEV_SEARCH_DEVICES = 5126, //设备搜索 
EMSG_DEV_SET_WIFI_CFG = 5127, //设置EIFI配置 
EMSG_DEV_GET_CONFIG_JSON = 5128, //获取设备配置 
EMSG_DEV_SET_CONFIG_JSON = 5129, //设置设备配置  
EMSG_DEV_ON_TRANSPORT_COM_DATA = 5130, 
EMSG_DEV_CMD_EN = 5131, //设备通用命令查询 
EMSG_DEV_GET_LAN_ALARM = 5132, //局域网报警功能 
EMSG_DEV_SEARCH_PIC = 5133, //查询、下载设备缩略图 
EMSG_DEV_SEARCH_PIC_STOP = 5134, //停止查询、下载设备缩略图 
EMSG_DEV_START_UPLOAD_DATA = 5135, //开启上报数据 
EMSG_DEV_STOP_UPLOAD_DATA = 5136, //停止上报数据 
EMSG_DEV_ON_UPLOAD_DATA = 5137, //上报数据回调处理返回 
EMSG_ON_CLOSE_BY_LIB = 5138, 
EMSG_DEV_LOGIN = 5139, //设备登陆 
EMSG_DEV_BACKUP = 5140, 
EMSG_DEV_SLEEP = 5141, //适用于门铃，使设备进入休眠状态 
EMSG_DEV_WAKE_UP = 5142, //适用于门铃，唤醒设备，使之进入唤醒状态 
EMSG_DEV_SET_NET_IP_BY_UDP = 5143, //跨网段设置设备配置，目前只支持对有线网络配置进行设置 
 
EMSG_SET_PLAY_SPEED = FUN_USER_MSG_BEGIN_1 + 500, //播放速度控制 
EMSG_START_PLAY = 5501,//开始播放 
EMSG_STOP_PLAY = 5502, //停止播放 
EMSG_PAUSE_PLAY = 5503, //暂停播放 
 
EMSG_MEDIA_PLAY_DESTORY = 5504,        // 媒体播放退出,通知播放对象 
EMSG_START_SAVE_MEDIA_FILE = 5505,        // 保存录像,保存格式用后缀区分,.dav私有;.avi:AVI格式;.mp4:MP4格式 
EMSG_STOP_SAVE_MEDIA_FILE = 5506,        // 停止录像 
EMSG_SAVE_IMAGE_FILE = 5507,            // 抓图,保存格式用后缀区分,.bmp或.jpg 
EMSG_ON_PLAY_INFO = 5508,          // 回调播放信息 
EMSG_ON_PLAY_END = 5509,           // 录像播放结束 
EMSG_SEEK_TO_POS = 5510,           //播放位置定位 
EMSG_SEEK_TO_TIME = 5511,          //播放时间定位 
EMSG_SET_SOUND = 5512,                 // 打开，关闭声音 
EMSG_ON_MEDIA_NET_DISCONNECT = 5513,   // 媒体通道网络异常断开 
EMSG_ON_MEDIA_REPLAY = 5514,        // 媒体重新播放 
EMSG_START_PLAY_BYTIME = 5515, 
EMSG_ON_PLAY_BUFFER_BEGIN = 5516,   // 正在缓存数据 
EMSG_ON_PLAY_BUFFER_END = 5517,     // 缓存结束,开始播放 
EMSG_ON_PLAY_ERROR = 5518,          // 回调播放异常,长时间没有 
EMSG_ON_SET_PLAY_SPEED = 5519,      // 播放速度 
EMSG_REFRESH_PLAY = 5520,           //刷新视频 
EMSG_MEDIA_BUFFER_CHECK = 5521,     // 缓存检查 
EMSG_ON_MEDIA_SET_PLAY_SIZE = 5522, // 设置高清/标清 
EMSG_ON_MEDIA_FRAME_LOSS = 5523,    // 超过4S没有收到数据 
EMSG_ON_YUV_DATA = 5524,             // YUV数据回调 
EMSG_MEDIA_SETPLAYVIEW = 5525,        // 改变显示View 
EMSG_ON_FRAME_USR_DATA = 5526,        // 用户自定义信息帧回调 
EMSG_ON_Media_Thumbnail = 5527,     // 抓取视频缩略图 
EMSG_ON_MediaData_Save = 5528,        // 媒体数据开始保存 
EMSG_MediaData_Save_Process = 5529, // 媒体数据已保存大小 
EMSG_Stop_DownLoad = 5530,            //停止下载 
EMSG_START_IMG_LIST_DOWNLOAD = 5531,//图像列表下载 
EMSG_SET_INTELL_PLAY = 5532,   // 智能播放 
EMSG_ON_MEDIA_DATA = 5533,        //解码前数据回调 
EMSG_DOWN_RECODE_BPIC_START =  5534,    //录像缩略图下载开始 
EMSG_DOWN_RECODE_BPIC_FILE  =  5535,    //录像缩略图下载--文件下载结果返回 
EMSG_DOWN_RECODE_BPIC_COMPLETE =  5536, //录像缩略图下载-下载完成（结束） 
 
EMSG_MC_LinkDev = 6000, //报警订阅 
EMSG_MC_UnlinkDev = 6001,//取消报警订阅 
EMSG_MC_SendControlData = 6002,  
EMSG_MC_SearchAlarmInfo = 6003, //查询报警信息 
EMSG_MC_SearchAlarmPic = 6004,  //下载报警图片 
EMSG_MC_ON_LinkDisCb= 6005,  // 设备断线 
EMSG_MC_ON_ControlCb = 6006, 
EMSG_MC_ON_AlarmCb = 6007,// 订阅实时报警消息 
EMSG_MC_ON_PictureCb = 6008, 
EMSG_MC_ConnectDev = 6009, 
EMSG_MC_DisconnectDev = 6010, 
EMSG_MC_INIT_INFO = 6011, //报警初始化 
EMSG_MC_DeleteAlarm = 6012, //删除报警信息 
EMSG_MC_SearchAlarmByMoth = 6014, //查询历史报警信息-日期 
EMSG_MC_OnRecvAlarmJsonData = 6015,  //第三方报警服务器收到报警数据处理回调 
 
 
EMSG_XD_LinkMedia=7001, 
EMSG_XD_UnlinkMedia=7002, 
EMSG_XD_PublicHistoryList=7003, 
EMSG_XD_PublicCurrentList=7004, 
EMSG_XD_PublicDevInfo=7005, 
EMSG_XD_FetchPicture=7006, 
 
EMSG_CD_MediaTimeSect = FUN_USER_MSG_BEGIN_1 + 1200,// 废弃，不再使用 
EMSG_MC_SearchMediaByMoth = 6202, //查询Media通过指定日期 
EMSG_MC_SearchMediaByTime = 6203, //查询Media通过指定时间 
EMSG_MC_DownloadMediaThumbnail = 6204, //下载录像等媒体的缩略图 
 
EMSG_DL_ON_DOWN_FILE = FUN_USER_MSG_BEGIN_1 + 1500, 
EMSG_DL_ON_INFORMATION, 
 
EMSG_CSS_API_CMD = FUN_USER_MSG_BEGIN_1 + 1600,// CSS接口的获取 
EMSG_KSS_API_UP_LOAD_VIDEO, //KSS API POST(VIDEO) 上传视频至金山云 
EMSG_KSS_API_CMD_GET, //KSS API GET 
EMSG_KSS_API_UP_LOAD_PHOTO, //KSS API POST(PHOTO) 
 
EMSG_MC_ON_Alarm_NEW = FUN_USER_MSG_BEGIN_1 + 1700, 
 
EMSG_FIR_IM_CHECK_LATEST = FUN_USER_MSG_BEGIN_1 + 1800, 
 
EMSG_QT_API_INIT = FUN_USER_MSG_BEGIN_1 + 2000, // QintTing API 初始化蜻蜓库 
EMSG_QT_GET_CATEGORYIES, //获取目录 
EMSG_QT_GET_CHANNELS, //获取点播电台 
EMSG_QT_GET_LIVE_CHANNELS, //获取直播电台 
EMSG_QT_GET_PROGRAMS, //获取指定节目信息 
EMSG_QT_GET_LIVE_PROGRAMS, //获取指定节目信息（直播） 
EMSG_QT_GET_PROGRAMS_DETAIL, //获取指定节目信息（点播） 
EMSG_QT_SEARCH_CONTENT, //检索内容 
 
EMSG_JPEG_TO_MP4_ON_PROGRESS = FUN_USER_MSG_BEGIN_1 + 3000, // JPEG转MP4方法 进度 
EMSG_JPEG_TO_MP4_ADD_FILE, //创建 
EMSG_JPEG_TO_MP4_CLOSE,  //关闭 
EMSG_JPEG_TO_MP4_CANCEL, //取消 
 
//视频广场、雄迈云 
EMSG_SYS_EDIT_USER_PHOTOS = FUN_USER_MSG_BEGIN_1 + 3500, //修改用户相册 
EMSG_SYS_CHECK_USER_PHONE, //检查用户手机号是否已被注册 
EMSG_SYS_CHECK_USER_MAIL,  //检查用户邮箱是否已被注册 
EMSG_SYS_CHANGE_DEV_LOGIN_PWD, //设备基本信息修改 
EMSG_SYS_BINDING_ACCOUNT, //用户账号绑定 
 
// 其它自定义消息 
// 广告更新等消息返回 
EMSG_CM_ON_VALUE_CHANGE = FUN_USER_MSG_BEGIN_1 + 3600, 
EMSG_CM_ON_GET_SYS_MSG = 8603, //获取系统当前最新消息 
EMSG_CM_ON_GET_SYS_MSG_LIST = 8604, //获取系统当前最新消息list  


</div> </pre>
 


## 对象属性<label style="color:Dodgerblue">EOBJ_ATTR</label>枚举值说明</b>

<div style="margin-left:20px;"> <pre>
typedef enum EOBJ_ATTR 
{ 
     EOA_DEVICE_ID = 10000, 
     EOA_CHANNEL_ID = 10001, 
     EOA_IP = 10002, 
     EOA_PORT = 10003, 
     EOA_IP_PORT = 10004, 
     EOA_STREAM_TYPE = 10005, 
     EOA_NET_MODE = 10006, 
     EOA_COM_TYPE = 10007, 
     EOA_VIDEO_WIDTH_HEIGHT = 10008,    // 获取视频的宽和高信息 
     EOA_VIDEO_FRATE = 10009,          // 获取视频帧率信息 
     EOA_VIDEO_BUFFER_SIZE = 10010,    // 获取缓冲的帧数 
     EOA_PLAY_INFOR = 10011, 
     EOA_PCM_SET_SOUND = 10012,          // -100~100 
     EOA_CUR_PLAY_TIME = 10013,       // 获取当前播放的时间,返回uint64单位毫秒 
     EOA_MEDIA_YUV_USER = 10014,                // 设置YUV回调 
     EOA_SET_MEDIA_VIEW_VISUAL = 10015,        // 是否画视频数据 
     EOA_SET_MEDIA_DATA_USER_AND_NO_DEC = 10016, //解码前数据回调，不播放 
     EOA_SET_MEDIA_DATA_USER = 10017,    //解码前数据回调，同时播放 
     EOA_DISABLE_DSS_FUN = 10018,            // 禁用DSS功能 
     EOA_DEV_REAL_PLAY_TYPE = 10019,            // 实时媒体连接方式指定 
     EOA_SET_PLAYER_USER = 10020,            // 设置回调消息接收者 
     EOA_GET_ON_FRAME_USER_DATA = 10021,     // 重新回调一次信息帧（ON_FRAME_USER_DATA）,如果没有就没有回调 
}EOBJ_ATTR;  
</pre></div> 
 
## 设备状态<label style="color:Dodgerblue">EFunDevState</label>枚举值说明</b>

<div> <pre>
typedef enum EFunDevState
 {
    EDevState_UNKOWN = 0,           // 未知
    EDevState_ON_LINE = 1,          // 在线（如果是门铃，同时说明在唤醒状态）
    EDevState_ON_SLEEP = 2,         // 休眠状态
    EDevState_OFF_LINE = -1,        // 不在线
    EDevState_NO_SUPPORT = -2,      // 不支持
    EDevState_NotAllowed = -3,      // 没权限
}EFunDevState;

 </pre></div>

## 设备状态类型<label style="color:Dodgerblue">EFunDevStateType</label>枚举值说明</b>

<div><pre>
typedef enum EFunDevStateType
{
    EFunDevStateType_P2P = 0,        //P2P要用新的状态服务查下
    EFunDevStateType_TPS_V0 = 1,     //老的那种转发，用于老程序（2016年以前的）的插座，新的插座程序使用的是TPS
    EFunDevStateType_TPS = 2,        //透传服务
    EFunDevStateType_DSS = 3,        //媒体直播服务
    EFunDevStateType_CSS = 4,        //云存储服务
    EFunDevStateType_P2P_V0 = 5,     //P2P用老的方式,通过穿透库查询获取到的设备P2P状态
    EFunDevStateType_IP = 6,         //IP方式
    EFunDevStateType_RPS = 7,        //RPS可靠的转发
    EFunDevStateType_IDR = 8,        //门铃状态
    EFunDevStateType_SIZE,           //NUM....
}EFunDevStateType;
</pre></div>

## 设备普通网络设置<label style="color:Dodgerblue">SDK_CONFIG_NET_COMMON_V2</label>结构体说明</b>

<div><pre>
ypedef struct SDK_CONFIG_NET_COMMON_V2
{
    //!主机名
    char HostName[NET_NAME_PASSWORD_LEN];
    //!主机IP
    CONFIG_IPAddress HostIP;
    //!子网掩码
    CONFIG_IPAddress Submask;
    //!网关IP
    CONFIG_IPAddress Gateway;
    //!HTTP服务端口
    int HttpPort;
    //!TCP侦听端口
    int TCPPort;
    //!SSL侦听端口
    int SSLPort;
    //!UDP侦听端口
    int UDPPort;
    //!最大连接数
    int MaxConn;
    //!监视协议 {"TCP","UDP","MCAST",⋯}
    int MonMode;
    //!限定码流值
    int MaxBps;
    //!传输策略
    //char TransferPlan[NET_NAME_PASSWORD_LEN];
    int TransferPlan;
    
    //!是否启用高速录像下载测率
    bool bUseHSDownLoad;
    
    //!MAC地址
    char sMac[NET_MAX_MAC_LEN];
    
    char sSn[NET_MAX_MAC_LEN]; 	///序列号
#ifndef WIN32
    int DeviceType;   //设备类型,手机区分是插座还是普通设备
#endif
    int ChannelNum;			///通道数
    int	Device_Type;		///设备类型，见enum SDK_DevType
    char Resume[56];		///保留
}SDK_CONFIG_NET_COMMON_V2;

</pre></div>

## 录像文件<label style="color:Dodgerblue">H264_DVR_FILE_DATA</label>结构体说明</b>

<div><pre>
typedef struct H264_DVR_FILE_DATA
{
    int ch;						//通道号
    int size;					//文件大小
    char sFileName[108];		//文件名
    SDK_SYSTEM_TIME stBeginTime;//文件开始时间
    SDK_SYSTEM_TIME stEndTime;	//文件结束时间
    void *hWnd;					//窗口句柄
    int StreamType;				//码流类型是回放主码流还是辅助码流
#ifndef OS_IOS
    H264_DVR_FILE_DATA()
    {
        hWnd=0;
        StreamType =0;
    };
#endif
}H264_DVR_FILE_DATA;

</pre></div>

## 视频流畅度等级<label style="color:Dodgerblue">EDECODE_TYPE</label>枚举值说明</b>

<div><pre>
typedef enum EDECODE_TYPE
{
    EDECODE_REAL_TIME_STREAM0,      // 最实时--适用于IP\AP模式等网络状态很好的情况
    EDECODE_REAL_TIME_STREAM1,      //
    EDECODE_REAL_TIME_STREAM2,      //
    EDECODE_REAL_TIME_STREAM3,      // 中等
    EDECODE_REAL_TIME_STREAM4,      //
    EDECODE_REAL_TIME_STREAM5,      //
    EDECODE_REAL_TIME_STREAM6,      // 最流畅--适用于网络不好,网络波动大的情况
    EDECODE_FILE_STREAM = 100,        // 文件流
} EDECODE_TYPE;

</pre></div>

## 捕获压缩格式类型<label style="color:Dodgerblue">SDK_CAPTURE_COMP_t</label>枚举值说明</b>

<div><pre>
/// 捕获压缩格式类型
enum SDK_CAPTURE_COMP_t {
    SDK_CAPTURE_COMP_DIVX_MPEG4,	///< DIVX MPEG4。
    SDK_CAPTURE_COMP_MS_MPEG4,		///< MS MPEG4。
    SDK_CAPTURE_COMP_MPEG2,			///< MPEG2。
    SDK_CAPTURE_COMP_MPEG1,			///< MPEG1。
    SDK_CAPTURE_COMP_H263,			///< H.263
    SDK_CAPTURE_COMP_MJPG,			///< MJPG
    SDK_CAPTURE_COMP_FCC_MPEG4,		///< FCC MPEG4
    SDK_CAPTURE_COMP_H264,			///< H.264
    SDK_CAPTURE_COMP_H265,			///< H.265
    SDK_CAPTURE_COMP_NR				///< 枚举的压缩标准数目。
};
</pre>
</div>

## 分辨率<label style="color:Dodgerblue">SDK_CAPTURE_SIZE_t</label>枚举值说明</b>

<div><pre>
//这些结构体和枚举是提供给外部使用，所有可能会和设备那边定义了2次,所以都在前面加了SDK_
enum SDK_CAPTURE_SIZE_t {
    SDK_CAPTURE_SIZE_D1,		///< 720*576(PAL)	720*480(NTSC)
    SDK_CAPTURE_SIZE_HD1,		///< 352*576(PAL)	352*480(NTSC)
    SDK_CAPTURE_SIZE_BCIF,		///< 720*288(PAL)	720*240(NTSC)
    SDK_CAPTURE_SIZE_CIF,		///< 352*288(PAL)	352*240(NTSC)
    SDK_CAPTURE_SIZE_QCIF,		///< 176*144(PAL)	176*120(NTSC)
    SDK_CAPTURE_SIZE_VGA,		///< 640*480(PAL)	640*480(NTSC)
    SDK_CAPTURE_SIZE_QVGA,		///< 320*240(PAL)	320*240(NTSC)
    SDK_CAPTURE_SIZE_SVCD,		///< 480*480(PAL)	480*480(NTSC)
    SDK_CAPTURE_SIZE_QQVGA,		///< 160*128(PAL)	160*128(NTSC)
    SDK_CAPTURE_SIZE_ND1 = 9,     ///< 240*192
    SDK_CAPTURE_SIZE_650TVL,      ///< 926*576
    SDK_CAPTURE_SIZE_720P,        ///< 1280*720
    SDK_CAPTURE_SIZE_1_3M,        ///< 1280*960
    SDK_CAPTURE_SIZE_UXGA ,       ///< 1600*1200
    SDK_CAPTURE_SIZE_1080P,       ///< 1920*1080
    SDK_CAPTURE_SIZE_WUXGA,       ///< 1920*1200
    SDK_CAPTURE_SIZE_2_5M,        ///< 1872*1408
    SDK_CAPTURE_SIZE_3M,          ///< 2048*1536
    SDK_CAPTURE_SIZE_5M,          ///< 3744*1408
    SDK_CAPTURE_SIZE_NR =19,
    SDK_CAPTURE_SIZE_1080N = 19,     ///< 960*1080
    SDK_CAPTURE_SIZE_4M,        ///< 2592*1520
    SDK_CAPTURE_SIZE_6M,		///< 3072×2048
    SDK_CAPTURE_SIZE_8M,		///< 3264×2448
    SDK_CAPTURE_SIZE_12M,		///< 4000*3000
    SDK_CAPTURE_SIZE_4K,		///< 4096 * 2160通用/3840*2160海思
    SDK_CAPTURE_SIZE_EXT_V2_NR =25,
    SDK_CAPTURE_SIZE_720N = 25,  		//  640*720
    SDK_CAPTURE_SIZE_WSVGA,			///< 1024*576
    SDK_CAPTURE_SIZE_NHD,      		// 0*0
    SDK_CAPTURE_SIZE_3M_N,      		// 0*0
    SDK_CAPTURE_SIZE_4M_N,      		// 0*0
    SDK_CAPTURE_SIZE_5M_N,      		// 0*0
    SDK_CAPTURE_SIZE_4K_N,      		// 0*0
    SDK_CAPTURE_SIZE_EXT_V3_NR,
};

</pre></div>

## 设备类型<label style="color:Dodgerblue">EFUN_DEV_TYPE</label>枚举值说明</b>

<div><pre>
// 库对象全局变量设置
typedef enum EFUN_DEV_TYPE
{
    EE_DEV_NORMAL_MONITOR,                              //传统监控设备
    EE_DEV_INTELLIGENTSOCKET,                           //智能插座
    EE_DEV_SCENELAMP,                                   //情景灯泡
    EE_DEV_LAMPHOLDER,                                  //智能灯座
    EE_DEV_CARMATE,                                     //汽车伴侣
    EE_DEV_BIGEYE,                                      //大眼睛
    EE_DEV_SMALLEYE,                                    //小眼睛/小雨点
    EE_DEV_BOUTIQUEROBOT,                               //精品机器人 雄迈摇头机
    EE_DEV_SPORTCAMERA,                                 //运动摄像机
    EE_DEV_SMALLRAINDROPS_FISHEYE,                      //鱼眼小雨点
    EE_DEV_LAMP_FISHEYE,                                //鱼眼灯泡
    EE_DEV_MINIONS,                                     //小黄人
    EE_DEV_MUSICBOX,                                    //智能音响 wifi音乐盒
    EE_DEV_SPEAKER,                                     //wifi音响
    EE_DEV_LINKCENTERT = 14,                            //智联中心
    EE_DEV_DASH_CAMERA,                                 //勇士行车记录仪
    EE_DEV_POWERSTRIP,                                  //智能排插
    EE_DEV_FISH_FUN,                                    //鱼眼模组
    EE_DEV_DRIVE_BEYE = 18,                             //大眼睛行车记录仪
    EE_DEV_SMARTCENTER  = 19,                           //智能中心
    EE_DEV_UFO = 20,                                    //飞碟
    EE_DEV_IDR = 21,                                    //门铃--xmjp_idr_xxxx
    EE_DEV_BULLET = 22,                                 //E型枪机--XMJP_bullet_xxxx
    EE_DEV_DRUM = 23,                                   //架子鼓--xmjp_drum_xxxx
    EE_DEV_CAMERA = 24,                                 //摄像机--camera_xxxx
    EE_DEV_FEEDER = 25,                                 //喂食器设备--feeder_xxxx
    EE_DEV_PEEPHOLE = 26,                               //猫眼设备--xmjp_peephole
    EE_DEV_CZ_IDR = 0x11130001,                         //定制门铃1--dev_cz_idr_xxxx
    
    EE_DEV_NSEYE = 601,                                 //直播小雨点
}EFUN_DEV_TYPE;

</pre></div>
