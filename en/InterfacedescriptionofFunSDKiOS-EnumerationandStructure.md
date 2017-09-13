<b>7.1.Message<label style="color:Dodgerblue">MsgContent</label>description</b><br/>
<div>
<label style="color:#606"><b>public class</b> </label>MsgContent {<br/>
<div style="margin-left:30px;">
    <label style="color:#606"><b>public int </b> </label><label style="color:blue">sender;</label>   <label style="color:green">// Message sender</label><br/>
    <label style="color:#606"><b>public int </b> </label><label style="color:blue">arg3;</label>   <label style="color:green">// Message returned value</label><br/>
    <label style="color:#606"><b>public</b> </label>String <label style="color:blue">str;</label>   <label style="color:green">// Message returned value</label><br/>
    <label style="color:#606"><b>public byte[] </b> </label><label style="color:blue"> pData;</label>   <label style="color:green">// Message returned value</label><br/>
    <label style="color:#606"><b>int </b> </label><label style="color:blue">seq; </label>   <label style="color:green">// Serial number</label><br/>
</div>
};
</div>
<b>7.2.Massage<label style="color:Dodgerblue">EUIMSG</label> enumeration value description</b><br/>
<div style="margin-left:20px;">
EUIMSG .EMSG_SYS_GET_DEV_INFO_BY_USER = USER_MSG_BEGIN, <label style="color:green">// Get device information</label><br/>

EUIMSG .EMSG_SYS_USER_REGISTER,        <label style="color:green">// Register user
</label><br/>

EUIMSG .EMSG_SYS_USER_CHECKVALID,   <label style="color:green">// Check if the user name is available</label><br/>

EUIMSG .EMSG_SYS_PSW_CHANGE,           <label style="color:green">// modify user password</label><br/>

EUIMSG .EMSG_SYS_ADD_DEVICE,             <label style="color:green">// Add user device</label><br/>

EUIMSG .EMSG_SYS_CHANGEDEVINFO,           <label style="color:green"> // Modify user device information</label><br/>

EUIMSG .EMSG_SYS_DELETE_DEV,             <label style="color:green"> // Delete device</label><br/>

EUIMSG .EMSG_SYS_TESTUPDATE,             <label style="color:green">// Update pictures</label><br/>

EUIMSG .EMSG_SYS_PSW_RESTORE,          <label style="color:green"> // User password recovery</label><br/>

EUIMSG. EMSG_SYS_GET_DEV_STATE,       <label style="color:green">// Get device status</label><br/>

EUIMSG.EMSG_SYS_GET_PHONE_CHECK_CODE, <label style="color:green">// Get phone verification code</label><br/><br/>


EUIMSG.EMSG_SYS_REGISER_USER_XM,      <label style="color:green">// User register
</label><br/>

EUIMSG.EMSG_ SYS_GET_DEV_INFO_BY_USER_XM, <label style="color:green">//Synchronous login</label><br/>

EUIMSG.EMSG_SYS_EDIT_PWD_XM,            <label style="color:green">// Forget user login password</label><br/>

EUIMSG.EMSG_SYS_FORGET_PWD_XM,            <label style="color:green"> // Forget user login password</label><br/>

EUIMSG.EMSG_SYS_REST_PWD_CHECK_XM,  <label style="color:green">// Verify verification code</label><br/>

EUIMSG.EMSG_SYS_RESET_PWD_XM,        <label style="color:green"> // Reset user login password </label><br/><br/>

 

EUIMSG .EMSG_DEV_GET_CHN_NAME,           <label style="color:green">  // Device obtain channel name</label><br/>

EUIMSG .EMSG_DEV_FIND_FILE,                 <label style="color:green"> // Device query file</label><br/>

EUIMSG .EMSG_DEV_ON_DISCONNECT,          <label style="color:green"> // Device disconnect</label><br/>

EUIMSG. EMSG_DEV_PTZ_CONTROL,      <label style="color:green"> // PTZ control
</label><br/>

EUIMSG. EMSG_ DEV_START_TALK,        <label style="color:green"> //Voice talk-back - start</label><br/>

