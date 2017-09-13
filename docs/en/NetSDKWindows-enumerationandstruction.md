
<div name="hong" id="hong" style="font-size:20px;"><b>1.Macro definition </b></div>
<div style="margin-left:15px;">
  #define <label style="color:#69f">NET_MAX_CHANNUM </label>	64    <label style="color:#c33">//Maximum numberof  channels </label><br/>
  #define <label style="color:#69f">NET_DECORDR_CH  </label>    64    <label style="color:#c33">  //Maximum number of decoded channels</label><br/>
  #define <label style="color:#69f">NET_MAX_USER_NUM	</label>60	  <label style="color:#c33">//Maximum number of users</label><br/>
  #define <label style="color:#69f">NET_MAX_RIGTH_NUM	</label>200	  <label style="color:#c33">//Maximum number of rights </label><br/>
  #define <label style="color:#69f">NET_MAX_GROUP_NUM	</label>50	  <label style="color:#c33">//Maximum number of groups </label><br/>
  #define <label style="color:#69f">NET_MAX_USER_LENGTH	</label>32	  <label style="color:#c33">//Username password maximum length </label><br/>
  #define <label style="color:#69f">NET_MAX_COMBINE_NUM	</label>2	  <label style="color:#c33">//Maximum number of combined coding channels</label><br/>
  #define <label style="color:#69f">NET_MAX_DECORDR_CH  </label>64    <label style="color:#c33">  //Maximum number of decoded channels </label>	<br/>
  #define <label style="color:#69f">NET_MAX_DDNS_TYPE	</label>5	  <label style="color:#c33">//Supported DDNS types </label><br/>
  #define <label style="color:#69f">NET_MAX_ARSP_TYPE	</label>	5<br/>
  #define <label style="color:#69f">NET_MAX_ALARMSERVER_TYPE </label>5 <label style="color:#c33"> //Support alarm center type</label><br/>
  #define <label style="color:#69f">NET_MAX_SYSFUNC	</label>20 <label style="color:#c33">//Maximum number of system functions</label><br/>
  #define <label style="color:#69f">NET_MAX_PTZ_PROTOCOL_LENGTH</label>32<label style="color:#c33">//Maximum length of PTZ protocol name</label><br/>
  #define <label style="color:#69f">NET_N_WEEKS		</label>7	<label style="color:#c33">//Week number</label><br/>
  #define <label style="color:#69f">NET_N_TSECT		</label>6	<label style="color:#c33">		//Number of time periods </label><br/>
  #define <label style="color:#69f">NET_MD_REGION_ROW	</label>32	<label style="color:#c33">	//Dynamic detection area line number</label><br/>
  #define <label style="color:#69f">NET_COVERNUM	</label>8	<label style="color:#c33">		//Number of coverage area </label><br/>
  #define <label style="color:#69f">NET_MAX_FILTERIP_NUM</label>64	<label style="color:#c33">	//Maximum filter number of IP address </label><br/>
  #define <label style="color:#69f">NET_NAME_PASSWORD_LEN</label>	64	<label style="color:#c33">	//Maximum length of username password </label><br/>
  #define <label style="color:#69f">NET_MAX_PATH_LENGTH	  </label>260<label style="color:#c33">	//Path length </label><br/>
  #define <label style="color:#69f">NET_N_MIN_TSECT		</label>	2<br/>
  #define <label style="color:#69f">NET_MAX_RETURNED_LOGLIST</label>128	<label style="color:#c33">	//Maximum bar number of log </label><br/>
  #define <label style="color:#69f">NET_MAX_MAC_LEN      </label> 32  <label style="color:#c33">    //Maximum character length of MAC address</label><br/>
  #define <label style="color:#69f">NET_IW_ENCODING_TOKEN_MAX  </label>       128<br/>
  #define <label style="color:#69f">NET_MAX_AP_NUMBER     </label>  32 <label style="color:#c33">   //SID maximum number, tentative 10 </label><br/>
  #define <label style="color:#69f">NET_MAX_INFO_LEN	</label>	     128<br/>
  #define <label style="color:#69f">NET_MAX_USERNAME_LENGTH	</label>	128<br/>
  #define <label style="color:#69f">NET_MAX_SERIALNO_LENGTH	</label> 128<label style="color:#c33">  //Maximum number of decoded channels</label><br/>
  #define <label style="color:#69f">NET_CHANNEL_NAME_MAX_LEN </label>    64<label style="color:#c33">//Maximum length of channel name </label><br/>
  #define <label style="color:#69f">NET_MAX_LINE_PER_OSD_AREA   </label>  12<label style="color:#c33">	//Maximum number of characters that can be displayed in the OSD region of the code 
</label><br/>

  <label style="color:#c33">//DDNS parameters <br/></label><br/>
  #define <label style="color:#69f">DDNS_MAX_DDNS_NAMELEN  </label>    64  	<label style="color:#c33">	//Host name length</label><br/>
  #define <label style="color:#69f">DDNS_MAX_DDNS_PWDLEN   </label>    32   	<label style="color:#c33">//Password length </label><br/>
  #define <label style="color:#69f">DDNS_MAX_DDNS_IPSIZE   </label>   64   	<label style="color:#c33">//IP address length</label><br/>
  #define <label style="color:#69f">DDNS_MAX_DDNS_IDSIZE    </label>32  <label style="color:#c33">//Device identifier length</label><br/>
  #define <label style="color:#69f">DDNS_MAX_SERIALINFO_SIZE  </label>16 <label style="color:#c33">	//Serial number and username length</label><br/>

  #define  <label style="color:#69f">NET_MAX_MSK_SIZE  </label>       128<label style="color:#c33">//Size of mask array </label><br/><br/>


  <label style="color:#c33">//Camera parameters  </label><br/>
  #define <label style="color:#69f">CAMERAPARA_MAXNUM   </label>     16<label style="color:#c33">//Current maximum length in the exposure ability </label><br/><br/>
  <label style="color:#c33">//Maximum number of messages</label><br/>
  #define <label style="color:#69f">NET_MAX_RECIVE_MSG_PHONE_COUNT</label>3<label style="color:#c33">///<Maximum number of text messages</label><br/><br/>


  <label style="color:#c33">//VGA resolution   </label><br/>
  #define <label style="color:#69f">VGA_MAXNUM    </label>    32       <label style="color:#c33">//Resolution type </label><br/>
  #define <label style="color:#69f">VGA_NAME_LENGTH  </label>  10      <label style="color:#c33">	//Resolution length		</label><br/><br/>

  <label style="color:#c33">//Displayed device list (device search) </label><br/>
  #define <label style="color:#69f">DEV_LIST_SHOW </label>    256<br/><br/>

  <label style="color:#c33">//IP SIZE</label><br/>
  #define <label style="color:#69f">IP_SIZE  </label>      16<br/>
  #define<label style="color:#69f">  MAX_HVR_CHNCAP  16</label><br/>
  <label style="color:#c33">//DDNS server device information</label><br/><br/>


 <label style="color:#c33"> //Channel mode </label><br/>
  #define <label style="color:#69f">MAX_HVR_CHNCAP_CHN</label>  32<br/>

  #define  <label style="color:#69f">NET_NAME_TOKEN_LEN</label> 128<br/>

  #define  <label style="color:#69f">NET_NAME_URL_LEN </label> 128<br/>
  #define  <label style="color:#69f">NET_NAME_ID_LEN </label>  64<br/>
  #define  <label style="color:#69f">NET_MAX_POS_FUNC_KEYWORDS</label>4<label style="color:#c33"> //Maximum number of keywords supported in the POS function</label><br/>
  #define  <label style="color:#69f">NET_MAX_TITLE_DOT_BUF_LEN</label>	64*24*24<br/>
  <label style="color:#c33">//Hard disk information </label><br/>
  #define <label style="color:#69f">NET_FSLEN</label>  8  <label style="color:#c33">//从IConstraint::FS_LEN拷过来</label><br/>

</div>
<hr>
<br/><br/>

<div name="meiju" id="meiju" style="font-size:20px;"><b>2.Enumeration Definition</b></div>

<div name="meiju1" id="meiju1" style="font-size:15px;"><b>2.1 PTZ operation type </b></div>


enum PTZ_ControlType
{
<div style="margin-left:20px;">
	TILT_UP = 0,					<label style="color:#c33">//Up</label>  <br/>
	TILT_DOWN,					<label style="color:#c33">//Down </label>     <br/>  
	PAN_LEFT,					<label style="color:#c33">//Left</label>  <br/>   
	PAN_RIGHT,					<label style="color:#c33">//Right</label>   <br/>  
	PAN_LEFTTOP,					<label style="color:#c33">//Left top </label> <br/>      
	PAN_LEFTDOWN,					<label style="color:#c33">//Left down </label>  <br/>
	PAN_RIGTHTOP,					<label style="color:#c33">//Right top </label><br/>
	PAN_RIGTHDOWN,					<label style="color:#c33">//Right down </label><br/>
	ZOOM_OUT_1,					<label style="color:#c33">//Zoom small</label><br/>
	ZOOM_IN_1,					<label style="color:#c33">//Zoom large  </label><br/>
	FOCUS_FAR,					<label style="color:#c33">//Focus backward adjust </label><br/>
	FOCUS_NEAR,					<label style="color:#c33">//Focus forward adjust </label><br/>
	IRIS_OPEN,					<label style="color:#c33">//Aperture expansion</label><br/>
	IRIS_CLOSE,					<label style="color:#c33">//Aperture narrowing 13</label><br/>

	EXTPTZ_OPERATION_ALARM,			   <label style="color:#c33"> //Alarm function   </label><br/>
	EXTPTZ_LAMP_ON,					<label style="color:#c33">//Turn on light</label><br/>
	EXTPTZ_LAMP_OFF,				<label style="color:#c33">//Turn off light</label><br/>
	EXTPTZ_POINT_SET_CONTROL,		   <label style="color:#c33"> //Set preset point   </label><br/>
	EXTPTZ_POINT_DEL_CONTROL,		   <label style="color:#c33"> //Clear preset point   </label><br/>
	EXTPTZ_POINT_MOVE_CONTROL,		   <label style="color:#c33"> //Move preset point</label><br/>
	EXTPTZ_STARTPANCRUISE,			   <label style="color:#c33"> //Start horizontal rotation 	</label><br/>
	EXTPTZ_STOPPANCRUISE,			   <label style="color:#c33"> //Stop horizontal rotation 		</label><br/>
	EXTPTZ_SETLEFTBORDER,			   <label style="color:#c33"> //Set left boundary 	</label><br/>	
	EXTPTZ_SETRIGHTBORDER,			   <label style="color:#c33"> //Set right boundary	</label><br/>
	EXTPTZ_STARTLINESCAN,			   <label style="color:#c33"> //Automatic scanning start  </label><br/>
	EXTPTZ_CLOSELINESCAN,			   <label style="color:#c33"> //Automatic scanning stop  </label><br/>
	EXTPTZ_ADDTOLOOP,				<label style="color:#c33">//Add the preset point to cruise line  p1 cruise line  p2 preset point  value</label><br/>
	EXTPTZ_DELFROMLOOP,				<label style="color:#c33">//Delete the preset point in the cruise line  p1 cruise line  p2 preset point value</label><br/>
	EXTPTZ_POINT_LOOP_CONTROL,		   <label style="color:#c33"> //Start cruise </label><br/>
	EXTPTZ_POINT_STOP_LOOP_CONTROL,	      <label style="color:#c33">  //Stop cruise</label><br/>
	EXTPTZ_CLOSELOOP,				<label style="color:#c33">//Clear cruise  p1 cruise line </label><br/>	
	EXTPTZ_FASTGOTO,				<label style="color:#c33">//Fast positioning	</label><br/>
	EXTPTZ_AUXIOPEN,	<label style="color:#c33">//Auxiliary switch, off is in the sub command//param1 see SDK_PtzAuxStatus, param2 incoming specific values</label><br/>
	EXTPTZ_OPERATION_MENU,			    <label style="color:#c33">//Dome camera menu operation, including open, close, confirm, etc</label><br/>
	EXTPTZ_REVERSECOMM,				<label style="color:#c33">//Lens flip</label><br/>
	EXTPTZ_OPERATION_RESET,			  <label style="color:#c33">  //PTZ reset </label><br/>

	EXTPTZ_TOTAL,
</div>
};

<hr>
<br/><br/>
<div name="meiju2" id="meiju2" style="font-size:15px;"><b>2.2Device configuration command enumeration </b></div>


