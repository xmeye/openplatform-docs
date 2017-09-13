## 消息<label style="color:Dodgerblue">MsgContent</label>类说明</b><br/>

<div style="margin-left:20px;">
<label style="color:#606"><b>public class</b> </label>MsgContent {<br/>
<div style="margin-left:30px;">
    <label style="color:#606"><b>public int </b> </label><label style="color:blue">sender;</label>   <label style="color:green">// 消息发送者</label><br/>
    <label style="color:#606"><b>public int </b> </label><label style="color:blue">arg3;</label>   <label style="color:green">// 消息返回值</label><br/>
    <label style="color:#606"><b>public</b> </label>String <label style="color:blue">str;</label>   <label style="color:green">// 消息返回值</label><br/>
    <label style="color:#606"><b>public byte[] </b> </label><label style="color:blue"> pData;</label>   <label style="color:green">// 消息返回值</label><br/>
    <label style="color:#606"><b>int </b> </label><label style="color:blue">seq; </label>   <label style="color:green">// 消息返回值</label><br/>
</div>
};
</div>

## 消息<label style="color:Dodgerblue">EUIMSG</label>枚举值说明

<div style="margin-left:20px;">
EUIMSG .EMSG_SYS_GET_DEV_INFO_BY_USER = USER_MSG_BEGIN, <label style="color:green">// 获取设备信息</label><br/>

EUIMSG .EMSG_SYS_USER_REGISTER,        <label style="color:green">// 注册用户</label><br/>

EUIMSG .EMSG_SYS_USER_CHECKVALID,   <label style="color:green">// 检查用户名是否可用</label><br/>

EUIMSG .EMSG_SYS_PSW_CHANGE,           <label style="color:green">// 修改用户密码</label><br/>

EUIMSG .EMSG_SYS_ADD_DEVICE,             <label style="color:green">// 增加用户设备</label><br/>

EUIMSG .EMSG_SYS_CHANGEDEVINFO,           <label style="color:green"> // 修改用户设备信息</label><br/>

EUIMSG .EMSG_SYS_DELETE_DEV,             <label style="color:green"> // 删除设备</label><br/>

EUIMSG .EMSG_SYS_TESTUPDATE,             <label style="color:green">// 更新图片</label><br/>

EUIMSG .EMSG_SYS_PSW_RESTORE,          <label style="color:green"> // 用户密码恢复</label><br/>

EUIMSG. EMSG_SYS_GET_DEV_STATE,       <label style="color:green">// 获取设备状态</label><br/>

EUIMSG.EMSG_SYS_GET_PHONE_CHECK_CODE, <label style="color:green">// 获取手机验证码</label><br/><br/>


EUIMSG.EMSG_SYS_REGISER_USER_XM,      <label style="color:green">// 用户注册</label><br/>

EUIMSG.EMSG_ SYS_GET_DEV_INFO_BY_USER_XM, <label style="color:green">//同步登录</label><br/>

EUIMSG.EMSG_SYS_EDIT_PWD_XM,            <label style="color:green">// 忘记用户登录密码</label><br/>

EUIMSG.EMSG_SYS_FORGET_PWD_XM,            <label style="color:green"> // 忘记用户登录密码</label><br/>

EUIMSG.EMSG_SYS_REST_PWD_CHECK_XM,  <label style="color:green">// 验证验证码</label><br/>

EUIMSG.EMSG_SYS_RESET_PWD_XM,        <label style="color:green"> // 重置用户登录密码</label><br/><br/>

 

EUIMSG .EMSG_DEV_GET_CHN_NAME,           <label style="color:green">  // 设备获取通道名称</label><br/>

EUIMSG .EMSG_DEV_FIND_FILE,                 <label style="color:green"> // 设备查询文件</label><br/>

EUIMSG .EMSG_DEV_ON_DISCONNECT,          <label style="color:green"> // 设备断开连接</label><br/>

EUIMSG. EMSG_DEV_PTZ_CONTROL,      <label style="color:green"> // 云台控制</label><br/>

EUIMSG. EMSG_ DEV_START_TALK,        <label style="color:green"> //语音对讲-开始</label><br/>

