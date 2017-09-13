## 消息<label style="color:Dodgerblue">MsgContent类说明

```
public class MsgContent {
       public int sender;               // 消息发送者
       public int arg3;                 // 消息返回值
       public String str;               // 消息返回值
       public byte[] pData;             // 消息返回值
       int seq;                         // 序列号
};
```

## 消息<label style="color:Dodgerblue">EUIMSG枚举值说明

```
EUIMSG .EMSG_SYS_GET_DEV_INFO_BY_USER = USER_MSG_BEGIN, // 获取设备信息
EUIMSG .EMSG_SYS_USER_REGISTER,        // 注册用户
EUIMSG .EMSG_SYS_USER_CHECKVALID,   // 检查用户名是否可用
EUIMSG .EMSG_SYS_PSW_CHANGE,           // 修改用户密码
EUIMSG .EMSG_SYS_ADD_DEVICE,             // 增加用户设备
EUIMSG .EMSG_SYS_CHANGEDEVINFO,            // 修改用户设备信息
EUIMSG .EMSG_SYS_DELETE_DEV,              // 删除设备
EUIMSG .EMSG_SYS_TESTUPDATE,             // 更新图片
EUIMSG .EMSG_SYS_PSW_RESTORE,           // 用户密码恢复
EUIMSG. EMSG_SYS_GET_DEV_STATE,       // 获取设备状态
EUIMSG.EMSG_SYS_GET_PHONE_CHECK_CODE, // 获取手机验证码
EUIMSG.EMSG_SYS_REGISER_USER_XM,      // 用户注册
EUIMSG.EMSG_ SYS_GET_DEV_INFO_BY_USER_XM, //同步登录
EUIMSG.EMSG_SYS_EDIT_PWD_XM,            // 忘记用户登录密码
EUIMSG.EMSG_SYS_FORGET_PWD_XM,             // 忘记用户登录密码
EUIMSG.EMSG_SYS_REST_PWD_CHECK_XM,  // 验证验证码
EUIMSG.EMSG_SYS_RESET_PWD_XM,         // 重置用户登录密码
EUIMSG .EMSG_DEV_GET_CHN_NAME,             // 设备获取通道名称
EUIMSG .EMSG_DEV_FIND_FILE,                  // 设备查询文件
EUIMSG .EMSG_DEV_ON_DISCONNECT,           // 设备断开连接
EUIMSG. EMSG_DEV_PTZ_CONTROL,       // 云台控制
EUIMSG. EMSG_ DEV_START_TALK,         //语音对讲-开始
EUIMSG. EMSG_ DEV_STOP_TALK,           //语音对讲-停止
EUIMSG. EMSG_DEV_SEND_MEDIA_DATA,      //语音对讲-发送数据
EUIMSG. EMSG_EMSG_DEV_SEARCH_DEVICES,//设备搜索
EUIMSG. EMSG_DEV_GET_CONFIG,         //获取设备配置
EUIMSG. EMSG_DEV_GET_CONFIG_JSON,    //获取设备配置（Json）
EUIMSG. EMSG_DEV_SET_CONFIG,         //设置设备配置
EUIMSG. EMSG_DEV_SET_CONFIG_JSON,    //设置设备配置（Json）
EUIMSG. EMSG_DEV_GET_ATTR,             //获取设备属性
EUIMSG. EMSG_DEV_SET_ATTR,               //设置设备属性
EUIMSG.EMSG_DEV_AP_CONFIG,                   //快速配置
EUIMSG.EMSG_DEV_SET_WIFI_CFG,           //设置WIFI配置 
EUIMSG.EUIMSG. EMSG_DEV_OPTION,            //设备选项
EUIMSG. EMSG_DEV_CHECK_UPGRADE,          //检查升级情况
EUIMSG. EMSG_DEV_START_UPGRADE,           //设备升级 
EUIMSG.EMSG_DEV_STOP_UPGRADE,        //停止设备升级 
EUIMSG. EMSG_CHECK_FILE_COMPLETE,          //升级文件下载完成情况
EUIMSG.EMSG_DEV_ON_UPGRADE_PROGRESS,      //升级进度
EUIMSG .EMSG_SET_PLAY_SPEED,              // 视频控制—设置播放速度
EUIMSG .EMSG_START_PLAY,               // 视频控制—播放视频
EUIMSG .EMSG_STOP_PLAY,                        // 视频控制—停止播放
EUIMSG .EMSG_PAUSE_PLAY,                     // 视频控制—继续/暂停
EUIMSG .EMSG_MEDIA_PLAY_DESTORY,          // 媒体播放退出,通知播放对象
EUIMSG .EMSG_START_SAVE_MEDIA_FILE,       // 保存录像,保存格式用后缀区分,.dav私有;.avi:AVI格式;.mp4:MP4格式
EUIMSG .EMSG_STOP_SAVE_MEDIA_FILE,  // 保存录像,保存格式用后缀区分,.dav私有;.avi:AVI格式;.mp4:MP4格式
EUIMSG .EMSG_SAVE_IMAGE_FILE,             // 抓图,保存格式用后缀区分,.bmp或.jpg
EUIMSG .EMSG_ON_PLAY_INFO,                 // 回放过程中的信息
EUIMSG .EMSG_ON_PLAY_END,                  // 回放结束
EUIMSG .EMSG_ SEEK_TO_POS,                   // 播放位置定位
EUIMSG .EMSG_ SEEK_TO_TIME,                 // 播放时间定位
EUIMSG .EMSG_ SET_SOUND,                     // 声音设置
EUIMSG .EMSG_ON_FILE_DOWNLOAD,             // 文件下载
EUIMSG.EMSG_ON_FILE_DLD_COMPLETE,    // 文件下载完成
EUIMSG. EMSG_ON_FILE_DLD_POS,        // 文件下载进度
EUISG. ELOG_MSG_INIT,                 // 日志初始化
EUISG. EMSG_APP_ON_MSG_LOG            // 日志信息回调
EUISG. EMSG_DEV_GET_LAN_ALARM         //局域网报警
EUIMSG . DEV_CMD_EN                      //录像日历查询
EUIMSG . DEV_SEARCH_PIC               //设备缩略图
EUIMSG . EMSG_DEV_START_UPLOAD_DATA               //开启上报数据
EUIMSG . EMSG_DEV_STOP_UPLOAD_DATA               //停止上报数据
EUIMSG . EMSG_DEV_ON_UPLOAD_DATA              //上报数据回调处理返回
EUIMSG. SYS_DEV_UPLOAD_VIDEO         //上传本地视频
EUIMSG . EMSG_SYS_CHECK_USER_REGISTE = 5046;//检查用户是否已被注册
EUIMSG . EMSG_SYS_LOGOUT_TO_XM = 5047; //同步退出
EUIMSG . EMSG_SYS_NO_VALIDATED_REGISTER = 5048; // 无需验证注册
EUIMSG . EMSG_SYS_GET_USER_INFO = 5049; // 获取用户信息
EUIMSG . EMSG_SYS_SEND_BINDING_PHONE_CODE = 5050; // 绑定安全手机(1)—发送验证码
EUIMSG . EMSG_SYS_BINDING_PHONE = 5051; // 绑定安全手机(2)—验证code并绑定
EUIMSG . SYS_CLOUDUPGRADE_CHECK = 5052; // 设备是否需要升级查询
EUIMSG . SYS_CLOUDUPGRADE_DOWNLOAD = 5053; // 设备云升级下载
EUIMSG . SYS_SEND_BINDING_EMAIL_CODE = 5054; // 绑定安全邮箱(1)—发送验证码
EUIMSG . SYS_BINDING_EMAIL = 5055; // 绑定安全邮箱(2)—验证code并绑定
EUIMSG . EMSG_SYS_REGISER_USER_XM_EXTEND = 5056;      // 用户注册(Extend)
EUIMSG . EMSG_SYS_REGISTE_BY_EMAIL_EXTEND = 5057;   // 邮箱注册(Extend)
EUIMSG . EMSG_SYS_NO_VALIDATED_REGISTER_EXTEND = 5058;  // 无需验证注册(Extend)
EUIMSG . STOP_CLOUDUPGRADE_DOWNLOAD = 5059; // 停止下载
```
 
## 对象属性<label style="color:Dodgerblue">EOBJ_ATTR枚举值说明

```
       EOA_DEVICE_ID = 1,
       EOA_CHANNEL_ID,
       EOA_IP,
       EOA_PORT,
       EOA_IP_PORT,
       EOA_STREAM_TYPE,
       EOA_NET_MODE,
       EOA_COM_TYPE,
```


 