typedef enum <label style="color:#69f">_SDK_CONFIG_TYPE</label>
{
<div style="margin-left:20px;">
E_SDK_CONFIG_NOTHING = 0,
E_SDK_CONFIG_USER,		<label style="color:#c33">//User information, including permissions list, user list and group list   the corresponding structure <a href="http://open.xmeye.net/zh/#USER_MANAGE_INFO">USER\_MANAGE\_INFO</a> </label><br/>
E_SDK_CONFIG_ADD_USER,		<label style="color:#c33">//Add the user --- the corresponding structure USER_INFO<a href="http://open.xmeye.net/zh/#USER_INFO">USER\_INFO </a>   </label><br/>
E_SDK_CONFIG_MODIFY_USER,			<label style="color:#c33">//Modify the user --- the corresponding structure <a href="http://open.xmeye.net/zh/#CONF_MODIFYUSER">CONF\_MODIFYUSER </a> </label>  <br/>
E_SDK_CONFIG_DELETE_USER,			<label style="color:#c33">//The corresponding structure---<a href="">USER\_INFO </a>  </label><br/>
E_SDK_CONFIG_ADD_GROUP,				<label style="color:#c33">//Add group --- the corresponding structure <a href="http://open.xmeye.net/zh/#USER_GROUP_INFO">USER\_GROUP\_INFO  </a> </label><br/>
E_SDK_CONFIG_MODIFY_GROUP,			<label style="color:#c33">//Modify group--- the corresponding structure <a href="http://open.xmeye.net/zh/#CONF_MODIFYGROUP">CONF\_MODIFYGROUP  </a> </label><br/>
E_SDK_COFIG_DELETE_GROUP,			<label style="color:#c33">//Modify the user --- the corresponding structure <a href="http://open.xmeye.net/zh/#USER_GROUP_INFO">USER\_GROUP\_INFO </a>  </label><br/>
E_SDK_CONFIG_MODIFY_PSW,			<label style="color:#c33">//Modify password--- the corresponding structure<a href="http://open.xmeye.net/zh/#CONF_MODIFY_PSW">\_CONF\_MODIFY\_PSW    </a>   </label> <br/>             
E_SDK_CONFIG_ABILITY_SYSFUNC = 9,	    <label style="color:#c33">//Supported network function---the corresponding structure <a href="http://open.xmeye.net/zh/#SystemFunction">SDK\_SystemFunction </a> </label>  <br/>              
E_SDK_CONFIG_ABILTY_ENCODE = 10,	    <label style="color:#c33">//First to get the coding ability---the corresponding structure <a href="http://open.xmeye.net/zh/#CONFIG_EncodeAbility">CONFIG\_EncodeAbility</a>    </label>   <br/>    
E_SDK_CONFIG_ABILITY_PTZPRO,		    <label style="color:#c33">//PTZ protocol---the corresponding structure <a href="http://open.xmeye.net/zh/#PTZPROTOCOLFUNC ">SDK\_PTZPROTOCOLFUNC    </a> </label>     <br/>   
E_SDK_COMFIG_ABILITY_COMMPRO,		    <label style="color:#c33">//Serial port protocol ---the corresponding structure <a href="http://open.xmeye.net/zh/#COMMFUNC">SDK\_COMMFUNC          </a>  </label><br/>
E_SDK_CONFIG_ABILITY_MOTION_FUNC,	    <label style="color:#c33">//Dynamic detection block<a href="http://open.xmeye.net/zh/#MotionDetectFunction">SDK\_MotionDetectFunction </a> </label>   <br/>    
E_SDK_CONFIG_ABILITY_BLIND_FUNC,	    <label style="color:#c33">//Video block ---the corresponding structure <a href="http://open.xmeye.net/zh/#BlindDetectFunction">SDK\_BlindDetectFunction  </a> </label>    <br/>       
E_SDK_CONFIG_ABILITY_DDNS_SERVER,	   <label style="color:#c33"> //DDNS service supported type ---the corresponding structure <a href="http://open.xmeye.net/zh/#DDNSServiceFunction">SDK\_DDNSServiceFunction</a>  </label>   <br/>      
E_SDK_CONFIG_ABILITY_TALK,			<label style="color:#c33">//Intercom coding type ---the corresponding structure <a href="http://open.xmeye.net/zh/#DDNSServiceFunction">SDK\_DDNSServiceFunction</a>  </label>      <br/>    
E_SDK_CONFIG_SYSINFO = 17,			<label style="color:#c33">//System information ---the corresponding structure <a href="http://open.xmeye.net/zh/#H264_DVR_DEVICEINFO">H264\_DVR\_DEVICEINFO   </a>   </label>      <br/>
E_SDK_CONFIG_SYSNORMAL,				<label style="color:#c33">//Common configuration---the corresponding structure <a href="http://open.xmeye.net/zh/#CONFIG_NORMAL">SDK\_CONFIG\_NORMAL     </a>  </label>      <br/>
E_SDK_CONFIG_SYSENCODE,				<label style="color:#c33">//Coding configuration---the corresponding structure <a href="http://open.xmeye.net/zh/#EncodeConfigAll">SDK\_EncodeConfigAll    </a>  </label>     <br/>
E_SDK_CONFIG_SYSNET = 20,			<label style="color:#c33">//Network configuration---the corresponding structure <a href="http://open.xmeye.net/zh/#CONFIG_NET_COMMON ">SDK\_CONFIG\_NET\_COMMON  </a> </label>       <br/> 
E_SDK_CONFIG_PTZ,				<label style="color:#c33">//PTZ page---the corresponding structure <a href="http://open.xmeye.net/zh/#STR_PTZCONFIG_ALL">SDK\_STR\_PTZCONFIG\_ALL    </a>        </label><br/>
E_SDK_CONFIG_COMM,				<label style="color:#c33">//Serial port page---the corresponding structure <a href="http://open.xmeye.net/zh/#CommConfigAll">SDK\_CommConfigAll       </a>     </label><br/>
E_SDK_CONFIG_RECORD,				<label style="color:#c33">//Video setting interface---the corresponding structure <a href="http://open.xmeye.net/zh/#RECORDCONFIG">SDK\_RECORDCONFIG      </a>     </label><br/>
E_SDK_CONFIG_MOTION,				<label style="color:#c33">//Dynamic detection page---the corresponding structure <a href="http://open.xmeye.net/zh/#MOTIONCONFIG">SDK\_MOTIONCONFIG      </a>    </label><br/>
E_SDK_CONFIG_SHELTER,				<label style="color:#c33">//Video occlusion--the corresponding structure <a href="http://open.xmeye.net/zh/#BLINDDETECTCONFIG">SDK\_BLINDDETECTCONFIG     </a>      </label>  <br/>
E_SDK_CONFIG_VIDEO_LOSS,  			<label style="color:#c33">//Video loss---the corresponding structure <a href="http://open.xmeye.net/zh/#VIDEOLOSSCONFIG">SDK\_VIDEOLOSSCONFIG      </a>     </label><br/>
E_SDK_CONFIG_ALARM_IN,				<label style="color:#c33">//Alarm input---the corresponding structure <a href="http://open.xmeye.net/zh/#ALARM_INPUTCONFIG">SDK\_ALARM\_INPUTCONFIG    </a>     </label><br/>
E_SDK_CONFIG_ALARM_OUT,				<label style="color:#c33">//Alarm output ---the corresponding structure <a href="http://open.xmeye.net/zh/#AlarmOutConfigAll">SDK\_AlarmOutConfigAll      </a>   </label> <br/>
E_SDK_CONFIG_DISK_MANAGER,			<label style="color:#c33">//Hard disk management interface---the corresponding structure <a href="http://open.xmeye.net/zh/#StorageDeviceControl">SDK\_StorageDeviceControl  </a>   </label>  <br/>    
E_SDK_CONFIG_OUT_MODE = 30,			<label style="color:#c33">//Output mode interface---the corresponding structure <a href="http://open.xmeye.net/zh/#VideoWidgetConfigAll">SDK\_VideoWidgetConfigAll   </a>    </label>     <br/>
E_SDK_CONFIG_CHANNEL_NAME,			<label style="color:#c33">//Channel name ---the corresponding structure <a href="http://open.xmeye.net/zh/#ChannelNameConfigAll">SDK\_ChannelNameConfigAll   </a>    </label>     <br/>   
E_SDK_CONFIG_AUTO,				<label style="color:#c33">//Automatic maintenance interface configuration---the corresponding structure <a href="http://open.xmeye.net/zh/#AutoMaintainConfig">SDK\_AutoMaintainConfig    </a>     </label>      <br/>
E_SDK_CONFIG_DEFAULT,     			<label style="color:#c33">//Restore default interface configuration---the corresponding structure <a href="http://open.xmeye.net/zh/#SetDefaultConfigTypes">SDK\_SetDefaultConfigTypes </a>    </label>    <br/>  
E_SDK_CONFIG_DISK_INFO,				<label style="color:#c33">//Hard disk information---the corresponding structure <a href="http://open.xmeye.net/zh/#StorageDeviceInformationAll">SDK\_StorageDeviceInformationAll </a>   </label>     <br/>    
E_SDK_CONFIG_LOG_INFO,				<label style="color:#c33">//Query log---the corresponding structure <a href="http://open.xmeye.net/zh/#LogList">SDK\_LogList      </a>       </label><br/>
E_SDK_CONFIG_NET_IPFILTER,			<label style="color:#c33">//Black list configuration---the corresponding structure <a href="http://open.xmeye.net/zh/#NetIPFilterConfig">SDK\_NetIPFilterConfig  </a>    </label>     <br/>   
E_SDK_CONFIG_NET_DHCP,				<label style="color:#c33">//DHCP configuration---the corresponding structure <a href="http://open.xmeye.net/zh/#NetDHCPConfigAll">SDK\_NetDHCPConfigAll   </a>   </label>    <br/>  
E_SDK_CONFIG_NET_DDNS,				<label style="color:#c33">//DDNS information---the corresponding structure<a href="http://open.xmeye.net/zh/#NetDDNSConfigALL">SDK\_NetDDNSConfigALL </a>    </label>    <br/>  
E_SDK_CONFIG_NET_EMAIL,				<label style="color:#c33">//EMAIL---the corresponding structure<a href="http://open.xmeye.net/zh/#NetEmailConfig">SDK\_NetEmailConfig   </a>   </label>   <br/>
E_SDK_CONFIG_NET_MULTICAST = 40,	    <label style="color:#c33">//Multicast---the corresponding structure <a href="http://open.xmeye.net/zh/#NetMultiCastConfig">SDK\_NetMultiCastConfig </a>  </label>    <br/>  
E_SDK_CONFIG_NET_NTP,				<label style="color:#c33">//NTP---the corresponding structure <a href="http://open.xmeye.net/zh/#NetNTPConfig">SDK\_NetNTPConfig   </a>   </label>     <br/>
E_SDK_CONFIG_NET_PPPOE,				<label style="color:#c33">//PPPOE---the corresponding structure <a href="http://open.xmeye.net/zh/#NetPPPoEConfig">SDK\_NetPPPoEConfig  </a>  </label>   <br/> 
E_SDK_CONFIG_NET_DNS,				<label style="color:#c33">//DNS---the corresponding structure <a href="http://open.xmeye.net/zh/#NetDNSConfig">SDK\_NetDNSConfig   </a>   </label>     <br/>
E_SDK_CONFIG_NET_FTPSERVER,			<label style="color:#c33">//FTP---the corresponding structure <a href="http://open.xmeye.net/zh/#FtpServerConfig">SDK\_FtpServerConfig  </a>     </label>   <br/>
E_SDK_CONFIG_SYS_TIME,	   <label style="color:#c33">//System time---the corresponding structure <a href="http://open.xmeye.net/zh/#SYSTEM_TIME">SDK\_SYSTEM_TIME</a>(interface <a href="http://open.xmeye.net/zh/#SetSystemDateTime">H264\_DVR\_SetSystemDateTime</a>can also achieve) </label>  <br/>           
E_SDK_CONFIG_CLEAR_LOG,				<label style="color:#c33">//Clear log (interface<a href="http://open.xmeye.net/zh/#ControlDVR">H264_DVR\_ControlDVR)	</label>	<br/>          									

E_SDK_REBOOT_DEV,				<label style="color:#c33">//Reset device (interface <a href="http://open.xmeye.net/zh/#ControlDVR">H264\_DVR\_ControlDVR)</a>	 </label>    <br/>     											

E_SDK_CONFIG_ABILITY_LANG,			<label style="color:#c33">//Support language---the corresponding structure <a href="http://open.xmeye.net/zh/#MultiLangFunction">SDK\_MultiLangFunction </a>   </label> <br/>      
E_SDK_CONFIG_VIDEO_FORMAT,							
E_SDK_CONFIG_COMBINEENCODE = 50, <label style="color:#c33">//Combined coding---the corresponding structure <a href="http://open.xmeye.net/zh/#CombineEncodeConfigAll">SDK\_CombineEncodeConfigAll </a> </label>    <br/>     
E_SDK_CONFIG_EXPORT,				<label style="color:#c33">//Configuration export			</label>		<br/>	             
E_SDK_CONFIG_IMPORT,				<label style="color:#c33">//Configuration import      </label>     <br/>
E_SDK_LOG_EXPORT,				<label style="color:#c33">//Log export			</label>			<br/>						            		
E_SDK_CONFIG_COMBINEENCODEMODE, 	    <label style="color:#c33">//Combined coding mode---the corresponding structure <a href="http://open.xmeye.net/zh/#CombEncodeModeAll">SDK\_CombEncodeModeAll </a>     </label> <br/>
E_SDK_WORK_STATE,		    <label style="color:#c33">//Running state---<a href="http://open.xmeye.net/zh/#DVR_WORKSTATE">SDK\_DVR\_WORKSTATE</a>(interface <a href="http://open.xmeye.net/zh/#GetDVRWorkState">H264\_DVR\_GetDVRWorkState</a>also can get)	 </label> <br/>         														

E_SDK_ABILITY_LANGLIST, 			<label style="color:#c33">//Actual supported language set---the corresponding structure <a href="http://open.xmeye.net/zh/#MultiLangFunction">SDK\_MultiLangFunction</a>	   </label>  <br/>  

E_SDK_CONFIG_NET_ARSP,				<label style="color:#c33">//ARSP---the corresponding structure <a href="http://open.xmeye.net/zh/#NetARSPConfigAll">SDK\_NetARSPConfigAll   </a>     </label>  <br/>
E_SDK_CONFIG_SNAP_STORAGE,			<label style="color:#c33">//Capture settings---the corresponding structure <a href="http://open.xmeye.net/zh/#SnapshotConfig">SDK\_SnapshotConfig  </a>     </label>      <br/> 
E_SDK_CONFIG_NET_3G, 				<label style="color:#c33">//3G dial---the corresponding structure <a href="http://open.xmeye.net/zh/#Net3GConfig">SDK\_Net3GConfig    </a>    </label><br/>
E_SDK_CONFIG_NET_MOBILE = 60, 		  <label style="color:#c33">  //Mobile phone monitoring---the corresponding structure <a href="http://open.xmeye.net/zh/#NetMoblieConfig">SDK\_NetMoblieConfig  </a>  </label>       <br/>
E_SDK_CONFIG_UPGRADEINFO, 			<label style="color:#c33">//Get update information/parameters/file name---the corresponding structure <a href="http://open.xmeye.net/zh/#UpgradeInfo">SDK\_UpgradeInfo  </a>  </label>  <br/>      
E_SDK_CONFIG_NET_DECODER,			<label style="color:#c33">//Set V1 to decoder address (abandon)---the corresponding structure <a href="http://open.xmeye.net/zh/#NetDecoderConfigAll">SDK\_NetDecoderConfigAll </a>  </label>    <br/>     
E_SDK_ABILITY_VSTD, 				<label style="color:#c33">//Actual supported video format---the corresponding structure <a href="http://open.xmeye.net/zh/#MultiVstd">SDK\_MultiVstd   </a>     </label>   <br/>
E_SDK_CONFIG_ABILITY_VSTD,			<label style="color:#c33">//Supported video format---the corresponding structure <a href="http://open.xmeye.net/zh/#MultiVstd">SDK\_MultiVstd   </a>   </label><br/>
E_SDK_CONFIG_NET_UPNP, 				<label style="color:#c33">//UPUN set---the corresponding structure <a href="http://open.xmeye.net/zh/#NetUPNPConfig">SDK\_NetUPNPConfig  </a>      </label>    <br/> 
E_SDK_CONFIG_NET_WIFI,				<label style="color:#c33">//WIFI---the corresponding structure <a href="http://open.xmeye.net/zh/#NetWifiConfig">SDK\_NetWifiConfig   </a>    </label><br/>
E_SDK_CONFIG_NET_WIFI_AP_LIST,		    <label style="color:#c33">//Searched wifi list---the corresponding structure <a href="http://open.xmeye.net/zh/#NetWifiDeviceAll">SDK\_NetWifiDeviceAll </a>  </label>  <br/>      
E_SDK_CONFIG_SYSENCODE_SIMPLIIFY, 	    <label style="color:#c33">//Simplified code configuration---the corresponding structure <a href="http://open.xmeye.net/zh/#EncodeConfigAll_SIMPLIIFY">SDK\_EncodeConfigAll\_SIMPLIIFY </a> </label>   <br/>       
E_SDK_CONFIG_ALARM_CENTER,  		    <label style="color:#c33">//Alarm center---the corresponding structure <a href="http://open.xmeye.net/zh/#NetAlarmServerConfigAll">SDK\_NetAlarmServerConfigAll </a> </label>     <br/>      
E_SDK_CONFIG_NET_ALARM = 70,		    <label style="color:#c33">//Network alarm ---the corresponding structure <a href="http://open.xmeye.net/zh/#NETALARMCONFIG_ALL">SDK\_NETALARMCONFIG_ALL</a>	</label>	   <br/>             																

E_SDK_CONFIG_NET_MEGA,     			<label style="color:#c33">//互信互通---the corresponding structure <a href="http://open.xmeye.net/zh/#CONFIG_NET_MEGA">SDK\_CONFIG\_NET\_MEGA </a>    </label>     <br/>
E_SDK_CONFIG_NET_XINGWANG, 			<label style="color:#c33">//星望---the corresponding structure <a href="http://open.xmeye.net/zh/#CONFIG_NET_XINGWANG">SDK\_CONFIG\_NET\_XINGWANG </a> </label>      <br/> 
E_SDK_CONFIG_NET_SHISOU,   			<label style="color:#c33">//视搜---the corresponding structure <a href="http://open.xmeye.net/zh/#CONFIG_NET_SHISOU ">SDK\_CONFIG\_NET\_SHISOU  </a>  </label>      <br/>  
E_SDK_CONFIG_NET_VVEYE,    			<label style="color:#c33">//VVEYE---the corresponding structure <a href="http://open.xmeye.net/zh/#CONFIG_NET_VVEYE">SDK\_CONFIG\_NET\_VVEYE  </a>   </label>      <br/> 
E_SDK_CONFIG_NET_PHONEMSG,  		    <label style="color:#c33">//Message---the corresponding structure <a href="http://open.xmeye.net/zh/#NetShortMsgCfg">SDK\_NetShortMsgCfg  </a> </label>         <br/>  
E_SDK_CONFIG_NET_PHONEMEDIAMSG,  	    <label style="color:#c33">//Multimedia message---the corresponding structure <a href="http://open.xmeye.net/zh/#NetMultimediaMsgCfg">SDK\_NetMultimediaMsgCfg  </a></label>       <br/>    
E_SDK_VIDEO_PREVIEW,				<label style="color:#c33">//</label>
E_SDK_CONFIG_NET_DECODER_V2,		   <label style="color:#c33">//Set V2 to decoder address (abandon)---the corresponding structure <a href="http://open.xmeye.net/zh/#NetDecorderConfigAll_V2">SDK\_NetDecorderConfigAll\_V2 </a>  </label> <br/>      
E_SDK_CONFIG_NET_DECODER_V3,		    <label style="color:#c33">//Set V3 to decoder address---the corresponding structure <a href="http://open.xmeye.net/zh/#NetDecorderConfigAll_V3">SDK_NetDecorderConfigAll\_V3 </a> </label>      <br/>
E_SDK_CONFIG_ABILITY_SERIALNO = 80,	    <label style="color:#c33">//Serial number---the corresponding structure <a href="http://open.xmeye.net/zh/#AbilitySerialNo">SDK\_AbilitySerialNo</a> (by the test, it is not a device serial number (temporarily abandon), serial number can be obtain ed from the login interface) </label> <br/>       
E_SDK_CONFIG_NET_RTSP,    			<label style="color:#c33">//RTSP---the corresponding structure <a href="http://open.xmeye.net/zh/#NetRTSPConfig">SDK\_NetRTSPConfig  </a>     </label>   <br/>
E_SDK_GUISET,              		<label style="color:#c33">//Local GUI output settings---the corresponding structure <a href="http://open.xmeye.net/zh/#GUISetConfig">SDK\_GUISetConfig  </a>   </label>        <br/> 
E_SDK_CATCHPIC,               		<label style="color:#c33">//Capture image 											</label>		
E_SDK_VIDEOCOLOR,             		<label style="color:#c33">//Video color settings---the corresponding structure <a href="http://open.xmeye.net/zh/#VideoColorConfigAll">SDK\_VideoColorConfigAll   </a>  </label>   <br/>    
E_SDK_CONFIG_COMM485,				<label style="color:#c33">//Serial port 485 protocol configuration---the corresponding structure <a href="http://open.xmeye.net/zh/#RS485CONFIG">SDK\_STR\_RS485CONFIG\_ALL</a>  </label>   <br/>   
E_SDK_COMFIG_ABILITY_COMMPRO485, 	    <label style="color:#c33">//Serial port 485 protocol---the corresponding structure <a href="http://open.xmeye.net/zh/#COMMFUNC">SDK\_COMMFUNC  </a>     </label>     <br/>
E_SDK_CONFIG_SYS_TIME_NORTC,		    <label style="color:#c33">//Set system time noRtc---the corresponding structure <a href="http://open.xmeye.net/zh/#SYSTEM_TIME">SDK\_SYSTEM\_TIME </a>  </label>  <br/>      
E_SDK_CONFIG_REMOTECHANNEL,   		   <label style="color:#c33"> //Remote channel---abandon            </label><br/>
E_SDK_CONFIG_OPENTRANSCOMCHANNEL , 	   <label style="color:#c33"> //Open the transparent serial port---the corresponding structure TransComChannel  </label>    <br/>  
E_SDK_CONFIG_CLOSETRANSCOMCHANNEL = 90,  <label style="color:#c33">   //Close the transparent serial port</label><br/>
E_SDK_CONFIG_SERIALWIRTE,  			<label style="color:#c33">//Write the transparent serial port information</label><br/>
E_SDK_CONFIG_SERIALREAD,   			<label style="color:#c33">//Read the transparent serial port information</label><br/>
E_SDK_CONFIG_CHANNELTILE_DOT,		   <label style="color:#c33"> //Lattice information- modify the IPC channel name requires lattice information---the corresponding structure <a href="http://open.xmeye.net/zh/#TitleDot">SDK\_TitleDot</a></label><br/>
E_SDK_CONFIG_CAMERA,           		<label style="color:#c33">//Camera parameters---the corresponding structure <a href="http://open.xmeye.net/zh/#CameraParam">SDK\_CameraParam</a></label><br/>
E_SDK_CONFIG_ABILITY_CAMERA,    	   <label style="color:#c33"> //Exposure ability level---the corresponding structure <a href="http://open.xmeye.net/zh/#CameraAbility">SDK\_CameraAbility</a></label><br/>
E_SDK_CONFIG_BUGINFO,    			<label style="color:#c33">//Command debug 						</label>					<br/>		
E_SDK_CONFIG_STORAGENOTEXIST,		    <label style="color:#c33">//Hard disk does not exist---the corresponding structure <a href="http://open.xmeye.net/zh/#VIDEOLOSSCONFIG">SDK\_VIDEOLOSSCONFIG</a></label><br/>
E_SDK_CONFIG_STORAGELOWSPACE, 		   <label style="color:#c33"> //Insufficient hard disk capacity---the corresponding structure <a href="http://open.xmeye.net/zh/#StorageLowSpaceConfig">SDK\_StorageLowSpaceConfig	</a></label>	<br/>						

E_SDK_CONFIG_STORAGEFAILURE, 		   <label style="color:#c33"> //Hard disk error---the corresponding structure <a href="http://open.xmeye.net/zh/#StorageFailConfig">SDK\_StorageFailConfig</a></label><br/>
E_SDK_CFG_NETIPCONFLICT = 100,   	   <label style="color:#c33"> //IP conflict---the corresponding structure <a href="http://open.xmeye.net/zh/#VIDEOLOSSCONFIG">SDK\_VIDEOLOSSCONFIG</a></label><br/>
E_SDK_CFG_NETABORT,  				<label style="color:#c33">//Network abnormal---the corresponding structure <a href="http://open.xmeye.net/zh/#VIDEOLOSSCONFIG">SDK\_VIDEOLOSSCONFIG</a></label><br/>
E_SDK_CONFIG_CHNSTATUS, 			<label style="color:#c33">//Channel status---the corresponding structure <a href="http://open.xmeye.net/zh/#NetDecorderChnStatusAll">SDK\_NetDecorderChnStatusAll</a></label><br/>
E_SDK_CONFIG_CHNMODE,  			<label style="color:#c33">//Channel mode---the corresponding structure <a href="http://open.xmeye.net/zh/#NetDecorderChnModeConfig">SDK\_NetDecorderChnModeConfig</a></label><br/>
E_SDK_CONFIG_NET_DAS,    			<label style="color:#c33">//Active registration---the corresponding structure <a href="http://open.xmeye.net/zh/#DASSerInfo">SDK\_DASSerInfo</a></label><br/>
E_SDK_CONFIG_CAR_INPUT_EXCHANGE,   <label style="color:#c33">  //The correspondence between the external information input and the vehicle state 
---the corresponding structure <a href="http://open.xmeye.net/zh/#CarStatusExchangeAll">SDK\_CarStatusExchangeAll</a>	</label>	<br/>	
E_SDK_CONFIG_DELAY_TIME,       		<label style="color:#c33">//Vehicle system delay allocation---the corresponding structure <a href="http://open.xmeye.net/zh/#CarDelayTimeConfig">SDK\_CarDelayTimeConfig</a></label><br/>
E_SDK_CONFIG_NET_ORDER,                 <label style="color:#c33">//Network priority---the corresponding structure <a href="http://open.xmeye.net/zh/#NetOrderConfig">SDK\_NetOrderConfig</a></label><br/>
E_SDK_CONFIG_ABILITY_NETORDER , 	    <label style="color:#c33">//Network priority setting capability---the corresponding structure <a href="http://open.xmeye.net/zh/#NetOrderFunction">SDK\_NetOrderFunction</a></label><br/>
E_SDK_CONFIG_CARPLATE,				<label style="color:#c33">//License plate number configuration---the corresponding structure<a href="http://open.xmeye.net/zh/#CarPlates">SDK\_CarPlates</a></label><br/>
E_SDK_CONFIG_LOCALSDK_NET_PLATFORM = 110,    <label style="color:#c33">//Network platform information setting---the corresponding structure <a href="http://open.xmeye.net/zh/#LocalSdkNetPlatformConfig">SDK\_LocalSdkNetPlatformConfig</a></label><br/>
E_SDK_CONFIG_GPS_TIMING,               <label style="color:#c33">//GPS time correlation configuration---the corresponding structure <a href="http://open.xmeye.net/zh/#GPSTimingConfig">SDK\_GPSTimingConfig</a></label><br/>
E_SDK_CONFIG_VIDEO_ANALYZE, 		    <label style="color:#c33">//Video analysis (smart DVR)---the corresponding structure <a href="http://open.xmeye.net/zh/#ANALYSECONFIG">SDK\_ANALYSECONFIG</a></label><br/>
E_SDK_CONFIG_GODEYE_ALARM,			<label style="color:#c33">//God's eye alarm center system---the corresponding structure <a href="http://open.xmeye.net/zh/#GodEyeConfig">SDK\_GodEyeConfig</a></label><br/>
E_SDK_CONFIG_NAT_STATUS_INFO,   	   <label style="color:#c33"> //nat Status information---the corresponding structure <a href="http://open.xmeye.net/zh/#NatStatusInfo">SDK\_NatStatusInfo	</a></label><br/>
E_SDK_CONFIG_BUGINFOSAVE,     		<label style="color:#c33">//Command debug (save)								</label>	<br/> 
E_SDK_CONFIG_MEDIA_WATERMARK,		   <label style="color:#c33"> //Watermark setting---the corresponding structure <a href="http://open.xmeye.net/zh/#WaterMarkConfigAll">SDK\_WaterMarkConfigAll</a></label><br/>
E_SDK_CONFIG_ENCODE_STATICPARAM,	   <label style="color:#c33"> //Encoder static parameters---the corresponding structure <a href="http://open.xmeye.net/zh/#EncodeStaticParamAll">SDK\_EncodeStaticParamAll</a></label><br/>
E_SDK_CONFIG_LOSS_SHOW_STR,		    <label style="color:#c33"> //Video loss display string </label><br/>
E_SDK_CONFIG_DIGMANAGER_SHOW,	      <label style="color:#c33">  //Channel management display configuration---the corresponding structure <a href="http://open.xmeye.net/zh/#DigManagerShowStatus">SDK\_DigManagerShowStatus</a></label><br/>
E_SDK_CONFIG_ABILITY_ANALYZEABILITY = 120,  <label style="color:#c33"> //Smart analysis ability ---the corresponding structure <a href="http://open.xmeye.net/zh/#ANALYZEABILITY">SDK\_ANALYZEABILITY</a></label><br/>
E_SDK_CONFIG_VIDEOOUT_PRIORITY,         <label style="color:#c33"> //Display HDMI VGA priority configuration</label><br/>
E_SDK_CONFIG_NAT,		 		<label style="color:#c33">//NAT function, MTU value configuration---the corresponding structure <a href="http://open.xmeye.net/zh/#NatConfig">SDK\_NatConfig</a></label><br/>
E_SDK_CONFIG_CPCINFO,		         <label style="color:#c33">//Smart CPC count data information---the corresponding structure <a href="http://open.xmeye.net/zh/#CPCDataAll">SDK\_CPCDataAll</a></label><br/>
E_SDK_CONFIG_STORAGE_POSITION,          <label style="color:#c33">// Video storage device type---the corresponding structure <a href="http://open.xmeye.net/zh/#RecordStorageType">SDK\_RecordStorageType</a></label><br/>
E_SDK_CONFIG_ABILITY_CARSTATUSNUM,      <label style="color:#c33"> //Vehicle state number---the corresponding structure <a href="http://open.xmeye.net/zh/#CarStatusNum">SDK\_CarStatusNum</a></label><br/>
E_SDK_CFG_VPN,					<label style="color:#c33">//VPN---the corresponding structure <a href="http://open.xmeye.net/zh/#VPNConfig">SDK\_VPNConfig</a></label><br/>
E_SDK_CFG_VIDEOOUT,				<label style="color:#c33">//VGA video resolution---the corresponding structure <a href="http://open.xmeye.net/zh/#VGAresolution">SDK\_VGAresolution</a></label><br/>
E_SDK_CFG_ABILITY_VGARESOLUTION,      <label style="color:#c33">  //Supported VGA resolution list---the corresponding structure <a href="http://open.xmeye.net/zh/#VGAResolutionAbility">SDK\_VGAResolutionAbility</a></label><br/>
E_SDK_CFG_NET_LOCALSEARCH,            <label style="color:#c33"> //Search device, local area network device---the corresponding structure <a href="http://open.xmeye.net/zh/#NetDevList">SDK\_NetDevList</a></label><br/>
E_SDK_CFG_NETPLAT_KAINENG = 130,      <label style="color:#c33">  //Client configuration---the corresponding structure <a href="http://open.xmeye.net/zh/#CONFIG_KAINENG_INFO">SDK\_CONFIG\_KAINENG\_INFO</a></label><br/>
E_SDK_CFG_ENCODE_STATICPARAM_V2,      <label style="color:#c33">  //DVR encoder static parameters---the corresponding structure <a href="http://open.xmeye.net/zh/#EncodeStaticParamV2">SDK\_EncodeStaticParamV2</a></label><br/>
E_SDK_ABILITY_ENC_STATICPARAM,	      <label style="color:#c33">  //Static code capability set---the corresponding structure <a href="http://open.xmeye.net/zh/#EncStaticParamAbility">SDK\_EncStaticParamAbility</a>(Mask)</label><br/>
E_SDK_CFG_C7_PLATFORM,              <label style="color:#c33">  //C7 platform configuration---the corresponding structure <a href="http://open.xmeye.net/zh/#C7PlatformConfig">SDK\_C7PlatformConfig</a></label><br/>
E_SDK_CFG_MAIL_TEST,                <label style="color:#c33">  //E-mail test ---the corresponding structure <a href="http://open.xmeye.net/zh/#NetEmailConfig">SDK\_NetEmailConfig</a></label><br/>
E_SDK_CFG_NET_KEYBOARD,            <label style="color:#c33">   //Network keyboard service---the corresponding structure <a href="http://open.xmeye.net/zh/#NetKeyboardConfig">SDK\_NetKeyboardConfig</a></label><br/>
E_SDK_ABILITY_NET_KEYBOARD,		  <label style="color:#c33">  //Network keyboard protocol---the corresponding structure <a href="http://open.xmeye.net/zh/#NetKeyboardAbility">SDK\_NetKeyboardAbility  </a></label><br/>
E_SDK_CFG_SPVMN_PLATFORM,         <label style="color:#c33">     //28181 protocol configuration---the corresponding structure <a href="http://open.xmeye.net/zh/#ASB_NET_VSP_CONFIG">SDK\_ASB\_NET\_VSP\_CONFIG</a>	</label><br/>
E_SDK_CFG_PMS,				    <label style="color:#c33"> //Mobile phone service---the corresponding structure <a href="http://open.xmeye.net/zh/#PMSConfig">SDK\_PMSConfig</a></label><br/>
E_SDK_CFG_OSD_INFO,              <label style="color:#c33">    //Screen prompt information---the corresponding structure <a href="http://open.xmeye.net/zh/#OSDInfoConfigAll">SDK\_OSDInfoConfigAll</a></label><br/>
E_SDK_CFG_KAICONG = 140,         <label style="color:#c33">     //Customer configuration---the corresponding structure <a href="http://open.xmeye.net/zh/#KaiCongAlarmConfig">SDK\_KaiCongAlarmConfig</a></label><br/>
E_SDK_CFG_DIGITAL_REAL,			 <label style="color:#c33">   //Truly supported channel mode---the corresponding structure <a href="http://open.xmeye.net/zh/#VideoChannelManage">SDK\_VideoChannelManage</a></label><br/>
E_SDK_ABILITY_PTZCONTROL,		 <label style="color:#c33">   //PTZ control capability set---the corresponding structure <a href="http://open.xmeye.net/zh/#PTZControlAbility">SDK\_PTZControlAbility</a></label><br/>
E_SDK_CFG_XMHEARTBEAT,			 <label style="color:#c33">   //the corresponding structure <a href="http://open.xmeye.net/zh/#XMHeartbeatConfig">SDK\_XMHeartbeatConfig</a></label><br/>
E_SDK_CFG_MONITOR_PLATFORM,		 <label style="color:#c33">   //Platform configuration---the corresponding structure <a href="http://open.xmeye.net/zh/#NetKeyboardConfig">SDK\_MonitorPlatformConfig</a></label><br/>
E_SDK_CFG_PARAM_EX,				<label style="color:#c33">//Camera extension parameters---the corresponding structure <a href="http://open.xmeye.net/zh/#MonitorPlatformConfig">SDK\_CameraParamEx</a></label><br/>
E_SDK_CFG_NETPLAT_ANJU_P2P,		 <label style="color:#c33">   //安巨P2P---the corresponding structure <a href="http://open.xmeye.net/zh/#NetPlatformCommonCfg">SDK\_NetPlatformCommonCfg </a> </label><br/>
E_SDK_GPS_STATUS,				<label style="color:#c33">//GPS connection information---the corresponding structure <a href="http://open.xmeye.net/zh/#GPSStatusInfo">SDK\_GPSStatusInfo </a></label><br/>
E_SDK_WIFI_STATUS,				<label style="color:#c33">//WiFi connection information---the corresponding structure <a href="http://open.xmeye.net/zh/#WifiStatusInfo">SDK\_WifiStatusInfo</a></label><br/>
E_SDK_3G_STATUS,  				<label style="color:#c33">//3G connection information---the corresponding structure <a href="http://open.xmeye.net/zh/#WirelessStatusInfo">SDK\_WirelessStatusInfo</a></label><br/>
E_SDK_DAS_STATUS = 150, 		<label style="color:#c33">    //Active registration status---the corresponding structure <a href="http://open.xmeye.net/zh/#DASStatusInfo">SDK\_DASStatusInfo </a></label><br/>
E_SDK_ABILITY_DECODE_DELEY,		<label style="color:#c33">    //Decoding strategy capability---the corresponding structure <a href="http://open.xmeye.net/zh/#DecodeDeleyTimePrame">SDK\_DecodeDeleyTimePrame</a></label><br/>
E_SDK_CFG_DECODE_PARAM,     	 <label style="color:#c33">       //Decoding maximum delay---the corresponding structure <a href="http://open.xmeye.net/zh/#DecodeParam">SDK\_DecodeParam</a></label><br/>
E_SDK_CFG_VIDEOCOLOR_CUSTOM,     <label style="color:#c33">       //<a href="http://open.xmeye.net/zh/#VIDEOCOLOR_PARAM_CUSTOM">SDK\_VIDEOCOLOR\_PARAM\_CUSTOM</a></label><br/>
E_SDK_ABILITY_ONVIF_SUB_PROTOCOL, <label style="color:#c33">       //onvif sub protocol---the corresponding structure <a href="http://open.xmeye.net/zh/#AbilityMask">SDK\_AbilityMask </a> </label> <br/>
E_SDK_CONFIG_EXPORT_V2,      	   <label style="color:#c33"> //Export device default configuration, that is, factory configuration</label>
E_SDK_CFG_CAR_BOOT_TYPE,      	   <label style="color:#c33"> //Vehicle mounted turning-on-and-off mode---the corresponding structure <a href="http://open.xmeye.net/zh/#CarBootTypeConfig">SDK\_CarBootTypeConfig</a></label><br/>
E_SDK_CFG_IPC_ALARM,			   <label style="color:#c33"> //IPC network alarm---the corresponding structure <a href="http://open.xmeye.net/zh/#IPCAlarmConfigAll">SDK\_IPCAlarmConfigAll</a></label><br/>
E_SDK_CFG_NETPLAT_TUTK_IOTC,	   <label style="color:#c33">     //TUTK IOTC platform configuration---the corresponding structure <a href="http://open.xmeye.net/zh/#NetPlatformCommonCfg">SDK\_NetPlatformCommonCfg</a></label><br/>
E_SDK_CFG_BAIDU_CLOUD,     		   <label style="color:#c33"> //Baidu Cloud---the corresponding structure <a href="http://open.xmeye.net/zh/#BaiduCloudCfg">SDK\_BaiduCloudCfg</a></label><br/>
E_SDK_CFG_PMS_MSGNUM = 160,		   <label style="color:#c33"> //Mobile phone subscriptions ---the corresponding structure <a href="http://open.xmeye.net/zh/#PhoneInfoNum">SDK\_PhoneInfoNum</a></label><br/>
E_SDK_CFG_IPC_IP,           	   <label style="color:#c33"> //Control DVR to modify the device IP---the corresponding structure <a href="http://open.xmeye.net/zh/#IPSetCfg">SDK\_IPSetCfg</a></label><br/>
E_SDK_ABILITY_DIMEN_CODE,           <label style="color:#c33">   //Two-dimensional code lattice---the corresponding structure <a href="http://open.xmeye.net/zh/#DimenCodeAll">SDK\_DimenCodeAll</a></label><br/>
E_SDK_CFG_MOBILE_WATCH, 		   <label style="color:#c33"> //China Telecom mobile phone shop platform configuration---the corresponding structure <a href="http://open.xmeye.net/zh/#MobileWatchCfg">SDK\_MobileWatchCfg</a></label><br/>
E_SDK_CFG_BROWSER_LANGUAGE,   	    <label style="color:#c33">    //The using language when use a browser---the corresponding structure <a href="http://open.xmeye.net/zh/#BrowserLanguageType">SDK\_BrowserLanguageType</a></label><br/>
E_SDK_CFG_TIME_ZONE,			    <label style="color:#c33">//Timezone configuration---the corresponding structure <a href="http://open.xmeye.net/zh/#TimeZone">SDK\_TimeZone</a></label><br/>
E_SDK_CFG_NETBJTHY,       		    <label style="color:#c33">//Customer configuration---the corresponding structure <a href="http://open.xmeye.net/zh/#MonitorPlatformConfig">SDK\_MonitorPlatformConfig</a></label><br/>
E_SDK_ABILITY_MAX_PRE_RECORD,       <label style="color:#c33">   //Maximum pre record time which can be set 1~30---the corresponding structure <a href="http://open.xmeye.net/zh/#AbilityMask">SDK\_AbilityMask</a></label><br/>
E_SDK_CFG_DIG_TIME_SYN,			<label style="color:#c33">//Digital channel time synchronization configuration (determine the front end synchronization mode)---the corresponding structure <a href="http://open.xmeye.net/zh/#TimeSynParam">SDK\_TimeSynParam</a></label><br/>
E_SDK_CONFIG_OSDINFO_DOT,		 <label style="color:#c33">   //Three lines OSD  </label><br/>
E_SDK_CFG_NET_POS = 170,		 <label style="color:#c33">   //POS machine configuration---the corresponding structure <a href="http://open.xmeye.net/zh/#NetPosConfigAll">SDK\_NetPosConfigAll</a></label><br/>
E_SDK_CFG_CUSTOMIZE_OEMINFO,	  <label style="color:#c33">      //Custom OEM client version information---the corresponding structure <a href="http://open.xmeye.net/zh/#CustomizeOEMInfo">SDK\_CustomizeOEMInfo</a></label><br/><br/>
E_SDK_CFG_DIGITAL_ENCODE, 		<label style="color:#c33">//Digital channel compact-edition coding configuration---the corresponding structure <a href="http://open.xmeye.net/zh/#EncodeConfigAll_SIMPLIIFY">SDK\_EncodeConfigAll\_SIMPLIIFY</a></label><br/>
E_SDK_CFG_DIGITAL_ABILITY, 		<label style="color:#c33">    //Coding capability of digital channel---the corresponding structure <a href="http://open.xmeye.net/zh/#DigitDevInfo">SDK\_DigitDevInfo</a></label><br/>
E_SDK_CFG_ENCODECH_DISPLAY,		<label style="color:#c33">    //The front end channel number displayed by IE code configuration---the corresponding structure <a href="http://open.xmeye.net/zh/#EncodeChDisplay">SDK\_EncodeChDisplay</a></label><br/>
E_SDK_CFG_RESUME_PTZ_STATE,		<label style="color:#c33">    //Boot PTZ status---the corresponding structure </label><br/>
E_SDK_CFG_LAST_SPLIT_STATE,   	 <label style="color:#c33">       //Picture segmentation mode in last time, used to restore the previous segmentation mode after the reboot</label><br/>
E_SDK_CFG_SYSTEM_TIMING_WORK,  <label style="color:#c33"> //Device timing turning-on-and-off time configuration. Hidden in the automatic maintenance page, and need to use a super password login to see the interface.
</label><br/>
E_SDK_CFG_GBEYESENV,			<label style="color:#c33">    //environmental monitoring platform configuration ---the corresponding structure <a href="http://open.xmeye.net/zh/#NetPlatformCommonCfg">SDK\_NetPlatformCommonCfg</a></label><br/>
E_SDK_ABILITY_AHD_ENCODE_L, 	<label style="color:#c33">        //AHDL capability sets---the corresponding structure <a href="http://open.xmeye.net/zh/#AHDEncodeLMask">SDK\_AHDEncodeLMask</a></label><br/>
E_SDK_CFG_SPEEDALARM = 180,		<label style="color:#c33">    //Speed alarm---the corresponding structure <a href="http://open.xmeye.net/zh/#SpeedAlarmConfigAll">SDK\_SpeedAlarmConfigAll</a></label><br/>
E_SDK_CFG_CORRESPONDENT_INFO,	 <label style="color:#c33">       //User custom configuration---the corresponding structure <a href="http://open.xmeye.net/zh/#CorrespondentOwnInfo">SDK\_CorrespondentOwnInfo</a></label><br/>
E_SDK_SET_OSDINFO,				<label style="color:#c33">//OSD information setting---the corresponding structure <a href="http://open.xmeye.net/zh/#OSDInfo">SDK\_OSDInfo</a>,(this function only supports analog channel)</label><br/>
E_SDK_SET_OSDINFO_V2,	        <label style="color:#c33">    //OSD information superposition，the configuration is not saved---the corresponding structure <a href="http://open.xmeye.net/zh/#OSDInfoConfigAll">SDK\_OSDInfoConfigAll</a>，(this function only supports analog channel)</label><br/>
E_SDK_ABILITY_SUPPORT_EXTSTREAM, <label style="color:#c33">       //Support sub stream record---the corresponding structure <a href="http://open.xmeye.net/zh/#AbilityMask">SDK\_AbilityMask</a></label><br/>
E_SDK_CFG_EXT_RECORD,			 <label style="color:#c33">   //Sub stream configuration---the corresponding structure <a href="http://open.xmeye.net/zh/#RECORDCONFIG">SDK_RECORDCONFIG\_ALL/SDK\_RECORDCONFIG</a></label><br/>
E_SDK_CFG_APP_DOWN_LINK,		 <label style="color:#c33">   //Used to user customize download link ---the corresponding structure <a href="http://open.xmeye.net/zh/#AppDownloadLink">SDK\_AppDownloadLink</a></label><br/>
E_SDK_CFG_EX_USER_MAP,			 <label style="color:#c33">   //Used to save the clear text data---the corresponding structure <a href="http://open.xmeye.net/zh/#UserMap">SDK\_UserMap</a></label><br/>
E_SDK_CFG_TRANS_COMM_DATA,    <label style="color:#c33"> //The serial port data is actively uploaded to the UDP or TCP server, and the TCP server can support the two-way communication.---the corresponding structure <a href="">SDK\_NetTransCommData</a></label><br/>
E_SDK_EXPORT_LANGUAGE,		      <label style="color:#c33">  //Language export </label><br/>
E_SDK_IMPORT_LANGUAGE = 190,	     <label style="color:#c33">   //Language import </label><br/>
E_SDK_DELETE_LANGUAGE,			   <label style="color:#c33"> //languages delete </label><br/>
E_SDK_CFG_UPGRADE_VERSION_LIST,	     <label style="color:#c33">   //Cloud upgrade file list---the corresponding structure <a href="http://open.xmeye.net/zh/#CloudUpgradeList">SDK\_CloudUpgradeList</a></label><br/>
E_SDK_CFG_GSENSORALARM,			    <label style="color:#c33">//GSENSOR alarm</label><br/>
E_SDK_CFG_USE_PROGRAM,			   <label style="color:#c33"> //Start client applet---the corresponding structure <a href="http://open.xmeye.net/zh/#NetUseProgram">SDK\_NetUseProgram</a></label><br/>
E_SDK_CFG_FTP_TEST,                 <label style="color:#c33"> //FTP test---the corresponding structure <a href="http://open.xmeye.net/zh/#FtpServerConfig">SDK\_FtpServerConfig</a></label><br/>
E_SDK_CFG_FbExtraStateCtrl,  	      <label style="color:#c33">  //The status of the video light of consumer products---the corresponding structure <a href="http://open.xmeye.net/zh/#FbExtraStateCtrl">SDK\_FbExtraStateCtrl</a></label><br/>
E_SDK_CFG_PHONE,				<label style="color:#c33">//Mobile phone use </label><br/>
E_SDK_PicInBuffer,				<label style="color:#c33">//Mobile phone capture image, abandon </label><br/>
E_SDK_GUARD,					<label style="color:#c33">//Guard, abandon </label><br/>
E_SDK_UNGUARD = 200,			<label style="color:#c33">    //Unguard, abandon   </label><br/>
E_SDK_CFG_START_UPGRADE,		<label style="color:#c33">    //Start to upgrade, abandon</label><br/>
E_SDK_CFG_AUTO_SWITCH,	         <label style="color:#c33">   //Socket timing switch--- use H264_DVR_GetDevConfig_Json</a> to get configuration,configuration use<a href="">H264\_DVR\_SetDevConfig\_Json</a>(the format in configuration see the using command of smart socket .Doc) (two interface referred to as the Json interface, hereinafter referred to as) "Name":"PowerSocket.AutoSwitch"</label><br/>
E_SDK_CFG_POWER_SOCKET_SET,		  <label style="color:#c33">  //Control socket switch---Json interface  "Name":"OPPowerSocketGet"</label><br/>
E_SDK_CFG_AUTO_ARM,				<label style="color:#c33">//Socket timing removal---Json interface "Name":"PowerSocket.AutoArm"</label><br/>
E_SDK_CFG_WIFI_MODE,			<label style="color:#c33"> //WiFi mode configuration, used to driving recorder to switch AP mode---the corresponding structure <a href="http://open.xmeye.net/zh/#NetWifiMode">SDK\_NetWifiMode</a></label><br/>
E_SDK_CFG_CIENT_INFO,			<label style="color:#c33"> //Pass mobile phone client information---Json interface  "Name":"PowerSocket.ClientInfo"</label><br/>
E_SDK_CFG_ATHORITY,				<label style="color:#c33">//SDK_Authority---Json interface "Name":"PowerSocket.Authority"</label><br/>
E_SDK_CFG_ARM ,					<label style="color:#c33">//SDK_Arm---Json interface "Name":"PowerSocket.Arm"</label><br/>
E_SDK_CFG_AUTOLIGHT,			<label style="color:#c33">//Set the timing switch function of night light---Json interface  "Name" : "PowerSocket.AutoLight",</label><br/>
E_SDK_CFG_LIGHT = 210,			  <label style="color:#c33">  //Enable and prohibit the dynamic response function of the night lights---Json interface  "Name" : "PowerSocket.Light",</label><br/>
E_SDK_CFG_WORKRECORD,			 <label style="color:#c33">   //Power statistics---Json interface  "Name" : "PowerSocket.WorkRecord",</label><br/>
E_SDK_CFG_SYSTEMTIME,			<label style="color:#c33">//Set the time order, when LAN connection, send proofreading time command---Json interface  "Name":"System.Time"</label><br/>
E_SDK_CFG_USB,					<label style="color:#c33">//usb interface control function---Json interface  "Name":"PowerSocket.Usb"</label><br/>
E_SDK_CFG_NETPLAT_BJHONGTAIHENG,     <label style="color:#c33">   //北京鸿泰恒平台---the corresponding structure <a href="http://open.xmeye.net/zh/#CONFIG_NET_BJHONGTAIHENG">SDK\_CONFIG\_NET\_BJHONGTAIHENG</a></label><br/>
E_SDK_CFG_CLOUD_STORAGE,		  <label style="color:#c33">  //Cloud storage related configuration---the corresponding structure <a href="http://open.xmeye.net/zh/#CloudRecordConfigAll">SDK\_CloudRecordConfigAll</a></label><br/>
E_SDK_CFG_IDLE_PTZ_STATE,           <label style="color:#c33">   //PTZ idle action related configuration---the corresponding structure <a href="http://open.xmeye.net/zh/#_PtzIdleStateAll">SDK\_PtzIdleStateAll</a></label><br/>
E_SDK_CFG_CAMERA_CLEAR_FOG,	       <label style="color:#c33"> //Fog elimination function configuration---the corresponding structure <a href="http://open.xmeye.net/zh/#CameraClearFogAll">SDK\_CameraClearFogAll</a></label><br/>
E_SDK_CFG_WECHATACCOUNT,		   <label style="color:#c33"> //---Corresponding json "Name":"PowerSocket.WechatAccount"</label><br/>
E_SDK_CFG_WECHATRENEW,			   <label style="color:#c33"> //---Corresponding json "Name":"PowerSocket.WechatRenew" </label><br/>
E_SDK_CFG_POWERSOCKET_WIFI = 220,      <label style="color:#c33">  //---Corresponding   json "Name":"PowerSocket.WiFi"</label><br/><br/>
E_SDK_CFG_CAMERA_MOTOR_CONTROL,        <label style="color:#c33"> //Robot motor control ---the corresponding structure <a href="http://open.xmeye.net/zh/#CameraMotorCtrl">SDK\_CameraMotorCtrl</a></label><br/>
E_SDK_CFG_ENCODE_ADD_BEEP,		 <label style="color:#c33">   //Set to add the code into beep sound every 30 seconds---the corresponding structure <a href="http://open.xmeye.net/zh/#EncodeAddBeep">SDK\_EncodeAddBeep</a></label><br/>
E_SDK_CFG_DATALINK,		<label style="color:#c33">//datalink customer execution program enable configuration in the network service---the corresponding structure <a href="http://open.xmeye.net/zh/#DataLinkConfig">SDK\_DataLinkConfig</a></label><br/>
E_SDK_CFG_FISH_EYE_PARAM,	      <label style="color:#c33">  //Fisheye function parameter configuration---the corresponding structure <a href="http://open.xmeye.net/zh/#FishEyeParam">SDK\_FishEyeParam</a></label><br/>
E_SDK_OPERATION_SET_LOGO,	      <label style="color:#c33">  //Superimpose Xiongmai and other manufacturers' LOGO on the video ---the corresponding structure <a href="http://open.xmeye.net/zh/#SetLogo">SDK\_SetLogo</a></label><br/>
E_SDK_CFG_SPARSH_HEARTBEAT,		 <label style="color:#c33">   //Sparsh customer heartbeat function configuration---the corresponding structure  <a href="http://open.xmeye.net/zh/#SparshHeartbeat">SDK\_SparshHeartbeat</a></label><br/>
E_SDK_CFG_LOGIN_FAILED,	   <label style="color:#c33"> //When logging in failed to send mail, using the structure: the basic event structure---the corresponding structure <a href="http://open.xmeye.net/zh/#VIDEOLOSSCONFIG">SDK\_VIDEOLOSSCONFIG</a></label><br/>
E_SDK_CFG_NETPLAT_SPVMN_NAS,	   <label style="color:#c33">     //NAS server configuration of Anhui ultra-clear customers---the corresponding structure <a href="http://open.xmeye.net/zh/#SPVMN_NAS_SERVER">SDK\_SPVMN\_NAS\_SERVER</a></label><br/>
E_SDK_CFG_DDNS_APPLY,			 <label style="color:#c33">   //DDNS key function test ---the corresponding structure <a href="http://open.xmeye.net/zh/#NetDDNSConfigALL">SDK\_NetDDNSConfigALL</a></label><br/>
E_SDK_OPERATION_NEW_UPGRADE_VERSION_REQ = 230,	<label style="color:#c33">///Version query request of new version cloud upgrade---the corresponding structure <a href="http://open.xmeye.net/zh/#CloudUpgradeVersionRep">SDK\_CloudUpgradeVersionRep</a></label><br/>
E_SDK_CFG_IPV6_ADDRESS,			   <label style="color:#c33"> //ipv6------the corresponding structure <a href="http://open.xmeye.net/zh/#IPAddressV6">SDK\_IPAddressV6</a></label><br/>
E_SDK_CFG_DDNS_IPMSG,         	    <label style="color:#c33">//DDNS extranet IP address </label><br/>
E_SDK_CFG_ONLINE_UPGRADE,		   <label style="color:#c33"> //Online upgrade related configuration-----the corresponding structure <a href="http://open.xmeye.net/zh/#OnlineUpgradeCfg">SDK\_OnlineUpgradeCfg</a></label><br/>
E_SDK_CFG_CONS_SENSOR_ALARM,       <label style="color:#c33">    //Household products 433 alarm linkage configuration-----the corresponding structure <a href="http://open.xmeye.net/zh/#ConsSensorAlarmCfg">SDK\_ConsSensorAlarmCfg</a></label><br/>
E_SDK_OPEARTION_SPLIT_CONTROL,      <label style="color:#c33">    //Image segmentation mode-----the corresponding structure <a href="http://open.xmeye.net/zh/#SplitControl">SDK\_SplitControl</a></label><br/>
E_SDK_CFG_Netinfo_TRANS_COMM,	    <label style="color:#c33">    //Netinfo_cctv customers add serial port data to the specified server configuration-----the corresponding structure <a href="http://open.xmeye.net/zh/#NetinfoNetTransComm">SDK\_NetinfoNetTransComm</a></label><br/>
E_SDK_CFG_RECORD_ENABLE,    <label style="color:#c33">   //Is ready to record and capture image, now for the Japanese customers through the serial port to control the opening and closing video function</label><br/>
E_SDK_CFG_NAS,					<label style="color:#c33">//NAS configuration 		//<a href="http://open.xmeye.net/zh/#NAS_LIST">SDK\_NAS\_LIST</a></label><br/>
E_SDK_CFG_NKB_DEVICE_LIST,		  <label style="color:#c33">  //Network keyboard device chain list   </label><br/>
E_SDK_CFG_PARKING_PORT = 240,	  <label style="color:#c33">      //Parking system port configuration SDK_PortService  SDK_PortService---the corresponding structure <a href="http://open.xmeye.net/zh/#PortService">SDK\_PortService</a></label><br/>
E_SDK_CFG_NET_GBEYES,			   <label style="color:#c33"> ///<信产全球眼平台 ---the corresponding structure <a href="http://open.xmeye.net/zh/#GbEyesCfg">SDK\_GbEyesCfg</a></label><br/>
E_SDK_CFG_GLOBALEYE,			   <label style="color:#c33"> //MEGA EYES configuration ---the corresponding structure <a href="http://open.xmeye.net/zh/#DefaultResponse">SDK\_DefaultResponse</a></label><br/>
E_SDK_OPERATION_FISHEYE_MODIFY_CENTER,	   <label style="color:#c33"> //Fisheye center correction ---the corresponding structure <a href="http://open.xmeye.net/zh/#Point">SDK\_Point</a></label><br/>
E_SDK_OPERATION_UTC_TIME_SETTING = 244,	  <label style="color:#c33">  //Set UTC time---the corresponding structure <a href="http://open.xmeye.net/zh/#SYSTEM_TIME">SDK\_SYSTEM\_TIME</a></label><br/>
E_SDK_CFG_INTELBRAS_SPECIAL_INFO,		<label style="color:#c33">//interbras Interbras special tcp port---the corresponding structure <a href="http://open.xmeye.net/zh/#IntelBrasSpecialInfo">SDK\_IntelBrasSpecialInfo</a></label><br/>
E_SDK_CFG_SPVMN_PLATFORM_SIP,			<label style="color:#c33">//28181 protocol configuration sip card ip---the corresponding structure <a href="http://open.xmeye.net/zh/#SIP_NET_IP_CONFIG">SDK\_SIP\_NET\_IP\_CONFIG</a></label><br/>
E_SDK_CFG_FISH_LENS_PARAM,			<label style="color:#c33">//Fisheye lens parameters---the corresponding structure <a href="http://open.xmeye.net/zh/#FishLensParam">SDK\_FishLensParam</a></label><br/>
E_SDK_CFG_PTZCTRLMODE,			<label style="color:#c33">//Select the control mode of the analog channel PTZ control---the corresponding structure <a href="http://open.xmeye.net/zh/#PTZControlModeAll">SDK\_PTZControlModeAll</a></label><br/>
E_SDK_CFG_ENCODE_SmartH264,			<label style="color:#c33">//SmartH264+configuration---the corresponding structure SmartH264ParamAll </label><br/>
E_SDK_CFG_WIFI_INFO,				<label style="color:#c33">   //WiFi information---the corresponding structure <a href="http://open.xmeye.net/zh/#WifiInfo">SDK\_WifiInfo</a></label><br/>
E_SDK_CFG_NET_RTMP,				<label style="color:#c33">   //RTMP protocol ---the corresponding structure <a href="http://open.xmeye.net/zh/#NetRTMPConfig">SDK\_NetRTMPConfig </a> </label><br/>

}SDK_CONFIG_TYPE;
<div>
<br/><br/>