EUIMSG. EMSG_ DEV_STOP_TALK,          <label style="color:green"> //语音对讲-停止</label><br/>

EUIMSG. EMSG_DEV_SEND_MEDIA_DATA,     <label style="color:green"> //语音对讲-发送数据</label><br/>

EUIMSG. EMSG_EMSG_DEV_SEARCH_DEVICES,<label style="color:green">//设备搜索</label><br/>

EUIMSG. EMSG_DEV_GET_CONFIG,         <label style="color:green">//获取设备配置</label><br/>

EUIMSG. EMSG_DEV_GET_CONFIG_JSON,    <label style="color:green">//获取设备配置（Json）</label><br/>

EUIMSG. EMSG_DEV_SET_CONFIG,         <label style="color:green">//设置设备配置</label><br/>

EUIMSG. EMSG_DEV_SET_CONFIG_JSON,    <label style="color:green">//设置设备配置（Json）</label><br/>

EUIMSG. EMSG_DEV_GET_ATTR,            <label style="color:green"> //获取设备属性</label><br/>

EUIMSG. EMSG_DEV_SET_ATTR,             <label style="color:green">  //设置设备属性</label><br/>

EUIMSG.EMSG_DEV_AP_CONFIG,            <label style="color:green">       //快速配置</label><br/>

EUIMSG.EMSG_DEV_SET_WIFI_CFG,         <label style="color:green">  //设置WIFI配置 </label><br/>

EUIMSG.EUIMSG. EMSG_DEV_OPTION,        <label style="color:green">    //设备选项</label><br/>

EUIMSG. EMSG_DEV_CHECK_UPGRADE,         <label style="color:green"> //检查升级情况</label><br/>

EUIMSG. EMSG_DEV_START_UPGRADE,         <label style="color:green">  //设备升级 </label><br/>

EUIMSG.EMSG_DEV_STOP_UPGRADE,       <label style="color:green"> //停止设备升级 </label><br/>

EUIMSG. EMSG_CHECK_FILE_COMPLETE,       <label style="color:green">   //升级文件下载完成情况</label><br/>

EUIMSG.EMSG_DEV_ON_UPGRADE_PROGRESS,     <label style="color:green"> //升级进度</label><br/><br/>

 

EUIMSG .EMSG_SET_PLAY_SPEED,            <label style="color:green">  // 视频控制—设置播放速度</label><br/>

EUIMSG .EMSG_START_PLAY,              <label style="color:green"> // 视频控制—播放视频</label><br/>

EUIMSG .EMSG_STOP_PLAY,                  <label style="color:green">      // 视频控制—停止播放</label><br/>

EUIMSG .EMSG_PAUSE_PLAY,                <label style="color:green">     // 视频控制—继续/暂停</label><br/>

EUIMSG .EMSG_MEDIA_PLAY_DESTORY,        <label style="color:green">  // 媒体播放退出,通知播放对象</label><br/>

EUIMSG .EMSG_START_SAVE_MEDIA_FILE,     <label style="color:green">  // 保存录像,保存格式用后缀区分,.dav私有;.avi:AVI格式;.mp4:MP4格式</label><br/>

EUIMSG .EMSG_STOP_SAVE_MEDIA_FILE, <label style="color:green"> // 保存录像,保存格式用后缀区分,.dav私有;.avi:AVI格式;.mp4:MP4格式</label><br/>

EUIMSG .EMSG_SAVE_IMAGE_FILE,            <label style="color:green"> // 抓图,保存格式用后缀区分,.bmp或.jpg</label><br/>

EUIMSG .EMSG_ON_PLAY_INFO,              <label style="color:green">   // 回放过程中的信息</label><br/>

EUIMSG .EMSG_ON_PLAY_END,                <label style="color:green">  // 回放结束</label><br/>

EUIMSG .EMSG_ SEEK_TO_POS,               <label style="color:green">    // 播放位置定位</label><br/>

EUIMSG .EMSG_ SEEK_TO_TIME,             <label style="color:green">    // 播放时间定位</label><br/>

EUIMSG .EMSG_ SET_SOUND,                 <label style="color:green">    // 声音设置</label><br/><br/>

 

EUIMSG .EMSG_ON_FILE_DOWNLOAD,          <label style="color:green">   // 文件下载</label><br/>