EUIMSG. EMSG_ DEV_STOP_TALK,          <label style="color:green"> //Voice talk-back - stop</label><br/>

EUIMSG. EMSG_DEV_SEND_MEDIA_DATA,     <label style="color:green"> //Voice talk-back - send data</label><br/>

EUIMSG. EMSG_EMSG_DEV_SEARCH_DEVICES,<label style="color:green">//Device search
</label><br/>

EUIMSG. EMSG_DEV_GET_CONFIG,         <label style="color:green">//Get device configuration</label><br/>

EUIMSG. EMSG_DEV_GET_CONFIG_JSON,    <label style="color:green">//Get device configuration (Json)</label><br/>

EUIMSG. EMSG_DEV_SET_CONFIG,         <label style="color:green">//Set device configuration</label><br/>

EUIMSG. EMSG_DEV_SET_CONFIG_JSON,    <label style="color:green">//Set device configuration（Json）</label><br/>

EUIMSG. EMSG_DEV_GET_ATTR,            <label style="color:green"> //Get device attributes</label><br/>

EUIMSG. EMSG_DEV_SET_ATTR,             <label style="color:green">  //Set device attributes</label><br/>

EUIMSG.EMSG_DEV_AP_CONFIG,            <label style="color:green">       //Quick configuration</label><br/>

EUIMSG.EMSG_DEV_SET_WIFI_CFG,         <label style="color:green">  //Set WiFi configuration </label><br/>

EUIMSG.EUIMSG. EMSG_DEV_OPTION,        <label style="color:green">    //Device options</label><br/>

EUIMSG. EMSG_DEV_CHECK_UPGRADE,         <label style="color:green"> //Check upgrade
</label><br/>

EUIMSG. EMSG_DEV_START_UPGRADE,         <label style="color:green">  //Device upgrade </label><br/>

EUIMSG.EMSG_DEV_STOP_UPGRADE,       <label style="color:green"> //Stop device upgrade </label><br/>

EUIMSG. EMSG_CHECK_FILE_COMPLETE,       <label style="color:green">   //Download completion of upgrade file</label><br/>

EUIMSG.EMSG_DEV_ON_UPGRADE_PROGRESS,     <label style="color:green"> //Upgrade progress 

</label><br/><br/>

 

EUIMSG .EMSG_SET_PLAY_SPEED,            <label style="color:green">  // 视Video control - set play speed</label><br/>

EUIMSG .EMSG_START_PLAY,              <label style="color:green"> // Video control - play video</label><br/>

EUIMSG .EMSG_STOP_PLAY,                  <label style="color:green">      // Video control – stop playing</label><br/>

EUIMSG .EMSG_PAUSE_PLAY,                <label style="color:green">     // Video control - continue / pause</label><br/>

EUIMSG .EMSG_MEDIA_PLAY_DESTORY,        <label style="color:green">  // Exit media play, notify playing object</label><br/>

EUIMSG .EMSG_START_SAVE_MEDIA_FILE,     <label style="color:green">  // Save video. Saving format is distinguished by suffix,.dav private;.avi: AVI format;.mp4: MP4 format</label><br/>

EUIMSG .EMSG_STOP_SAVE_MEDIA_FILE, <label style="color:green"> // Save video. Saving format is distinguished by suffix,.dav private;.avi: AVI format;.mp4: MP4 format</label><br/>

EUIMSG .EMSG_SAVE_IMAGE_FILE,            <label style="color:green"> // Capture image, saving format is distinguished by suffix, .bmp or .jpg</label><br/>

EUIMSG .EMSG_ON_PLAY_INFO,              <label style="color:green">   // Message in playback process</label><br/>

EUIMSG .EMSG_ON_PLAY_END,                <label style="color:green">  // Playback end</label><br/>

EUIMSG .EMSG_ SEEK_TO_POS,               <label style="color:green">    // Locate playing position</label><br/>

EUIMSG .EMSG_ SEEK_TO_TIME,             <label style="color:green">    // Locate playing time</label><br/>

EUIMSG .EMSG_ SET_SOUND,                 <label style="color:green">    // Sound setting</label><br/><br/>

 

EUIMSG .EMSG_ON_FILE_DOWNLOAD,          <label style="color:green">   // File download</label><br/>