<div name="meiju3" id="meiju3" style="font-size:15px;"><b>2.3Alarm event enumeration </b></div>

enum SDK_EventCodeTypes
<div style="margin-left:20px;">
{

SDK_EVENT_CODE_INIT = 0,<br/>
SDK_EVENT_CODE_LOCAL_ALARM = 1,		<label style="color:#c33">//Local alarm (external alarm)  </label><br/>
SDK_EVENT_CODE_NET_ALARM,		<label style="color:#c33">//Network alarm</label><br/>
SDK_EVENT_CODE_MANUAL_ALARM,		<label style="color:#c33">//Manual alarm </label><br/>
SDK_EVENT_CODE_VIDEO_MOTION,		<label style="color:#c33">//Dynamic detection</label><br/>
SDK_EVENT_CODE_VIDEO_LOSS,		<label style="color:#c33">//Video loss  </label><br/>
SDK_EVENT_CODE_VIDEO_BLIND,		<label style="color:#c33">//Video blind  </label><br/>
SDK_EVENT_CODE_VIDEO_TITLE,		<br/>
SDK_EVENT_CODE_VIDEO_SPLIT,<br/>
SDK_EVENT_CODE_VIDEO_TOUR,<br/>
SDK_EVENT_CODE_STORAGE_NOT_EXIST,	<label style="color:#c33">//Storage device does not exist</label><br/>
SDK_EVENT_CODE_STORAGE_FAILURE,    <label style="color:#c33">//Storage device visit failed </label><br/>
SDK_EVENT_CODE_LOW_SPACE,		<label style="color:#c33">//Storage device capacity is too low </label><br/>
SDK_EVENT_CODE_NET_ABORT,<br/>
SDK_EVENT_CODE_COMM,<br/>
SDK_EVENT_CODE_STORAGE_READ_ERROR,	<label style="color:#c33">//Storage device read error </label><br/>
SDK_EVENT_CODE_STORAGE_WRITE_ERROR,	<label style="color:#c33">//Storage device write error   </label><br/>
SDK_EVENT_CODE_NET_IPCONFLICT,		<label style="color:#c33">//IP conflict </label><br/>
SDK_EVENT_CODE_ALARM_EMERGENCY,<br/>
SDK_EVENT_CODE_DEC_CONNECT,	<br/>
SDK_EVENT_CODE_UPGRADE,<br/>
SDK_EVENT_CODE_BACK_UP,<br/>
SDK_EVENT_CODE_SHUT_DOWN,<br/>
SDK_EVENT_CODE_REBOOT,<br/>
SDK_EVENT_CODE_NEWFILE,<br/>
SDK_EVENT_CODE_VideoAnalyze,<br/>
SDK_EVENT_CODE_IPC_ALARM,<br/>
SDK_EVENT_CODE_SPEED_ALARM,<br/>
SDK_EVENT_CODE_GSENSOR_AlARM,<br/>
SDK_EVENT_CODE_LOGIN_FAILED,		<label style="color:#c33">//Login failed</label><br/>
SDK_EVENT_CODE_SERIAL_ALARM,<br/>
SDK_EVENT_CODE_CONSSENSOR_ALARM, 	<label style="color:#c33">//External device alarm of consumer product binding</label><br/>
SDK_EVENT_CODE_NR,<br/>
</div>
};

<label style="color:#c33">//Alarm information </label><br/>

typedef struct <a href="http://open.xmeye.net/zh/#ALARM_INFO">SDK\_ALARM\_INFO</a>
{<br/>
    int nChannel;   
    int iEvent; <label style="color:#c33">//Alarm event code: see enumeration<a href="http://open.xmeye.net/zh/#EventCodeTypes">SDK\_EventCodeTypes </a> </label><br/> 
    int iStatus; <label style="color:#c33">//0: alarm start, 1: alarm end   </label><br/> 
    <a href="http://open.xmeye.net/zh/#SYSTEM_TIME">SDK\_SYSTEM\_TIME SysTime;   </a><br/>
}SDK_AlarmInfo;  


<label style="color:#c33">//Type of encoding configuration     </label><br/>
enum SDK_ENCODE_TYPE_BY_RECORD   
{
	SDK_ENCODE_TYPE_TIM = 0,   
	SDK_ENCODE_TYPE_MTD = 1,    
	SDK_ENCODE_TYPE_ALM = 2,     
	SDK_ENCODE_TYPE_NUM = 3,     
	SDK_ENCODE_TYPE_SNAP_TIMER = 0,    
	SDK_ENCODE_TYPE_SNAP_TRIGGER = 1,     
};    
 #define SDK_EXTRATYPES 3 <label style="color:#c33">//Sub stream type    </label><br/> 


<label style="color:#c33">//Network transmission strategy       </label><br/>  
enum SDK_TransferPolicy     
{<br/>
SDK_TRANSFER_POLICY_AUTO,		<label style="color:#c33">///< Self-adaption    </label><br/>    
SDK_TRANSFER_POLICY_QUALITY,		<label style="color:#c33">/// Quality priority     </label><br/>     
SDK_TRANSFER_POLICY_FLUENCY,		<label style="color:#c33">/// Data traffic priority   </label><br/>    
SDK_TRANSFER_POLICY_TRANSMISSION,	<label style="color:#c33">/// Network transmission priority   </label><br/>   
SDK_TRANSFER_POLICY_NR,<br/>
};


<label style="color:#c33">/// Network transport protocol type </label><br/>    
enum SDK_NetTransProtocolType    
{<br/>
SDK_NET_TRANS_PRO_TCP = 0,  <br/>  
SDK_NET_TRANS_PRO_UDP = 1,  <br/>   
};


<label style="color:#c33">/// Encoding function    </label><br/>  
enum SDK_EncodeFunctionTypes   
{
SDK_ENCODE_FUNCTION_TYPE_DOUBLE_STREAM,		<label style="color:#c33">/// Dual stream function   </label><br/>      
SDK_ENCODE_FUNCTION_TYPE_COMBINE_STREAM,	    <label style="color:#c33">/// Combined coding function</label><br/>      
SDK_ENCODE_FUNCTION_TYPE_SNAP_STREAM,		<label style="color:#c33">///Capture image function     </label><br/>  
SDK_ENCODE_FUNCTION_TYPE_WATER_MARK,		<label style="color:#c33">///Watermark function   </label><br/>   
SDK_ENCODE_FUNCTION_TYPE_IFRAME_RANGE,		<label style="color:#c33">/// I frame interval    </label><br/>  
SDK_ENCODE_FUNCTION_TYPE_LOW_BITRATE,   	   <label style="color:#c33"> ///Low bit rate  </label><br/>    
SDK_ENCODE_FUNCTION_TYPE_SmartH264,		<label style="color:#c33">//H264+    </label><br/>  
SDK_ENCODE_FUNCTION_TYPE_NR,   
};


<label style="color:#c33">/// Alarm function   </label><br/>  
enum SDK_AlarmFucntionTypes   
{<br/>  
SDK_ALARM_FUNCTION_TYPE_MOTION_DETECT,		<label style="color:#c33">///Dynamic detection </label><br/>     
SDK_ALARM_FUNCTION_TYPE_BLIND_DETECT,		<label style="color:#c33">///Video occlusion   </label><br/>      
SDK_ALARM_FUNCTION_TYPE_LOSS_DETECT,		<label style="color:#c33">///Video loss  </label><br/>       
SDK_ALARM_FUNCTION_TYPE_LOCAL_ALARM,		<label style="color:#c33">///Local alarm  </label><br/>          
SDK_ALARM_FUNCTION_TYPE_NET_ALARM,		<label style="color:#c33">///Network alarm   </label><br/>         
SDK_ALARM_FUNCTION_TYPE_IP_CONFLICT,		<label style="color:#c33">///IP address conflict </label><br/>    
SDK_ALARM_FUNCTION_TYPE_NET_ABORT,		<label style="color:#c33">///Network abnormal   </label><br/>              
SDK_ALARM_FUNCTION_TYPE_STORAGE_NOTEXIST,	   <label style="color:#c33"> ///Storage device does not exist </label><br/>              
SDK_ALARM_FUNCTION_TYPE_STORAGE_LOWSPACE,	   <label style="color:#c33"> ///Insufficient storage capacity</label><br/>             
SDK_ALARM_FUNCTION_TYPE_STORAGE_FAILURE,	   <label style="color:#c33"> ///Storage device visit failed </label><br/>            
SDK_ALARM_FUNCTION_TYPE_VIDEOANALYSE,		<label style="color:#c33">///Video analysis   </label><br/>           
SDK_ALARM_FUNCTION_TYPE_NET_ABORT_EXTEND,	 <label style="color:#c33">   ///Network anomaly extension   </label><br/>           
SDK_ALARM_FUNCTION_TYPE_IPC_ALARM,		<label style="color:#c33">///IPC alarm    </label><br/>         
SDK_ALARM_FUNCTION_TYPE_CONSUMER_433ALARM,	<label style="color:#c33">///Household products 433 device alarm</label><br/>           
SDK_ALARM_FUNCTION_TYPE_CONSUMER_REMOTE, 	   <label style="color:#c33"> ///Household products 2.4G remote controller         </label><br/>  
SDK_ALARM_FUNCTION_TYPE_NR  <br/>        
};

<label style="color:#c33">/// Network service function    </label><br/>         
enum SDK_NetServerTypes         
{<br/>  
SDK_NET_SERVER_TYPES_IPFILTER,		<label style="color:#c33">///White black list  </label><br/>           
SDK_NET_SERVER_TYPES_DHCP,		<label style="color:#c33">///DHCP function    </label><br/>           
SDK_NET_SERVER_TYPES_DDNS,		<label style="color:#c33">///DDNS function  </label><br/>            
SDK_NET_SERVER_TYPES_EMAIL,		<label style="color:#c33">///Email function    </label><br/>           
SDK_NET_SERVER_TYPES_MULTICAST,		<label style="color:#c33">///Multicast function     </label><br/>                            
SDK_NET_SERVER_TYPES_NTP,			<label style="color:#c33">///NTP function     </label><br/>            
SDK_NET_SERVER_TYPES_PPPOE,             <br/>  
SDK_NET_SERVER_TYPES_DNS,   <br/>  
SDK_NET_SERVER_TYPES_ARSP,		<label style="color:#c33">///Active registration service    </label><br/>                 
SDK_NET_SERVER_TYPES_3G,           <label style="color:#c33"> /// 3G dial    </label><br/>             
SDK_NET_SERVER_TYPES_MOBILE=10,     	<label style="color:#c33">/// Mobile phone monitoring      </label><br/>                 
SDK_NET_SERVER_TYPES_UPNP,		<label style="color:#c33">///< UPNP       </label><br/>       
SDK_NET_SERVER_TYPES_FTP,			<label style="color:#c33">///< FTP      </label><br/>          
SDK_NET_SERVER_TYPES_WIFI,          	<label style="color:#c33">///Alarm center   </label><br/>               
SDK_NET_SERVER_TYPES_ALARM_CENTER,  	<label style="color:#c33">///< 告警中心 </label><br/>        
SDK_NET_SERVER_TYPES_NETPLAT_MEGA,  	<label style="color:#c33">///< 互信互通 </label><br/>          
SDK_NET_SERVER_TYPES_NETPLAT_XINWANG,  	<label style="color:#c33">///< 星望   </label><br/>         
SDK_NET_SERVER_TYPES_NETPLAT_SHISOU,  	<label style="color:#c33">///< 视搜    </label><br/>          
SDK_NET_SERVER_TYPES_NETPLAT_VVEYE,  	<label style="color:#c33">///< 威威眼    </label><br/>            
SDK_NET_SERVER_TYPES_RTSP,     		<label style="color:#c33">///< RTSP   </label><br/>            
SDK_NET_SERVER_TYPES_PHONEMSG=20,     	<label style="color:#c33">///< Mobile phone information send configuration </label><br/>            
SDK_NET_SERVER_TYPES_PHONEMULTIMEDIAMSG, <label style="color:#c33">///< Mobile phone information send configuration   </label><br/>             
SDK_NET_SERVER_TYPES_DAS,          	<label style="color:#c33">///< Active registration     </label><br/>  
SDK_NET_SERVER_TYPES_LOCALSDK_PLATFORM,  <label style="color:#c33">///< Network platform information setting          </label><br/>     
SDK_NET_SERVER_TYPES_GOD_EYE,		<label style="color:#c33">///< 神眼接警中心系统   </label><br/>   
SDK_NET_SERVER_TYPES_NAT,			<label style="color:#c33">///< NAT penetration, MTU configuration  </label><br/>    
SDK_NET_SERVER_TYPES_VPN,     		<label style="color:#c33">///< VPN     </label><br/>  
SDK_NET_SERVER_TYPES_NET_KEYBOARD,	<label style="color:#c33">///< Network keyboard configuration  </label><br/>      
SDK_NET_SERVER_TYPES_SPVMN,		<label style="color:#c33">///< 28181 protocol configuration    </label><br/>  
SDK_NET_SERVER_TYPES_PMS,      	<label style="color:#c33">///< Mobile phone service     </label><br/>  
SDK_NET_SERVER_TYPE_KAICONG,	   <label style="color:#c33"> ///< Kai Cong configuration   </label><br/>   
SDK_NET_SERVER_TYPE_PROTOCOL_MAC,		<label style="color:#c33">///< Support MAC protocol </label><br/>    
SDK_NET_SERVER_TYPE_XMHEARTBEAT, 		<label style="color:#c33">///< XM heartbeat   </label><br/>    
SDK_NET_SERVER_TYPES_MONITOR_PLATFORM, 	<label style="color:#c33">///< Digital China monitoring platform  </label><br/>       
SDK_NET_SERVER_TYPES_ANJUP2P,		<label style="color:#c33">///< P2P </label><br/>           
SDK_NET_SERVER_TYPES_TUTKIOTC,		<label style="color:#c33">///< TUTK IOTC platform </label><br/>            
SDK_NET_SERVER_TYPES_BAIDUCLOUD, 		<label style="color:#c33">///< Baidu Cloud   </label><br/>             
SDK_NET_SERVER_TYPES_MOBILWATCH,		<label style="color:#c33">///< Mobile phone shop   </label><br/>           
SDK_NET_SERVER_TYPES_BJLTHY,		<label style="color:#c33">///< 北京龙腾访问服务器平台 </label><br/>              
SDK_NET_SERVER_TYPES_OPENVPN,		<label style="color:#c33">///< Openvpn configuration </label><br/>              
SDK_NET_SERVER_TYPES_PROTOCOL_NAT,	<label style="color:#c33">///< Support NAT protocol   </label><br/>            
SDK_NET_SERVER_TYPES_PLATFORM_GBEYES,	<label style="color:#c33">///< Support environmental data superposition</label><br/>             
SDK_NET_SERVER_TYPES_GBEYES,		<label style="color:#c33">///< 信产全球眼平台</label><br/>          
SDK_NET_SERVER_TYPES_DATALINK,		<label style="color:#c33">///< Datalink customer execution program enable configuration in the network service      </label><br/>       
SDK_NET_SERVER_TYPES_WIFI_MODE,		<label style="color:#c33">///< Whether to support WiFi mode related configuration </label><br/>          
SDK_NET_SERVER_TYPES_IPV6,		<label style="color:#c33">///< Support ipv6    </label><br/>         
SDK_NET_SERVER_TYPES_PMS_V2,		<label style="color:#c33">///< New PMS page   </label><br/>            
SDK_NET_SERVER_TYPES_4G,		    <label style="color:#c33">///< The drop down box whether to display 4G in wireless dial-up protocol </label><br/>          
SDK_NET_SERVER_TYPES_SPVMN_SIP,		<label style="color:#c33">///< 28181 configuration SIP card address</label><br/>       
SDK_NET_SERVER_TYPES_RTMP,		<label style="color:#c33">///< RTMP协议 </label><br/>      
SDK_NET_SERVER_TYPES_NR,         <br/>  
};

<label style="color:#c33">/// Preview function       </label><br/>    
enum SDK_PreviewTypes <br/>         
{ 
   SDK_PREVIEW_TYPES_TOUR,		<label style="color:#c33">///< Round cruise    </label><br/>         
   SDK_PREVIEW_TYPES_TALK,		<label style="color:#c33">///< GUI interface configuration        </label><br/>      
   SDK_PREVIEW_TYPES_NR            <br/>  
};

<label style="color:#c33">///Serial port type    </label><br/>         
enum SDK_CommTypes <br/>          
{  
   SDK_COMM_TYPES_RS485,		<label style="color:#c33">///<485 serial port   </label><br/>                 
   SDK_COMM_TYPES_RS232,		<label style="color:#c33">///<232 serial port    </label><br/>        
   SDK_COMM_TYPES_NR       
};

<label style="color:#c33">//Input method limitation    </label><br/>      
enum SDK_InPutMethod  <br/>       
{
SDK_NO_SUPPORT_CHINESE,		<label style="color:#c33">//Chinese input is not supported     </label><br/>         
SDK_NO_SUPPORT_NR    <br/>      
};

<label style="color:#c33">//Label display in alarm      </label><br/>     
 
enum SDK_TipShow    <br/>         
{
SDK_NO_BEEP_TIP_SHOW,  		<label style="color:#c33">//Buzz tips  </label><br/>        
SDK_NO_FTP_TIP_SHOW,  		<label style="color:#c33">//FTP tips      </label><br/>       
SDK_NO_EMAIL_TIP_SHOW,  	    <label style="color:#c33">//EMAIL tips      </label><br/>          
SDK_NO_DISK_MANAGER_SHOW,     <label style="color:#c33">//Do not display the hard disk management page partition and type modification and other buttons</label><br/>             
SDK_NO_TIP_SHOW_NR  <br/>  

};

<label style="color:#c33">///Vehicle on-board function   </label><br/>           

enum SDK_MobileCar    <br/>  
{
SDK_MOBILEDVR_STATUS_EXCHANGE,			<label style="color:#c33">//Vehicle status  </label><br/>            
SDK_MOBILEDVR_DELAY_SET,	 			<label style="color:#c33">//Delay settings    </label><br/>          
SDK_MOBILEDVR_CARPLATE_SET,          <br/>  
SDK_MOBILEDVR_GPS_TIMING,	 			<label style="color:#c33">//GPS time correlation   </label><br/>           
SDK_MOBILEDVR_DVR_BOOT_TYPE_SET,           <br/>  
SDK_MOBILEDVR_NR        <br/>  
};




<label style="color:#c33">///Other functions     </label><br/>       

enum SDK_OtherFunction<br/> 
{  
<div style="margin-left:20px;">
SDK_OTHER_DOWNLOADPAUSE,				<label style="color:#c33">//Video download pause function  </label><br/>            
SDK_OTHER_USB_SUPPORT_RECORD,			<label style="color:#c33">//USB support video function      </label><br/>       
SDK_OTHER_SD_SUPPORT_RECORD,			<label style="color:#c33">//SD support video function     </label><br/>          
SDK_OTHER_ONVIF_CLIENT_SUPPORT,			<label style="color:#c33">//Whether to support ONVIF client  </label><br/>           
SDK_OTHER_NET_LOCALSEARCH_SUPPORT,		<label style="color:#c33">//Whether to support remote search   </label><br/>           
SDK_OTHER_MAXPLAYBACK_SUPPORT, 			<label style="color:#c33">//Whether to support the maximum playback channel number display </label><br/>                
SDK_OTHER_NVR_SUPPORT, 				<label style="color:#c33">//Whether is the professional NVR        </label><br/>      
SDK_OTHER_C7_PLATFORM_SUPPORT,			<label style="color:#c33">//Support C7 platform         </label><br/>       
SDK_OTHER_MAIL_TEST_SUPPORT,			<label style="color:#c33">//Support mail test      </label><br/>       
SDK_OTHER_SHOW_OSD_INFO,            	<label style="color:#c33">//Support to display 3 lines OSD information  </label><br/>              
SDK_OTHER_HIDE_DIGITAL, 				<label style="color:#c33">//Channel mode shielding function   </label><br/>        
SDK_OTHER_ACUTANCE_HORIZONTAL,			<label style="color:#c33">//Sharpness         </label><br/>    
SDK_OTHER_ACUTANCE_VERTIAL,            
SDK_OTHER_BROAD_TRENDS,				<label style="color:#c33">//Wide dynamic function      </label><br/>     
SDK_OTHER_NO_TALK,				<label style="color:#c33">//Intercom ability         </label><br/>      
SDK_OTHER_ALTER_DIGITAL_NAME,			<label style="color:#c33">//Modify digital channel name   </label><br/>          
SDK_OTHER_SHOW_CONNECT_STATUS,      	   <label style="color:#c33"> //Support for display WiFi 3G active registration and other connection   </label><br/>  
SDK_OTHER_SUPPORT_ECACT_SEEK,			<label style="color:#c33">//Support playback precision positioning  </label><br/>             
SDK_OTHER_UPLOAD_TITLEANDSTATE,			<label style="color:#c33">//Channel header and digital channel status upload capability set </label><br/>             
SDK_OTHER_NO_HDD_RECORD,				<label style="color:#c33">//No hard disk video   </label><br/>         
SDK_OTHER_MUSICFILE_PLAY,				<label style="color:#c33">//Play audio file   </label><br/>          
SDK_OTHER_SUPPORT_SET_DIG_IP,			<label style="color:#c33">//Set front end IP capability   </label><br/>          
SDK_OTHER_VERSION_PRODUCT_TYPE,			<label style="color:#c33">//Support display device model in version information</label><br/>     
SDK_OTHER_SUPPORT_CAMERA_IMG_STYLE,		<label style="color:#c33">//Support camera image style </label><br/>    
SDK_OTHER_SUPPORT_TITLE_ABILITY,		  <label style="color:#c33">  //Support to modify onvif title   </label><br/>    
SDK_OTHER_SUPPORT_DIMEN_CODE,			<label style="color:#c33">//Support two-dimensional code   </label><br/>  
SDK_OTHER_STORAGE_NAS_SUPPORT,			<label style="color:#c33">//Whether to support the NAS storage function  </label><br/>    
SDK_OTHER_SHOWFALSE_CHECKTIME,			<label style="color:#c33">//Shield decoder time synchronization function  </label><br/>   
SDK_OTHER_SUPPORT_TIME_ZONE, 			<label style="color:#c33">//Time zone configuration    </label><br/>  
SDK_OTHER_SHOW_ALARM_LEVEL_REGION,		<label style="color:#c33">//Display the sensitivity and regional setting of digital channel alarm function </label><br/>     
SDK_OTHER_SUPPORT_POS,				<label style="color:#c33">//Support POS </label><br/>     
SDK_OTHER_HDD_LOWSPACE_USE_MB,			<label style="color:#c33">//Hard disk space shortage alarm limit with MB </label><br/>     
SDK_OTHER_SUPPORT_CUSTOMIZE_OEMINFO,	   <label style="color:#c33"> //Custom OEM client version information </label><br/>    
SDK_OTHER_DIGITAL_ENCODE,				<label style="color:#c33">//Digital channel coding configuration   </label><br/>  
SDK_OTHER_RESUME_PTZ_STATE,			<label style="color:#c33">//Boot recovery PTZ status   </label><br/>  
SDK_OTHER_SUPPORT_SNAP_CFG,			<label style="color:#c33">//Support capture configuration     </label><br/>  
SDK_OTHER_ABNORMITY_SEND_EMAIL,			<label style="color:#c33">//Storage devices exist and storage exception and storage space is not enough to send e-mail messages   </label><br/>  
SDK_OTHER_SUPPORT_DIGITAL_PRE,			<label style="color:#c33">//Support digital channel pre record  </label><br/>      
SDK_OTHER_SUPPORT_WRITE_LOG, 			<label style="color:#c33">//Alarm page adding whether to write log check box </label><br/>    
SDK_OTHER_SUPPORT_CHANGE_ONVIF_PORT,	    <label style="color:#c33">//Support to modify onvif port   </label><br/>    
SDK_OTHER_SUPPORT_COMM_DATA_UPLOAD,  	    <label style="color:#c33">//Supports serial port data upload to the specified server</label><br/>      
SDK_OTHER_SUPPORT_TEXT_PASSWORD,		    <label style="color:#c33">//Record the clear text password  </label><br/>    
SDK_OTHER_SUPPORT_CLOUD_UPGRADE,		    <label style="color:#c33">// Support cloud upgrade    </label><br/>    
SDK_OTHER_SUPPORT_USER_PROGRAM,			<label style="color:#c33">//Support start client applet  </label><br/>    
SDK_OTHER_SUPPORT_MODIFY_FRONT_CFG,		<label style="color:#c33">//Support modify front end configuration   </label><br/>   
SDK_OTHER_SUPPORT_FTP_TEST,    			<label style="color:#c33">//The new program supports FTP, support FTP test, the old program does not support.</label><br/>     
SDK_OTHER_SUPPORT_PTZ_IDLE_STATE, 		<label style="color:#c33">//What kind of operational configuration to execute when the PTZ is idle </label><br/>   
SDK_OTHER_SUPPORT_IMP_RCD,			<label style="color:#c33">//What kind of operational configuration to execute when the PTZ is idle	</label><br/>    
SDK_OTHER_SUPPORT_CAMERA_MOTOR_CTRL, 	   <label style="color:#c33"> //Support robot motor control    </label><br/>    
SDK_OTHER_SUPPORT_ENCODE_ADD_BEEP,		<label style="color:#c33">// Add into beep sound in video code every 30 seconds  </label><br/>   
SDK_OTHER_SUPPORT_FISH_EYE,	       	<label style="color:#c33">//Fisheye function capability set     </label><br/>  
SDK_OTHER_SUPPORT_SPVMN_NAS_SERVER,		<label style="color:#c33">//NAS server configuration of Anhui ultra-clear customers </label><br/>     
SDK_OTHER_SUPPORT_SMALL_CHN_TITLE_FONT,      <label style="color:#c33">//IE pass 12*18 channel title lattice</label><br/>      
SDK_OTHER_SUPPORT_CFG_CLOUD_UPGRADE, 	   <label style="color:#c33"> //Support new cloud upgrade function configuration
  </label><br/>   
SDK_OTHER_SUPPORT_STORAGE_FAIL_REBOOT,	    <label style="color:#c33">//Automatically reset  after all the hard disks go wrong </label><br/>     
SDK_OTHER_SUPPORT_SPLIT_CONTROL,		   <label style="color:#c33"> //Support CMS client screen segmentation  </label><br/>       
SDK_OTHER_RTSP_CLIENT_SUPPORT,			<label style="color:#c33">//Digital channel whether to support to connect front-end device by RTSP</label><br/>       
SDK_OTHER_LOW_LUX_MODE,				<label style="color:#c33">//Twilight mode  </label><br/>      
SDK_OTHER_SUPPORT_Switch_Resolution,	    <label style="color:#c33">//Modify front end digital channel resolution  </label><br/>    
SDK_OTHER_LOW_MOTION,				<label style="color:#c33">//Motion camera slow motion  </label><br/>    
SDK_OTHER_SUPPORT_CORRIDOR_MODE,           <label style="color:#c33"> //Support corridor mode  </label><br/>    
SDK_OTHER_WIFINVR_SUPPORT,			<label style="color:#c33">//Whether is WIFINVR      </label><br/>  
SDK_OTHER_NR      <br/>   
</div> 
};