EUIMSG.EMSG_ON_FILE_DLD_COMPLETE,   <label style="color:green"> // 文件下载完成</label><br/>

EUIMSG. EMSG_ON_FILE_DLD_POS,       <label style="color:green"> // 文件下载进度</label><br/><br/>

 

EUISG. ELOG_MSG_INIT,               <label style="color:green">  // 日志初始化</label><br/>

EUISG. EMSG_APP_ON_MSG_LOG           <label style="color:green"> // 日志信息回调</label><br/>

EUISG. EMSG_DEV_GET_LAN_ALARM        <label style="color:green"> //局域网报警</label><br/>

EUIMSG . DEV_CMD_EN                    <label style="color:green">  //录像日历查询</label><br/>

EUIMSG . DEV_SEARCH_PIC               <label style="color:green">//设备缩略图</label><br/>

EUIMSG . EMSG_DEV_START_UPLOAD_DATA        <label style="color:green">       //开启上报数据</label><br/>

EUIMSG . EMSG_DEV_STOP_UPLOAD_DATA          <label style="color:green">     //停止上报数据</label><br/>

EUIMSG . EMSG_DEV_ON_UPLOAD_DATA           <label style="color:green">   //上报数据回调处理返回</label><br/><br/>

 

 

EUIMSG. SYS_DEV_UPLOAD_VIDEO        <label style="color:green"> //上传本地视频</label><br/>

EUIMSG . EMSG_SYS_CHECK_USER_REGISTE = 5046;<label style="color:green">//检查用户是否已被注册</label><br/>

EUIMSG . EMSG_SYS_LOGOUT_TO_XM = 5047; <label style="color:green">//同步退出</label><br/>

EUIMSG . EMSG_SYS_NO_VALIDATED_REGISTER = 5048; <label style="color:green">// 无需验证注册</label><br/>

EUIMSG . EMSG_SYS_GET_USER_INFO = 5049; <label style="color:green">// 获取用户信息</label><br/>

EUIMSG . EMSG_SYS_SEND_BINDING_PHONE_CODE = 5050; <label style="color:green">// 绑定安全手机(1)—发送验证码</label><br/>

EUIMSG . EMSG_SYS_BINDING_PHONE = 5051; <label style="color:green">// 绑定安全手机(2)—验证code并绑定</label><br/>

EUIMSG . SYS_CLOUDUPGRADE_CHECK = 5052; <label style="color:green">// 设备是否需要升级查询</label><br/>

EUIMSG . SYS_CLOUDUPGRADE_DOWNLOAD = 5053; <label style="color:green">// 设备云升级下载</label><br/>

EUIMSG . SYS_SEND_BINDING_EMAIL_CODE = 5054; <label style="color:green">// 绑定安全邮箱(1)—发送验证码</label><br/>

EUIMSG . SYS_BINDING_EMAIL = 5055; <label style="color:green">// 绑定安全邮箱(2)—验证code并绑定</label><br/>

EUIMSG . EMSG_SYS_REGISER_USER_XM_EXTEND = 5056;     <label style="color:green"> // 用户注册(Extend)</label><br/>

EUIMSG . EMSG_SYS_REGISTE_BY_EMAIL_EXTEND = 5057;  <label style="color:green"> // 邮箱注册(Extend)</label><br/>

EUIMSG . EMSG_SYS_NO_VALIDATED_REGISTER_EXTEND = 5058; <label style="color:green"> // 无需验证注册(Extend)</label><br/>

EUIMSG . STOP_CLOUDUPGRADE_DOWNLOAD = 5059; <label style="color:green">// 停止下载</label><br/>
</div>
 


## 对象属性<label style="color:Dodgerblue">EOBJ_ATTR</label>枚举值说明

<div style="margin-left:20px;">
       EOA_DEVICE_ID = 1,<br/>
       EOA_CHANNEL_ID,<br/>
       EOA_IP,<br/>
       EOA_PORT,<br/>
       EOA_IP_PORT,<br/>
       EOA_STREAM_TYPE,<br/>
       EOA_NET_MODE,<br/>
       EOA_COM_TYPE,<br/>

</div>

 