EUIMSG.EMSG_ON_FILE_DLD_COMPLETE,   <label style="color:green"> // File download complete</label><br/>

EUIMSG. EMSG_ON_FILE_DLD_POS,       <label style="color:green"> // File download progress</label><br/><br/>

 

EUISG. ELOG_MSG_INIT,               <label style="color:green">  // Log initialization</label><br/>

EUISG. EMSG_APP_ON_MSG_LOG           <label style="color:green"> // Log information callback</label><br/>

EUISG. EMSG_DEV_GET_LAN_ALARM        <label style="color:green"> //Local area network alarm</label><br/>

EUIMSG . DEV_CMD_EN                    <label style="color:green">  //Video calendar query</label><br/>

EUIMSG . DEV_SEARCH_PIC               <label style="color:green">//Device compressed pictures</label><br/>

EUIMSG . EMSG_DEV_START_UPLOAD_DATA        <label style="color:green">       //Open reported data</label><br/>

EUIMSG . EMSG_DEV_STOP_UPLOAD_DATA          <label style="color:green">     //Stop reported data</label><br/>

EUIMSG . EMSG_DEV_ON_UPLOAD_DATA           <label style="color:green">   //Reported data callback return</label><br/><br/>

 

 

EUIMSG. SYS_DEV_UPLOAD_VIDEO        <label style="color:green"> //Upload local video</label><br/>

EUIMSG . EMSG_SYS_CHECK_USER_REGISTE = 5046;<label style="color:green">//Check if the user has been registered</label><br/>

EUIMSG . EMSG_SYS_LOGOUT_TO_XM = 5047; <label style="color:green">//Synchronization exit</label><br/>

EUIMSG . EMSG_SYS_NO_VALIDATED_REGISTER = 5048; <label style="color:green">// No need to verify registration</label><br/>

EUIMSG . EMSG_SYS_GET_USER_INFO = 5049; <label style="color:green">// Get user information</label><br/>

EUIMSG . EMSG_SYS_SEND_BINDING_PHONE_CODE = 5050; <label style="color:green">// Bind security phone (1) - send verification code</label><br/>

EUIMSG . EMSG_SYS_BINDING_PHONE = 5051; <label style="color:green">// Bind security phone (2) - verify code and bind</label><br/>

EUIMSG . SYS_CLOUDUPGRADE_CHECK = 5052; <label style="color:green">// Does the device need to upgrade query</label><br/>

EUIMSG . SYS_CLOUDUPGRADE_DOWNLOAD = 5053; <label style="color:green">// Device cloud upgrade download</label><br/>

EUIMSG . SYS_SEND_BINDING_EMAIL_CODE = 5054; <label style="color:green">// Bind security mailbox (1) - send verification code</label><br/>

EUIMSG . SYS_BINDING_EMAIL = 5055; <label style="color:green">// Bind security mailbox (2) - verify code and bind</label><br/>

EUIMSG . EMSG_SYS_REGISER_USER_XM_EXTEND = 5056;     <label style="color:green"> // User register (Extend)</label><br/>

EUIMSG . EMSG_SYS_REGISTE_BY_EMAIL_EXTEND = 5057;  <label style="color:green"> // Mailbox register (Extend)</label><br/>

EUIMSG . EMSG_SYS_NO_VALIDATED_REGISTER_EXTEND = 5058; <label style="color:green"> // No need to verify registration (Extend)</label><br/>

EUIMSG . STOP_CLOUDUPGRADE_DOWNLOAD = 5059; <label style="color:green">// Stop downloading</label><br/>
</div>
 


<b>7.3.Object properties <label style="color:Dodgerblue">EOBJ_ATTR</label>enumeration value description</b><br/>
<div style="margin-left:20;">
       EOA_DEVICE_ID = 1,<br/>
       EOA_CHANNEL_ID,<br/>
       EOA_IP,<br/>
       EOA_PORT,<br/>
       EOA_IP_PORT,<br/>
       EOA_STREAM_TYPE,<br/>
       EOA_NET_MODE,<br/>
       EOA_COM_TYPE,<br/>

</div>

 