<label style="color:#c33">///Supported system functions   </label><br/>  

typedef struct SDK\_SystemFunction<br/> 
{ 
<div style="margin-left:20px;">
bool vEncodeFunction[SDK_ENCODE_FUNCTION_TYPE_NR];	<label style="color:#c33">///<  Encoding function <a href="http://open.xmeye.net/zh/#EncodeFunctionTypes">SDK_EncodeFunctionTypes</a></label><br/>

bool vAlarmFunction[SDK_ALARM_FUNCTION_TYPE_NR];	   <label style="color:#c33"> ///< Alarm function <a href="http://open.xmeye.net/zh/#AlarmFucntionTypes">AlarmFucntionTypes</a></label><br/>

bool vNetServerFunction[SDK_NET_SERVER_TYPES_NR];	   <label style="color:#c33"> ///< Network service function <a href="http://open.xmeye.net/zh/#NetServerTypes">NetServerTypes</a></label><br/>

bool vPreviewFunction[SDK_PREVIEW_TYPES_NR];		<label style="color:#c33">///< Preview function <a href="http://open.xmeye.net/zh/#PreviewTypes">PreviewTypes</a></label><br/>

bool vCommFunction[SDK_COMM_TYPES_NR];			<label style="color:#c33">///< Serial port type <a href="http://open.xmeye.net/zh/#CommTypes">SDK_CommTypes</a></label><br/>

bool vInputMethodFunction[SDK_NO_SUPPORT_NR];  		<label style="color:#c33">///< Input method limitation <a href="http://open.xmeye.net/zh/#InPutMethod">SDK_InPutMethod</a>></label><br/>

bool vTipShowFunction[SDK_NO_TIP_SHOW_NR];           <label style="color:#c33">///< Alarm label display <a href="http://open.xmeye.net/zh/#TipShow">SDK_TipShow></a></label><br/>

bool vMobileCarFunction[SDK_MOBILEDVR_NR];		<label style="color:#c33">///< Vehicle on-board function</label><br/>

bool vOtherFunction[SDK_OTHER_NR];			<label style="color:#c33">///< Other functions <a href="http://open.xmeye.net/zh/#OtherFunction">OtherFunction</a></label><br/>
</div>
}<a href="http://open.xmeye.net/zh/#SystemFunction">SDK_SystemFunction</a>; <br/>

<label style="color:#c33">/// Supported DDNS types</label><br/>

typedef struct <a href="http://open.xmeye.net/zh/#DDNSServiceFunction">SDK_DDNSServiceFunction</a><br/> 
{ 
int  nTypeNum; <br/>
char vDDNSType[<a href="http://open.xmeye.net/zh/#NET_MAX_DDNS_TYPE">NET\_MAX\_DDNS\_TYPE</a>][64]; <br/>
}SDK_DDNSServiceFunction;<br/>

<label style="color:#c33">/// Area occlusion Capability Set</label><br/>

typedef struct SDK\_BlindDetectFunction<br/> 
{ 
int iBlindConverNum;	<label style="color:#c33">///< Regional block number</label><br/>

}SDK_BlindDetectFunction;<br/>




<label style="color:#c33">/// Dynamic inspection area Capability Set</label><br/>

typedef struct SDK\_MotionDetectFunction<br/> 
{
int iGridRow;</label><br/>

int iGridColumn;</label><br/>

}SDK\_MotionDetectFunction; <br/>




typedef struct SDK\_EncodeInfo<br/> 
{ 
bool bEnable;			<label style="color:#c33">///< Enable item</label><br/>

bool bHaveAudio;			<label style="color:#c33">///< Whether support audio?</label><br/>

int  iStreamType;		<label style="color:#c33">///< Code stream type，capture_channel_t</label><br/>

unsigned int uiCompression;	<label style="color:#c33">///< capture_comp_t mask</label><br/>

unsigned int uiResolution;	<label style="color:#c33">///< SDK_CAPTURE_SIZE_t mask</label><br/>

}SDK_EncodeInfo; <br/>

<label style="color:#c33">/// Coding ability</label><br/>

typedef struct CONFIG\_EncodeAbility<br/> 
{ 
unsigned int iMaxEncodePower;				<label style="color:#c33">///< Maximum encoding capability supported</label><br/>

int iChannelMaxSetSync;					<label style="color:#c33">///< Does each channel resolution require synchronization, 0- asynchrony, and 1 - synchronization?</label><br/>

unsigned int nMaxPowerPerChannel[<a href="http://open.xmeye.net/zh/#NET_MAX_CHANNUM">NET_MAX_CHANNUM</a>];	<label style="color:#c33">///< The maximum coding capability supported by each channel</label><br/>

unsigned int ImageSizePerChannel[<a href="http://open.xmeye.net/zh/#NE_MA_CHANNUM">NE_MA_CHANNUM</a>];	<label style="color:#c33">///< The image resolution supported by each channel</label><br/>

unsigned int ExImageSizePerChannel[<a href="http://open.xmeye.net/zh/#NE_MA_CHANNUM">NE_MA_CHANNUM</a>];	<label style="color:#c33">///< The image resolution of the auxiliary code stream supported by each channel</label><br/>

unsigned int CompressionMask[<a href="http://open.xmeye.net/zh/#NET_MAX_CHANNUM">NET\_MAX\_CHANNUM</a>];		<label style="color:#c33">///< Coding mode capture\_comp\_t mask</label><br/>

unsigned int ThridImageSize[<a href="http://open.xmeye.net/zh/#NET_MAX_CHANNUM">NET\_MAX\_CHANNUM</a>];		<label style="color:#c33">///< CHL\_3IRD\_T Image resolution supported by codestream</label><br/>

unsigned int FourthImageSize[<a href="http://open.xmeye.net/zh/#NET_MAX_CHANNUM">NET\_MAX\_CHANNUM</a>];		<label style="color:#c33">///< CHL\_4RTH\_T Image resolution supported by codestream</label><br/>

SDK_EncodeInfo vEncodeInfo[<a href="http://open.xmeye.net/zh/#CHL_FUNCTION">SDK\_CHL\_FUNCTION\_NUM</a>];		<label style="color:#c33">///< Encoding information, temporarily maximum 4 bit stream</label><br/>

SDK_EncodeInfo vCombEncInfo[<a href="http://open.xmeye.net/zh/#CHL_FUNCTION_NUM">SDK\_CHL\_FUNCTION\_NUM</a>];	<label style="color:#c33">///< Combine coded information, temporarily maximum 4 bit stream</label><br/>

int	iMaxBps;					<label style="color:#c33">///<Highest code streamKbps</label><br/>

unsigned int ExImageSizePerChannelEx[<a href="http://open.xmeye.net/zh/#NET_MAX_CHANNUM">NET\_MAX\_CHANNUM</a>][<a href="http://open.xmeye.net/zh/#CAPTURE_SIZE_EXT_V3_NR">SDK\_CAPTURE\_SIZE\_EXT\_V3\_NR</a>];<label style="color:#c33">///< The image resolution of the auxiliary bit stream supported by each channel</label><br/>

}CONFIG_EncodeAbility; <br/>

<label style="color:#c33">///< Automatic maintenance settings</label><br/>

typedef struct SDK\_AutoMaintainConfig
{<br/>
int iAutoRebootDay;		<label style="color:#c33">///< Auto restart setting date</label><br/>

int iAutoRebootHour;		<label style="color:#c33">///< Restart full time	[0, 23]</label><br/>

int iAutoDeleteFilesDays;		<label style="color:#c33">///< Auto delete file time[0, 30]</label><br/>

}SDK\_AutoMaintainConfig; <br/>

<label style="color:#c33">// PTZ linkage type</label><br/>

enum <a href="http://open.xmeye.net/zh/#PtzLinkTypes">PtzLinkTypes</a>
{<br/>
PTZ_LINK_NONE,		<label style="color:#c33">// Linkage is not required</label><br/>

PTZ_LINK_PRESET,	<label style="color:#c33">// Go to preset point </label><br/>

PTZ_LINK_TOUR,		<label style="color:#c33">// cruise </label><br/>

PTZ_LINK_PATTERN	<label style="color:#c33">// trajectory </label><br/>

};




<label style="color:#c33">//  PTZ linkage structure</label><br/>

typedef struct SDK\_PtzLinkConfig<br/> 
{ 

int iType;		<label style="color:#c33">// Type of linkage -- corresponding structure<a href="http://open.xmeye.net/zh/#PtzLinkTypes">PtzLinkTypes</a></label><br/>

int iValue;		<label style="color:#c33">// The type of linkage corresponds to the value</label><br/>

}SDK\_PtzLinkConfig;<br/>


 #define <a href="http://open.xmeye.net/zh/#CHANNELNAME_MAX_LEN">CHANNELNAME\_MAX\_LEN</a> 64 <label style="color:#c33"> //Maximum length of channel name</label><br/>

<label style="color:#c33">//Because you want to be compatible with multichannel devices, you need to modify the type of the structure</label><br/>

typedef struct <a href="http://open.xmeye.net/zh/#EventHandler">SDK\_EventHandler</a><br/> 
{ 
char	dwRecord[<a href="http://open.xmeye.net/zh/#NET_MAX_MSK_SIZE">NET\_MAX\_MSK\_SIZE</a>];		<label style="color:#c33">// Video mask </label><br/>

int		iRecordLatch;			<label style="color:#c33">// Video delay：10?300 sec</label><br/>

char	dwTour[<a href="http://open.xmeye.net/zh/#NET_MAX_MSK_SIZE">NET\_MAX\_MSK\_SIZE</a>];		<label style="color:#c33">// Wheel patrol mask </label><br/>	

char	dwSnapShot[<a href="http://open.xmeye.net/zh/#NET_MAX_MSK_SIZE">NET\_MAX\_MSK\_SIZE</a>];		<label style="color:#c33">// Capture mask</label><br/> 

char	dwAlarmOut[<a href="http://open.xmeye.net/zh/#NET_MAX_MSK_SIZE">NET\_MAX\_MSK\_SIZE</a>];		<label style="color:#c33">// Alarm output channel mask </label><br/>

char	dwMatrix[<a href="http://open.xmeye.net/zh/#NET_MAX_MSK_SIZE">NET\_MAX\_MSK\_SIZE</a>];		<label style="color:#c33">// Matrix mask</label><br/>

int		iEventLatch;			<label style="color:#c33">// Linkage start delay time, s in units</label><br/>

int		iAOLatch;			<label style="color:#c33">// Alarm output delay：10?300 sec</label><br/>

<a href="http://open.xmeye.net/zh/#PtzLinkConfig PtzLink"> SDK\_PtzLinkConfig PtzLink[<a href="http://open.xmeye.net/zh/#NET_MAX_CHANNUM">NET\_MAX\_CHANNUM</a>];	<label style="color:#c33">// Pan tilt linkage</label><br/>

<a href="http://open.xmeye.net/zh/#CONFIG_WORKSHEET">SDK\_CONFIG\_WORKSHEET</a> schedule;			<label style="color:#c33">// Video recording time</label><br/>



bool	bRecordEn;				<label style="color:#c33">// Video enable</label><br/>

bool	bTourEn;				<label style="color:#c33">// Round trip enable</label><br/>

bool	bSnapEn;				<label style="color:#c33">// Capture enable</label><br/>

bool	bAlarmOutEn;			  <label style="color:#c33">  // Alarm enable</label><br/>

bool	bPtzEn;



<label style="color:#c33">// PTZ linkage enable</label><br/>

bool	bTip;					<label style="color:#c33">// Screen prompt enable</label><br/>

bool	bMail;					<label style="color:#c33">// Send mail</label><br/>

bool	bMessage;				<label style="color:#c33">// Send messages to the alarm center</label><br/>

bool	bBeep;					<label style="color:#c33">// Beep</label><br/>

bool	bVoice;					<label style="color:#c33">// Voice prompt</label><br/>

bool	bFTP;					<label style="color:#c33">// Start FTP transport</label><br/>

bool	bMatrixEn;				<label style="color:#c33">// Matrix enable</label><br/>

bool	bLog;					<label style="color:#c33">// Log enable</label><br/>

bool	bMessagetoNet;			  <label style="color:#c33">  // Messages uploaded to the network enable</label><br/>



bool    bShowInfo;                   <label style="color:#c33"> // Is the alarm information displayed on the GUI and in the code?</label><br/>

char    dwShowInfoMask[<a href="http://open.xmeye.net/zh/#NET_MAX_MSK_SIZE">NET\_MAX\_MSK\_SIZE</a>]; 	<label style="color:#c33">// A channel mask that is linked to display alarm information</label><br/>

char    pAlarmInfo[<a href="http://open.xmeye.net/zh/#CHANNELNAME_MAX_LEN">CHANNELNAME\_MAX\_LEN</a>]; 	<label style="color:#c33">//The alert information to display</label><br/>



bool    bShortMsg;             <label style="color:#c33"> //Send text messages</label><br/>

bool    bMultimediaMsg;         <label style="color:#c33">//Send MMS</label><br/>

}SDK_EventHandler;

<label style="color:#c33">///< Dynamic detection settings</label><br/>

typedef struct SDK\_MOTIONCONFIG<br/> 
{ 

bool bEnable;				<label style="color:#c33">// Dynamic detection open</label><br/>

int iLevel;				<label style="color:#c33">// sensitivity</label><br/>

unsigned int mRegion[<a href="http://open.xmeye.net/zh/#NET_MD_REGION_ROW">NET\_MD\_REGION\_ROW</a>]; 	<label style="color:#c33">// Region, each row uses a binary string</label><br/>

<a href="http://open.xmeye.net/zh/#EventHandler">SDK\_EventHandler</a> hEvent</a>; 			<label style="color:#c33">// Dynamic detection linkage</label><br/>

}SDK\_MOTIONCONFIG;




<label style="color:#c33">/// Full channel dynamic detection configuration</label><br/>

typedef struct  SDK_MOTIONCONFIG_ALL<br/> 
{

<a href="http://open.xmeye.net/zh/#MOTIONCONFIG">SDK_MOTIONCONFIG</a> vMotionDetectAll[<a href="http://open.xmeye.net/zh/#EventHandler">NET_MAX_CHANNUM</a>];

}SDK_MOTIONCONFIG_ALL;

<label style="color:#c33">///< Occlusion detection configuration</label><br/>

typedef struct  SDK_BLINDDETECTCONFIG<br/> 
{

bool	bEnable;	<label style="color:#c33">///< Occlusion detection open</label><br/>

int		iLevel;<label style="color:#c33">	///< sensitivity：1?6</label><br/>

<a href="http://open.xmeye.net/zh/#EventHandler">SDK_EventHandler</a> hEvent;	<label style="color:#c33">///< Occlusion detection linkage</label><br/>

}SDK_BLINDDETECTCONFIG;




<label style="color:#c33">/// Full channel occlusion detection configuration</label><br/>

typedef struct  SDK_BLINDDETECTCONFIG_ALL<br/> 
{
<a href="http://open.xmeye.net/zh/#BLINDDETECTCONFIG">SDK\_BLINDDETECTCONFIG</a> vBlindDetectAll[<a href="http://open.xmeye.net/zh/#MAX_CHANNUM">NET\_MAX\_CHANNUM</a>];

}SDK_BLINDDETECTCONFIG_ALL;

<label style="color:#c33">///< Basic event structure video loss</label><br/>

typedef struct SDK_VIDEOLOSSCONFIG<br/> 
{

bool bEnable;		<label style="color:#c33">///< Enable</label><br/>

<a href="http://open.xmeye.net/zh/#EventHandler">SDK\_EventHandler</a> hEvent;	<label style="color:#c33">///< Handle parameter</label><br/>

}SDK\_VIDEOLOSSCONFIG;




<label style="color:#c33">/// The basic time structure of all channels</label><br/>

typedef struct SDK_VIDEOLOSSCONFIG_ALL<br/> 
{

<a href="http://open.xmeye.net/zh/#VIDEOLOSSCONFIG">SDK\_VIDEOLOSSCONFIG</a> vGenericEventConfig[<a href="http://open.xmeye.net/zh/#MAX_CHANNUM">NET\_MAX\_CHANNUM</a>];

}SDK\_VIDEOLOSSCONFIG_ALL;


<label style="color:#c33">///< Alarm input configuration</label><br/>

typedef struct  SDK_ALARM_INPUTCONFIG<br/> 
{

bool	bEnable;		<label style="color:#c33">///< Alarm input switch</label><br/>

int		iSensorType;	<label style="color:#c33">///< Sensor type normally open, or normally closed</label><br/>

<a href="http://open.xmeye.net/zh/#EventHandler">SDK\_EventHandler</a> hEvent;	    <label style="color:#c33">///< action with alarm</label><br/>

}SDK\_ALARM\_INPUTCONFIG;




<label style="color:#c33">///< All channel alarm inputs are configured</label><br/>

typedef struct  SDK_ALARM_INPUTCONFIG_ALL<br/> 
{

   <a href="http://open.xmeye.net/zh/#ALARM_INPUTCONFIG"> SDK\_ALARM\_INPUTCONFIG</a> vAlarmConfigAll[<a href="http://open.xmeye.net/zh/#MAX_CHANNUM">NET\_MAX\_CHANNUM</a>];

}SDK\_ALARM\_INPUTCONFIG_ALL;

<label style="color:#c33">///< Network alarm</label><br/>

typedef struct  SDK_NETALARMCONFIG<br/> 
{

bool bEnable;		<label style="color:#c33">///< Enable</label><br/>

<a href="http://open.xmeye.net/zh/#EventHandler">SDK\_EventHandler</a> hEvent;	<label style="color:#c33">///< Handle parament</label><br/>

}SDK\_NETALARMCONFIG;




<label style="color:#c33">/// Network alarm structure for all channels</label><br/>

typedef struct  SDK\_NETALARMCONFIG\_ALL<br/> 
{

<a href="http://open.xmeye.net/zh/#NETALARMCONFIG">SDK\_NETALARMCONFIG</a> vNetAlarmConfig[<a href="http://open.xmeye.net/zh/#MAX_CHANNUM">NET\_MAX\_CHANNUM</a>];

}SDK\_NETALARMCONFIG\_ALL;




<label style="color:#c33">///< Local alarm output configuration</label><br/>

typedef struct  SDK\_AlarmOutConfig<br/> 
{

int nAlarmOutType;	<label style="color:#c33">///< Alarm output type: configuration, manual, closed</label><br/>

int nAlarmOutStatus;    <label style="color:#c33">///< Alarm status: 0: opens 1; closes</label><br/>

}SDK\_AlarmOutConfig;

<label style="color:#c33">///< Alarm output configuration for all channels</label><br/>

typedef struct  SDK_AlarmOutConfigAll<br/> 
{

<a href="http://open.xmeye.net/zh/#AlarmOutConfig">SDK\_AlarmOutConfig</a> vAlarmOutConfigAll[<a href="http://open.xmeye.net/zh/#MAX\CHANNUM">NET\_MAX\_CHANNUM</a>];

}SDK\_AlarmOutConfigAll;

<label style="color:#c33">/// Set the V2 version of all channel decoder addresses</label><br/>

typedef struct  SDK\_AbilitySerialNo<br/> 
{

char serialNo[<a href="http://open.xmeye.net/zh/#MAX_SERIALNO_LENGTH">NET\_MAX\_SERIALNO\_LENGTH</a>];

char productType[<a href="http://open.xmeye.net/zh/#MAX_SERIALNO_LENGTH">NET\_MAX\_SERIALNO\_LENGTH</a>];

}SDK\_AbilitySerialNo;




<label style="color:#c33">///< Drive information structure</label><br/>

typedef struct  SDK\_DriverInformation<br/> 
{

int		iDriverType;		<label style="color:#c33">///< Drive type</label><br/>

bool	    bIsCurrent;		<label style="color:#c33">///< Is the current working disk?</label><br/>

unsigned int	uiTotalSpace;		<label style="color:#c33">///< Total capacity, MB is unit</label><br/>

unsigned int	uiRemainSpace;		<label style="color:#c33">///< remainder capacity，MB is unit</label><br/>

int		iStatus;		<label style="color:#c33">///< Error flag, file system initialization is set</label><br/>

int		iLogicSerialNo;	    <label style="color:#c33">///< Logical serial number</label><br/>

<a href="http://open.xmeye.net/zh/#SYSTEM">SDK\_SYSTEM\_TIME</a>  tmStartTimeNew;	    <label style="color:#c33">///< The start time of the new video time</label><br/>

<a href="http://open.xmeye.net/zh/#SYSTEM_TIME">SDK\_SYSTEM\_TIME</a>  tmEndTimeNew;		<label style="color:#c33">///< The end of the new video time period</label><br/>

<a href="http://open.xmeye.net/zh/#SYSTEM_TIME">SDK\_SYSTEM\_TIME</a>  tmStartTimeOld;	   <label style="color:#c33"> ///< The start time of the old video recording time</label><br/>

<a href="http://open.xmeye.net/zh/#SYSTEM_TIME">SDK\_SYSTEM\_TIME</a>  tmEndTimeOld;		<label style="color:#c33">///< The end time of the old video recording time</label><br/>

char		fsType[<a href="http://open.xmeye.net/zh/#FSLEN">NET\_FSLEN</a>];	<label style="color:#c33">///<file type</label><br/>

}SDK\_DriverInformation;

<label style="color:#c33">/// Video mode categories</label><br/>

enum  SDK\_RecordModeTypes<br/> 
{

SDK_RECORD_MODE_CLOSED,		<label style="color:#c33">///< Close video</label><br/>

SDK_RECORD_MODE_MANUAL,		<label style="color:#c33">///< Manual video recording</label><br/>

SDK_RECORD_MODE_CONFIG,		<label style="color:#c33">///< Video by configuration</label><br/>

SDK_RECORD_MODE_NR,

};

<label style="color:#c33">///< Video settings</label><br/>

typedef struct  SDK\_RECORDCONFIG<br/> 
{

int iPreRecord;			        <label style="color:#c33">///< The record time is zero to indicate closing</label><br/>

bool bRedundancy;			       <label style="color:#c33"> ///< Redundancy switch</label><br/>

 <label style="color:#c33">//bool bSnapShot;			       ///< Snapshot switch</label><br/>

int iPacketLength;		        <label style="color:#c33">///< Video package length (minutes)[1, 255]</label><br/>

int iRecordMode;				    <label style="color:#c33">///< Video mode, 0 off, 1 forbidden, 2 configuration</label><br/>

<a href="http://open.xmeye.net/zh/#CONFIG_WORKSHEET">SDK\_CONFIG\_WORKSHEET</a> wcWorkSheet;		<label style="color:#c33">///< Video recording time</label><br/>

unsigned int typeMask [<a href="http://open.xmeye.net/zh/#N_WEEKS">NET\_N\_WEEKS</a>][<a href="http://open.xmeye.net/zh/#N_TSECT">NET\_N\_TSECT</a>];	<label style="color:#c33">///< Video type mask</label><br/>

}SDK_RECORDCONFIG;

<label style="color:#c33">//Video settings structure</label><br/>

typedef struct  SDK_RECORDCONFIG_ALL<br/> 
{

<a href="http://open.xmeye.net/zh/#RECORDCONFIG">SDK\_RECORDCONFIG</a> vRecordConfigAll[<a href="http://open.xmeye.net/zh/#MAX_CHANNUM">NET\_MAX\_CHANNUM</a>];

}SDK_RECORDCONFIG_ALL;

<label style="color:#c33">///< Picture settings</label><br/>

typedef struct  SDK_SnapshotConfig<br/> 
{

int iPreSnap;			        <label style="color:#c33">///< Number of scratch pictures</label><br/>

bool bRedundancy;					<label style="color:#c33">///< Redundancy switch</label><br/>

int iSnapMode;					<label style="color:#c33">///< Video mode，see<a href="http://open.xmeye.net/zh/#RecordModeTypes">RecordModeTypes</a></label><br/>

<a href="http://open.xmeye.net/zh/#CONFIG_WORKSHEET">SDK\_CONFIG\_WORKSHEET</a> wcWorkSheet;			<label style="color:#c33">///< Video recording time</label><br/>

unsigned int typeMask[<a href="http://open.xmeye.net/zh/#N_WEEKS">NET\_N\_WEEKS</a>][<a href="http://open.xmeye.net/zh/#N_TSECT">NET\_N\_TSECT</a>];	<label style="color:#c33">///< Video type mask，见enum <a href="http://open.xmeye.net/zh/#RecordTypes">RecordTypes</a></label><br/>

}SDK_SnapshotConfig;


typedef struct  SDK\_SnapshotConfigAll<br/> 
{

<a href="http://open.xmeye.net/zh/#SnapshotConfig">SDK\_SnapshotConfig</a> vSnapshotConfigAll[<a href="http://open.xmeye.net/zh/#MAX_CHANNUM">NET\_MAX\_CHANNUM</a>];

}SDK_SnapshotConfigAll;

<label style="color:#c33">//General configuration page structure</label><br/>

typedef struct\_SDK\_CONFIG\_NORMAL<br/> 
{

<a href="http://open.xmeye.net/zh/#SYSTEM_TIME">SDK\_SYSTEM\_TIME</a> sysTime;	<label style="color:#c33">//system time</label><br/>


int  iLocalNo;			<label style="color:#c33">///< Local number:[0, 998] */</label><br/>

int  iOverWrite;		<label style="color:#c33">///< Full time processing of hard disk "OverWrite（iOverWrite=1）", "StopRecord（iOverWrite=0）" */	</label><br/>	

char cIranCalendarEnable;	<label style="color:#c33">///< Whether to enable the Iran calendar, 1 means to enable, and 0 means not enabled</label><br/>

char cFontSize;			<label style="color:#c33">///< Vector font size</label><br/>

char reserved[2];

char sMachineName[64];		<label style="color:#c33">///< machine name</label><br/>

int  iVideoStartOutPut;	<label style="color:#c33">///< Output mode */</label><br/>

int  iAutoLogout;		<label style="color:#c33">///<Local menu auto logout (min)	[0, 120]</label><br/>




int  iVideoFormat;		<label style="color:#c33">///< Video standard:“PAL”:0, “NTSC”:1, “SECAM” */</label><br/>

int  iLanguage;		<label style="color:#c33">///< Language choice:“English”, “SimpChinese”, “TradChinese”, “Italian”, “Spanish”, “Japanese”, “Russian”, “French”, “German” */	</label><br/>

int  iDateFormat;		<label style="color:#c33">///< Date format:“YYMMDD”, “MMDDYY”, “DDMMYY” */</label><br/>

int  iDateSeparator;		<label style="color:#c33">///< Date separator:“.”, “-”, “/” */</label><br/>

int  iTimeFormat;		<label style="color:#c33">///< Time format:“12”, “24” */</label><br/>

int  iDSTRule;			<label style="color:#c33">///< Daylight saving time rule </label><br/>

int  iWorkDay;			<label style="color:#c33">///< Working day</label><br/>

<a href="http://open.xmeye.net/zh/#DSTPoint">DSTPoint</a> dDSTStart;

<a href="http://open.xmeye.net/zh/#DSTPoint">DSTPoint</a> dDSTEnd;

}SDK\_CONFIG\_NORMAL;

<label style="color:#c33">//The following encoding configurations are relevant</label><br/>

<label style="color:#c33">// Code settings</label><br/>

typedef struct  SDK\_CONFIG\_ENCODE
{

<a href="http://open.xmeye.net/zh/#MEDIA_FORMAT">SDK\_MEDIA\_FORMAT</a> dstMainFmt[<a href="http://open.xmeye.net/zh/#ENCODE_TYPE_NUM">SDK\_ENCODE\_TYPE\_NUM</a>];	<label style="color:#c33">//  Primary bitstream format </label><br/>	
 
 <a href="http://open.xmeye.net/zh/#MEDIA_FORMAT">SDK\_MEDIA\_FORMAT</a> dstExtraFmt[<a href="http://open.xmeye.net/zh/#EXTRATYPES">SDK\_EXTRATYPES</a>];		<label style="color:#c33">// Sub stream format </label><br/>

 <a href="http://open.xmeye.net/zh/#MEDIA_FORMAT">SDK\_MEDIA\_FORMAT</a> dstSnapFmt[<a href="http://open.xmeye.net/zh/#ENCODE_TYPE_NUM">SDK\_ENCODE\_TYPE\_NUM</a>];	<label style="color:#c33">//  Capture format </label><br/>

}SDK\_CONFIG\_ENCODE;

typedef struct  SDK\_EncodeConfigAll<br/> 
{

<a href="http://open.xmeye.net/zh/#CONFIG_ENCODE">SDK\_CONFIG\_ENCODE</a> vEncodeConfigAll[<a href="http://open.xmeye.net/zh/#MAX_CHANNUM">NET\_MAX\_CHANNUM</a>];

}SDK\_EncodeConfigAll;




<label style="color:#c33">// Simplified version code configuration</label><br/>

<label style="color:#c33">/// Media format</label><br/>

typedef struct  SDK\_MEDIA\_FORMAT\_SIMPLIIFY<br/> 
{

<a href="http://open.xmeye.net/zh/#VIDEO_FORMAT">SDK\_VIDEO\_FORMAT</a> vfFormat;		<label style="color:#c33">//  Video format definition </label><br/>			

bool	bVideoEnable;			<label style="color:#c33">//  Open video encoding </label><br/>

bool	bAudioEnable;			<label style="color:#c33">//  Open audio encoding </label><br/>	

}SDK\_MEDIA\_FORMAT\_SIMPLIIFY;




<label style="color:#c33">/// Code settings</label><br/>

typedef struct  SDK\_CONFIG\_ENCODE\_SIMPLIIFY<br/> 
{

<a href="http://open.xmeye.net/zh/#MEDIA_FORMAT">SDK\_MEDIA\_FORMAT</a> dstMainFmt;	<label style="color:#c33">//  Primary bitstream format </label><br/>	

<a href="http://open.xmeye.net/zh/#MEDIA_FORMAT">SDK\_MEDIA\_FORMAT</a> dstExtraFmt;	<label style="color:#c33">//  Sub stream format </label><br/>

}SDK\_CONFIG\_ENCODE\_SIMPLIIFY;




<label style="color:#c33">/// Full channel coded configuration</label><br/>

typedef struct SDK\_EncodeConfigAll\_SIMPLIIFY<br/> 
{

<a href="http://open.xmeye.net/zh/#CONFIG_ENCODE_SIMPLIIFY">SDK\_CONFIG\_ENCODE\_SIMPLIIFY</a> vEncodeConfigAll[NET\_MAX\_CHANNUM];

}SDK\_EncodeConfigAll\_SIMPLIIFY;


typedef struct  SDK\_CombineEncodeConfigAll<br/> 
{

<a href="http://open.xmeye.net/zh/#CONFIG_ENCODE">SDK\_CONFIG\_ENCODE</a> vEncodeConfigAll[NET\_MAX\_COMBINE\_NUM];

}SDK_CombineEncodeConfigAll;




<label style="color:#c33">/// Combinatorial encoding model</label><br/>

typedef struct  SDK\_CombEncodeParam<br/> 
{

int iEncodeMode;	//see <a href="http://open.xmeye.net/zh/#CombineEncodeMode">CombineEncodeMode</a>

}SDK\_CombEncodeParam;




typedef struct  SDK\_CombEncodeModeAll<br/> 
{

<a href="http://open.xmeye.net/zh/#CombEncodeParam">SDK\_CombEncodeParam</a> vEncodeParam[NET\_MAX\_COMBINE\_NUM];

}SDK\_CombEncodeModeAll;




<label style="color:#c33">//!Video object structure</label><br/>

typedef struct   SDK\_VIDEO\_WIDGET<br/> 
{

unsigned int rgbaFrontground;	<label style="color:#c33">///< The foreground, MakeRGB, and transparency of the object	</label><br/>

unsigned int rgbaBackground;	<label style="color:#c33">///< The background of the MakeRGB object, and transparency	</label><br/>

<a href="http://open.xmeye.net/zh/#sdkRect">sdkRect</a>	rcRelativePos;		<label style="color:#c33">///< Object margin to full length ratio*8191</label><br/>

bool	bPreviewBlend;		<label style="color:#c33">///< Preview overlay whether or not to show 1: Show 0: hide</label><br/>

bool	bEncodeBlend;		<label style="color:#c33">///< Code superposition</label><br/>

}SDK\_VIDEO\_WIDGET;




<label style="color:#c33">//!Video object settings</label><br/>

typedef struct  SDK\_CONFIG\_VIDEOWIDGET<br/> 
{

<a href="http://open.xmeye.net/zh/#VIDEO_WIDGET">SDK\_VIDEO\_WIDGET</a>	dstCovers[<a href="http://open.xmeye.net/zh/#EventHandler">NET\_COVERNUM</a>];

<a href="http://open.xmeye.net/zh/#VIDEO_WIDGET">SDK\_VIDEO\_WIDGET</a>	ChannelTitle;       <label style="color:#c33">//Channel name</label><br/>

<a href="http://open.xmeye.net/zh/#VIDEO_WIDGET">SDK\_VIDEO\_WIDGET</a>	TimeTitle;	     <label style="color:#c33">//Equipment time</label><br/>

struct <br/> 
{

char strName[<a href="http://open.xmeye.net/zh/#NAME_PASSWORD_LEN">NET\_NAME\_PASSWORD\_LEN</a>];

__int64 iSerialNo;	

}ChannelName;			    <label style="color:#c33">///< Channel name</label><br/>

int		iCoverNum;		<label style="color:#c33">///< Currently, the channel has several superimposed areas */</label><br/>

}SDK\_CONFIG\_VIDEOWIDGET;




<label style="color:#c33">/// Video object (output mode dialog box)</label><br/>

typedef struct  SDK\_VideoWidgetConfigAll<br/> 
{

<a href="http://open.xmeye.net/zh/#CONFIG_VIDEOWIDGET">SDK\_CONFIG\_VIDEOWIDGET</a> vVideoWidegetConfigAll[<a href="http://open.xmeye.net/zh/#MAX_CHANNUM">NET\_MAX\_CHANNUM</a>];

}SDK\_VideoWidgetConfigAll;

<label style="color:#c33">//Video color</label><br/>

typedef struct   SDK\_VIDEOCOLOR\_PARAM<br/> 
{

int	nBrightness;		<label style="color:#c33">///< brightness	0-100</label><br/>

int	nContrast;		<label style="color:#c33">///< contrast ratio	0-100</label><br/>

int	nSaturation;		<label style="color:#c33">///< saturation	0-100</label><br/>

int	nHue;			<label style="color:#c33">///< chroma	0-100</label><br/>

int	mGain;			<label style="color:#c33">///< gain	0-100 The seventh position 1 represents an automatic gain</label><br/>		

int	mWhitebalance;		<label style="color:#c33">///< Automatic white level control, bit7 setting means open automatic control,.0x0,0x1,0x2 represents low, middle and high level respectively</label><br/>

int nAcutance;           <label style="color:#c33"> ///< Sharpness   0-15</label><br/>

}SDK\_VIDEOCOLOR\_PARAM;

<label style="color:#c33">///< Video color settings</label><br/>

typedef struct SDK\_VIDEOCOLOR<br/> 
{

<a href="http://open.xmeye.net/zh/#TIMESECTION">SDK\_TIMESECTION</a>		tsTimeSection;		<label style="color:#c33">/// Time segment</label><br/>

<a href="http://open.xmeye.net/zh/#VIDEOCOLOR_PARAM">SDK\_VIDEOCOLOR\_PARAM</a>	dstColor;		<label style="color:#c33">/// Color definition</label><br/>

int	iEnable;

}SDK\_VIDEOCOLOR;




typedef struct  SDK\_CONFIG\_VIDEOCOLOR<br/> 
{

<a href="http://open.xmeye.net/zh/#VIDEOCOLOR">SDK\_VIDEOCOLOR</a> dstVideoColor[<a href="http://open.xmeye.net/zh/#NET_N_MIN_TSECT">NET\_N\_MIN\_TSECT</a>];

}SDK\_CONFIG\_VIDEOCOLOR;




typedef struct  SDK\_VideoColorConfigAll<br/> 
{

<a href="http://open.xmeye.net/zh/#CONFIG_VIDEOCOLOR">SDK\_CONFIG\_VIDEOCOLOR</a> vVideoColorAll[<a href="http://open.xmeye.net/zh/#NET_MAX_CHANNUM">NET\_MAX\_CHANNUM</a>];

}SDK\_VideoColorConfigAll;

<label style="color:#c33">/// All channel name headers</label><br/>

typedef struct SDK\_ChannelNameConfigAll<br/> 
{

char channelTitle[<a href="http://open.xmeye.net/zh/#NET_MAX_CHANNUM">NET\_MAX\_CHANNUM</a>][<a href="http://open.xmeye.net/zh/#NET_NAME_PASSWORD_LEN">NET\_NAME\_PASSWORD\_LEN</a>];

}SDK\_ChannelNameConfigAll;

<label style="color:#c33">///Output mode</label><br/>

typedef struct  SDK\_GUISetConfig<br/> 
{

int iWindowAlpha;		<label style="color:#c33">///< Window transparency	[128, 255]</label><br/>

bool bTimeTitleEn;		<label style="color:#c33">///< Time title display enable</label><br/>

bool bChannelTitleEn;		<label style="color:#c33">///< Channel title display enable	</label><br/>

bool bAlarmStatus;		<label style="color:#c33">///< Alarm status</label><br/>

bool bRecordStatus;		<label style="color:#c33">///< Video status display enable</label><br/>

bool bChanStateRecEn;		<label style="color:#c33">///< Video mark display enable</label><br/>

bool bChanStateVlsEn;		<label style="color:#c33">///< Video loss flag display enable</label><br/>

bool bChanStateLckEn;		<label style="color:#c33">///< Channel lock flag display enable</label><br/>	

bool bChanStateMtdEn;		<label style="color:#c33">///< Dynamic detection flag display enable</label><br/>

bool bBitRateEn;		<label style="color:#c33">///< Bitstream display enable</label><br/>

bool bRemoteEnable;	<label style="color:#c33">///< Remote control enable</label><br/>

bool bDeflick;			<label style="color:#c33">///< anti-Shake</label><br/>

}SDK\_GUISetConfig;

<label style="color:#c33">////!Common network settings</label><br/>

typedef struct SDK\_CONFIG\_NET\_COMMON<br/> 
{

<label style="color:#c33">//!main engine name</label><br/>

char HostName[<a href="http://open.xmeye.net/zh/#NET_NAME_PASSWORD_LEN">NET\_NAME\_PASSWORD\_LEN</a>]; <br/>

<label style="color:#c33">//!main engine IP</label><br/>

<a href="http://open.xmeye.net/zh/#CONFIG_IPAddress">CONFIG\_IPAddress</a> HostIP; <br/>

<label style="color:#c33">//!Subnet mask</label><br/>

<a href="http://open.xmeye.net/zh/#CONFIG_IPAddress">CONFIG\_IPAddress</a> Submask; <br/>

<label style="color:#c33">//!Gateway IP</label><br/>

<a href="http://open.xmeye.net/zh/#CONFIG_IPAddress">CONFIG\_IPAddress</a> Gateway; <br/>

<label style="color:#c33">//!HTTP service port</label><br/>

int HttpPort;   <br/> 

<label style="color:#c33">//!TCP listening port</label><br/>

int TCPPort;	 <br/> 

<label style="color:#c33">//!SSL listening port</label><br/>

int SSLPort; <br/>

<label style="color:#c33">//!UDP listening port</label><br/>

int UDPPort; <br/>

<label style="color:#c33">//!maximum connection </label><br/> 

int MaxConn; <br/>

<label style="color:#c33">//!Monitoring protocol {"TCP","UDP","MCAST",…}</label>

int MonMode; <br/>

<label style="color:#c33">//!Limited bitstream value</label><br/>

int MaxBps;  <br/>

<label style="color:#c33">//!Transmission strategy</label><br/>

//char TransferPlan[<a href="http://open.xmeye.net/zh/#NET_NAME_PASSWORD_LEN">NET\_NAME\_PASSWORD\_LEN</a>]; <br/>

int TransferPlan; <br/>

<label style="color:#c33">//!Do you want to enable high-speed video download?</label><br/>

bool bUseHSDownLoad; <br/>

<label style="color:#c33">//!MAC address</label><br/>

char sMac[<a href="http://open.xmeye.net/zh/#NET_MAX_MAC_LEN">NET\_MAX\_MAC\_LEN</a>]; <br/>

}SDK\_CONFIG\_NET\_COMMON;




typedef enum SDK\_DevType<br/> 
{

SDK\_DEV\_TYPE\_IPC,

SDK\_DEV\_TYPE\_DVR,

SDK\_DEV\_TYPE\_HVR,

SDK\_DEV\_TYPE\_POEIPC,

SDK\_DEV\_TYPE\_NVR,

SDK\_DEV\_TYPE\_RTSPIPC,

SDK\_DEV\_TYPE\_NR

 }SDK\_DevType;

<label style="color:#c33">////!Common network settings</label><br/>

typedef struct SDK\_CONFIG\_NET\_COMMON\_V2<br/> 
{

<label style="color:#c33">//!host name</label><br/>

char HostName[NET\_NAME\_PASSWORD\_LEN];

<label style="color:#c33">//!Host IPv</label><br/>

CONFIG_IPAddress HostIP;

<label style="color:#c33">//!Subnet mask</label><br/>

CONFIG_IPAddress Submask;

<label style="color:#c33">//!Gateway IP</label><br/>

CONFIG_IPAddress Gateway;

char pLocalLinkAddr[32];	<label style="color:#c33">//Local link address</label><br/>

char pAddr[64];			<label style="color:#c33">//IPv6 address</label><br/>

char pGateway[64];

<label style="color:#c33">//!HTTP service port</label><br/>

int HttpPort;

<label style="color:#c33">//!TCP listening port</label><br/>

int TCPPort;	

<label style="color:#c33">//!SSL listening port</label><br/>

int SSLPort;

<label style="color:#c33">//!UDP listening port</label><br/>

int UDPPort;

<label style="color:#c33">//!maximum connection</label><br/>

int MaxConn;

<label style="color:#c33">//!Monitoring protocol {"TCP","UDP","MCAST",…}</label><br/>

int MonMode;

<label style="color:#c33">//!Limited bitstream value</label><br/>

int MaxBps;

<label style="color:#c33">//!Transmission strategy

//char TransferPlan[<a href="http://open.xmeye.net/zh/#NET_NAME_PASSWORD_LEN">NET\_NAME\_PASSWORD\_LEN</a>];</label><br/>

int  TransferPlan;				<label style="color:#c33">///Transmission strategy</label><br/>

bool bUseHSDownLoad;				<label style="color:#c33">///Whether to enable high-speed video download?</label><br/>

char sMac[<a href="http://open.xmeye.net/zh/#NET_MAX_MAC_LEN">NET\_MAX\_MAC\_LEN</a>];			<label style="color:#c33">///MAC address</label><br/>

char sSn[<a href="http://open.xmeye.net/zh/#NET_MAX_MAC_LEN">NET\_MAX\_MAC\_LEN</a>]; 	      <label style="color:#c33">  ///Serial number (used in the search for equipment Dahua and save changes required for IP data)</label><br/>

 #ifndef WIN32

int  DeviceType;   				<label style="color:#c33">///Device type: is mobile phone a socket or an ordinary device?</label><br/>

 #endif

int ChannelNum;			        <label style="color:#c33">///Channel number</label><br/>

int	Device_Type;		        <label style="color:#c33">///Device type，see enum <a href="http://open.xmeye.net/zh/#DevType">SDK\_DevType</a></label><br/>

 #ifdef OME

char Version[<a href="http://open.xmeye.net/zh/#NET_MAX_INFO_LEN">NET\_MAX\_INFO\_LEN</a>];         <label style="color:#c33">  //Version information</label><br/>

<a href="http://open.xmeye.net/zh/#SYSTEM_TIME">SDK\_SYSTEM\_TIME</a> BuildDate;  			<label style="color:#c33">//Version date</label><br/>

 #endif

char OtherFunction[49];    <label style="color:#c33"> ///Used to save and modify the information required by other manufacturers IP </label><br/>

char Resume[7];			<label style="color:#c33">///Retain</label><br/>


}SDK\_CONFIG\_NET\_COMMON\_V2;




<label style="color:#c33">////!Cross - segment setting IP required --</label><br/>

typedef struct SDK\_CONFIG\_NET\_COMMON\_V3<br/> 
{

char HostName[<a href="http://open.xmeye.net/zh/#NET_NAME_PASSWORD_LEN">NET\_NAME\_PASSWORD\_LEN</a>];	    <label style="color:#c33">///host name </label><br/>

<a href="http://open.xmeye.net/zh/#CONFIG_IPAddress">CONFIG\_IPAddress</a> HostIP;				<label style="color:#c33">///host IP</label><br/>

<a href="http://open.xmeye.net/zh/#CONFIG_IPAddress">CONFIG\_IPAddress</a> Submask;			<label style="color:#c33">///Subnet mask</label><br/>
<a href="http://open.xmeye.net/zh/#CONFIG_IPAddress">CONFIG\_IPAddress</a> Gateway;			<label style="color:#c33">///Gateway IP  </label><br/>

int  HttpPort;					<label style="color:#c33">///HTTP service port   </label><br/>

int  TCPPort;					<label style="color:#c33">///TCP listening port  </label><br/> 

int  SSLPort;					<label style="color:#c33">///SSL listening port</label><br/>

int  UDPPort;					<label style="color:#c33">///UDP listening port </label><br/> 

int  MaxConn;					<label style="color:#c33">///maximum connection</label><br/>

int  MonMode;					<label style="color:#c33">///Monitoring protocol {"TCP","UDP","MCAST",?}</label><br/>

int  MaxBps;					<label style="color:#c33">///Limited bitstream value</label><br/>

<label style="color:#c33">//char TransferPlan[NET\_NAME\_PASSWORD\_LEN]; </label><br/>

int  TransferPlan;				<label style="color:#c33">///Transmission strategy</label><br/>

bool bUseHSDownLoad; 			   <label style="color:#c33"> ///Whether to enable high-speed video download?</label><br/>

char sMac[NET_MAX_MAC_LEN];			<label style="color:#c33">///MAC address</label><br/>

char UserName[NET_NAME_PASSWORD_LEN];	    <label style="color:#c33">///Device username</label><br/>

char Password[NET_NAME_PASSWORD_LEN];	  <label style="color:#c33">  ///Device password</label><br/>

char LocalMac[NET_MAX_MAC_LEN]; <br/>

int  nPasswordType; <br/>

char Resume[92];				    <label style="color:#c33">///Retain</label><br/>

}SDK\_CONFIG\_NET\_COMMON\_V3;
<label style="color:#c33">//DHCP</label><br/>

 #define <a href="http://open.xmeye.net/zh/#EventHandler">SDK_MAX_ETH_NUM</a> 4

typedef struct SDK\_NetDHCPConfig<br/> 
{
bool bEnable;

char ifName[32];

}SDK\_NetDHCPConfig;

<label style="color:#c33">/// DHCP configuration of all network adapters</label><br/>

typedef struct SDK\_NetDHCPConfigAll<br/> 
{
<a href="http://open.xmeye.net/zh/#NetDHCPConfig">SDK\_NetDHCPConfig</a> vNetDHCPConfig[<a href="http://open.xmeye.net/zh/#MAX_ETH_NUM">SDK\_MAX\_ETH\_NUM</a>];

}SDK_NetDHCPConfigAll;


<label style="color:#c33">///< DNS settings</label><br/>

typedef struct SDK\_NetDNSConfig<br/> 
{
<a href="http://open.xmeye.net/zh/#CONFIG_IPAddress">CONFIG\_IPAddress</a>	PrimaryDNS;

<a href="http://open.xmeye.net/zh/#CONFIG_IPAddress">CONFIG\_IPAddress</a>	SecondaryDNS;

}SDK\_NetDNSConfig;

<label style="color:#c33">///< Server structure definition</label><br/>

typedef struct SDK\_RemoteServerConfig<br/> 
{
char ServerName[<a href="http://open.xmeye.net/zh/#NET_NAME_PASSWORD_LEN">NET\_NAME\_PASSWORD\_LEN</a>];		<label style="color:#c33">///< service name</label><br/>

<a href="http://open.xmeye.net/zh/#CONFIG_IPAddress">CONFIG\_IPAddress</a> ip;				<label style="color:#c33">///< IP address</label><br/>

int Port;						<label style="color:#c33">///< Port number</label><br/>

char UserName[<a href="http://open.xmeye.net/zh/#NET_NAME_PASSWORD_LEN">NET\_NAME\_PASSWORD\_LEN</a>];		<label style="color:#c33">///< Ursename</label><br/>

char Password[<a href="http://open.xmeye.net/zh/#NET_NAME_PASSWORD_LEN">NET\_NAME\_PASSWORD\_LEN</a>];	<label style="color:#c33">	///< password</label><br/>

bool Anonymity;					<label style="color:#c33">///< Anonymous login?</label><br/>

}SDK\_RemoteServerConfig;

<label style="color:#c33">///< IP permissions settings</label><br/>

typedef struct SDK\_NetIPFilterConfig<br/> 
{
bool Enable;					<label style="color:#c33">///< Whether to open</label><br/>

<a href="http://open.xmeye.net/zh/#CONFIG_IPAddress">CONFIG_IPAddress</a> BannedList[<a href="http://open.xmeye.net/zh/#NET_MAX_FILTERIP_NUM">NET_MAX_FILTERIP_NUM</a>];<label style="color:#c33">///< Blacklist list</label><br/>

<a href="http://open.xmeye.net/zh/#CONFIG_IPAddress">CONFIG_IPAddress</a> TrustList[<a href="http://open.xmeye.net/zh/#NET_MAX_FILTERIP_NUM">NET_MAX_FILTERIP_NUM</a>];	<label style="color:#c33">///< List of white lists</label><br/>

}SDK\_NetIPFilterConfig;


<label style="color:#c33">///< Multicast settings</label><br/>

typedef struct SDK\_NetMultiCastConfig<br/> 
{
bool Enable;				<label style="color:#c33">///< Whether to open</label><br/>

<a href="http://open.xmeye.net/zh/#RemoteServerConfig">SDK\_RemoteServerConfig</a> Server;		<label style="color:#c33">///< Multicast server</label><br/>

}SDK\_NetMultiCastConfig;


<label style="color:#c33">///< PPPoE settings</label><br/>

typedef struct SDK_NetPPPoEConfig<br/> 
{
bool Enable;				<label style="color:#c33">///< Whether to open</label><br/>

<a href="http://open.xmeye.net/zh/#RemoteServerConfig">SDK\_RemoteServerConfig</a> Server;		<label style="color:#c33">///< PPPOE server</label><br/>

<a href="http://open.xmeye.net/zh/#CONFIG_IPAddress">CONFIG\_IPAddress</a> addr;			<label style="color:#c33">///< The IP address obtained after dialing</label><br/>

}SDK\_NetPPPoEConfig;

<label style="color:#c33">///< DDNS设置</label><br/>

typedef struct SDK\_NetDDNSConfig<br/> 
{

bool Enable;				<label style="color:#c33">///< Whether to open </label><br/>

bool Online;				<label style="color:#c33">///< Is it online?</label><br/>

char DDNSKey[<a href="http://open.xmeye.net/zh/#NET_NAME_PASSWORD_LEN">NET\_NAME\_PASSWORD\_LEN</a>];	<label style="color:#c33">///< DDNS type name, currently available: JUFENG</label><br/>

char HostName[<a href="http://open.xmeye.net/zh/#NET_NAME_PASSWORD_LEN">NET\_NAME\_PASSWORD\_LEN</a>];	<label style="color:#c33">///< Host name</label><br/>

<a href="http://open.xmeye.net/zh/#RemoteServerConfig">SDK\_RemoteServerConfig</a> Server;		<label style="color:#c33">///< DDNS server</label><br/>

}SDK\_NetDDNSConfig;
<label style="color:#c33">///< DDNS settings</label><br/>

typedef struct SDK\_NetDDNSConfigALL<br/> 
{

<a href="http://open.xmeye.net/zh/#NetDDNSConfig">SDK\_NetDDNSConfig</a> ddnsConfig[<a href="http://open.xmeye.net/zh/#NET_MAX_DDNS_TYPE">NET\_MAX\_DDNS\_TYPE</a>];

}SDK\_NetDDNSConfigALL;

<label style="color:#c33">///< FTP settings</label><br/>

typedef struct SDK\_FtpServerConfig<br/> 
{

bool bEnable;        			<label style="color:#c33">///< Server enable</label><br/>

SDK_RemoteServerConfig Server;		<label style="color:#c33">///< FTP server</label><br/>

char cRemoteDir[<a href="http://open.xmeye.net/zh/#NET_MAX_PATH_LENGTH">NET\_MAX\_PATH\_LENGTH</a>];	<label style="color:#c33">///< Remote directory</label><br/>

int  iMaxFileLen;			<label style="color:#c33">///< Maximum file length</label><br/>

}SDK\_FtpServerConfig;

<label style="color:#c33">///< NTP settings</label><br/>

typedef struct SDK\_NetNTPConfig<br/> 
{

bool Enable;             <label style="color:#c33">///< Whether to open</label><br/>

<a href="http://open.xmeye.net/zh/#RemoteServerConfig">SDK\_RemoteServerConfig</a> Server;    <label style="color:#c33"> ///< PPPOE server</label><br/>

int  UpdatePeriod;          <label style="color:#c33">///< Update cycle</label><br/>

int  TimeZone;           <label style="color:#c33"> ///< time zone</label><br/>

}SDK\_NetNTPConfig;

 #define <a href="http://open.xmeye.net/zh/#NET_MAX_EMAIL_TITLE_LEN"> NET\_MAX\_EMAIL\_TITLE\_LEN</a> 64

 #define  <a href="http://open.xmeye.net/zh/#NET_MAX_EMAIL_RECIEVERS">NET\_MAX\_EMAIL\_RECIEVERS</a>  5

 #define  <a href="http://open.xmeye.net/zh/#NET_EMAIL_ADDR_LEN">NET\_EMAIL\_ADDR\_LEN</a>  64



<label style="color:#c33">///< EMAIL settings</label><br/>

typedef struct SDK\_NetEmailConfig<br/> 
{

<label style="color:#c33">///< whether to open</label><br/>

bool Enable;

<label style="color:#c33">///< The SMTP server address is filled in string</label><br/>

<label style="color:#c33">///< You can either fill in the IP or fill in the domain name</label><br/>

<a href="http://open.xmeye.net/zh/#RemoteServerConfig">SDK\_RemoteServerConfig</a> Server;

bool bUseSSL;

<label style="color:#c33">///< Send address</label><br/>

char SendAddr[<a href="http://open.xmeye.net/zh/#NET_EMAIL_ADDR_LEN">NET\_EMAIL\_ADDR\_LEN</a>];

<label style="color:#c33">///< The recipient address</label><br/>

char Recievers[<a href="http://open.xmeye.net/zh/#NET_MAX_EMAIL_RECIEVERS">NET\_MAX\_EMAIL\_RECIEVERS</a>][<a href="http://open.xmeye.net/zh/#NET_EMAIL_ADDR_LEN">NET\_EMAIL\_ADDR\_LEN</a>];

<label style="color:#c33">///< Mail topic</label><br/>

char Title[<a href="http://open.xmeye.net/zh/#NET_MAX_EMAIL_TITLE_LEN">NET\_MAX\_EMAIL\_TITLE\_LEN</a>];

<label style="color:#c33">///< Email effective time</label><br/>

<a href="http://open.xmeye.net/zh/#TIMESECTION">SDK\_TIMESECTION</a> Schedule[<a href="http://open.xmeye.net/zh/#NET_N_MIN_TSECT">NET\_N\_MIN\_TSECT</a>];

}SDK_NetEmailConfig;




<label style="color:#c33">///< ARSP (active registration server) settings</label><br/>

typedef struct SDK\_NetARSPConfig<br/> 
{

bool bEnable;				<label style="color:#c33">///< Whether to open</label><br/>

char sARSPKey[<a href="http://open.xmeye.net/zh/#NET_NAME_PASSWORD_LEN">NET\_NAME\_PASSWORD\_LEN</a>];	<label style="color:#c33">///< DNS type name</label><br/>

int  iInterval;				<label style="color:#c33">///< Retention interval</label><br/>

char sURL[<a href="http://open.xmeye.net/zh/#NET_NAME_PASSWORD_LEN">NET\_NAME\_PASSWORD\_LEN</a>];    	<label style="color:#c33">///< Native domain name</label><br/>

<a href="http://open.xmeye.net/zh/#RemoteServerConfig">SDK\_RemoteServerConfig</a> Server;		<label style="color:#c33">///< DDNS server</label><br/>

int  nHttpPort;                 <label style="color:#c33">///< Server HTTP port</label><br/>

}SDK\_NetARSPConfig;
typedef struct SDK\_NetARSPConfigAll<br/> 
{

<a href="http://open.xmeye.net/zh/#NetARSPConfig">SDK\_NetARSPConfig</a> vNetARSPConfigAll[<a href="http://open.xmeye.net/zh/#NET_MAX_ARSP_TYPE">NET\_MAX\_ARSP\_TYPE</a>];

}SDK\_NetARSPConfigAll;




<label style="color:#c33">///< Decoder address settings</label><br/>

typedef struct SDK\_NetDecoderConfig<br/> 
{

bool Enable;				<label style="color:#c33">///< whether to open</label><br/>

char UserName[<a href="http://open.xmeye.net/zh/#NET_NAME_PASSWORD_LEN">NET\_NAME\_PASSWORD\_LEN</a>];	<label style="color:#c33">///<DDNS type name, currently available: JUFENG</label><br/>

char PassWord[<a href="http://open.xmeye.net/zh/#NET_NAME_PASSWORD_LEN">NET\_NAME\_PASSWORD\_LEN</a>];	<label style="color:#c33">///< Host name</label><br/>

char Address[<a href="http://open.xmeye.net/zh/#NET_NAME_PASSWORD_LEN">NET\_NAME\_PASSWORD\_LEN</a>];  <br/>

int  Protocol;

int  Port;				<label style="color:#c33">///< Decoder port</label><br/>

int  Channel;				<label style="color:#c33">///< Decoder connection channel number</label><br/>

int  Interval;                  <label style="color:#c33">///< Interval between rounds(s)</label><br/>

}SDK\_NetDecoderConfig;

<label style="color:#c33">/// The decoder address settings for all channels</label><br/>

typedef struct SDK\_NetDecoderConfigAll<br/> 
{

<a href="http://open.xmeye.net/zh/#NetDecoderConfig"> SDK\_NetDecoderConfig</a> vNetDecoderConfig[<a href="http://open.xmeye.net/zh/#NET_MAX_DECORDR_CH">NET\_MAX\_DECORDR_CH</a>];

}SDK\_NetDecoderConfigAll;

<label style="color:#c33">/// The decoder address is set in V2 version</label><br/>

typedef struct SDK\_NetDecoderConfig_V2<br/> 
{

int nTotalNum;     <label style="color:#c33">//The number of valid arrays, the maximum is<a href="http://open.xmeye.net/zh/#NET_MAX_CHANNUM">NET\_MAX\_CHANNUM</a></label><br/>

<a href="http://open.xmeye.net/zh/#NetDecoderConfig">SDK\_NetDecoderConfig</a> vNetDecoderConfig[<a href="http://open.xmeye.net/zh/#NET_MAX_CHANNUM">NET\_MAX\_CHANNUM</a>];

}SDK\_NetDecoderConfig\_V2;




<label style="color:#c33">/// Set the V2 version of all channel decoder addresses</label><br/>

typedef struct SDK\_NetDecoderConfigAll\_V2<br/> 
{

<a href="http://open.xmeye.net/zh/#NetDecoderConfig_V2">SDK\_NetDecoderConfig\_V2</a> vNetDecoderArray[<a href="http://open.xmeye.net/zh/#NET_MAX_DECORDR_CH">NET\_MAX\_DECORDR\_CH</a>];

}SDK\_NetDecoderConfigAll\_V2;

<label style="color:#c33">/// Capture channel type</label><br/>

enum SDK\_CaptureChannelTypes <br/> 
{

SDK\_CAPTURE\_CHN\_MAIN = 0,		<label style="color:#c33">///< Main channel - main stream 1 </label><br/>

SDK\_CAPTURE\_CHN\_2END = 1,		<label style="color:#c33">///< Auxiliary channel - out stream 2</label><br/>

SDK\_CAPTURE\_CHN\_3IRD = 2,		<label style="color:#c33">///< Auxiliary channel - out stream 3 </label><br/>

SDK\_CAPTURE\_CHN\_4RTH = 3,		<label style="color:#c33">///<Auxiliary channel - out stream 4 </label><br/>

SDK\_CAPTURE\_CHN\_JPEG = 4,		<label style="color:#c33">///< The auxiliary channel - JPEG capture</label><br/>

SDK\_CAPTURE\_CHN\_NR,

};

<label style="color:#c33">///< Decoder address settings</label>

typedef struct SDK\_NetDecorderConfigV3<br/> 
{

bool Enable;				<label style="color:#c33">///< Whether to open</label><br/>

char UserName[<a href="http://open.xmeye.net/zh/#NET_NAME_URL_LEN">NET\_NAME\_PASSWORD\_LEN</a>];	<label style="color:#c33">///< DDNS type name, currently available: JUFENG</label><br/>

char PassWord[<a href="http://open.xmeye.net/zh/#NET_NAME_URL_LEN">NET\_NAME\_PASSWORD\_LEN</a>];	<label style="color:#c33">///< host name</label><br/>

char Address[<a href="http://open.xmeye.net/zh/#NET_NAME_URL_LEN">NET\_NAME\_URL\_LEN</a>]; <br/>

int  Protocol;			    <label style="color:#c33">///see enum <a href="http://open.xmeye.net/zh/#TransferProtocol_V2">SDK\_TransferProtocol_V2</a></label><br/>

int  Port;				<label style="color:#c33">///< Decoder port</label><br/>

int  Channel;				<label style="color:#c33">///< Decoder connection channel number</label><br/>

int  Interval;                 <label style="color:#c33"> ///< Round robin interval time (s), 0: means permanent</label><br/>

char ConfName[<a href="http://open.xmeye.net/zh/#NET_NAME_PASSWORD_LEN">NET\_NAME\_PASSWORD\_LEN</a>];	<label style="color:#c33">///<Configuration name</label><br/>

int  DevType;				<label style="color:#c33">///<Device type</label><br/>

int  StreamType;				<label style="color:#c33">///<Link bitstream type see enum <a href="http://open.xmeye.net/zh/#CaptureChannelTypes">SDK\_CaptureChannelTypes</a></label><br/>

}SDK\_NetDecorderConfigV3;


<label style="color:#c33">/*Decoder connection type*/</label><br/>

enum SDK\_DecorderConnType<br/> 
{

SDK\_CONN\_SINGLE = 0, 	<label style="color:#c33">/*Single connection*/</label><br/>

SDK\_CONN\_MULTI = 1,	<label style="color:#c33">/*Multiple connection wheel patrol*/</label><br/>

SDK\_CONN\_TYPE\_NR, <br/>

};




<label style="color:#c33">/*Digital channel configuration*/</label><br/>

typedef struct SDK\_NetDigitChnConfig<br/> 
{

bool Enable;			    <label style="color:#c33">/*Is the digital channel open?*/</label><br/>

int  ConnType;			   <label style="color:#c33"> /*line type，take the value <a href="http://open.xmeye.net/zh/#DecoderConnectType">DecoderConnectType</a>*/</label><br/>

int  TourIntv;			   <label style="color:#c33"> /*When a guard interval multiple connections*/</label><br/>

unsigned int SingleConnId;     <label style="color:#c33">   /*Connection configuration ID for single connection, starting at 1, and 0 indicating invalid*/</label><br/>

bool EnCheckTime;			  <label style="color:#c33">  /*Opening timing*/</label><br/>

<a href="http://open.xmeye.net/zh/#NetDecorderConfigV3">SDK\_NetDecorderConfigV3</a> NetDecorderConf[32];<label style="color:#c33"> /*Network device channel configuration table*/</label><br/>

int  nNetDeorde; 			  <label style="color:#c33">/* How many? */</label><br/>

bool EnSynchResolution;			  <label style="color:#c33">//The synchronous resolution enable switch, 0 means open, and 1 means closing</label><br/>

}SDK\_NetDigitChnConfig;




<label style="color:#c33">/*Configuration of all digital channels*/</label><br/>

typedef struct SDK\_NetDecorderConfigAll_V3<br/> 
{

<a href="http://open.xmeye.net/zh/#NetDigitChnConfig">SDK\_NetDigitChnConfig</a> DigitChnConf[<a href="http://open.xmeye.net/zh/#NET_MAX_DECORDR_CH">NET\_MAX\_DECORDR\_CH</a>];

}SDK\_NetDecorderConfigAll\_V3;




typedef struct SDK\_HVR\_CHNCAP<br/> 
{

int nD1Chn;			<label style="color:#c33">// Support the D1 way</label><br/>

int n960HChn;			<label style="color:#c33">// Support the 960H way</label><br/>

int n720PChn;			<label style="color:#c33">// Support the 720P way</label><br/>

int n1080PChn;			<label style="color:#c33">// Support the 1080P way</label><br/>

int nCIFChn;			<label style="color:#c33">//Support the CIF Channel number</label><br/>

int nHD1Chn;			<label style="color:#c33">//Support the HD1 Channel number</label><br/>

unsigned char nPlayChn; 	    <label style="color:#c33">//Support playback channels</label><br/>

unsigned char nDigiTalChn; 	<label style="color:#c33">//The maximum number of digital channel support</label><br/>

unsigned char n960PChn; 	   <label style="color:#c33"> //Number of supported 960P channels</label><br/>

unsigned char n3MChn; 		<label style="color:#c33">//Number of supported 3M channels</label><br/>

unsigned char n5MChn; 		<label style="color:#c33">//Number of supported 5M channels</label><br/>

unsigned char nWUXGAChn; 	   <label style="color:#c33"> //Number of supported WUXGA channels</label><br/>

unsigned char n1080NChn;	  <label style="color:#c33">  //Support 1080N channel number</label><br/>

unsigned char n4MChn;		<label style="color:#c33">//Support 4M channel number</label><br/>

//unsigned char nResChar[2];   <label style="color:#c33"> //redundancy</label><br/>

}SDK\_HVR\_CHNCAP, *SDK\_PHVR\_CHNCAP;




typedef struct SDK\_HVR\_CHNCAPV2<br/> 
{

unsigned char nD1Chn;		<label style="color:#c33">// Support the D1 way</label><br/>

unsigned char n960HChn;		<label style="color:#c33">// Support the 960H way</label><br/>

unsigned char n720PChn;		<label style="color:#c33">// Support the 720P way</label><br/>

unsigned char n1080PChn;	    <label style="color:#c33">// Support the 1080P way</label><br/>

unsigned char nCIFChn;		<label style="color:#c33">//Number of supported CIF channels</label><br/>

unsigned char nHD1Chn;		<label style="color:#c33">//Number of supported HD1 channels</label><br/>

unsigned char nPlayChn; 	  <label style="color:#c33">  //Support playback channels</label><br/>

unsigned char nDigiTalChn; 	<label style="color:#c33">//The maximum number of digital channel support</label><br/>

unsigned char n960PChn; 	   <label style="color:#c33"> //Number of supported 960P channels</label><br/>

unsigned char n3MChn; 		<label style="color:#c33">//Number of supported 3M channels</label><br/>

unsigned char n5MChn; 		<label style="color:#c33">//Number of supported 5M channels</label><br/>

unsigned char nWUXGAChn; 	    <label style="color:#c33">//Number of supported WUXGA channels</label><br/>

unsigned char n1080NChn;	   <label style="color:#c33"> //Support 1080N channel number</label><br/>

unsigned char n4MChn;		<label style="color:#c33">//Support 4M channel number</label><br/>

unsigned char n720NChn;		<label style="color:#c33">//Support 720N channel number</label><br/>

unsigned char nWSVGAChn;	<label style="color:#c33">//Support WSVGA (1024*576) channel number</label><br/>

unsigned char n4KChn;		<label style="color:#c33">//Number of supported 4K channels</label><br/>

unsigned char n3M_NChn;		<label style="color:#c33">//Number of supported 3M_N channels</label><br/>

unsigned char n4M_NChn;		<label style="color:#c33">//Number of supported 4M_N channels</label><br/>

unsigned char n5M_NChn;		<label style="color:#c33">//Number of supported 5M_N channels</label><br/>

unsigned char n4K_NChn;		<label style="color:#c33">//Number of supported 4k_N channels</label><br/>

unsigned char nRes[11]; <br/>

}SDK\_HVR\_CHNCAPV2, *SDK\_PHVR\_CHNCAPV2; <br/>




typedef struct SDK\_CAPTURE\_HVRCAP  	<label style="color:#c33">//Switch to CAPTURE\_HVRCAPV2 for compatibility with old reservations</label><br/>
{

<a href="http://open.xmeye.net/zh/#HVR_CHNCAP">SDK\_HVR\_CHNCAP</a> DigitalCap;	<label style="color:#c33">// Supported digital channel information</label><br/>

<a href="http://open.xmeye.net/zh/#HVR_CHNCAP">SDK\_HVR\_CHNCAP</a> AnalogCap;		<label style="color:#c33">// Analog channel information supported</label><br/>

}SDK\_CAPTURE\_HVRCAP, *SDK\_PCAPTURE\_HVRCAP; <br/>




typedef struct SDK\_CAPTURE\_HVRCAPV2<br/> 
{

<a href="http://open.xmeye.net/zh/#HVR_CHNCAPV2">SDK\_HVR\_CHNCAPV2</a> DigitalCap;	<label style="color:#c33">// Supported digital channel information</label><br/>

<a href="http://open.xmeye.net/zh/#HVR_CHNCAPV2">SDK\_HVR\_CHNCAPV2</a> AnalogCap;	<label style="color:#c33">// Analog channel information supported</label><br/>

}SDK\_CAPTURE\_HVRCAPV2, *SDK\_PCAPTURE\_HVRCAPV2; <br/>




typedef struct SDK\_CAPTURE\_TOTAL\_HVRCAP <label style="color:#c33">//Switch to CAPTURE\_TOTAL\_HVRCAPV2，for compatibility with old reservations</label><br/>
{

int	nHVRCap;				<label style="color:#c33">// Actually supported model</label><br/>

<a href="http://open.xmeye.net/zh/#CAPTURE_HVRCAP">SDK\_CAPTURE\_HVRCAP</a> HVRCap[<a href="http://open.xmeye.net/zh/#MAX_HVR_CHNCAP_CHN">MAX\_HVR\_CHNCAP\_CHN</a>];	<label style="color:#c33">// Summary of all patterns</label><br/>

}SDK\_CAPTURE\_TOTAL\_HVRCAP, *SDK\_PCAPTURE\_TOTAL\_HVRCAP; <br/>




typedef struct SDK\_CAPTURE\_TOTAL\_HVRCAPV2<br/> 
{

int		nHVRCap;			<label style="color:#c33">// Actually supported model</label><br/>

<a href="http://open.xmeye.net/zh/#CAPTURE_HVRCAPV2">SDK\_CAPTURE\_HVRCAPV2</a> HVRCap[<a href="http://open.xmeye.net/zh/#MAX_HVR_CHNCAP_CHN">MAX\_HVR\_CHNCAP\_CHN</a>];	<label style="color:#c33">// Summary of all patterns</label><br/>

}SDK\_CAPTURE\_TOTAL\_HVRCAPV2, *SDK\_PCAPTURE\_TOTAL\_HVRCAPV2;




<label style="color:#c33">//Channel mode configuration</label><br/>

typedef struct SDK\_NetDecorderChnModeConfig<br/> 
{

<a href="http://open.xmeye.net/zh/#CAPTURE_TOTAL_HVRCAPV2">SDK\_CAPTURE\_TOTAL\_HVRCAPV2</a>  HVRTotalCap;

int HVRCurCapMode;

}SDK\_NetDecorderChnModeConfig;




<label style="color:#c33">/* Digital channel status */</label><br/>

typedef struct SDK\_NetDecorderChnStatus<br/> 
{

char ChnName[<a href="http://open.xmeye.net/zh/#NET_NAME_PASSWORD_LEN">NET\_NAME\_PASSWORD\_LEN</a>];

char pMaxResName[50];

char pCurResName[50];

char pStatus[50];

}SDK\_NetDecorderChnStatus;




<label style="color:#c33">/*All digital channel states*/</label><br/>

typedef struct SDK\_NetDecorderChnStatusAll<br/> 
{

<a href="http://open.xmeye.net/zh/#NetDecorderChnStatus"> SDK\_NetDecorderChnStatus</a> ChnStatusAll[<a href="http://open.xmeye.net/zh/#NET_MAX_DECORDR_CH">NET\_MAX\_DECORDR\_CH</a>];

}SDK\_NetDecorderChnStatusAll;




<label style="color:#c33">//Pos device type</label><br/>

enum SDK\_PosDevType<br/> 
{

SDK\_POS\_TYPE\_MANY\_LINES, <label style="color:#c33">//After the total amount is calculated, the product information is sent together</label><br/>

SDK\_POS\_TYPE\_ONE\_LINE,   <label style="color:#c33">//Every statistic of a commodity sends the information of this commodity</label><br/>

SDK\_POS\_NR

};




<label style="color:#c33">//Text encoding format</label><br/>

enum SDK\_WordEncode<br/> 
{

SDK\_WORD\_ENCODE\_GB2312,  <label style="color:#c33"> //Chinese character coding GB2312</label><br/>

SDK\_WORD\_ENCODE\_UNICODE,  <label style="color:#c33">//unicode Unicode</label><br/>

SDK\_WORD\_ENCODE\_UTF8,    <label style="color:#c33">//UTF-8</label><br/>

};




 #define SDK\_MAX\_POS\_FUNC\_KEYWORDS 4

<label style="color:#c33">// POS related configuration</label><br/>

typedef struct SDK\_NetPosConfig<br/> 
{

bool Enable;		<label style="color:#c33">/*POS channel enable*/</label><br/>

int  Devtype;		<label style="color:#c33">//Type of POS machine</label><br/>

int  Protocol;		<label style="color:#c33">//communication protocol</label><br/>

int  Port;	    <label style="color:#c33">//Protocol port number</label><br/>

bool SnapEnable;		<label style="color:#c33">//Snap enable</label>

int  StartLine;		<label style="color:#c33">//How many lines of information are received from the start?</label><br/>

int  WordEncodeType;	<label style="color:#c33">//A literal encoding format, such as enumeration values <a href="http://open.xmeye.net/zh/#WordEncodeType">WordEncodeType</a>  </label><br/>

bool KeyWordEnable; 	<label style="color:#c33">//Keyword log enabled</label><br/>

char SearchWrod[<a href="http://open.xmeye.net/zh/#MAX_POS_FUNC_KEYWORDS">SDK\_MAX\_POS\_FUNC\_KEYWORDS</a>][16]; <label style="color:#c33">//Words that need to be added to the log</label><br/>

int  HideTime;        <label style="color:#c33">//The time that the hidden channel displays the POS information is in seconds, and 0 indicates that it is not hidden automatically</label><br/>

int  res;		<label style="color:#c33">//Retain</label><br/>

}SDK\_NetPosConfig;

<label style="color:#c33">//All POS related configurations</label><br/>

typedef struct SDK\_NetPosConfigAll<br/> 
{

<a href="http://open.xmeye.net/zh/#NetPosConfig">SDK\_NetPosConfig</a> PosConfig[<a href="http://open.xmeye.net/zh/#MAX_HVR_CHNCAP_CHN">MAX\_HVR\_CHNCAP\_CHN</a>];

}SDK\_NetPosConfigAll;




<label style="color:#c33">///< 3G dial settings</label><br/>

typedef struct SDK\_Net3GConfig<br/> 
{

bool bEnable;			   <label style="color:#c33"> ///< Wireless module enable flag</label><br/>

int  iNetType;			 	<label style="color:#c33">///< Wireless network type</label><br/>

char sAPN[<a href="http://open.xmeye.net/zh/#NET_NAME_PASSWORD_LEN">NET\_NAME\_PASSWORD\_LEN</a>];		<label style="color:#c33">///< Access point name</label><br/>

char sDialNum[<a href="http://open.xmeye.net/zh/#NET_NAME_PASSWORD_LEN">NET\_NAME\_PASSWORD\_LEN</a>];    <label style="color:#c33">///< Dial number</label><br/>

char sUserName[<a href="http://open.xmeye.net/zh/#NET_NAME_PASSWORD_LEN">NET\_NAME\_PASSWORD\_LEN</a>];   <label style="color:#c33">///< Dial-up user name</label><br/>

char sPassword[<a href="http://open.xmeye.net/zh/#NET_NAME_PASSWORD_LEN">NET\_NAME\_PASSWORD\_LEN</a>];  <label style="color:#c33"> ///< Dial-up password</label><br/>

<a href="http://open.xmeye.net/zh/#CONFIG_IPAddress">CONFIG_IPAddress</a> addr;			<label style="color:#c33">///< The IP address obtained after dialing</label><br/>

char sOperators[<a href="http://open.xmeye.net/zh/#NET_NAME_PASSWORD_LEN">NET\_NAME\_PASSWORD\_LEN</a>]; <label style="color:#c33"> ///< Operator</label><br/>

}SDK\_Net3GConfig;




<label style="color:#c33">///< Mobile monitor settings include</label><br/>

typedef struct SDK\_NetMoblieConfig<br/> 
{

bool bEnable;			<label style="color:#c33">///< Whether to open</label><br/>

<a href="http://open.xmeye.net/zh/#RemoteServerConfig">SDK\_RemoteServerConfig</a> Server;	<label style="color:#c33">///< The server</label><br/>

}SDK\_NetMoblieConfig;




<label style="color:#c33">//RTSP</label>

typedef struct SDK\_NetRTSPConfig<br/> 
{

bool bServer;

bool bClient;

<a href="http://open.xmeye.net/zh/#RemoteServerConfig">SDK\_RemoteServerConfig</a> Server;	<label style="color:#c33">///< Server mode</label><br/>

<a href="http://open.xmeye.net/zh/#RemoteServerConfig">SDK\_RemoteServerConfig</a> Client;	<label style="color:#c33">///< Client mode</label><br/>

}SDK\_NetRTSPConfig;




<label style="color:#c33">///< UPNP settings</label><br/>

typedef struct SDK\_NetUPNPConfig<br/> 
{

bool bEnable;			<label style="color:#c33">///< Enable sign</label><br/>

bool bState;			<label style="color:#c33">///< status, 1: OK 0: NOK</label><br/>

int  iHTTPPort;			<label style="color:#c33">///< The port after the HTTP connection map</label><br/>

int  iMediaPort;			<label style="color:#c33">///< The port after the media connection is mapped</label><br/>

int  iMobliePort;		<label style="color:#c33">///< The port after the mobile phone monitor is mapped</label><br/>

}SDK\_NetUPNPConfig;




<label style="color:#c33">///< WIFI settings</label><br/>

typedef struct SDK\_NetWifiConfig<br/> 
{

bool bEnable;

char sSSID[36];            	<label style="color:#c33">///< SSID Number</label><br/>

int  nChannel;             <label style="color:#c33">///< channel</label><br/>

char sNetType[32];         <label style="color:#c33">	///< Infra, Adhoc</label><br/>

char sEncrypType[32];      	<label style="color:#c33">///< NONE, WEP, TKIP, AES</label><br/>

char sAuth[32];            	<label style="color:#c33">///< OPEN, SHARED, WEPAUTO, WPAPSK, WPA2PSK, WPANONE, WPA, WPA2</label><br/>

int  nKeyType;             <label style="color:#c33">///< 0:Hex 1:ASCII</label><br/>

char sKeys[<a href="http://open.xmeye.net/zh/#NET_IW_ENCODING_TOKEN_MAX">NET\_IW\_ENCODING\_TOKEN\_MAX</a>]; <br/>

<a href="http://open.xmeye.net/zh/#CONFIG_IPAddress">CONFIG\_IPAddress</a> HostIP;	   <label style="color:#c33">///< host ip</label><br/>

CONFIG_IPAddress Submask;	   <label style="color:#c33"> ///< netmask</label><br/>

CONFIG_IPAddress Gateway;	   <label style="color:#c33"> ///< gateway</label><br/>

}SDK\_NetWifiConfig;




enum SDK\_RSSI\_SINGNAL<br/> 
{

SDK\_RSSI\_NO\_SIGNAL,   <label style="color:#c33"> //<= -90db</label>

SDK\_RSSI\_VERY\_LOW,    <label style="color:#c33"> //<= -81db</label>

SDK\_RSSI\_LOW,       <label style="color:#c33"> //<= -71db</label>

SDK\_RSSI\_GOOD,      <label style="color:#c33">  //<= -67db</label>

SDK\_RSSI\_VERY\_GOOD,   <label style="color:#c33"> //<= -57db</label>

SDK\_RSSI\_EXCELLENT     <label style="color:#c33">//<= -57db</label>

};




typedef struct SDK\_NetWifiDevice<br/> 
{

char sSSID[36];          <label style="color:#c33"> //SSID Number</label><br/>

int  nRSSI;            <label style="color:#c33"> //SEE SDK\_RSSI\_SINGNAL</label><br/>

int  nChannel; <br/>

char sNetType[32];        <label style="color:#c33"> //Infra, Adhoc</label><br/>

char sEncrypType[32];      <label style="color:#c33"> //NONE, WEP, TKIP, AES</label><br/>

char sAuth[32];          <label style="color:#c33"> //OPEN, SHARED, WEPAUTO, WPAPSK, WPA2PSK, WPANONE, WPA, WPA2</label><br/>

}SDK\_NetWifiDevice;




typedef struct SDK\_NetWifiDeviceAll<br/> 
{

int nDevNumber;

<a href="http://open.xmeye.net/zh/#NetWifiDevice">SDK\_NetWifiDevice</a> vNetWifiDeviceAll[<a href="http://open.xmeye.net/zh/#NET_MAX_AP_NUMBER">NET\_MAX\_AP\_NUMBER</a>];

}SDK\_NetWifiDeviceAll;

<label style="color:#c33">/// Voice intercom format</label><br/>

typedef struct SDK\_AudioInFormatConfigAll<br/> 
{

<a href="http://open.xmeye.net/zh/#AudioInFormatConfig">SDK\_AudioInFormatConfig</a> vAudioInFormatConfig[<a href="http://open.xmeye.net/zh/#AUDIO_ENCODE_TYPES_NR">SDK\_AUDIO\_ENCODE\_TYPES\_NR</a>];

}SDK\_AudioInFormatConfigAll;




<label style="color:#c33">/// Alarm status</label><br/>

typedef struct SDK\_DVR\_ALARMSTATE<br/> 
{

char iVideoMotion[NET\_MAX\_MSK\_SIZE];<label style="color:#c33">///< Move detection status, use mask to indicate channel number, byte0 stands for channel one, and so on, 1: has alarm, 0: has no alarm</label><br/>

char iVideoBlind[NET\_MAX\_MSK\_SIZE];<label style="color:#c33">///< Video occlusion state, with a mask to indicate the channel number, byte0 represents the channel one, and so on, 1:, there is alarm, 0: no alarm</label><br/>

char iVideoLoss[NET\_MAX\_MSK\_SIZE];<label style="color:#c33">///< Video missing state, use mask to indicate channel number, byte0 stands for channel one, and so on, 1: has alarm 0:, no alarm</label><br/>

char iAlarmIn[NET\_MAX\_MSK\_SIZE];<label style="color:#c33">///< Alarm input status, with a mask to indicate the channel number, byte0 represents the channel one, and so on, 1:, there is alarm, 0: no alarm</label><br/>

char iAlarmOut[NET\_MAX\_MSK\_SIZE];<label style="color:#c33">///< The alarm output state is represented by a mask, the channel number is 0:, and the byte0 represents the channel one, and so on, 1: has an alarm and no alarm</label><br/>

}SDK\_DVR\_ALARMSTATE;




<label style="color:#c33">//Channel status</label><br/>

typedef struct SDK\_DVR\_CHANNELSTATE<br/> 
{

bool bRecord;   <label style="color:#c33">///< Are you recording?</label><br/>

int iBitrate;	<label style="color:#c33">///< Current bitrate</label><br/>

}SDK\_DVR\_CHANNELSTATE;




<label style="color:#c33">// DVR working status</label><br/>

typedef struct SDK\_DVR\_WORKSTATE<br/> 
{

<a href="http://open.xmeye.net/zh/#DVR_CHANNELSTATE">SDK\_DVR_CHANNELSTATE</a> vChnState[<a href="http://open.xmeye.net/zh/#NET_MAX_CHANNUM">NET\_MAX\_CHANNUM</a>];

<a href="http://open.xmeye.net/zh/#DVR_ALARMSTATE">SDK\_DVR\_ALARMSTATE</a> vAlarmState;

}SDK\_DVR\_WORKSTATE;

<label style="color:#c33">/// Support language</label><br/>

typedef struct SDK\_MultiLangFunction<br/> 
{

<label style="color:#c33"> //Each protocol consists of 64 characters at most</label><br/>

int nLangNum;

char vLanguageName[128][64];

}SDK\_MultiLangFunction;




<label style="color:#c33">/// Supported video formats</label><br/>

typedef struct SDK\_MultiVstd<br/> 
{

<label style="color:#c33">//Each protocol consists of 3 characters at most</label><br/>

int nVstdNum;

char vVstdName[3][64];

}SDK\_MultiVstd;

<label style="color:#c33">/// Default configuration types for recovery</label><br/>

typedef struct SDK\_SetDefaultConfigTypes<br/> 
{

bool vSetDefaultKinds[<a href="http://open.xmeye.net/zh/#DEFAULT_CFG_END">SDK\_DEFAULT\_CFG\_END</a>];

bool vDefaultFactory;		<label style="color:#c33">//Restore factory settings configuration</label><br/>

}SDK\_SetDefaultConfigTypes;

<label style="color:#c33">// Upgrade information access</label><br/>

typedef struct SDK\_UpgradeInfo<br/> 
{

char szSerial[64];

char szHardware[64];

char szVendor[64];

unsigned int uiLogoArea[2];

char szLogoPartType[64];

}SDK\_UpgradeInfo;




typedef struct <br/> 
{

int left;

int top;

int right;

int bottom;

}sdkRect;

<label style="color:#c33">/// Audio input format, voice intercom</label><br/>

typedef struct SDK\_AudioInFormatConfig<br/> 
{

int iBitRate;	  <label style="color:#c33">///<The bitstream size is Kbps, such as,192kbps，128kbps</label><br/>

int iSampleRate;  <label style="color:#c33"> ///< The sampling rate is Hz, for example 44100Hz</label><br/>

int iSampleBit;  <label style="color:#c33">  ///< Sampling bit depth</label><br/>

int iEncodeType;   <label style="color:#c33">///< Encoding mode, reference to the<a href="http://open.xmeye.net/zh/#AudioEncodeTypes">AudioEncodeTypes</a>definition</label><br/>

}SDK\_AudioInFormatConfig;




<label style="color:#c33">//Voice intercom format</label><br/>

typedef enum\_TALK\_CODING\_TYPE<br/> 
{

TALK\_DEFAULT = 0,

TALK\_PCM = 1,		//PCM

TALK\_G711a,		//G711a

TALK\_AMR,		//AMR

TALK\_G711u,		//G711u

TALK\_G726,		//G726

}TALK\_CODING\_TYPE;

<label style="color:#c33">//Voice intercom </label><br/>

typedef struct H264\_DVR\_TALKDECODE\_INFO<br/> 
{

<a href="http://open.xmeye.net/zh/#TALK_CODING_TYPE">TALK\_CODING\_TYPE</a>	encodeType;	<label style="color:#c33">//Encoding type</label><br/>

int	nAudioBit;	<label style="color:#c33">//Represented by actual values, such as 8, and the fill value is 8</label><br/>

unsigned int dwSampleRate;<label style="color:#c33">//The sampling rate, such as 16K, is 16000</label><br/>

char reserved[64]; <br/>

}H264\_DVR\_TALKDECODE\_INFO;

typedef struct SDK\_VIDEO\_FORMAT<br/> 
{

int		iCompression;	<label style="color:#c33">//  Compressed mode (video format) reference<a href="http://open.xmeye.net/zh/#CAPTURE_COMP_t">enum SDK\_CAPTURE\_COMP\_t</a> 	</label><br/>

int		iResolution;	<label style="color:#c33">//  Resolution reference enumeration<a href="http://open.xmeye.net/zh/#CAPTURE_SIZE_t">SDK\_CAPTURE\_SIZE\_t</a></label><br/>

int		iBitRateControl;<label style="color:#c33">//  Stream control reference enumeration<a href="http://open.xmeye.net/zh/#capture_brc_t">SDK\_capture\_brc\_t</a></label><br/>

int		iQuality;	<label style="color:#c33">//  The bitstream quality is 1-6</label><br/>		

int		nFPS;		<label style="color:#c33">// Frame rate. NTSC/PAL is not distinguished. Negative numbers represent seconds	</label><br/>	

int		nBitRate;	<label style="color:#c33">//  0-4096k, the list is saved primarily by the client and the device receives only the actual bitstream value instead of the index.</label><br/>

int		iGOP;		<label style="color:#c33">//  Describe the time interval between two respectively.，2-12</label><br/> 

} SDK\_VIDEO\_FORMAT;




typedef struct  SDK\_AUDIO\_FORMAT<br/> 
{

int		nBitRate;	<label style="color:#c33">//  Stream kbps	</label><br/>

int		nFrequency;	<label style="color:#c33">//  sampling frequency	</label><br/>

int		nMaxVolume;	<label style="color:#c33">//  Maximum volume threshold</label><br/>

}SDK\_AUDIO\_FORMAT;




<label style="color:#c33">// Media format</label><br/>

typedef struct SDK\_MEDIA\_FORMAT<br/> 
{

<a href="http://open.xmeye.net/zh/#VIDEO_FORMAT">SDK\_VIDEO\_FORMAT</a> vfFormat;	<label style="color:#c33">//  Video format definition </label><br/>			

<a href="http://open.xmeye.net/zh/#AUDIO_FORMAT">SDK\_AUDIO\_FORMAT</a> afFormat;	<label style="color:#c33">//  Audio format definition </label><br/>

bool	bVideoEnable;		<label style="color:#c33">//  Open video encoding </label><br/>

bool	bAudioEnable;		<label style="color:#c33">//  Open audio encoding </label><br/>	

} SDK\_MEDIA\_FORMAT;




typedef union {//IP addr<br/> 

unsigned char	c[4];<br/> 

unsigned short	s[2];<br/> 

unsigned int 	l;<br/> 

}CONFIG\_IPAddress;<br/> 

<label style="color:#c33">//SMS configuration</label><br/>

typedef struct SDK\_NetShortMsgCfg<br/> 
{

bool bEnable;       <label style="color:#c33">//Is the function of sending SMS enabled?</label><br/>

char pDesPhoneNum[<a href="http://open.xmeye.net/zh/#NET_MAX_RECIVE_MSG_PHONE_COUNT">NET\_MAX\_RECIVE\_MSG\_PHONE\_COUNT</a>][16]; <br/>

int  sendTimes;     <label style="color:#c33">//How many SMS messages do you need to send to each cell phone?</label><br/>

}SDK\_NetShortMsgCfg;

<label style="color:#c33">//MMS configuration</label><br/>

typedef struct SDK\_NetMultimediaMsgCfg<br/> 
{

bool bEnable;				<label style="color:#c33">// Is the function of sending mobile phone MMS enabled?</label><br/>

char pDesPhoneNum[<a href="http://open.xmeye.net/zh/#NET_MAX_RECIVE_MSG_PHONE_COUNT">NET\_MAX\_RECIVE\_MSG\_PHONE\_COUNT</a>][16]; <label style="color:#c33">//Receive MMS phone number, now supports 3 mobile phone number</label><br/>

char pGateWayDomain[40];	       <label style="color:#c33"> // Gateway address, domain name or IP</label><br/>

int  gateWayPort;			<label style="color:#c33">// Gateway port</label><br/>

char pMmscDomain[40];		   <label style="color:#c33"> // MMS address, IP, or domain name</label><br/>

int  mmscPort;				<label style="color:#c33">// MMS server port number</label><br/>

}SDK\_NetMultimediaMsgCfg;

<label style="color:#c33">//Fisheye lens type enumeration</label><br/>

typedef enum SDK\_E\_FISH\_LENS\_TYPE<br/> 
{

SDK\_FISH\_LENS\_NORMAL,  <label style="color:#c33">//General lens, not app side for image correction</label><br/>

SDK\_FISH\_LENS\_360VR,

SDK\_FISH\_LENS\_360LVR,

SDK\_FISH\_LENS\_180VR,

SDK\_FISH\_LENS\_DUAL\_360VR,

SDK\_FISH\_LENS\_DUAL\_180VR,

SDK\_FISH\_LENS\_NR,

}SDK\_E\_FISH\_LENS\_TYPE;




<label style="color:#c33">//Fisheye lens configuration parameters</label><br/>

typedef struct SDK\_FishLensParam<br/> 
{

char  version;		<label style="color:#c33">//The version number of the structure (if you modify the following member to cause app to be processed separately from the new and old programs, you need to add 1 of the version number in the parameter settings tool and modify the default configuration on the device)</label><br/>

char  lensType;      <label style="color:#c33">//Lens type, such as enumeration<a href="http://open.xmeye.net/zh/#E_FISH_LENS_TYPE">SDK\_E\_FISH\_LENS\_TYPE</a></label><br/>

short centerOffsetX;   <label style="color:#c33">//Center deviation cross coordinate Unit: pixel point</label><br/>

short centerOffsetY;  <label style="color:#c33"> //Center deviation ordinate  Unit: pixel point</label><br/>

short radius;        <label style="color:#c33">//Radius unit: pixel point</label><br/>

short imageWidth;     <label style="color:#c33"> //The image width at the center of the correction  unit: pixel point</label><br/>

short imageHeight;	<label style="color:#c33">//Image height at center correction  unit: pixel point</label><br/>

char  viewAngle;	<label style="color:#c33">//View 0: overlooking 1: head up</label><br/>

char  viewMode;      <label style="color:#c33">//display mode   0:360VR</label><br/>

short zoom;		 <label style="color:#c33">//Scaling. In order to facilitate transmission, it will cost 100 times enlarged</label><br/>

char  resv[8];	

} SDK\_FishLensParam;




<label style="color:#c33">//Fisheye lens parameter configuration for all channels</label><br/>

typedef struct SDK\_FishLensParamAll<br/> 
{

<a href="http://open.xmeye.net/zh/#FishLensParamv">SDK\_FishLensParamv</a> vLensParamAll[<a href="http://open.xmeye.net/zh/#NET_MAX_CHANNUM">NET\_MAX\_CHANNUM</a>];

}SDK\_FishLensParamAll;




<label style="color:#c33">//Control setting of pan tilt configuration</label><br/>

typedef enum SDK\_PTZ\_CTRL\_TYPE<br/> 
{

PTZ\_CTRL\_COAX = 0,<label style="color:#c33">//Through coaxial lines</label><br/>

PTZ\_CTRL\_RS485,   <label style="color:#c33">//Through the 485 lines</label><br/>

PTZ\_CTRL\_BOTH,    <label style="color:#c33">//Both the coaxial line and the 485 line send control commands</label><br/>

}SDK\_PTZ\_CTRL\_TYPE;




typedef struct SDK\_PTZControlMode<br/> 
{
int ctrlMode;			<label style="color:#c33">//PTZ control mode[<a href="http://open.xmeye.net/zh/#PTZ_CTRL_TYPE">PTZ\_CTRL\_TYPE</a> Three enumerated values]</label><br/>

} SDK\_PTZControlMode;




typedef struct SDK\_PTZControlModeAll<br/> 
{
<a href="http://open.xmeye.net/zh/#PTZControlMode">SDK\_PTZControlMode</a> CtrlModeAll[<a href="http://open.xmeye.net/zh/#NET_MAX_CHANNUM">NET\_MAX\_CHANNUM</a>];

}SDK\_PTZControlModeAll;




typedef struct SDK\_SmartH264Param<br/> 
{

bool SmartH264;

}SDK\_SmartH264Param;




typedef struct SDK\_SmartH264ParamAll<br/> 
{

<a href="http://open.xmeye.net/zh/#SmartH264Param">SDK\_SmartH264Param</a> SmartH264All[<a href="http://open.xmeye.net/zh/#NET_MAX_CHANNUM">NET\_MAX\_CHANNUM</a>];

}SDK\_SmartH264ParamAll;




typedef struct SDK\_WifiInfo<br/> 
{

char ssid[32];		<label style="color:#c33">//Wireless SSID information</label><br/>

char wifiVersion[32];	<label style="color:#c33">//Version information for wireless modules</label><br/>

int advance;		<label style="color:#c33">//Performance enhancement model</label><br/>

}SDK\_WifiInfo;




<label style="color:#c33">///< According to the interval of capture</label><br/>

struct SDK\_IntervalSnapMode<br/> 
{

int iFTPTime;

int iEmailTime;

int iStorageTime;

};

<label style="color:#c33">///< According to the timing of capture</label><br/>

struct SDK\_TriggerSnapMode<br/> 
{

SDK\_SYSTEM\_TIME TriggerTime;

bool bFTP;

bool bEmail;

bool bStorage;

};

<label style="color:#c33">///< Capture plan</label>

struct SDK\_SnapSchedule<br/> 
{

int iSnapType;		<label style="color:#c33">// 0: capture interval;1: timing capture 2: turn off</label><br/>

<a href="http://open.xmeye.net/zh/#IntervalSnapMode">SDK\_IntervalSnapMode</a> intervalMode; <br/>

<a href="http://open.xmeye.net/zh/#TriggerSnapMode">SDK\_TriggerSnapMode</a> vTriggerMode[256]; <br/>

};




<label style="color:#c33">//All channel plan capture configuration</label><br/>

struct SDK\_SnapScheduleAll<br/> 
{  

<a href="http://open.xmeye.net/zh/#SnapSchedule">SDK\_SnapSchedule</a> vSnapScheduleAll[<a href="http://open.xmeye.net/zh/#NET_MAX_CHANNUM">NET\_MAX\_CHANNUM</a>];

};




<label style="color:#c33">Network keyboard key definition</label><br/>


<label style="color:#c33">/// Button values can not be changed at will</label><br/>

enum SDK\_NetKeyBoardValue<br/> 
{

SDK\_NET\_KEY\_0, SDK\_NET\_KEY\_1, SDK\_NET\_KEY\_2, SDK\_NET\_KEY\_3, SDK\_NET\_KEY\_4, SDK\_NET\_KEY\_5, SDK\_NET\_KEY\_6, SDK_NET_KEY_7, SDK_NET_KEY_8, SDK\_NET\_KEY\_9, <br/>

SDK\_NET\_KEY\_10, SDK\_NET\_KEY\_11, SDK\_NET\_KEY\_12, SDK\_NET\_KEY\_13, SDK\_NET\_KEY\_14, SDK\_NET\_KEY\_15, SDK\_NET\_KEY\_16, SDK\_NET\_KEY\_10PLUS,SDK\_NET\_KEY\_DIGIT, <br/>

SDK\_NET\_KEY\_UP = 20,     <label style="color:#c33">// Up or pan head up</label><br/>

SDK\_NET\_KEY\_DOWN,        <label style="color:#c33">// Down or pan down</label><br/>

SDK\_NET\_KEY\_LEFT,        <label style="color:#c33">// Left or pan head to left</label><br/>

SDK\_NET\_KEY\_RIGHT,       <label style="color:#c33">// Right or pan head to the right</label><br/>

SDK\_NET\_KEY\_SHIFT, <br/>

SDK\_NET\_KEY\_PGUP,        <label style="color:#c33">// Previous page</label><br/>

SDK\_NET\_KEY\_PGDN,       <label style="color:#c33"> // next page</label><br/>

SDK\_NET\_KEY\_RET,         <label style="color:#c33">// confirm</label><br/>

SDK\_NET\_KEY\_ESC,         <label style="color:#c33">// Cancel or exit</label><br/>

SDK\_NET\_KEY\_FUNC,        <label style="color:#c33">// Toggle input method</label><br/>

SDK\_NET\_KEY\_PLAY,        <label style="color:#c33">// Play / pause</label><br/>

SDK\_NET\_KEY\_BACK,        <label style="color:#c33">// Upside down</label><br/>

SDK\_NET\_KEY\_STOP,       <label style="color:#c33"> // Stop </label><br/>

SDK\_NET\_KEY\_FAST,        <label style="color:#c33">// Quick release</label><br/>

SDK\_NET\_KEY\_SLOW,        <label style="color:#c33">// Slow down</label><br/>

SDK\_NET\_KEY\_NEXT,        <label style="color:#c33">// Next file</label><br/>

SDK\_NET\_KEY\_PREV,        <label style="color:#c33">// Previous file</label><br/>

SDK\_NET\_KEY\_PAUSE,     <label style="color:#c33"> // pause</label><br/>

SDK\_NET\_KEY\_FUNC\_A,	  <label style="color:#c33">// Function key A</label><br/>

SDK\_NET\_KEY\_FUNC\_B,	  <label style="color:#c33">// The function key B (on consumer products, A and B functions differently depending on the device)</label><br/>

SDK\_NET\_KEY\_REC = 40,    <label style="color:#c33">//Video settings</label><br/>

SDK\_NET\_KEY\_SEARCH,      <label style="color:#c33">// Video query</label><br/>

SDK\_NET\_KEY\_INFO,        <label style="color:#c33">// system information</label><br/>

SDK\_NET\_KEY\_ALARM,       <label style="color:#c33">// Alarm output</label><br/>

SDK\_NET\_KEY\_ADDR,        <label style="color:#c33">// Remote address settings</label><br/>

SDK\_NET\_KEY\_BACKUP,      <label style="color:#c33">//backups</label><br/>

SDK\_NET\_KEY\_SPLIT,       <label style="color:#c33">// Frame split mode switching, switching to the next style mode each time</label><br/>

SDK\_NET\_KEY\_SPLIT1,      <label style="color:#c33">// Single screen</label><br/>

SDK\_NET\_KEY\_SPLIT4,      <label style="color:#c33">// Four pictures</label><br/>

SDK\_NET\_KEY\_SPLIT8,      <label style="color:#c33">// Eight pictures</label><br/>

SDK\_NET\_KEY\_SPLIT9,      <label style="color:#c33">// Nine pictures</label><br/>

SDK\_NET\_KEY\_SPLIT16,     <label style="color:#c33">// sixty pictures</label><br/>

SDK\_NET\_KEY\_SHUT,        <label style="color:#c33">// Shutdown</label><br/>

SDK\_NET\_KEY\_MENU,        <label style="color:#c33">// menu</label><br/>

SDK\_NET\_KEY\_SPLIT25,	<label style="color:#c33">// 25 pictures</label><br/>

SDK\_NET\_KEY\_SPLIT36,     <label style="color:#c33">// 36 pictures</label><br/>

SDK\_NET\_KEY\_PTZ = 60,    <label style="color:#c33">// Enter the pan tilt control mode</label><br/>

SDK\_NET\_KEY\_TELE,        <label style="color:#c33">// Zoom out</label><br/>

SDK\_NET\_KEY\_WIDE,        <label style="color:#c33">// Doubly</label><br/>

SDK\_NET\_KEY\_IRIS\_SMALL, <label style="color:#c33"> // Aperture gain</label><br/>

SDK\_NET\_KEY\_IRIS\_LARGE,  <label style="color:#c33">// Aperture subtraction</label><br/>

SDK\_NET\_KEY\_FOCUS\_NEAR,  <label style="color:#c33">// Focusing distance</label><br/>

SDK\_NET\_KEY\_FOCUS\_FAR,   <label style="color:#c33">// Focus near</label><br/>

SDK\_NET\_KEY\_BRUSH,      <label style="color:#c33"> // Wiper</label><br/>

SDK\_NET\_KEY\_LIGHT,       <label style="color:#c33">// lighting</label><br/>

SDK\_NET\_KEY\_SPRESET,     <label style="color:#c33">// Set preset point</label><br/>

SDK\_NET\_KEY\_GPRESET,     <label style="color:#c33">// Go to preset point</label><br/>

SDK\_NET\_KEY\_DPRESET,     <label style="color:#c33">// Clear preset points</label><br/>

SDK\_NET\_KEY\_PATTERN,     <label style="color:#c33">// Pattern</label><br/>

SDK\_NET\_KEY\_AUTOSCAN,    <label style="color:#c33">// The automatic scan begins and ends</label><br/>

SDK\_NET\_KEY\_AUTOTOUR,    <label style="color:#c33">// cruise control</label><br/>

SDK\_NET\_KEY\_AUTOPAN,     <label style="color:#c33">// Line scan start / end</label><br/>

};




<label style="color:#c33">/// Button status</label><br/>

enum SDK\_NetKeyBoardState<br/> 
{

SDK\_NET\_KEYBOARD\_KEYDOWN,	<label style="color:#c33"> // Press button</label><br/>

SDK\_NET\_KEYBOARD\_KEYUP,	 <label style="color:#c33">// Button release</label><br/>

};




typedef struct SDK_NetKeyBoardData<br/> 
{

int iValue; <label style="color:#c33">//enumeration<a href="http://open.xmeye.net/zh/#NetKeyBoardValue">SDK\_NetKeyBoardValue</a></label><br/>

int iState; <label style="color:#c33">//enumeration<a href="http://open.xmeye.net/zh/#NetKeyBoardState">SDK\_NetKeyBoardState</a></label><br/>

}SDK_NetKeyBoardData;
<br/><br/>

<div name="jiegouti" id="jiegouti" style="font-size:20px;"><b>3 Struct definition</b></div>


<div name="jiegouti1" id="jiegouti1" style="font-size:15px;"><b>3.1Device information H264\_DVR\_DEVICEINFO structural </b></div>

typedef struct \_H264\_DVR\_DEVICEINFO<br/>
{

char sSoftWareVersion[64];	<label style="color:#c33">///< Software version information</label><br/>

char sHardWareVersion[64];	<label style="color:#c33">///< Hardware version information</label><br/>

char sEncryptVersion[64];	   <label style="color:#c33"> ///< Encrypted version information</label><br/>

<a href="http://open.xmeye.net/zh/#SYSTEM_TIME">SDK\_SYSTEM\_TIME </a>tmBuildTime;  <label style="color:#c33"> ///< Software creation time</label><br/>

char sSerialNumber[64];		<label style="color:#c33">///< Device serial number</label><br/>

int byChanNum;			<label style="color:#c33">///< Number of video input channels</label><br/>

int iVideoOutChannel;		<label style="color:#c33">///< Video output channel</label><br/>

int byAlarmInPortNum;		<label style="color:#c33">///< Number of alarm input channels</label><br/>

int byAlarmOutPortNum;		<label style="color:#c33">///< Number of alarm output channels</label><br/>

int iTalkInChannel;		<label style="color:#c33">///< Talkback input channel number</label><br/>

int iTalkOutChannel;		<label style="color:#c33">///< Talkback output channel</label><br/>

int iExtraChannel;		<label style="color:#c33">///< Extended channel number</label><br/>

int iAudioInChannel;		<label style="color:#c33">///< Number of audio input channels</label><br/>

int iCombineSwitch;		<label style="color:#c33">///< Does the combination coding channel partition mode support switching?</label><br/>

int iDigChannel;			<label style="color:#c33">///<Number of channels</label><br/>

unsigned int uiDeviceRunTime;  <label style="color:#c33">///<System running time</label><br/>

<a href="http://open.xmeye.net/zh/#DeviceType">SDK\_DeviceType </a>deviceTye;	<label style="color:#c33">///Device type</label><br/>

char sHardWare[64];		<label style="color:#c33">///<Equipment type</label><br/>

char uUpdataTime[20];		<label style="color:#c33">///<Update date, for example 2013-09-03 14:15:13</label><br/>

unsigned int uUpdataType;	    <label style="color:#c33">///<Update content</label><br/>

int nLanguage;<label style="color:#c33">//The language of the country is ID, 0 English, 1 Chinese, 2 Chinese, 3 Korean, 4 German, 5 Portuguese, 6 Russian</label><br/>

char sCloudErrCode[<a href="http://open.xmeye.net/zh/#NET_MAX_PATH_LENGTH">NET\_MAX\_PATH\_LENGTH</a>];<label style="color:#c33">//Cloud landing specific error content</label><br/>

int status[32];<br/>

<label style="color:#c33">//Determine if the new connection is forwarded by proxy, and if so, follow server 3</label><br/>

<label style="color:#c33">//The restrictions are returned to limit。</label><br/>

<label style="color:#c33">//status[0] Number limit: 0 means no limit, n represents the limit of N Road</label><br/>

<label style="color:#c33">//status[1]Bitstream restriction. 0: no restrictions. 1 limits cannot see the main stream.</label><br/>

<label style="color:#c33">//status[2]Limited time. 0: is not limited. N: limits n minutes.</label><br/>

<label style="color:#c33">//status[3]The limited bit rate is currently divided into four tranches. 0: is not limited. 1: is limited to CIF, 6 frames 100K, and subsequent pending</label><br/>

<label style="color:#c33">//status[4]Reserved bits, subsequent extensions.</label><br/>

<label style="color:#c33">//Among them, status[0] and status[1] are embodied here.</label><br/>

<label style="color:#c33">//status[2]和status[3] in the process of transmitting the bitstream</label><br/>

}H264\_DVR\_DEVICEINFO,*LPH264\_DVR\_DEVICEINFO;
<br/><br/>
<div name="jiegouti2" id="jiegouti2" style="font-size:15px;"><b>3.2Temporal information; SDK_SYSTEM_TIME structure</b></div>



<label style="color:#c33">/// System time structure</label><br/>

typedef struct SDK\_SYSTEM\_TIME<br/>
{

int  year;		<label style="color:#c33">///< year。   </label><br/>

int  month;		<label style="color:#c33">///< month，January = 1, February = 2, and so on.  </label> <br/>

int  day;		<label style="color:#c33">///< day。   </label><br/>

int  wday;		<label style="color:#c33">///< week，Sunday = 0, Monday = 1, and so on  </label> <br/>

int  hour;		<label style="color:#c33">///< hour。   </label><br/>

int  minute;	 <label style="color:#c33">   ///< minute。   </label><br/>

int  second;	<label style="color:#c33">    ///< second。 </label>  <br/>

int  isdst;		<label style="color:#c33">///< Daylight saving time sign。 </label> <br/> 

}SDK\_SYSTEM\_TIME;<br/>




<label style="color:#c33">//Video settings related structures</label><br/>

typedef struct SDK\_TIMESECTION<br/>

{

<label style="color:#c33">//!enable</label><br/>

int enable;<br/>

<label style="color:#c33">//!Start time: hour</label><br/>

int startHour;<br/>

<label style="color:#c33">//!Start time: minute</label><br/>

int	startMinute;<br/>

<label style="color:#c33">//!Start time: second</label><br/>

int	startSecond;<br/>

<label style="color:#c33">//!End time: hour</label><br/>

int	endHour;<br/>

<label style="color:#c33">//!End time: minute</label><br/>

int	endMinute;<br/>

<label style="color:#c33">//!End time: second</label><br/>

int	endSecond;<br/>

}SDK\_TIMESECTION;<br/>




typedef struct<br/>
{

int dwYear;	<label style="color:#c33">//year</label><br/>

int dwMonth;	<label style="color:#c33">//month</label><br/>

int dwDay;	<label style="color:#c33">//day</label><br/>

int dwHour;	<label style="color:#c33">//hour</label><br/>

int dwMinute;	<label style="color:#c33">//minute</label><br/>

int dwSecond;	<label style="color:#c33">//second</label><br/>

}H264\_DVR\_TIME,*LPH264\_DVR\_TIME;<br/>




<label style="color:#c33">//Time structure</label>

typedef struct\_NEW\_NET\_TIME<br/>
{

unsigned int second		:6;		<label style="color:#c33">//	second	1-60		</label><br/>

unsigned int minute		:6;		<label style="color:#c33">//	minute	1-60		</label><br/>

unsigned int hour		:5;		<label style="color:#c33">//	hour	1-24		</label><br/>

unsigned int day		:5;		<label style="color:#c33">//	day	1-31		</label><br/>

unsigned int month		:4;		<label style="color:#c33">//	month	1-12		</label><br/>

unsigned int year		:6;		<label style="color:#c33">//	year	2000-2063	</label><br/>

}NEW\_NET\_TIME, *LPNET\_TIME;<br/>

<label style="color:#c33">///< Daylight saving time structure</label><br/>

typedef struct DSTPoint<br/>
{

int	iYear;<br/>

int	iMonth;<br/>

int	iWeek;		<label style="color:#c33">///<周1:first  to2 3 4 -1:last one   0:represents a method of daily calculation[-1,4]</label><br/>

int	iWeekDay;	<label style="color:#c33">///<weekday from sunday=0	[0, 6]</label><br/>

int Hour;<br/>

int Minute;<br/>

}DSTPoint;
<br/><br/>

<div name="jiegouti3" id="jiegouti3" style="font-size:15px;"><b>3.3Video file information H264\_DVR\_FINDINFO structure</b></div>

typedef struct H264\_DVR\_FINDINFO

{

int nChannelN0;		<label style="color:#c33">//channel number</label><br/>

int nFileType;		<label style="color:#c33">//file type, see<a href="http://open.xmeye.net/zh/#File_Type">SDK\_File\_Type</a></label><br/>

<a href="http://open.xmeye.net/zh/#TIME">H264\_DVR\_TIME</a> startTime; <label style="color:#c33">//start time</label><br/>

<a href="http://open.xmeye.net/zh/#TIME">H264\_DVR\_TIME</a> endTime;	<label style="color:#c33">//end time</label><br/>

char szFileName[32];	<label style="color:#c33">//File name, null, system processing, value, system adoption</label><br/>

void *hWnd;        <label style="color:#c33">//Window handle</label><br/>

int  StreamType;		<label style="color:#c33">//The bitstream type of the query, the main stream: 0, the auxiliary bitstream:1</label><br/>

}H264\_DVR\_FINDINFO;<br/>




<label style="color:#c33">//Video file return structure</label><br/>

typedef struct H264_DVR_FILE_DATA<br/>
{

int ch;				<label style="color:#c33">//Channel number</label><br/>

int size;				<label style="color:#c33">//file size</label><br/>

char sFileName[108];		<label style="color:#c33">//file name</label><br/>

<a href="http://open.xmeye.net/zh/#SYSTEM_TIME">SDK\_SYSTEM\_TIME</a> stBeginTime;  <label style="color:#c33"> //file start time</label><br/>

<a href="http://open.xmeye.net/zh/#SYSTEM_TIME">SDK\_SYSTEM\_TIME</a> stEndTime;	<label style="color:#c33">//file end time</label><br/>

void *hWnd;			<label style="color:#c33">//Window handle</label><br/>

int StreamType;			<label style="color:#c33">//Is the bitstream type to play back the main stream (0) or the auxiliary bitstream（1）</label><br/>

}H264\_DVR\_FILE\_DATA;<br/>




//Query by time

typedef struct SDK\_SearchByTime<br/>
{

int nHighChannel;			<label style="color:#c33">///< 33~64Video channel mask</label><br/>

int nLowChannel;			<label style="color:#c33">///< 1~32Video channel mask</label><br/>

int nFileType;             <label style="color:#c33">///< file type, see<a href="http://open.xmeye.net/zh/#File_Type">SDK\_File\_Type</a></label><br/>

<a href="http://open.xmeye.net/zh/#SYSTEM_TIME">SDK\_SYSTEM\_TIME</a> stBeginTime;   <label style="color:#c33">///< Query start time</label><br/>

<a href="http://open.xmeye.net/zh/#SYSTEM_TIME">SDK\_SYSTEM\_TIME </a>stEndTime;	<label style="color:#c33">///< Query end time</label><br/>

int    iSync;             <label style="color:#c33">///< Whether need synchronization?</label><br/>

unsigned int nHighStreamType;  <label style="color:#c33">///< 33~64The video stream type, the binary bit is 0, the main bit stream, and the 1 represents the auxiliary bitstream</label><br/>

unsigned int nLowStreamType;   <label style="color:#c33">///< 1~32The video stream type, the binary bit is 0, the main bit stream, and the 1 represents the auxiliary bitstream</label><br/>

}SDK\_SearchByTime;




<label style="color:#c33">//Video information for each channel</label>

typedef struct SDK\_SearchByTimeInfo<br/>
{

int iChannel;			<label style="color:#c33">///< Video channel number</label><br/>

<label style="color:#c33">///< The video record represents 1440 minutes of the day with 720 bytes of 5760 bits</label><br/>

<label style="color:#c33"> ///< 0000:No video recording 0001:F\_COMMON 0002:F\_ALERT 0003:F\_DYNAMIC 0004:F\_CARD 0005:F_HAND</label><br/>

unsigned char cRecordBitMap[720];<br/>

}SDK\_SearchByTimeInfo;<br/>




typedef struct SDK\_SearchByTimeResult<br/>
{

int nInfoNum;	  <label style="color:#c33">///< Number of video recording messages for channels</label><br/>

<a href="http://open.xmeye.net/zh/#SearchByTimeInfo">SDK\_SearchByTimeInfo</a> ByTimeInfo[<a href="http://open.xmeye.net/zh/#NET_MAX_CHANNUM">NET\_MAX\_CHANNUM</a>];    <label style="color:#c33">///< Channel video recording information</label><br/>

}SDK\_SearchByTimeResult;<br/>

<label style="color:#c33"><a href="http://open.xmeye.net/zh/#3.3.1">Serial protocol information</a></label><br/>



typedef struct SDK\_COMMATTRI<br/>
{

int	iDataBits;	<label style="color:#c33">// The data bit value is 5,6,7,8</label><br/>

int	iStopBits;	<label style="color:#c33">// Stop bit</label><br/>

int	iParity;	<label style="color:#c33">// Check digit</label><br/>

int	iBaudRate;	<label style="color:#c33">// Actual baud rate</label><br/>

}SDK\_COMMATTRI;<br/>

<label style="color:#c33">// Serial protocol</label><br/>

enum SDK\_CommProtocol<br/>
{

SDK_CONSOLE = 0,<br/>

SDK_KEYBOARD,<br/>

SDK_COM_TYPES,<br/>

};

<label style="color:#c33">/// Serial protocol</label><br/>

typedef struct SDK\_COMMFUNC<br/>
{

<label style="color:#c33">//Each protocol consists of 64 characters at most</label><br/>

int nProNum;<br/>

char vCommProtocol[100][32];<br/>

}SDK\_COMMFUNC;<br/>

<label style="color:#c33">// Serial port configuration</label><br/>

typedef struct SDK\_CONFIG\_COMM\_X<br/>
{

char iProtocolName[32];	<label style="color:#c33">// Serial protocol:“Console”</label><br/>

int iPortNo;		<label style="color:#c33">// Port number</label><br/>

<a href="http://open.xmeye.net/zh/#COMMATTRI>SDK\_COMMATTRI</a> aCommAttri;	<label style="color:#c33">// Serial attribute</label><br/>

}SDK\_CONFIG\_COMM\_X;<br/>

<label style="color:#c33">PTZ protocol</label><br/>


typedef struct SDK\_STR\_CONFIG_PTZ<br/>
{

char sProtocolName[<a href="http://open.xmeye.net/zh/#NET_MAX_PTZ_PROTOCOL_LENGTH>NET\_MAX\_PTZ\_PROTOCOL\_LENGTH</a>];	<label style="color:#c33">// Protocol name</label><br/>

int	ideviceNo;			<label style="color:#c33">	// PTZ address number</label><br/>

int	iNumberInMatrixs;			<label style="color:#c33">// A uniform number in the matrix</label><br/>

int iPortNo;					<label style="color:#c33">// Serial port number	[1, 4]</label><br/>

<a href="http://open.xmeye.net/zh/#COMMATTRI>SDK\_COMMATTRI</a> dstComm;
<label style="color:#c33">	// Serial attribute</label><br/>

}SDK\_STR\_CONFIG\_PTZ;<br/>

<label style="color:#c33">/// PTZ protocol</label><br/>

typedef struct SDK\_PTZPROTOCOLFUNC<br/>
{

<label style="color:#c33">//Each protocol consists of 64 characters at most</label><br/>

int nProNum;<br/>

char vPTZProtocol[100][<a href="http://open.xmeye.net/zh/#NET_MAX_PTZ_PROTOCOL_LENGTH>NET\_MAX\_PTZ\_PROTOCOL\_LENGTH</a>];<br/>

}SDK\_PTZPROTOCOLFUNC;<br/>

<label style="color:#c33">//All channel pan protocol</label><br/>

typedef struct SDK\_STR\_PTZCONFIG\_ALL<br/>
{

<a href="http://open.xmeye.net/zh/#STR_CONFIG_PTZ>SDK\_STR\_CONFIG\_PTZ</a> ptzAll[<a href="http://open.xmeye.net/zh/#NET_MAX_CHANNUM>NET\_MAX\_CHANNUM</a>];<br/>

}SDK\_STR\_PTZCONFIG\_ALL;<br/>




<label style="color:#c33">//RS485</label><br/>

typedef struct SDK\_STR\_RS485CONFIG\_ALL<br/>
{

<a href="http://open.xmeye.net/zh/#STR_CONFIG_PTZ>SDK\_STR\_CONFIG\_PTZ</a> ptzAll[<a href="http://open.xmeye.net/zh/#NET_MAX_CHANNUM>NET\_MAX\_CHANNUM</a>];

}SDK\_STR\_RS485CONFIG_ALL;

<label style="color:#c33">User management function data structure</label>


typedef struct\_OPR\_RIGHT<br/>
{

char name[<a href="http://open.xmeye.net/zh/#NET_MAX_USER_LENGTH">NET\_MAX\_USER\_LENGTH</a>];<br/>

}OPR\_RIGHT;<br/>




typedef struct\ _USER\_INFO<br/>
{

int rigthNum;<br/>

char rights[<a href="http://open.xmeye.net/zh/#NET_MAX_RIGTH_NUM">NET\_MAX\_RIGTH\_NUM][<a href="http://open.xmeye.net/zh/#NET_MAX_USER_LENGTH">NET\_MAX\_USER\_LENGTH</a>];<br/>

char Groupname[<a href="http://open.xmeye.net/zh/#NET_MAX_USER_LENGTH">NET\_MAX\_USER\_LENGTH</a>];<br/>

char memo[<a href="http://open.xmeye.net/zh/#NET_MAX_USER_LENGTH">NET\_MAX\_USER\_LENGTH</a>];<br/>

char name[<a href="http://open.xmeye.net/zh/#NET_MAX_USER_LENGTH">NET\_MAX\_USER\_LENGTH</a>];<br/>

char passWord[<a href="http://open.xmeye.net/zh/#NET_MAX_USER_LENGTH">NET\_MAX\_USER\_LENGTH</a>];<br/>

bool reserved; <label style="color:#c33">//Whether to retain</label><br/>

bool shareable; <label style="color:#c33">//Does this user allow multiplex 1- multiplexing, and 0- does not reuse?</label><br/>

}USER\_INFO;<br/>




typedef struct \_USER\_GROUP\_INFO<br/>
{

int rigthNum;<br/>

char memo[<a href="http://open.xmeye.net/zh/#NET_MAX_USER_LENGTH">NET\_MAX\_USER\_LENGTH</a>]; <br/>

char name[<a href="http://open.xmeye.net/zh/#NET_MAX_USER_LENGTH">NET\_MAX\_USER\_LENGTH</a>];<br/>

char rights[<a href="http://open.xmeye.net/zh/#NET_MAX_RIGTH_NUM">NET\_MAX\_RIGTH\_NUM][<a href="http://open.xmeye.net/zh/#NET_MAX_USER_LENGTH">NET\_MAX\_USER\_LENGTH];  <label style="color:#c33">//Permissions list</label><br/>

}USER\_GROUP\_INFO;<br/>




<label style="color:#c33">//User information configuration structure</label><br/>

typedef struct\_USER\_MANAGE\_INFO<br/>
{

int rigthNum;<br/>

<a href="http://open.xmeye.net/zh/#OPR_RIGHT">OPR\_RIGHT</a> rightList[<a href="http://open.xmeye.net/zh/#NET_MAX_RIGTH_NUM">NET\_MAX\_RIGTH\_NUM</a>];<br/>

int groupNum;<br/>

<a href="http://open.xmeye.net/zh/#USER_GROUP_INFO">USER\_GROUP\_INFO groupList[<a href="http://open.xmeye.net/zh/#NET_MAX_GROUP_NUM">NET\_MAX\_GROUP\_NUM</a>];<br/>

int userNum;<br/>

<a href="http://open.xmeye.net/zh/#USER_INFO">USER_INFO</a> userList[<a href="http://open.xmeye.net/zh/#NET_MAX_USER_NUM">NET\_MAX\_USER\_NUM</a>];<br/>

}<a href="http://open.xmeye.net/zh/#USER_MANAGE_INFO">USER\_MANAGE\_INFO</a>;<br/>




<label style="color:#c33">//Modify user</label><br/>

typedef struct\_CONF\_MODIFYUSER<br/>
{

char UserName[<a href="http://open.xmeye.net/zh/#NET_MAX_USER_LENGTH">NET\_MAX\_USER\_LENGTH</a>];<br/>

<a href="http://open.xmeye.net/zh/#USER_INFO">USER\_INFO</a> User;<br/>

}<a href="http://open.xmeye.net/zh/#CONF_MODIFYUSER">CONF\_MODIFYUSER</a>;<br/>




<label style="color:#c33">//Modify group</label><br/>

typedef struct\_CONF\_MODIFYGROUP<br/>
{

char GroupName[<a href="http://open.xmeye.net/zh/#NET_MAX_USER_LENGTH">NET\_MAX\_USER\_LENGTH</a>];<br/>

<a href="http://open.xmeye.net/zh/#USER_GROUP_INFO">USER\_GROUP\_INFO </a>Group;<br/>

}<a href="http://open.xmeye.net/zh/#CONF_MODIFYGROUP">CONF_MODIFYGROUP;<br/>




<label style="color:#c33">/// Modify user password request</label><br/>

struct\_CONF\_MODIFY\_PSW<br/>
{

char sUserName[<a href="http://open.xmeye.net/zh/#NET_MAX_USER_LENGTH">NET\_MAX\_USER\_LENGTH</a>];<br/>

char Password[<a href="http://open.xmeye.net/zh/#NET_MAX_USER_LENGTH">NET\_MAX\_USER\_LENGTH</a>];<br/>

char NewPassword[<a href="http://open.xmeye.net/zh/#NET_MAX_USER_LENGTH">NET\_MAX\_USER\_LENGTH</a>];<br/>

};

<label style="color:#c33">log information</label><br/>


 #define <a href="http://open.xmeye.net/zh/#NET_MAX_RETURNED_LOGLIST">NET\_MAX\_RETURNED\_LOGLIST</a>   1024      <label style="color:#c33"> //Maximum number of logs</label><br/>

<label style="color:#c33">/// Log query condition</label><br/>

struct <a href="http://open.xmeye.net/zh/#LogSearchCondition">SDK\_LogSearchCondition</a><br/>
{

int nType;   <label style="color:#c33"> ///< Log type</label><br/>

 int iLogPosition;           <label style="color:#c33"> ///< The log pointer from the end of the last query</label><br/>

<a href="http://open.xmeye.net/zh/#SYSTEM_TIME">SDK\_SYSTEM\_TIME </a>stBeginTime;    <label style="color:#c33">///< Query log start time</label><br/>

<a href="http://open.xmeye.net/zh/#SYSTEM_TIME">SDK\_SYSTEM\_TIME</a> stEndTime;     <label style="color:#c33"> ///< Query log end time</label><br/>

};

struct <a href="http://open.xmeye.net/zh/#LogItem">SDK\_LogItem</a><br/>
{

 char sType[24];    <label style="color:#c33">///< log type</label><br/>

 char sUser[32];   <label style="color:#c33"> ///< log user</label><br/>

 char sData[68];   <label style="color:#c33"> ///< log data</label><br/>

 <a href="http://open.xmeye.net/zh/#SYSTEM_TIME">SDK\_SYSTEM\_TIME </a>stLogTime;  <label style="color:#c33">///< log time</label><br/>

 int iLogPosition;       <label style="color:#c33"> ///< The log pointer from the end of the last query</label><br/>

};

<label style="color:#c33">//Log return information</label><br/>

struct <a href="http://open.xmeye.net/zh/#LogList">SDK\_LogList</a><br/>
{

 int iNumLog;<br/>

 <a href="http://open.xmeye.net/zh/#LogItem">SDK\_LogItem</a> Logs[<a href="http://open.xmeye.net/zh/#NET_MAX_RETURNED_LOGLIST">NET\_MAX\_RETURNED\_LOGLIST</a>];<br/>

};

<label style="color:#c33">Query the return data structure of the hard disk information</label><br/>
enum<br/>
{

SDK_MAX_DRIVER_PER_DISK = 4,		<label style="color:#c33">///< The maximum number of partitions per disk</label><br/>

SDK_MAX_DISK_PER_MACHINE = 8,		<label style="color:#c33">///< Supports 8 hard disks at most</label><br/>

};

<label style="color:#c33">//HDD management</label><br/>

typedef struct <a href="http://open.xmeye.net/zh/#STORAGEDISK">SDK\_STORAGEDISK</a><br/>
{

int		iPhysicalNo;<br/>

int		iPartNumber;		<label style="color:#c33">// Partition number</label><br/>

<a href="http://open.xmeye.net/zh/#DriverInformation">SDK\_DriverInformation</a> diPartitions[<a href="http://open.xmeye.net/zh/#MAX_DRIVER_PER_DISK">SDK\_MAX\_DRIVER\_PER\_DISK</a>];<br/>

}SDK\_STORAGEDISK;<br/>




typedef struct <a href="http://open.xmeye.net/zh/#StorageDeviceInformationAll">SDK\_StorageDeviceInformationAll</a><br/>
{

int iDiskNumber;<br/>

<a href="http://open.xmeye.net/zh/#STORAGEDISK">SDK\_STORAGEDISK </a>vStorageDeviceInfoAll[<a href="http://open.xmeye.net/zh/#MAX_DISK_PER_MACHINE">SDK\_MAX\_DISK\_PER\_MACHINE</a>];<br/>

}SDK\_StorageDeviceInformationAll;<br/>

<label style="color:#c33">Network monitoring</label><br/>

typedef struct <a href="http://open.xmeye.net/zh/#CLIENTINFO">H264\_DVR\_CLIENTINFO</a><br/>
{

int nChannel;	<label style="color:#c33">//channel number</label><br/>

int nStream;	<label style="color:#c33">//0 represents the primary bitstream, and 1 represents the bitstream</label><br/>

int nMode;	<label style="color:#c33">//0：TCP mode, 1:UDP mode, 2: multicast mode, 3 - RTP mode, 4- audio and video separation(TCP)</label><br/>

int nComType;	<label style="color:#c33">//Only the combination coding channel is effective, and the jigsaw patterns of combinatorial coding channels are combined</label><br/>

  void* hWnd;    <label style="color:#c33"> //Preview the output window handle (for NULL, network data and decoding playback separately)</label><br/>

}*LPH264\_DVR\_CLIENTINFO;
<br/><br/>

<div name="jiegouti4" id="jiegouti4" style="font-size:15px;"><b>3.4Network alarm information</b></div>




typedef struct <a href="http://open.xmeye.net/zh/#NetAlarmInfo">SDK\_NetAlarmInfo</a><br/>
{

int iEvent;   <label style="color:#c33">//Not currently in use</label><br/>

int iState;   <label style="color:#c33">//Each bit represents a channel, the bit0: first channel, the 0- no alarm, the 1- alarm, and so on</label><br/>

}SDK\_NetAlarmInfo;<br/>





<label style="color:#c33">///< Alarm center settings</label><br/>

typedef struct <a href="http://open.xmeye.net/zh/#NetAlarmCenterConfig">SDK\_NetAlarmCenterConfig</a><br/>
{

bool bEnable;	<label style="color:#c33">///< Whether to open</label><br/>

char sAlarmServerKey[<a href="http://open.xmeye.net/zh/#NET_NAME_PASSWORD_LEN">NET\_NAME\_PASSWORD\_LEN</a>];	<label style="color:#c33">///< Alarm Center protocol type name,</label><br/>

<a href="http://open.xmeye.net/zh/#RemoteServerConfig">SDK\_RemoteServerConfig</a> Server;			<label style="color:#c33">///< Alarm center server</label><br/>

bool bAlarm;<br/>

bool bLog;<br/>

}SDK\_NetAlarmCenterConfig;<br/>




typedef struct <a href="http://open.xmeye.net/zh/#NetAlarmServerConfigAll">SDK\_NetAlarmServerConfigAll</a><br/>
{

<a href="http://open.xmeye.net/zh/#NetAlarmCenterConfig">SDK\_NetAlarmCenterConfig</a> vAlarmServerConfigAll[<a href="http://open.xmeye.net/zh/#NET_MAX_ALARMSERVER_TYPE">NET\_MAX\_ALARMSERVER\_TYPE</a>];<br/>

}SDK\_NetAlarmServerConfigAll;<br/>




<label style="color:#c33">// Alert Center message type</label><br/>

enum <a href="http://open.xmeye.net/zh/#AlarmCenterMsgType">SDK\_AlarmCenterMsgType</a><br/>
{

SDK\_ALARMCENTER\_ALARM,<br/>

SDK\_ALARMCENTER\_LOG,<br/>

};




<label style="color:#c33">// Alert Center message type</label><br/>

enum <a href="http://open.xmeye.net/zh/#AlarmCenterStatus">SDK\_AlarmCenterStatus</a><br/>
{

SDK\_AC\_START,<br/>

SDK\_AC\_STOP,<br/>

};




<label style="color:#c33">// Alert Center message content</label><br/>

typedef struct <a href="http://open.xmeye.net/zh/#NetAlarmCenterMsg">SDK\_NetAlarmCenterMsg</a><br/>
{

CONFIG_IPAddress HostIP;		<label style="color:#c33">///< device IP</label><br/>

int  nChannel;             <label style="color:#c33">///< channel </label><br/>

int  nType;               <label style="color:#c33">///< type see AlarmCenterMsgType</label>v

int  nStatus;              <label style="color:#c33">///< status see AlarmCenterStatus</label><br/>

<a href="http://open.xmeye.net/zh/#SYSTEM_TIME">SDK\_SYSTEM_TIME</a> Time;         <label style="color:#c33">///< Occurrence time</label><br/>

char sEvent[<a href="http://open.xmeye.net/zh/#NET_MAX_INFO_LEN">NET\_MAX\_INFO\_LEN</a>];  	<label style="color:#c33">///< Event</label><br/>

char sSerialID[<a href="http://open.xmeye.net/zh/#NET_MAX_MAC_LEN">NET\_MAX\_MAC\_LEN</a>]; <label style="color:#c33">	///< Device serial number</label><br/>

char sDescrip[<a href="http://open.xmeye.net/zh/#NET_MAX_INFO_LEN">NET\_MAX\_INFO\_LEN</a>]; <label style="color:#c33"> ///< describe</label><br/>

}SDK\_NetAlarmCenterMsg;
<br/><br/>

<div name="jiegouti5" id="jiegouti5" style="font-size:15px;"><b>3.5Storage device control information</b></div>



enum <a href="http://open.xmeye.net/zh/#StorageDeviceControlTypes">SDK\_StorageDeviceControlTypes</a><br/>
{

SDK\_STORAGE\_DEVICE\_CONTROL\_SETTYPE,	<label style="color:#c33">///< Setting type</label><br/>

SDK\_STORAGE\_DEVICE\_CONTROL\_RECOVER,	<label style="color:#c33">///< Recovery error</label><br/>

SDK\_STORAGE\_DEVICE\_CONTROL\_PARTITIONS,	<label style="color:#c33">///< Partitioning operation</label><br/>

SDK\_STORAGE\_DEVICE\_CONTROL\_CLEAR,		<label style="color:#c33">///< Cleanup operation</label><br/>



SDK\_STORAGE\_DEVICE\_CONTROL\_ADDNAS,	<label style="color:#c33">///<Add NAS</label><br/>

SDK\_STORAGE\_DEVICE\_CONTROL\_CHANGENAS,	<label style="color:#c33">///modify NAS</label><br/>

SDK\_STORAGE\_DEVICE\_CONTROL\_DELNAS,	<label style="color:#c33">///<delete NAS</label><br/>

SDK_STORAGE\_DEVICE\_CONTROL\_NR,<br/>

};
<br/><br/>


<div name="jiegouti6" id="jiegouti6" style="font-size:15px;"><b>3.6RTSP information</b></div>


typedef struct <a href="http://open.xmeye.net/zh/#NetRTSPConfig">SDK\_NetRTSPConfig</a><br/>
{

bool bServer;<br/>

bool bClient;<br/>

<a href="http://open.xmeye.net/zh/#RemoteServerConfig">SDK\_RemoteServerConfig </a>Server;		<label style="color:#c33">///< Server mode</label><br/>

<a href="http://open.xmeye.net/zh/#RemoteServerConfig">SDK\_RemoteServerConfig</a> Client;		<label style="color:#c33">///< Client mode</label><br/>

}SDK\_NetRTSPConfig;
<br/><br/>

<div name="jiegouti7" id="jiegouti7" style="font-size:15px;"><b>3.7互信互通</b></div>



typedef struct <a href="http://open.xmeye.net/zh/#CONFIG_NET_MEGA">SDK\_CONFIG\_NET\_MEGA</a><br/>
{

bool bEnable;<br/>

bool bNetManEnable;<br/>

CONFIG_IPAddress ServerIP;<br/>

int  iServerPort;<br/>

char sDeviceId[32];<br/>

char sUserName[24];<br/>

char sPasswd[32];<br/>

int  iMaxCon;<br/>

int  iVideoPort;<br/>

int  iAudioPort;<br/>

int  iMsgPort;<br/>

int  iUpdatePort;<br/>

}SDK\_CONFIG\_NET\_MEGA;<br/>
<br/><br/>


<div name="jiegouti8" id="jiegouti8" style="font-size:15px;"><b>3.8新望platform</b></div>


typedef struct <a href="http://open.xmeye.net/zh/#CONFIG_NET_XINGWANG">SDK\_CONFIG\_NET\_XINGWANG</a><br/>
{

bool bEnable;<br/>

bool bSyncTime;<br/>

bool bSubStream;<br/>

CONFIG_IPAddress ServerIP;<br/>

int  iServerPort;<br/>

int  iDownLoadPort;<br/>

char sPasswd[32];<br/>

char szSID[32];<br/>

}SDK\_CONFIG\_NET\_XINGWANG;
<br/><br/>


<div name="jiegouti9" id="jiegouti9" style="font-size:15px;"><b>3.9视搜platform</b></div>


typedef struct <a href="http://open.xmeye.net/zh/#CONFIG_NET_SHISOU">SDK\_CONFIG\_NET\_SHISOU</a><br/>
{

bool bEnable;<br/>

SDK_RemoteServerConfig Server;<br/>

char szSID[<a href="http://open.xmeye.net/zh/#NET_MAX_USERNAME\_LENGTH">NET\_MAX\_USERNAME\_LENGTH</a>];<br/>

}SDK\_CONFIG\_NET\_SHISOU;
<br/><br/>


<div name="jiegouti10" id="jiegouti10" style="font-size:15px;"><b>3.10VVEYE platform</b></div>


typedef struct <a href="http://open.xmeye.net/zh/#CONFIG">SDK\_CONFIG\_NET\_VVEYE</a><br/>
{

bool bEnable;<br/>

bool bCorpEnable;        <label style="color:#c33">//You only need to set up Server when you use the enterprise server</label><br/>

<a href="http://open.xmeye.net/zh/#RemoteServerConfig">SDK\_RemoteServerConfig </a>Server;<br/>

char szDeviceName[<a href="http://open.xmeye.net/zh/#NET_MAX_USERNAME_LENGTH">NET\_MAX\_USERNAME\_LENGTH</a>];<br/>

}SDK\_CONFIG\_NET\_VVEYE;
<br/><br/>


<div name="jiegouti11" id="jiegouti11" style="font-size:15px;"><b>3.11Media packages and package information</b></div>



typedef enum <a href="http://open.xmeye.net/zh/#SERIAL_TYPE">SERIAL\_TYPE</a><br/>
{

RS232 = 0,

RS485 = 1,

}SERIAL\_TYPE;







enum <a href="http://open.xmeye.net/zh/#MEDIA_PACK_TYPE">MEDIA\_PACK\_TYPE</a><br/>
{

FILE\_HEAD =	0,	   	<label style="color:#c33">// header file</label><br/>

VIDEO\_I\_FRAME = 1,		<label style="color:#c33">// Video I frames</label><br/>

VIDEO\_B\_FRAME =	2,		<label style="color:#c33">// Video B frames</label><br/>

VIDEO\_P\_FRAME = 3,		<label style="color:#c33">// Video P frames</label><br/>

VIDEO\_BP\_FRAME = 4,		<label style="color:#c33">// Video BP frames</label><br/>

VIDEO\_BBP\_FRAME	= 5,		<label style="color:#c33">// Video B frame, B frame, P frame</label><br/>

VIDEO\_J\_FRAME = 6,		<label style="color:#c33">// image frame</label><br/>

AUDIO\_PACKET = 10,		<label style="color:#c33">// audio frame</label><br/>

};




typedef struct<br/>
{

int	   nPacketType;	<label style="color:#c33">// Packet type,see MEDIA\_PACK\_TYPE</label><br/>

char*	    pPacketBuffer;	<label style="color:#c33">// Cache address</label><br/>

unsigned int   dwPacketSize;	<label style="color:#c33">// Packet size</label><br/>



// Absolute timescale<br/>

int	   nYear;	    <label style="color:#c33">// 时标:year</label><br/>

int	   nMonth;	    <label style="color:#c33">// 时标:month</label><br/>

int	   nDay;	    <label style="color:#c33">// 时标:day</label><br/>

int	   nHour;	    <label style="color:#c33">// 时标:hour</label><br/>

int	   nMinute;	    <label style="color:#c33">// 时标:minute</label><br/>

int       nSecond;	    <label style="color:#c33">// 时标:second</label><br/>

unsigned int   dwTimeStamp;	<label style="color:#c33">// The relative timescale is low, in milliseconds</label><br/>

unsigned int   dwTimeStampHigh; <label style="color:#c33">//The relative time scale is in milliseconds</label><br/>

unsigned int   dwFrameNum;     <label style="color:#c33">//Frame number</label><br/>

unsigned int   dwFrameRate;    <label style="color:#c33">//frame rate</label><br/>

unsigned short  uWidth;       <label style="color:#c33">//Image width</label><br/>

unsigned short  uHeight;      <label style="color:#c33">//Image height</label><br/>

unsigned int   Reserved[6];    <label style="color:#c33">//retain</label><br/>

} <a href="http://open.xmeye.net/zh/#PACKET_INFO_EX">PACKET\_INFO\_EX</a><br/>;


typedef struct <a href="http://open.xmeye.net/zh/#OEMInfo">SDK\_OEMInfo</a><br/>
{

int nOEMID;   <label style="color:#c33"> //OEM ID</label><br/>

char sCompanyName[<a href="http://open.xmeye.net/zh/#NET_MAX_USERNAME_LENGTH">NET\_MAX\_USERNAME\_LENGTH</a>]; <label style="color:#c33">//Company name</label><br/>

char sTel[<a href="http://open.xmeye.net/zh/#NET_MAX_USERNAME_LENGTH">NET\_MAX\_USERNAME\_LENGTH</a>];      <label style="color:#c33">//Telephone</label><br/>

char sAddr[<a href="http://open.xmeye.net/zh/#NET_MAX_USERNAME_LENGTH">NET\_MAX\_USERNAME\_LENGTH</a>];      <label style="color:#c33">//Address</label><br/>

}SDK\_OEMInfo;<br/>


typedef struct\_TransComChannel  <label style="color:#c33">//Transparent window</label><br/>
{

<a href="http://open.xmeye.net/zh/#SERIAL_TYPE">SERIAL\_TYPE</a> TransComType;	<label style="color:#c33">//SERIAL\_TYPE</label><br/>

unsigned int baudrate;<br/>

unsigned int databits;<br/>

unsigned int stopbits;<br/>

unsigned int parity;<br/>

} <a href="http://open.xmeye.net/zh/#TransComChannel">TransComChannel</a><br/>;

typedef enum <a href="http://open.xmeye.net/zh/#State_Type">SDK\_State\_Type</a><br/>
{

DEV\_STATE\_DDNS=0,</label><br/>

}SDK\_State\_Type;<br/>




<label style="color:#c33">//Camera parameters.....</label><br/>

<label style="color:#c33">//Exposure configuration</label><br/>

typedef struct <a href="http://open.xmeye.net/zh/#ExposureCfg">SDK\_ExposureCfg</a><br/>
{

int  level;    <label style="color:#c33">	//Exposure level</label><br/>

unsigned int leastTime;	<label style="color:#c33">//Automatic exposure time limit or manual exposure time, in units of microseconds</label><br/>

unsigned int mostTime; <label style="color:#c33">	//Automatic exposure time limit, unit microsecond</label><br/>

}SDK\_ExposureCfg;<br/>




 <label style="color:#c33">//Gain configuration</label><br/>

typedef struct <a href="http://open.xmeye.net/zh/#GainCfg">SDK\_GainCfg</a><br/>
{

int gain;   <label style="color:#c33"> //Automatic gain cap (automatic gain enable) or fixed gain value</label><br/>

int autoGain;<label style="color:#c33">//Automatic gain is enabled, 0: does not turn on, 1: opens</label><br/>

}SDK\_GainCfg;<br/>




 <label style="color:#c33">//Network camera configuration</label><br/>

typedef struct <a href="http://open.xmeye.net/zh/#CameraParam">SDK\_CameraParam</a><br/>
{

unsigned int whiteBalance;      <label style="color:#c33">//white balance</label><br/>

unsigned int dayNightColor;    <label style="color:#c33"> //Day and night mode, with color, automatic switching and black and white</label><br/>

int elecLevel;             <label style="color:#c33">	//Reference level value</label><br/>

unsigned int apertureMode;     <label style="color:#c33"> //Auto iris mode</label><br/>

unsigned int BLCMode;        <label style="color:#c33">  //Backlight compensation mode</label><br/>

<a href="http://open.xmeye.net/zh/#ExposureCfg">SDK\_ExposureCfg </a>exposureConfig;	 <label style="color:#c33">//Exposure configuration</label><br/>

<a href="http://open.xmeye.net/zh/#GainCfg">SDK\_GainCfg</a>     gainConfig;    <label style="color:#c33">//Gain configuration</label><br/>

unsigned int PictureFlip;		<label style="color:#c33">//Picture up and down</label><br/>

unsigned int PictureMirror;	<label style="color:#c33">//Flip image (mirror image)</label><br/>

unsigned int RejectFlicker;	<label style="color:#c33">//Anti flash function of daylight lamp</label><br/>

unsigned int EsShutter;		<label style="color:#c33">//Electronic slow shutter function</label><br/>

int ircut_mode;		<label style="color:#c33">//IR-CUT = 0 lamp synchronous switching switch,1 = Automatic switchover</label><br/>

int dnc_thr;		<label style="color:#c33">//Day night transition threshold</label><br/>

int ae_sensitivity;<label style="color:#c33">	//ae Sensitivity configuration</label><br/>

int Day_nfLevel;	<label style="color:#c33">//noise filter Level, 0-5,0 does not filter, and the greater the 1-5 value, the more obvious the filtering effect</label><br/>

int Night_nfLevel;<br/>

int Ircut_swap;		<label style="color:#c33">//ircut Normal order = 0 ,Reverse order = 1</label><br/>

int high_light;     <label style="color:#c33">//Highlight suppression function, 0~255, defaults to 16</label><br/>

}SDK\_CameraParam;<br/>




<label style="color:#c33">//All camera configurations</label><br/>

typedef struct <a href="http://open.xmeye.net/zh/#AllCameraParam">SDK\_AllCameraParam</a><br/>
{

SDK\_CameraParam vCameraParamAll[<a href="http://open.xmeye.net/zh/#NET_MAX_CHANNUM">NET\_MAX\_CHANNUM</a>];  <label style="color:#c33"> //All channels</label>

}SDK\_AllCameraParam;




<label style="color:#c33">//Exposure ability level</label>

typedef struct <a href="http://open.xmeye.net/zh/#CameraAbility">SDK\_CameraAbility</a><br/>
{

int  count;      			<label style="color:#c33">//Support exposure speed quantity</label><br/>

unsigned int speeds[<a href="http://open.xmeye.net/zh/#CAMERAPARA_MAXNUM">CAMERAPARA_MAXNUM</a>];  <label style="color:#c33">//Exposure speed</label><br/>

int  status;     		    <label style="color:#c33">//The normal working state > = 0 ,< 0 abnormal</label><br/>

int  elecLevel;  			<label style="color:#c33">//Reference level value</label><br/>

int  luminance;  			<label style="color:#c33">//Average brightness</label><br/>

char pVersion[64];			<label style="color:#c33">//xm 2a Edition</label><br/>

char isFishLens; <label style="color:#c33">//Is it a fisheye lens? If it is, then you need app and PC to do the image correction</label><br/>

char resv1[3];   <label style="color:#c33">//Reservations, if you increase the membership of type char, use here first</label><br/>

char reserve[28];<label style="color:#c33">//Reservations, if added to type int members, use here</label><br/>

}SDK\_CameraAbility;
<br/><br/>


<div name="jiegouti12" id="jiegouti12" style="font-size:15px;"><b>3.12Local play control</b></div>


enum <a href="http://open.xmeye.net/zh/#LoalPlayAction">SDK\_LoalPlayAction</a><br/>
{

SDK\_Local\_PLAY\_PAUSE,	<label style="color:#c33">/*<! Pause play */</label><br/>

SDK\_Local\_PLAY\_CONTINUE,	<label style="color:#c33">/*<! Play on again */</label><br/>

SDK\_Local\_PLAY\_FAST,	<label style="color:#c33">/*<! Accelerated playback */</label><br/>

SDK\_Local\_PLAY\_SLOW,	<label style="color:#c33">/*<! Slow playback */</label><br/>
};
<br/><br/>

<div name="jiegouti13" id="jiegouti13" style="font-size:15px;"><b>3.13 Active service</b></div>




<label style="color:#c33">//Active service callback data</label><br/>

typedef struct <a href="http://open.xmeye.net/zh/#ACTIVEREG_INFO">H264\_DVR\_ACTIVEREG\_INFO</a><br/>
{

char deviceSarialID[64];		<label style="color:#c33">//The device serial number is assigned 0 if greater than 64 bits</label>

<a href="http://open.xmeye.net/zh/#DEVICEINFO">H264\_DVR\_DEVICEINFO </a>deviceInfo;	<label style="color:#c33">//Device information</label>

char IP[<a href="http://open.xmeye.net/zh/#IP_SIZE">IP\_SIZE</a>];   		<label style="color:#c33">//Outer net IP</label>

}H264\_DVR\_ACTIVEREG\_INFO;

<br/><br/>
<div name="jiegouti14" id="jiegouti14" style="font-size:15px;"><b>3.14Sub connection type</b></div>




typedef enum <a href="http://open.xmeye.net/zh/#SubConnType">SubConnType</a><br/>
{

conn\_realTimePlay=1,

conn\_talk,

conn\_playback

}SubConnType;



<br/><br/>
<div name="jiegouti15" id="jiegouti15" style="font-size:15px;"><b>3.15connection type</b></div>



<label style="color:#c33">//Register with device</label>

enum <a href="http://open.xmeye.net/zh/#SocketStyle">SocketStyle</a><br/>
{

TCPSOCKET=0,

UDPSOCKET,	

PLUGLANSOCKET=4,		<label style="color:#c33">//Socket LAN login</label>

PLUGOUTERSOCKET,		<label style="color:#c33">//Socket extranet landing</label>

P2P\_TUTKSOCKET,			<label style="color:#c33">//TUTK P2P</label>

 SOCKETNR

};



<br/><br/>
<div name="jiegouti16" id="jiegouti16" style="font-size:15px;"><b>3.16Search protocol type</b></div>


typedef enum <a href="http://open.xmeye.net/zh/#TransferProtocol_V2">SDK\_TransferProtocol\_V2</a><br/>
{

SDK\_TRANSFER\_PROTOCOL\_NETIP,

SDK\_TRANSFER\_PROTOCOL\_ONVIF,

SDK\_TRANSFER\_PROTOCOL\_MAC,

SDK\_TRANSFER\_PROTOCOL\_NAT,

SDK\_TRANSFER\_PROTOCOL\_DAHUA,

SDK\_TRANSFER\_PROTOCOL\_RTSP,

SDK\_TRANSFER\_PROTOCOL\_NETIPV6,

SDK\_TRANSFER\_PROTOCOL\_NR_V2,

SDK\_TRANSFER\_PROTOCOL\_ONVIF\_DEFAULT = 128,

SDK\_TRANSFER\_PROTOCOL\_ONVIF\_NR\_V2

}SDK\_TransferProtocol\_V2;



<br/><br/>
<div name="jiegouti17" id="jiegouti17" style="font-size:15px;"><b>3.17Search for basic types of online devices</b></div>



typedef struct <a href="http://open.xmeye.net/zh/#SDevicesState">SDK\_SDevicesState</a><br/>
{

int 	num;	 	<label style="color:#c33">//device number</label>

char uuid[32][32];	<label style="color:#c33">//Maximum 32 serial numbers</label>

int state[32];    	<label style="color:#c33">//0:Not online，1:online</label>

}SDK\_SDevicesState;
<br/><br/>
<div name="jiegouti17" id="jiegouti17" style="font-size:15px;"><b>3.18 Password retrieval</b></div>


<label style="color:#c33">//Security problem configuration</label>

struct SDK_PwdPresetQsPair <br/>
{

int questionIndex;				<label style="color:#c33">//Question serial number</label>

char strAnswer[256];			<label style="color:#c33">//answer</label>

};

struct SDK_PasswordSafety <br/>
{

bool bTipPageHide;				<label style="color:#c33">//Whether to hide the prompt page when the password is empty?</label>

SDK_PwdPresetQsPair PwdResetQs[4];	<label style="color:#c33">//Security questions and answers</label>

char resv[20];

};




<label style="color:#c33">//Get the password back problem</label><br/>

struct SDK_QuestionDelivery<br/>
{

int  nStrNum;		<label style="color:#c33">//problem number</label>

char vQuestionStr[7][256];

};
<br/><br/>
<div name="jiegouti17" id="jiegouti17" style="font-size:15px;"><b>3.19.License plate recognition and face recognition</b></div>


typedef struct SDK\_PlateDetectWhiteList<br/>
{ 

int iAddrCount;			   <label style="color:#c33">//Number of plates</label><br/>

char vWhiteListAddr[256][256]; <label style="color:#c33">// License plate list address</label><br/>

}SDK\_PlateDetectWhiteList;<br/>




<label style="color:#c33">//License plate detection; lifting lever control</label><br/>

typedef struct SDK\_PlateDetectLiftBar<br/>
{ 

bool bLiftBarCmd;<br/>

int	iChannel;<br/>

}SDK\_PlateDetectLiftBar;<br/>




<label style="color:#c33">//Alarm callback type</label><br/>

enum <br/>
{ 

ALARM\_TYPE = 1,<br/>

PUSH\_TYPE,<br/>

};




enum SDK_INTEL_PUSH_TYPE<br/>
{ 

SDK\_INTEL\_PUSH\_TYPE\_CAR_PLATE = 0,	<label style="color:#c33">//Represents the type of license plate</label><br/>

SDK\_INTEL\_PUSH\_TYPE\_FACE      = 1,	<label style="color:#c33">//Face type</label><br/>

SDK\_INTEL\_PUSH\_TYPE\_ALL       = 255,<label style="color:#c33">//Represents all types</label><br/>

};

enum SDK\_INTEL\_PUSH\_IMG\_TYPE<br/>
{ 

SDK\_INTEL\_PUSH\_IMG\_TYPE\_FULL   = 1,	<label style="color:#c33">//As long as the big picture</label><br/>

SDK\_INTEL\_PUSH\_IMG\_TYPE\_TARGET = 2,	<label style="color:#c33">//As long as the small picture</label><br/>

SDK\_INTEL\_PUSH\_IMG\_TYPE\_NR			<label style="color:#c33">//That means two kinds of Graphs</label><br/>

};




<label style="color:#c33">//License plate area</label><br/>

typedef struct SDK\_RECT\_S<br/>
{ 

int leftX;<br/>

int topY;<br/>

int width;<br/>

int height;<br/>

} SDK\_RECT\_S;<br/>




typedef struct SDK\_PLATE\_DETECT
{<br/>

char acPlateCode[20];	<label style="color:#c33">//The license plate number, the end of a string Terminator"\0" </label><br/>

char acPlateColor[4];	<label style="color:#c33">//The color of the license plate, yellow, blue, black and white, or "no" stands for unknown, string Terminator"\0"，The character encoding format is</label><br/>

}SDK\_PLATE\_DETECT;<br/>




typedef struct SDK\_FACE\_DETECT<br/>
{ 

char sex;           <label style="color:#c33"> //sex</label><br/>

char age;            <label style="color:#c33">//age</label><br/>

char resv[20];<br/>

}SDK\_FACE\_DETECT;<br/>




typedef struct SDK\_IA\_LPR\_TARGET\_INFO<br/>
{

SDK\_RECT\_S stRect;<br/>

union<br/>
{

SDK\_FACE\_DETECT face;<br/>

SDK\_PLATE\_DETECT plate;<br/>

}DETECT;<br/>

char resv[16];<br/>

}SDK\_IA\_LPR\_TARGET\_INFO;<br/>




typedef struct SDK\_IA\_LPR\_REC\_S<br/>
{<br/>

unsigned short resultType; <label style="color:#c33">//Recognition type, type 0:, license plate, 1:, face recognition  </label><br/>

unsigned short picSubType; <label style="color:#c33">//0:big picture  1:small picture</label><br/>

unsigned short picFormat;  <label style="color:#c33">//0:jpg  1:bmp   2:yuv</label><br/>

unsigned short tagNum;		<label style="color:#c33">//Target number</label><br/>

SDK\_IA\_LPR\_TARGET\_INFO pTargetInfo[8]; <label style="color:#c33">//Supports 8 goals at most</label><br/>

char resv[32];<br/>

}SDK\_IA\_LPR\_REC\_S;<br/>




typedef struct SDK\_PushRetData<br/>
{<br/>

SDK\_IA\_LPR\_REC\_S iaLprRecs;	<br/>

int nChannel;				<label style="color:#c33">//channel number</label><br/>

int nLenSize;				<label style="color:#c33">//image size</label><br/>

unsigned char* pBuffer;		<label style="color:#c33">//image data</label><br/>

}SDK\_PushRetData;<br/>




typedef struct SDK\_PlateDetectCfg<br/>
{<br/>

int iDefaultL;<label style="color:#c33">//default letters for example"A" </label><br/>

int iDefaultP;<label style="color:#c33">// The default Chinese characters, such as "zhe", are encoded in GB2312</label><br/>

int resv;<br/>

SDK\_RECT\_S astLpRect[7];<br/>

int iMaxWidth;<br/>

int iMinWidth;<br/>

}SDK\_PlateDetectCfg;<br/>




<label style="color:#c33">//License plate detection</label><br/>

typedef struct SDK\_PlateDetect<br/>
{<br/>

bool	bEnable;				<label style="color:#c33">//true:open,false:Close</label><br/>

SDK\_PlateDetectCfg stPlateParam;<label style="color:#c33">//License plate detection parameter setting</label><br/>

SDK\_EventHandler hEvent;			<label style="color:#c33">//Vehicle license plate detection linkage parameter</label><br/>

}SDK\_PlateDetect;<br/>




<label style="color:#c33">//Full passage license plate detection</label><br/>

typedef struct SDK_PlateDetectAll<br/>
{<br/>

SDK\_PlateDetect vPlateDetect[NET\_MAX\_CHANNUM];<br/>

}SDK\_PlateDetectAll;




<label style="color:#c33">//Face related structure：</label><br/>

typedef struct SDK\_FaceRect<br/>
{<br/>
int s32X;<br/>
int s32Y;<br/>
int u32Width;<br/>
int u32Height;<br/>
}SDK\_FaceRect;<br/>




<label style="color:#c33">//Face detection</label><br/>

typedef struct SDK\_FaceDetect<br/>
{<br/>

bool	bEnable;			<label style="color:#c33">//true:open,false:close</label><br/>

SDK\_FaceRect stFaceParam;	<label style="color:#c33">//Face detection parameter settings</label><br/>

SDK\_EventHandler hEvent;	<label style="color:#c33">//Human face detection linkage parameter</label><br/>

}SDK\_FaceDetect;




<label style="color:#c33">//Full channel face detection</label><br/>

typedef struct SDK\_FaceDetectAll<br/>
{<br/>

SDK\_FaceDetect vFaceDetect[NET\_MAX\_CHANNUM];<br/>

}SDK\_FaceDetectAll;<br/>



 
​