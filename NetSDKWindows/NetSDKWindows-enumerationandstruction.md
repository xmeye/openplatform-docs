## 宏定义

```
  #define NET_MAX_CHANNUM 	64    //最大通道个数
  #define NET_DECORDR_CH      64      //最大解码通道个数
  #define NET_MAX_USER_NUM	60	  //最多用户数
  #define NET_MAX_RIGTH_NUM	200	  //最多权限数
  #define NET_MAX_GROUP_NUM	50	  //最多组数
  #define NET_MAX_USER_LENGTH	32	  //用户名密码最大长度
  #define NET_MAX_COMBINE_NUM	2	  //最大组合编码通道数
  #define NET_MAX_DECORDR_CH  64      //最大解码通道个数	
  #define NET_MAX_DDNS_TYPE	5	  //支持的DDNS种类
  #define NET_MAX_ARSP_TYPE		5
  #define NET_MAX_ALARMSERVER_TYPE 5  //支持报警中心种类
  #define NET_MAX_SYSFUNC	20 //最多系统功能个数
  #define NET_MAX_PTZ_PROTOCOL_LENGTH32//云台协议名称最大长度
  #define NET_N_WEEKS		7	//星期数
  #define NET_N_TSECT		6			//时间段数
  #define NET_MD_REGION_ROW	32		//动态检测区域行数
  #define NET_COVERNUM	8			//覆盖区域数
  #define NET_MAX_FILTERIP_NUM64		//IP地址最大过滤数
  #define NET_NAME_PASSWORD_LEN	64		//用户名密码最大长度
  #define NET_MAX_PATH_LENGTH	  260	//路径长度
  #define NET_N_MIN_TSECT			2
  #define NET_MAX_RETURNED_LOGLIST128		//最多日志条数
  #define NET_MAX_MAC_LEN       32      //MAC地址字符最大长度
  #define NET_IW_ENCODING_TOKEN_MAX         128
  #define NET_MAX_AP_NUMBER       32    //SID最大数量，暂定10
  #define NET_MAX_INFO_LEN		     128
  #define NET_MAX_USERNAME_LENGTH		128
  #define NET_MAX_SERIALNO_LENGTH	 128  //最大解码通道个数
  #define NET_CHANNEL_NAME_MAX_LEN     64//通道名称最大长度
  #define NET_MAX_LINE_PER_OSD_AREA     12	//编码中一个OSD区域最多可以显示的字符行数

  //DDNS参数
  
  #define DDNS_MAX_DDNS_NAMELEN      64  		//主机名长度
  
  #define DDNS_MAX_DDNS_PWDLEN       32   	//密码长度
  
  #define DDNS_MAX_DDNS_IPSIZE      64   	//IP地址长度
  
  #define DDNS_MAX_DDNS_IDSIZE    32  //设备标识长度
  
  #define DDNS_MAX_SERIALINFO_SIZE  16 	//序列号以及用户名长度

  #define  NET_MAX_MSK_SIZE         128//掩码数组的大小


  //摄象机参数
  #define CAMERAPARA_MAXNUM        16//曝光能力中目前最大长度
  //短信最大数量
  #define NET_MAX_RECIVE_MSG_PHONE_COUNT3///<最大发生短信数量


  //VGA分辨率
  #define VGA_MAXNUM        32       //分辨率 种类
  #define VGA_NAME_LENGTH    10      	//分辨率 长度	

  //显示的设备列表(设备端搜索)
  #define DEV_LIST_SHOW     256

  //IP SIZE
  #define IP_SIZE        16
  #define  MAX_HVR_CHNCAP  16
  //DDNS服务器设备的信息


  //通道模式
  #define MAX_HVR_CHNCAP_CHN  32

  #define  NET_NAME_TOKEN_LEN 128

  #define  NET_NAME_URL_LEN  128
  #define  NET_NAME_ID_LEN   64
  #define  NET_MAX_POS_FUNC_KEYWORDS4 //POS功能中最多支持的关键字个数
  #define  NET_MAX_TITLE_DOT_BUF_LEN	64*24*24
  //硬盘信息
  #define NET_FSLEN  8  //从IConstraint::FS_LEN拷过来
```

## 枚举定义

### 云台操作类型

```
enum PTZ_ControlType
{
	TILT_UP = 0,					//上  
	TILT_DOWN,					//下       
	PAN_LEFT,					//左     
	PAN_RIGHT,					//右     
	PAN_LEFTTOP,					//左上       
	PAN_LEFTDOWN,					//左下  
	PAN_RIGTHTOP,					//右上
	PAN_RIGTHDOWN,					//右下
	ZOOM_OUT_1,					//变倍小
	ZOOM_IN_1,					//变倍大
	FOCUS_FAR,					//焦点后调
	FOCUS_NEAR,					//焦点前调
	IRIS_OPEN,					//光圈扩大
	IRIS_CLOSE,					//光圈缩小13
	EXTPTZ_OPERATION_ALARM,			    //报警功能 
	EXTPTZ_LAMP_ON,					//灯光开
	EXTPTZ_LAMP_OFF,				//灯光关
	EXTPTZ_POINT_SET_CONTROL,		    //设置预置点 
	EXTPTZ_POINT_DEL_CONTROL,		    //清除预置点 
	EXTPTZ_POINT_MOVE_CONTROL,		    //转预置点
	EXTPTZ_STARTPANCRUISE,			    //开始水平旋转
	EXTPTZ_STOPPANCRUISE,			    //停止水平旋转	
	EXTPTZ_SETLEFTBORDER,			    //设置左边界		
	EXTPTZ_SETRIGHTBORDER,			    //设置右边界	
	EXTPTZ_STARTLINESCAN,			    //自动扫描开始 
	EXTPTZ_CLOSELINESCAN,			    //自动扫描开停止 
	EXTPTZ_ADDTOLOOP,				//加入预置点到巡航  p1巡航线路	p2预置点值 p3时间间隔
	EXTPTZ_DELFROMLOOP,				//删除巡航中预置点  p1巡航线路	p2预置点值 p3时间间隔
	EXTPTZ_POINT_LOOP_CONTROL,		    //开始巡航
	EXTPTZ_POINT_STOP_LOOP_CONTROL,	        //停止巡航
	EXTPTZ_CLOSELOOP,				//清除巡航	p1巡航线路	
	EXTPTZ_FASTGOTO,				//快速定位	
	EXTPTZ_AUXIOPEN,	//辅助开关，关闭在子命令中//param1 参见SDK_PtzAuxStatus，param2传入具体数值
	EXTPTZ_OPERATION_MENU,			    //球机菜单操作，其中包括开，关，确定等等
	EXTPTZ_REVERSECOMM,				//镜头翻转
	EXTPTZ_OPERATION_RESET,			    //云台复位

	EXTPTZ_TOTAL,
};
```

### 设备配置命令枚举

H264_DVR_GetDevConfig、H264_DVR_SetDevConfig的命令定义

typedef enum _SDK_CONFIG_TYPE
{
E_SDK_CONFIG_NOTHING = 0,
E_SDK_CONFIG_USER,		//用户信息，包含了权限列表，用户列表和组列表---对应结构体<a href="http://open.xmeye.net/zh/#USER_MANAGE_INFO">USER\_MANAGE\_INFO</a></br> 
E_SDK_CONFIG_ADD_USER,		//增加用户---对应结构体<a href="http://open.xmeye.net/zh/#USER_INFO">USER\_INFO </a></br>   
E_SDK_CONFIG_MODIFY_USER,			//修改用户---对应结构体<a href="http://open.xmeye.net/zh/#CONF_MODIFYUSER">CONF\_MODIFYUSER </a></br>   
E_SDK_CONFIG_DELETE_USER,			//对应结构体<a href="">USER\_INFO </a></br>  
E_SDK_CONFIG_ADD_GROUP,				//增加组---对应结构体<a href="http://open.xmeye.net/zh/#USER_GROUP_INFO">USER\_GROUP\_INFO  </a></br> 
E_SDK_CONFIG_MODIFY_GROUP,			//修改组---对应结构体<a href="http://open.xmeye.net/zh/#CONF_MODIFYGROUP">CONF\_MODIFYGROUP  </a></br> 
E_SDK_COFIG_DELETE_GROUP,			//删除组---对应结构体<a href="http://open.xmeye.net/zh/#USER_GROUP_INFO">USER\_GROUP\_INFO </a></br>  
E_SDK_CONFIG_MODIFY_PSW,			//修改密码---对应结构体<a href="http://open.xmeye.net/zh/#CONF_MODIFY_PSW">\_CONF\_MODIFY\_PSW    </a></br>                 
E_SDK_CONFIG_ABILITY_SYSFUNC = 9,	    //支持的网络功能---对应结构体<a href="http://open.xmeye.net/zh/#SystemFunction">SDK\_SystemFunction </a></br>                 
E_SDK_CONFIG_ABILTY_ENCODE = 10,	    //首先获得编码能力---对应结构体<a href="http://open.xmeye.net/zh/#CONFIG_EncodeAbility">CONFIG\_EncodeAbility</a></br>           
E_SDK_CONFIG_ABILITY_PTZPRO,		    //云台协议---对应结构体<a href="http://open.xmeye.net/zh/#PTZPROTOCOLFUNC ">SDK\_PTZPROTOCOLFUNC    </a></br>         
E_SDK_COMFIG_ABILITY_COMMPRO,		    //串口协议---对应结构体<a href="http://open.xmeye.net/zh/#COMMFUNC">SDK\_COMMFUNC          </a></br>  
E_SDK_CONFIG_ABILITY_MOTION_FUNC,	    //动态检测块---对应结构体<a href="http://open.xmeye.net/zh/#MotionDetectFunction">SDK\_MotionDetectFunction </a></br>        
E_SDK_CONFIG_ABILITY_BLIND_FUNC,	    //视频遮挡块---对应结构体<a href="http://open.xmeye.net/zh/#BlindDetectFunction">SDK\_BlindDetectFunction  </a></br>            
E_SDK_CONFIG_ABILITY_DDNS_SERVER,	    //DDNS服务支持类型---对应结构体<a href="http://open.xmeye.net/zh/#DDNSServiceFunction">SDK\_DDNSServiceFunction</a></br>           
E_SDK_CONFIG_ABILITY_TALK,			//对讲编码类型---对应结构体<a href="http://open.xmeye.net/zh/#DDNSServiceFunction">SDK\_DDNSServiceFunction</a></br>            
E_SDK_CONFIG_SYSINFO = 17,			//系统信息---对应结构体<a href="http://open.xmeye.net/zh/#H264_DVR_DEVICEINFO">H264\_DVR\_DEVICEINFO   </a></br>         
E_SDK_CONFIG_SYSNORMAL,				//普通配置---对应结构体<a href="http://open.xmeye.net/zh/#CONFIG_NORMAL">SDK\_CONFIG\_NORMAL     </a></br>        
E_SDK_CONFIG_SYSENCODE,				//编码配置---对应结构体<a href="http://open.xmeye.net/zh/#EncodeConfigAll">SDK\_EncodeConfigAll    </a></br>       
E_SDK_CONFIG_SYSNET = 20,			//网络设置---对应结构体<a href="http://open.xmeye.net/zh/#CONFIG_NET_COMMON ">SDK\_CONFIG\_NET\_COMMON  </a></br>         
E_SDK_CONFIG_PTZ,				//云台页面---对应结构体<a href="http://open.xmeye.net/zh/#STR_PTZCONFIG_ALL">SDK\_STR\_PTZCONFIG\_ALL    </a></br>        
E_SDK_CONFIG_COMM,				//串口页面---对应结构体<a href="http://open.xmeye.net/zh/#CommConfigAll">SDK\_CommConfigAll       </a></br>     
E_SDK_CONFIG_RECORD,				//录像设置界面---对应结构体<a href="http://open.xmeye.net/zh/#RECORDCONFIG">SDK\_RECORDCONFIG      </a></br>     
E_SDK_CONFIG_MOTION,				//动态检测页面---对应结构体<a href="http://open.xmeye.net/zh/#MOTIONCONFIG">SDK\_MOTIONCONFIG      </a></br>    
E_SDK_CONFIG_SHELTER,				//视频遮挡---对应结构体<a href="http://open.xmeye.net/zh/#BLINDDETECTCONFIG">SDK\_BLINDDETECTCONFIG     </a></br>        
E_SDK_CONFIG_VIDEO_LOSS,  			//视频丢失---对应结构体<a href="http://open.xmeye.net/zh/#VIDEOLOSSCONFIG">SDK\_VIDEOLOSSCONFIG      </a></br>     
E_SDK_CONFIG_ALARM_IN,				//报警输入---对应结构体<a href="http://open.xmeye.net/zh/#ALARM_INPUTCONFIG">SDK\_ALARM\_INPUTCONFIG    </a></br>     
E_SDK_CONFIG_ALARM_OUT,				//报警输出---对应结构体<a href="http://open.xmeye.net/zh/#AlarmOutConfigAll">SDK\_AlarmOutConfigAll      </a></br>    
E_SDK_CONFIG_DISK_MANAGER,			//硬盘管理界面---对应结构体<a href="http://open.xmeye.net/zh/#StorageDeviceControl">SDK\_StorageDeviceControl  </a></br>         
E_SDK_CONFIG_OUT_MODE = 30,			//输出模式界面---对应结构体<a href="http://open.xmeye.net/zh/#VideoWidgetConfigAll">SDK\_VideoWidgetConfigAll   </a></br>         
E_SDK_CONFIG_CHANNEL_NAME,			//通道名称---对应结构体<a href="http://open.xmeye.net/zh/#ChannelNameConfigAll">SDK\_ChannelNameConfigAll   </a></br>            
E_SDK_CONFIG_AUTO,				//自动维护界面配置---对应结构体<a href="http://open.xmeye.net/zh/#AutoMaintainConfig">SDK\_AutoMaintainConfig    </a></br>           
E_SDK_CONFIG_DEFAULT,     			//恢复默认界面配置---对应结构体<a href="http://open.xmeye.net/zh/#SetDefaultConfigTypes">SDK\_SetDefaultConfigTypes </a></br>          
E_SDK_CONFIG_DISK_INFO,				//硬盘信息---对应结构体<a href="http://open.xmeye.net/zh/#StorageDeviceInformationAll">SDK\_StorageDeviceInformationAll </a></br>            
E_SDK_CONFIG_LOG_INFO,				//查询日志---对应结构体<a href="http://open.xmeye.net/zh/#LogList">SDK\_LogList      </a></br>       
E_SDK_CONFIG_NET_IPFILTER,			//黑名单配置---对应结构体<a href="http://open.xmeye.net/zh/#NetIPFilterConfig">SDK\_NetIPFilterConfig  </a></br>            
E_SDK_CONFIG_NET_DHCP,				//DHCP配置---对应结构体<a href="http://open.xmeye.net/zh/#NetDHCPConfigAll">SDK\_NetDHCPConfigAll   </a></br>         
E_SDK_CONFIG_NET_DDNS,				//DDNS信息---对应结构体<a href="http://open.xmeye.net/zh/#NetDDNSConfigALL">SDK\_NetDDNSConfigALL </a></br>          
E_SDK_CONFIG_NET_EMAIL,				//EMAIL---对应结构体<a href="http://open.xmeye.net/zh/#NetEmailConfig">SDK\_NetEmailConfig   </a></br>      
E_SDK_CONFIG_NET_MULTICAST = 40,	    //组播---对应结构体<a href="http://open.xmeye.net/zh/#NetMultiCastConfig">SDK\_NetMultiCastConfig </a></br>        
E_SDK_CONFIG_NET_NTP,				//NTP---对应结构体<a href="http://open.xmeye.net/zh/#NetNTPConfig">SDK\_NetNTPConfig   </a></br>        
E_SDK_CONFIG_NET_PPPOE,				//PPPOE---对应结构体<a href="http://open.xmeye.net/zh/#NetPPPoEConfig">SDK\_NetPPPoEConfig  </a></br>      
E_SDK_CONFIG_NET_DNS,				//DNS---对应结构体<a href="http://open.xmeye.net/zh/#NetDNSConfig">SDK\_NetDNSConfig   </a></br>        
E_SDK_CONFIG_NET_FTPSERVER,			//FTP---对应结构体<a href="http://open.xmeye.net/zh/#FtpServerConfig">SDK\_FtpServerConfig  </a></br>        
E_SDK_CONFIG_SYS_TIME,	   //系统时间---对应结构体<a href="http://open.xmeye.net/zh/#SYSTEM_TIME">SDK\_SYSTEM_TIME</a></br>(接口<a href="http://open.xmeye.net/zh/#SetSystemDateTime">H264\_DVR\_SetSystemDateTime</a></br>也可以实现)              
E_SDK_CONFIG_CLEAR_LOG,				//清除日志(接口<a href="http://open.xmeye.net/zh/#ControlDVR">H264_DVR\_ControlDVR)		          									

E_SDK_REBOOT_DEV,				//重启启动设备(接口<a href="http://open.xmeye.net/zh/#ControlDVR">H264\_DVR\_ControlDVR)</a></br>	          											

E_SDK_CONFIG_ABILITY_LANG,			//支持语言---对应结构体<a href="http://open.xmeye.net/zh/#MultiLangFunction">SDK\_MultiLangFunction </a></br>          
E_SDK_CONFIG_VIDEO_FORMAT,							
E_SDK_CONFIG_COMBINEENCODE = 50, //组合编码---对应结构体<a href="http://open.xmeye.net/zh/#CombineEncodeConfigAll">SDK\_CombineEncodeConfigAll </a></br>          
E_SDK_CONFIG_EXPORT,				//配置导出						             
E_SDK_CONFIG_IMPORT,				//配置导入           
E_SDK_LOG_EXPORT,				//日志导出												            		
E_SDK_CONFIG_COMBINEENCODEMODE, 	    //组合编码模式---对应结构体<a href="http://open.xmeye.net/zh/#CombEncodeModeAll">SDK\_CombEncodeModeAll </a></br>      
E_SDK_WORK_STATE,		    //运行状态---<a href="http://open.xmeye.net/zh/#DVR_WORKSTATE">SDK\_DVR\_WORKSTATE</a></br>(接口<a href="http://open.xmeye.net/zh/#GetDVRWorkState">H264\_DVR\_GetDVRWorkState</a></br>也可以获取)	           														

E_SDK_ABILITY_LANGLIST, 			//实际支持的语言集---对应结构体<a href="http://open.xmeye.net/zh/#MultiLangFunction">SDK\_MultiLangFunction</a></br>	       

E_SDK_CONFIG_NET_ARSP,				//ARSP---对应结构体<a href="http://open.xmeye.net/zh/#NetARSPConfigAll">SDK\_NetARSPConfigAll   </a></br>       
E_SDK_CONFIG_SNAP_STORAGE,			//抓图设置---对应结构体<a href="http://open.xmeye.net/zh/#SnapshotConfig">SDK\_SnapshotConfig  </a></br>            
E_SDK_CONFIG_NET_3G, 				//3G拨号---对应结构体<a href="http://open.xmeye.net/zh/#Net3GConfig">SDK\_Net3GConfig    </a></br>    
E_SDK_CONFIG_NET_MOBILE = 60, 		    //手机监控---对应结构体<a href="http://open.xmeye.net/zh/#NetMoblieConfig">SDK\_NetMoblieConfig  </a></br>         
E_SDK_CONFIG_UPGRADEINFO, 			//获取升级信息/参数/文件名---对应结构体<a href="http://open.xmeye.net/zh/#UpgradeInfo">SDK\_UpgradeInfo  </a></br>          
E_SDK_CONFIG_NET_DECODER,			//解码器地址设置V1(弃用)---对应结构体<a href="http://open.xmeye.net/zh/#NetDecoderConfigAll">SDK\_NetDecoderConfigAll </a></br>           
E_SDK_ABILITY_VSTD, 				//实际支持的视频制式---对应结构体<a href="http://open.xmeye.net/zh/#MultiVstd">SDK\_MultiVstd   </a></br>        
E_SDK_CONFIG_ABILITY_VSTD,			//支持视频制式---对应结构体<a href="http://open.xmeye.net/zh/#MultiVstd">SDK\_MultiVstd   </a></br>   
E_SDK_CONFIG_NET_UPNP, 				//UPUN设置---对应结构体<a href="http://open.xmeye.net/zh/#NetUPNPConfig">SDK\_NetUPNPConfig  </a></br>           
E_SDK_CONFIG_NET_WIFI,				//WIFI---对应结构体<a href="http://open.xmeye.net/zh/#NetWifiConfig">SDK\_NetWifiConfig   </a></br>    
E_SDK_CONFIG_NET_WIFI_AP_LIST,		    //搜索到的wifi列表---对应结构体<a href="http://open.xmeye.net/zh/#NetWifiDeviceAll">SDK\_NetWifiDeviceAll </a></br>          
E_SDK_CONFIG_SYSENCODE_SIMPLIIFY, 	    //简化的编码配置---对应结构<a href="http://open.xmeye.net/zh/#EncodeConfigAll_SIMPLIIFY">SDK\_EncodeConfigAll\_SIMPLIIFY </a></br>           
E_SDK_CONFIG_ALARM_CENTER,  		    //告警中心---对应结构体<a href="http://open.xmeye.net/zh/#NetAlarmServerConfigAll">SDK\_NetAlarmServerConfigAll </a></br>            
E_SDK_CONFIG_NET_ALARM = 70,		    //网络告警---对应结构体<a href="http://open.xmeye.net/zh/#NETALARMCONFIG_ALL">SDK\_NETALARMCONFIG_ALL</a></br>		                																
E_SDK_CONFIG_NET_MEGA,     			//互信互通---对应结构体<a href="http://open.xmeye.net/zh/#CONFIG_NET_MEGA">SDK\_CONFIG\_NET\_MEGA </a></br>         
E_SDK_CONFIG_NET_XINGWANG, 			//星望---对应结构体<a href="http://open.xmeye.net/zh/#CONFIG_NET_XINGWANG">SDK\_CONFIG\_NET\_XINGWANG </a></br>        
E_SDK_CONFIG_NET_SHISOU,   			//视搜---对应结构体<a href="http://open.xmeye.net/zh/#CONFIG_NET_SHISOU ">SDK\_CONFIG\_NET\_SHISOU  </a></br>          
E_SDK_CONFIG_NET_VVEYE,    			//VVEYE---对应结构体<a href="http://open.xmeye.net/zh/#CONFIG_NET_VVEYE">SDK\_CONFIG\_NET\_VVEYE  </a></br>          
E_SDK_CONFIG_NET_PHONEMSG,  		    //短信---对应结构体<a href="http://open.xmeye.net/zh/#NetShortMsgCfg">SDK\_NetShortMsgCfg  </a></br>            
E_SDK_CONFIG_NET_PHONEMEDIAMSG,  	    //彩信---对应结构体<a href="http://open.xmeye.net/zh/#NetMultimediaMsgCfg">SDK\_NetMultimediaMsgCfg  </a></br>           
E_SDK_VIDEO_PREVIEW,				//
E_SDK_CONFIG_NET_DECODER_V2,		   //解码器地址设置V2(弃用)---对应结构体<a href="http://open.xmeye.net/zh/#NetDecorderConfigAll_V2">SDK\_NetDecorderConfigAll\_V2 </a></br>         
E_SDK_CONFIG_NET_DECODER_V3,		    //解码器地址设置V3---对应结构体<a href="http://open.xmeye.net/zh/#NetDecorderConfigAll_V3">SDK_NetDecorderConfigAll\_V3 </a></br>       
E_SDK_CONFIG_ABILITY_SERIALNO = 80,	    //序列号---对应结构体<a href="http://open.xmeye.net/zh/#AbilitySerialNo">SDK\_AbilitySerialNo</a></br>(经测试不是设备序列号(暂弃用),序列号可以从登陆接口获取到)         
E_SDK_CONFIG_NET_RTSP,    			//RTSP---对应结构体<a href="http://open.xmeye.net/zh/#NetRTSPConfig">SDK\_NetRTSPConfig  </a></br>        
E_SDK_GUISET,              		//本地GUI输出设置---对应结构体<a href="http://open.xmeye.net/zh/#GUISetConfig">SDK\_GUISetConfig  </a></br>            
E_SDK_CATCHPIC,               		//抓图												
E_SDK_VIDEOCOLOR,             		//视频颜色设置---对应结构体<a href="http://open.xmeye.net/zh/#VideoColorConfigAll">SDK\_VideoColorConfigAll   </a></br>         
E_SDK_CONFIG_COMM485,				//串口485协议配置---对应结构体<a href="http://open.xmeye.net/zh/#RS485CONFIG">SDK\_STR\_RS485CONFIG\_ALL</a></br>        
E_SDK_COMFIG_ABILITY_COMMPRO485, 	    //串口485协议---对应结构体<a href="http://open.xmeye.net/zh/#COMMFUNC">SDK\_COMMFUNC  </a></br>          
E_SDK_CONFIG_SYS_TIME_NORTC,		    //设置系统时间noRtc---对应结构体<a href="http://open.xmeye.net/zh/#SYSTEM_TIME">SDK\_SYSTEM\_TIME </a></br>          
E_SDK_CONFIG_REMOTECHANNEL,   		    //远程通道---弃用          
E_SDK_CONFIG_OPENTRANSCOMCHANNEL , 	    //打开透明串口---对应结构体TransComChannel        
E_SDK_CONFIG_CLOSETRANSCOMCHANNEL = 90,     //关闭透明串口
E_SDK_CONFIG_SERIALWIRTE,  			//写入透明串口信息
E_SDK_CONFIG_SERIALREAD,   			//读取透明串口信息
E_SDK_CONFIG_CHANNELTILE_DOT,		    //点阵信息-修改IPC通道名需要点阵信息---对应结构体<a href="http://open.xmeye.net/zh/#TitleDot">SDK\_TitleDot</a></br>
E_SDK_CONFIG_CAMERA,           		//摄象机参数---对应结构体<a href="http://open.xmeye.net/zh/#CameraParam">SDK\_CameraParam</a></br>
E_SDK_CONFIG_ABILITY_CAMERA,    	    //曝光能力级---对应结构体<a href="http://open.xmeye.net/zh/#CameraAbility">SDK\_CameraAbility</a></br>
E_SDK_CONFIG_BUGINFO,    			//命令调试													
E_SDK_CONFIG_STORAGENOTEXIST,		    //硬盘不存在---对应结构体<a href="http://open.xmeye.net/zh/#VIDEOLOSSCONFIG">SDK\_VIDEOLOSSCONFIG</a></br>
E_SDK_CONFIG_STORAGELOWSPACE, 		    //硬盘容量不足---对应结构体<a href="http://open.xmeye.net/zh/#StorageLowSpaceConfig">SDK\_StorageLowSpaceConfig	</a></br>							
E_SDK_CONFIG_STORAGEFAILURE, 		    //硬盘出错---对应结构体<a href="http://open.xmeye.net/zh/#StorageFailConfig">SDK\_StorageFailConfig</a></br>
E_SDK_CFG_NETIPCONFLICT = 100,   	    //IP冲突---对应结构体<a href="http://open.xmeye.net/zh/#VIDEOLOSSCONFIG">SDK\_VIDEOLOSSCONFIG</a></br>
E_SDK_CFG_NETABORT,  				//网络异常---对应结构体<a href="http://open.xmeye.net/zh/#VIDEOLOSSCONFIG">SDK\_VIDEOLOSSCONFIG</a></br>
E_SDK_CONFIG_CHNSTATUS, 			//通道状态---对应结构体<a href="http://open.xmeye.net/zh/#NetDecorderChnStatusAll">SDK\_NetDecorderChnStatusAll</a></br>
E_SDK_CONFIG_CHNMODE,  			//通道模式---对应结构体<a href="http://open.xmeye.net/zh/#NetDecorderChnModeConfig">SDK\_NetDecorderChnModeConfig</a></br>
E_SDK_CONFIG_NET_DAS,    			//主动注册---对应结构体<a href="http://open.xmeye.net/zh/#DASSerInfo">SDK\_DASSerInfo</a></br>
E_SDK_CONFIG_CAR_INPUT_EXCHANGE,     //外部信息输入与车辆状态的对应关系---对应结构体<a href="http://open.xmeye.net/zh/#CarStatusExchangeAll">SDK\_CarStatusExchangeAll</a></br>			
E_SDK_CONFIG_DELAY_TIME,       		//车载系统延时配置---对应结构体<a href="http://open.xmeye.net/zh/#CarDelayTimeConfig">SDK\_CarDelayTimeConfig</a></br>
E_SDK_CONFIG_NET_ORDER,                 //网络优先级---对应结构体<a href="http://open.xmeye.net/zh/#NetOrderConfig">SDK\_NetOrderConfig</a></br>
E_SDK_CONFIG_ABILITY_NETORDER , 	    //网络优先级设置能力---对应结构体<a href="http://open.xmeye.net/zh/#NetOrderFunction">SDK\_NetOrderFunction</a></br>
E_SDK_CONFIG_CARPLATE,				//车牌号配置---对应结构体<a href="http://open.xmeye.net/zh/#CarPlates">SDK\_CarPlates</a></br>
E_SDK_CONFIG_LOCALSDK_NET_PLATFORM = 110,    //网络平台信息设置---对应结构体<a href="http://open.xmeye.net/zh/#LocalSdkNetPlatformConfig">SDK\_LocalSdkNetPlatformConfig</a></br>
E_SDK_CONFIG_GPS_TIMING,               //GPS校时相关配置---对应结构体<a href="http://open.xmeye.net/zh/#GPSTimingConfig">SDK\_GPSTimingConfig</a></br>
E_SDK_CONFIG_VIDEO_ANALYZE, 		    //视频分析(智能DVR)---对应结构体<a href="http://open.xmeye.net/zh/#ANALYSECONFIG">SDK\_ANALYSECONFIG</a></br>
E_SDK_CONFIG_GODEYE_ALARM,			//神眼接警中心系统---对应结构体<a href="http://open.xmeye.net/zh/#GodEyeConfig">SDK\_GodEyeConfig</a></br>
E_SDK_CONFIG_NAT_STATUS_INFO,   	    //nat状态信息---对应结构体<a href="http://open.xmeye.net/zh/#NatStatusInfo">SDK\_NatStatusInfo	</a></br>
E_SDK_CONFIG_BUGINFOSAVE,     		//命令调试(保存)									 
E_SDK_CONFIG_MEDIA_WATERMARK,		    //水印设置---对应结构体<a href="http://open.xmeye.net/zh/#WaterMarkConfigAll">SDK\_WaterMarkConfigAll</a></br>
E_SDK_CONFIG_ENCODE_STATICPARAM,	    //编码器静态参数---对应结构体<a href="http://open.xmeye.net/zh/#EncodeStaticParamAll">SDK\_EncodeStaticParamAll</a></br>
E_SDK_CONFIG_LOSS_SHOW_STR,		     //视频丢失显示字符串
E_SDK_CONFIG_DIGMANAGER_SHOW,	        //通道管理显示配置---对应结构体<a href="http://open.xmeye.net/zh/#DigManagerShowStatus">SDK\_DigManagerShowStatus</a></br>
E_SDK_CONFIG_ABILITY_ANALYZEABILITY = 120,   //智能分析能力---对应结构体<a href="http://open.xmeye.net/zh/#ANALYZEABILITY">SDK\_ANALYZEABILITY</a></br>
E_SDK_CONFIG_VIDEOOUT_PRIORITY,          //显示HDMI VGA优先级别配置
E_SDK_CONFIG_NAT,		 		//NAT功能，MTU值配置---对应结构体<a href="http://open.xmeye.net/zh/#NatConfig">SDK\_NatConfig</a></br>
E_SDK_CONFIG_CPCINFO,		         //智能CPC计数数据信息---对应结构体<a href="http://open.xmeye.net/zh/#CPCDataAll">SDK\_CPCDataAll</a></br>
E_SDK_CONFIG_STORAGE_POSITION,          // 录像存储设备类型---对应结构体<a href="http://open.xmeye.net/zh/#RecordStorageType">SDK\_RecordStorageType</a></br>
E_SDK_CONFIG_ABILITY_CARSTATUSNUM,       //车辆状态数---对应结构体<a href="http://open.xmeye.net/zh/#CarStatusNum">SDK\_CarStatusNum</a></br>
E_SDK_CFG_VPN,					//VPN---对应结构体<a href="http://open.xmeye.net/zh/#VPNConfig">SDK\_VPNConfig</a></br>
E_SDK_CFG_VIDEOOUT,				//VGA视频分辨率---对应结构体<a href="http://open.xmeye.net/zh/#VGAresolution">SDK\_VGAresolution</a></br>
E_SDK_CFG_ABILITY_VGARESOLUTION,        //支持的VGA分辨率列表---对应结构体<a href="http://open.xmeye.net/zh/#VGAResolutionAbility">SDK\_VGAResolutionAbility</a></br>
E_SDK_CFG_NET_LOCALSEARCH,             //搜索设备，设备端的局域网设备---对应结构体<a href="http://open.xmeye.net/zh/#NetDevList">SDK\_NetDevList</a></br>
E_SDK_CFG_NETPLAT_KAINENG = 130,        //客户配置---对应结构体<a href="http://open.xmeye.net/zh/#CONFIG_KAINENG_INFO">SDK\_CONFIG\_KAINENG\_INFO</a></br>
E_SDK_CFG_ENCODE_STATICPARAM_V2,        //DVR编码器静态参数---对应结构体<a href="http://open.xmeye.net/zh/#EncodeStaticParamV2">SDK\_EncodeStaticParamV2</a></br>
E_SDK_ABILITY_ENC_STATICPARAM,	        //静态编码能力集---对应结构体<a href="http://open.xmeye.net/zh/#EncStaticParamAbility">SDK\_EncStaticParamAbility</a></br>(掩码)
E_SDK_CFG_C7_PLATFORM,                //C7平台配置---对应结构体<a href="http://open.xmeye.net/zh/#C7PlatformConfig">SDK\_C7PlatformConfig</a></br>
E_SDK_CFG_MAIL_TEST,                  //邮件测试---对应结构体<a href="http://open.xmeye.net/zh/#NetEmailConfig">SDK\_NetEmailConfig</a></br>
E_SDK_CFG_NET_KEYBOARD,               //网络键盘服务---对应结构体<a href="http://open.xmeye.net/zh/#NetKeyboardConfig">SDK\_NetKeyboardConfig</a></br>
E_SDK_ABILITY_NET_KEYBOARD,		    //网络键盘协议---对应结构体<a href="http://open.xmeye.net/zh/#NetKeyboardAbility">SDK\_NetKeyboardAbility  </a></br>
E_SDK_CFG_SPVMN_PLATFORM,              //28181协议配置---对应结构体<a href="http://open.xmeye.net/zh/#ASB_NET_VSP_CONFIG">SDK\_ASB\_NET\_VSP\_CONFIG</a></br>	
E_SDK_CFG_PMS,				     //手机服务---对应结构体<a href="http://open.xmeye.net/zh/#PMSConfig">SDK\_PMSConfig</a></br>
E_SDK_CFG_OSD_INFO,                  //屏幕提示信息---对应结构体<a href="http://open.xmeye.net/zh/#OSDInfoConfigAll">SDK\_OSDInfoConfigAll</a></br>
E_SDK_CFG_KAICONG = 140,              //客户配置---对应结构体<a href="http://open.xmeye.net/zh/#KaiCongAlarmConfig">SDK\_KaiCongAlarmConfig</a></br>
E_SDK_CFG_DIGITAL_REAL,			    //真正支持的通道模式---对应结构体<a href="http://open.xmeye.net/zh/#VideoChannelManage">SDK\_VideoChannelManage</a></br>
E_SDK_ABILITY_PTZCONTROL,		    //PTZ控制能力集---对应结构体<a href="http://open.xmeye.net/zh/#PTZControlAbility">SDK\_PTZControlAbility</a></br>
E_SDK_CFG_XMHEARTBEAT,			    //对应结构体<a href="http://open.xmeye.net/zh/#XMHeartbeatConfig">SDK\_XMHeartbeatConfig</a></br>
E_SDK_CFG_MONITOR_PLATFORM,		    //平台配置---对应结构体<a href="http://open.xmeye.net/zh/#NetKeyboardConfig">SDK\_MonitorPlatformConfig</a></br>
E_SDK_CFG_PARAM_EX,				//摄像头扩展参数---对应结构体<a href="http://open.xmeye.net/zh/#MonitorPlatformConfig">SDK\_CameraParamEx</a></br>
E_SDK_CFG_NETPLAT_ANJU_P2P,		    //安巨P2P---对应结构体<a href="http://open.xmeye.net/zh/#NetPlatformCommonCfg">SDK\_NetPlatformCommonCfg </a></br> 
E_SDK_GPS_STATUS,				//GPS连接信息---对应结构体<a href="http://open.xmeye.net/zh/#GPSStatusInfo">SDK\_GPSStatusInfo </a></br>
E_SDK_WIFI_STATUS,				//Wifi连接信息---对应结构体<a href="http://open.xmeye.net/zh/#WifiStatusInfo">SDK\_WifiStatusInfo</a></br>
E_SDK_3G_STATUS,  				//3G连接信息---对应结构体<a href="http://open.xmeye.net/zh/#WirelessStatusInfo">SDK\_WirelessStatusInfo</a></br>
E_SDK_DAS_STATUS = 150, 		    //主动注册状态---对应结构体<a href="http://open.xmeye.net/zh/#DASStatusInfo">SDK\_DASStatusInfo </a></br>
E_SDK_ABILITY_DECODE_DELEY,		    //解码策略能力---对应结构体<a href="http://open.xmeye.net/zh/#DecodeDeleyTimePrame">SDK\_DecodeDeleyTimePrame</a></br>
E_SDK_CFG_DECODE_PARAM,     	        //解码最大延时---对应结构体<a href="http://open.xmeye.net/zh/#DecodeParam">SDK\_DecodeParam</a></br>
E_SDK_CFG_VIDEOCOLOR_CUSTOM,            //<a href="http://open.xmeye.net/zh/#VIDEOCOLOR_PARAM_CUSTOM">SDK\_VIDEOCOLOR\_PARAM\_CUSTOM</a></br>
E_SDK_ABILITY_ONVIF_SUB_PROTOCOL,        //onvif子协议---对应结构体<a href="http://open.xmeye.net/zh/#AbilityMask">SDK\_AbilityMask </a></br>  
E_SDK_CONFIG_EXPORT_V2,      	    //导出设备默认配置，即出厂的配置
E_SDK_CFG_CAR_BOOT_TYPE,      	    //车载开关机模式---对应结构体<a href="http://open.xmeye.net/zh/#CarBootTypeConfig">SDK\_CarBootTypeConfig</a></br>
E_SDK_CFG_IPC_ALARM,			    //IPC网络报警---对应结构体<a href="http://open.xmeye.net/zh/#IPCAlarmConfigAll">SDK\_IPCAlarmConfigAll</a></br>
E_SDK_CFG_NETPLAT_TUTK_IOTC,	        //TUTK IOTC平台配置---对应结构体<a href="http://open.xmeye.net/zh/#NetPlatformCommonCfg">SDK\_NetPlatformCommonCfg</a></br>
E_SDK_CFG_BAIDU_CLOUD,     		    //百度云---对应结构体<a href="http://open.xmeye.net/zh/#BaiduCloudCfg">SDK\_BaiduCloudCfg</a></br>
E_SDK_CFG_PMS_MSGNUM = 160,		    //手机订阅数---对应结构体<a href="http://open.xmeye.net/zh/#PhoneInfoNum">SDK\_PhoneInfoNum</a></br>
E_SDK_CFG_IPC_IP,           	    //控制DVR去修改设备IP---对应结构体<a href="http://open.xmeye.net/zh/#IPSetCfg">SDK\_IPSetCfg</a></br>
E_SDK_ABILITY_DIMEN_CODE,              //二维码点阵---对应结构体<a href="http://open.xmeye.net/zh/#DimenCodeAll">SDK\_DimenCodeAll</a></br>
E_SDK_CFG_MOBILE_WATCH, 		    //中国电信手机看店平台配置---对应结构体<a href="http://open.xmeye.net/zh/#MobileWatchCfg">SDK\_MobileWatchCfg</a></br>
E_SDK_CFG_BROWSER_LANGUAGE,   	        //使用浏览器时使用的语言---对应结构体<a href="http://open.xmeye.net/zh/#BrowserLanguageType">SDK\_BrowserLanguageType</a></br>
E_SDK_CFG_TIME_ZONE,			    //时区配置---对应结构体<a href="http://open.xmeye.net/zh/#TimeZone">SDK\_TimeZone</a></br>
E_SDK_CFG_NETBJTHY,       		    //客户配置---对应结构体<a href="http://open.xmeye.net/zh/#MonitorPlatformConfig">SDK\_MonitorPlatformConfig</a></br>
E_SDK_ABILITY_MAX_PRE_RECORD,          //最大可设置预录时间1~30---对应结构体<a href="http://open.xmeye.net/zh/#AbilityMask">SDK\_AbilityMask</a></br>
E_SDK_CFG_DIG_TIME_SYN,			//数字通道时间同步配置(决定前端同步方式)---对应结构体<a href="http://open.xmeye.net/zh/#TimeSynParam">SDK\_TimeSynParam</a></br>
E_SDK_CONFIG_OSDINFO_DOT,		    //3行OSD
E_SDK_CFG_NET_POS = 170,		    //POS机配置---对应结构体<a href="http://open.xmeye.net/zh/#NetPosConfigAll">SDK\_NetPosConfigAll</a></br>
E_SDK_CFG_CUSTOMIZE_OEMINFO,	        //定制OEM客户版本信息---对应结构体<a href="http://open.xmeye.net/zh/#CustomizeOEMInfo">SDK\_CustomizeOEMInfo</a></br>
E_SDK_CFG_DIGITAL_ENCODE, 		//数字通道精简版编码配置---对应结构体<a href="http://open.xmeye.net/zh/#EncodeConfigAll_SIMPLIIFY">SDK\_EncodeConfigAll\_SIMPLIIFY</a></br>
E_SDK_CFG_DIGITAL_ABILITY, 		    //数字通道的编码能力---对应结构体<a href="http://open.xmeye.net/zh/#DigitDevInfo">SDK\_DigitDevInfo</a></br>
E_SDK_CFG_ENCODECH_DISPLAY,		    //IE端编码配置显示的前端通道号---对应结构体<a href="http://open.xmeye.net/zh/#EncodeChDisplay">SDK\_EncodeChDisplay</a></br>
E_SDK_CFG_RESUME_PTZ_STATE,		    //开机云台状态---对应结构体
E_SDK_CFG_LAST_SPLIT_STATE,   	        //最近一次的画面分割模式，用于重启后恢复之前的分割模式
E_SDK_CFG_SYSTEM_TIMING_WORK,   //设备定时开关机时间配置。隐藏在自动维护页面里，要用超级密码登陆才能看到界面
E_SDK_CFG_GBEYESENV,			    //宝威环境监测平台配置---对应结构体<a href="http://open.xmeye.net/zh/#NetPlatformCommonCfg">SDK\_NetPlatformCommonCfg</a></br>
E_SDK_ABILITY_AHD_ENCODE_L, 	        //AHDL能力集---对应结构体<a href="http://open.xmeye.net/zh/#AHDEncodeLMask">SDK\_AHDEncodeLMask</a></br>
E_SDK_CFG_SPEEDALARM = 180,		    //速度报警---对应结构体<a href="http://open.xmeye.net/zh/#SpeedAlarmConfigAll">SDK\_SpeedAlarmConfigAll</a></br>
E_SDK_CFG_CORRESPONDENT_INFO,	        //用户自定义配置---对应结构体<a href="http://open.xmeye.net/zh/#CorrespondentOwnInfo">SDK\_CorrespondentOwnInfo</a></br>
E_SDK_SET_OSDINFO,				//OSD信息设置---对应结构体<a href="http://open.xmeye.net/zh/#OSDInfo">SDK\_OSDInfo</a></br>,(此项功能只支持模拟通道)
E_SDK_SET_OSDINFO_V2,	            //OSD信息叠加，不保存配置---对应结构体<a href="http://open.xmeye.net/zh/#OSDInfoConfigAll">SDK\_OSDInfoConfigAll</a></br>，(此项功能只支持模拟通道)
E_SDK_ABILITY_SUPPORT_EXTSTREAM,        //支持辅码流录像---对应结构体<a href="http://open.xmeye.net/zh/#AbilityMask">SDK\_AbilityMask</a></br>
E_SDK_CFG_EXT_RECORD,			    //辅码流配置---对应结构体<a href="http://open.xmeye.net/zh/#RECORDCONFIG">SDK_RECORDCONFIG\_ALL/SDK\_RECORDCONFIG</a></br>
E_SDK_CFG_APP_DOWN_LINK,		    //用于用户定制下载链接---对应结构体<a href="http://open.xmeye.net/zh/#AppDownloadLink">SDK\_AppDownloadLink</a></br>
E_SDK_CFG_EX_USER_MAP,			    //用于保存明文数据---对应结构体<a href="http://open.xmeye.net/zh/#UserMap">SDK\_UserMap</a></br>
E_SDK_CFG_TRANS_COMM_DATA,     //串口数据主动上传到UDP或TCP服务器，其中TCP服务器可以支持双向通信---对应结构体<a href="">SDK\_NetTransCommData</a></br>
E_SDK_EXPORT_LANGUAGE,		        //语言导出
E_SDK_IMPORT_LANGUAGE = 190,	        //语言导入
E_SDK_DELETE_LANGUAGE,			    //语言删除
E_SDK_CFG_UPGRADE_VERSION_LIST,	        //云升级文件列表---对应结构体<a href="http://open.xmeye.net/zh/#CloudUpgradeList">SDK\_CloudUpgradeList</a></br>
E_SDK_CFG_GSENSORALARM,			    //GSENSOR报警
E_SDK_CFG_USE_PROGRAM,			    //启动客户小程序---对应结构体<a href="http://open.xmeye.net/zh/#NetUseProgram">SDK\_NetUseProgram</a></br>
E_SDK_CFG_FTP_TEST,                  //FTP测试---对应结构体<a href="http://open.xmeye.net/zh/#FtpServerConfig">SDK\_FtpServerConfig</a></br>
E_SDK_CFG_FbExtraStateCtrl,  	        //消费类产品的录像灯的状态---对应结构体<a href="http://open.xmeye.net/zh/#FbExtraStateCtrl">SDK\_FbExtraStateCtrl</a></br>
E_SDK_CFG_PHONE,				//手机用
E_SDK_PicInBuffer,				//手机抓图,弃用 
E_SDK_GUARD,					//布警 弃用
E_SDK_UNGUARD = 200,			    //撤警，弃用
E_SDK_CFG_START_UPGRADE,		    //开始升级，弃用
E_SDK_CFG_AUTO_SWITCH,	            //插座定时开关---获取配置都用<a href="http://open.xmeye.net/zh/#GetDevConfig_Json">H264_DVR_GetDevConfig_Json</a></br>,配置使用<a href="">H264\_DVR\_SetDevConfig\_Json</a></br>(配置时的格式见智能插座用到的命令.doc)(两个接口简称Json接口,下面用简称) "Name":"PowerSocket.AutoSwitch"
E_SDK_CFG_POWER_SOCKET_SET,		    //控制插座开关---Json接口 "Name":"OPPowerSocketGet"
E_SDK_CFG_AUTO_ARM,				//插座的定时布撤防---Json接口 "Name":"PowerSocket.AutoArm"
E_SDK_CFG_WIFI_MODE,			 //Wifi模式配置，用于行车记录仪切换AP模式---对应结构体<a href="http://open.xmeye.net/zh/#NetWifiMode">SDK\_NetWifiMode</a></br>
E_SDK_CFG_CIENT_INFO,			 //传递手机客户端信息---Json接口 "Name":"PowerSocket.ClientInfo"</br>
E_SDK_CFG_ATHORITY,				//SDK_Authority---Json接口 "Name":"PowerSocket.Authority"</br>
E_SDK_CFG_ARM ,					//SDK_Arm---Json接口 "Name":"PowerSocket.Arm"</br>
E_SDK_CFG_AUTOLIGHT,			//设置夜灯的定时开关功能 --Json接口 "Name" : "PowerSocket.AutoLight",</br>
E_SDK_CFG_LIGHT = 210,			    //使能和禁止夜灯的动检响应功能---Json接口 "Name" : "PowerSocket.Light",</br>
E_SDK_CFG_WORKRECORD,			    //进行电量统计---Json接口 "Name" : "PowerSocket.WorkRecord",</br>
E_SDK_CFG_SYSTEMTIME,			//设置时间的命令 ,当局域网连接的时候,连接的时候,发送对时命令 --Json接口 "Name":"System.Time"</br>
E_SDK_CFG_USB,					//usb接口控制功能---Json接口 "Name":"PowerSocket.Usb"</br>
E_SDK_CFG_NETPLAT_BJHONGTAIHENG,        //北京鸿泰恒平台---对应结构体<a href="http://open.xmeye.net/zh/#CONFIG_NET_BJHONGTAIHENG">SDK\_CONFIG\_NET\_BJHONGTAIHENG</a></br>
E_SDK_CFG_CLOUD_STORAGE,		    //云存储相关配置---对应结构体<a href="http://open.xmeye.net/zh/#CloudRecordConfigAll">SDK\_CloudRecordConfigAll</a></br>
E_SDK_CFG_IDLE_PTZ_STATE,              //云台空闲动作相关配置---对应结构体<a href="http://open.xmeye.net/zh/#_PtzIdleStateAll">SDK\_PtzIdleStateAll</a></br>
E_SDK_CFG_CAMERA_CLEAR_FOG,	        //去雾功能配置---对应结构体<a href="http://open.xmeye.net/zh/#CameraClearFogAll">SDK\_CameraClearFogAll</a></br>
E_SDK_CFG_WECHATACCOUNT,		    //---对应json "Name":"PowerSocket.WechatAccount"
E_SDK_CFG_WECHATRENEW,			    //---对应json "Name":"PowerSocket.WechatRenew" 
E_SDK_CFG_POWERSOCKET_WIFI = 220,        //---对应json "Name":"PowerSocket.WiFi"
E_SDK_CFG_CAMERA_MOTOR_CONTROL,         //机器人马达控制---对应结构体<a href="http://open.xmeye.net/zh/#CameraMotorCtrl">SDK\_CameraMotorCtrl</a></br>
E_SDK_CFG_ENCODE_ADD_BEEP,		    //设置编码加入每隔30秒beep声---对应结构体<a href="http://open.xmeye.net/zh/#EncodeAddBeep">SDK\_EncodeAddBeep</a></br>
E_SDK_CFG_DATALINK,		//datalink客户在网络服务中的执行程序使能配置---对应结构体<a href="http://open.xmeye.net/zh/#DataLinkConfig">SDK\_DataLinkConfig</a></br>
E_SDK_CFG_FISH_EYE_PARAM,	        //鱼眼功能参数配置---对应结构体<a href="http://open.xmeye.net/zh/#FishEyeParam">SDK\_FishEyeParam</a></br>
E_SDK_OPERATION_SET_LOGO,	        //视频上叠加雄迈等厂家的LOGO---对应结构体<a href="http://open.xmeye.net/zh/#SetLogo">SDK\_SetLogo</a></br>
E_SDK_CFG_SPARSH_HEARTBEAT,		    //Sparsh客户的心跳功能配置---对应结构体 <a href="http://open.xmeye.net/zh/#SparshHeartbeat">SDK\_SparshHeartbeat</a></br>
E_SDK_CFG_LOGIN_FAILED,	    //登录失败时发送邮件，使用结构体:基本事件结构---对应结构体<a href="http://open.xmeye.net/zh/#VIDEOLOSSCONFIG">SDK\_VIDEOLOSSCONFIG</a></br>
E_SDK_CFG_NETPLAT_SPVMN_NAS,	        //安徽超清客户的nas服务器配置---对应结构体<a href="http://open.xmeye.net/zh/#SPVMN_NAS_SERVER">SDK\_SPVMN\_NAS\_SERVER</a></br>
E_SDK_CFG_DDNS_APPLY,			    //ddns 按键功能测试---对应结构体<a href="http://open.xmeye.net/zh/#NetDDNSConfigALL">SDK\_NetDDNSConfigALL</a></br>
E_SDK_OPERATION_NEW_UPGRADE_VERSION_REQ = 230,	///新版云升级版本查询请求---对应结构体<a href="http://open.xmeye.net/zh/#CloudUpgradeVersionRep">SDK\_CloudUpgradeVersionRep</a></br>
E_SDK_CFG_IPV6_ADDRESS,			    //ipv6------对应的结构体<a href="http://open.xmeye.net/zh/#IPAddressV6">SDK\_IPAddressV6</a></br>
E_SDK_CFG_DDNS_IPMSG,         	    //DDNS外网IP地址
E_SDK_CFG_ONLINE_UPGRADE,		    //在线升级相关配置-----对应的结构体<a href="http://open.xmeye.net/zh/#OnlineUpgradeCfg">SDK\_OnlineUpgradeCfg</a></br>
E_SDK_CFG_CONS_SENSOR_ALARM,           //家用产品433报警联动项配置-----对应的<a href="http://open.xmeye.net/zh/#ConsSensorAlarmCfg">SDK\_ConsSensorAlarmCfg</a></br>
E_SDK_OPEARTION_SPLIT_CONTROL,          //画面分割模式-----对应的结构体<a href="http://open.xmeye.net/zh/#SplitControl">SDK\_SplitControl</a></br>
E_SDK_CFG_Netinfo_TRANS_COMM,	        //Netinfo_cctv客户增加串口数据到指定服务器配置-----对应的结构体<a href="http://open.xmeye.net/zh/#NetinfoNetTransComm">SDK\_NetinfoNetTransComm</a></br>
E_SDK_CFG_RECORD_ENABLE,       //是否准备好开始录像和抓图，现在用于日本客户通过串口控制开启和关闭录像功能
E_SDK_CFG_NAS,					//nas配置		//<a href="http://open.xmeye.net/zh/#NAS_LIST">SDK\_NAS\_LIST</a></br>
E_SDK_CFG_NKB_DEVICE_LIST,		    //网络键盘设备链表
E_SDK_CFG_PARKING_PORT = 240,	        //泊车系统端口号配置---对应结构体<a href="http://open.xmeye.net/zh/#PortService">SDK\_PortService</a></br>
E_SDK_CFG_NET_GBEYES,			    ///<信产全球眼平台 ---对应结构体<a href="http://open.xmeye.net/zh/#GbEyesCfg">SDK\_GbEyesCfg</a></br>
E_SDK_CFG_GLOBALEYE,			    //全球眼配置---对应结构体<a href="http://open.xmeye.net/zh/#DefaultResponse">SDK\_DefaultResponse</a></br>
E_SDK_OPERATION_FISHEYE_MODIFY_CENTER,	    //鱼眼圆心校正---对应结构体<a href="http://open.xmeye.net/zh/#Point">SDK\_Point</a></br>
E_SDK_OPERATION_UTC_TIME_SETTING = 244,	    //设置UTC时间---对应结构体<a href="http://open.xmeye.net/zh/#SYSTEM_TIME">SDK\_SYSTEM\_TIME</a></br>
E_SDK_CFG_INTELBRAS_SPECIAL_INFO,		//interbras 特殊tcp端口号---对应结构体<a href="http://open.xmeye.net/zh/#IntelBrasSpecialInfo">SDK\_IntelBrasSpecialInfo</a></br>
E_SDK_CFG_SPVMN_PLATFORM_SIP,			//28181协议配置sip板卡ip---对应结构体<a href="http://open.xmeye.net/zh/#SIP_NET_IP_CONFIG">SDK\_SIP\_NET\_IP\_CONFIG</a></br>
E_SDK_CFG_FISH_LENS_PARAM,			//魚眼鏡頭參數---对应结构体<a href="http://open.xmeye.net/zh/#FishLensParam">SDK\_FishLensParam</a></br>
E_SDK_CFG_PTZCTRLMODE,			//模拟通道云台控制的控制方式选择---对应结构体<a href="http://open.xmeye.net/zh/#PTZControlModeAll">SDK\_PTZControlModeAll</a></br>
E_SDK_CFG_ENCODE_SmartH264,			//SmartH264+配置---对应结构体SmartH264ParamAll 
E_SDK_CFG_WIFI_INFO,				   //无线WIFI信息---对应结构体<a href="http://open.xmeye.net/zh/#WifiInfo">SDK\_WifiInfo</a></br>
E_SDK_CFG_NET_RTMP,				   //RTMP协议---对应结构体<a href="http://open.xmeye.net/zh/#NetRTMPConfig">SDK\_NetRTMPConfig </a></br> 
}SDK_CONFIG_TYPE

### 报警事件枚举

enum SDK_EventCodeTypes
<div style="margin-left:20px;">
{

SDK_EVENT_CODE_INIT = 0,
SDK_EVENT_CODE_LOCAL_ALARM = 1,		//本地报警(外部报警)
SDK_EVENT_CODE_NET_ALARM,		//网络报警
SDK_EVENT_CODE_MANUAL_ALARM,		//手动报警
SDK_EVENT_CODE_VIDEO_MOTION,		//动态检测
SDK_EVENT_CODE_VIDEO_LOSS,		//视频丢失
SDK_EVENT_CODE_VIDEO_BLIND,		//视频遮挡
SDK_EVENT_CODE_VIDEO_TITLE,		
SDK_EVENT_CODE_VIDEO_SPLIT,
SDK_EVENT_CODE_VIDEO_TOUR,
SDK_EVENT_CODE_STORAGE_NOT_EXIST,	//存储设备不存在
SDK_EVENT_CODE_STORAGE_FAILURE,    //存储设备访问失败
SDK_EVENT_CODE_LOW_SPACE,		//存储设备容量过低
SDK_EVENT_CODE_NET_ABORT,
SDK_EVENT_CODE_COMM,
SDK_EVENT_CODE_STORAGE_READ_ERROR,	//存储设备读错误
SDK_EVENT_CODE_STORAGE_WRITE_ERROR,	//存储设备写错误
SDK_EVENT_CODE_NET_IPCONFLICT,		//ip冲突
SDK_EVENT_CODE_ALARM_EMERGENCY,
SDK_EVENT_CODE_DEC_CONNECT,	
SDK_EVENT_CODE_UPGRADE,
SDK_EVENT_CODE_BACK_UP,
SDK_EVENT_CODE_SHUT_DOWN,
SDK_EVENT_CODE_REBOOT,
SDK_EVENT_CODE_NEWFILE,
SDK_EVENT_CODE_VideoAnalyze,
SDK_EVENT_CODE_IPC_ALARM,
SDK_EVENT_CODE_SPEED_ALARM,
SDK_EVENT_CODE_GSENSOR_AlARM,
SDK_EVENT_CODE_LOGIN_FAILED,		//登录失败
SDK_EVENT_CODE_SERIAL_ALARM,
SDK_EVENT_CODE_CONSSENSOR_ALARM, 	//消费类产品绑定的外部设备报警
SDK_EVENT_CODE_NR,
</div>
};

//报警信息

typedef struct <a href="http://open.xmeye.net/zh/#ALARM_INFO">SDK\_ALARM\_INFO</a></br>
{
    int nChannel;   
    int iEvent; //报警事件码:见枚举<a href="http://open.xmeye.net/zh/#EventCodeTypes">SDK\_EventCodeTypes </a></br>  
    int iStatus; //0:报警开始，1:报警结束   
    <a href="http://open.xmeye.net/zh/#SYSTEM_TIME">SDK\_SYSTEM\_TIME SysTime;   </a></br>
}SDK_AlarmInfo;  


//! 编码配置的类型   
enum SDK_ENCODE_TYPE_BY_RECORD   
{
	SDK_ENCODE_TYPE_TIM = 0,   
	SDK_ENCODE_TYPE_MTD = 1,    
	SDK_ENCODE_TYPE_ALM = 2,     
	SDK_ENCODE_TYPE_NUM = 3,     
	SDK_ENCODE_TYPE_SNAP_TIMER = 0,    
	SDK_ENCODE_TYPE_SNAP_TRIGGER = 1,     
};    
 #define SDK_EXTRATYPES 3 //辅码流类型     


//网络传输策略     
enum SDK_TransferPolicy     
{
SDK_TRANSFER_POLICY_AUTO,		///< 自适应       
SDK_TRANSFER_POLICY_QUALITY,		///< 质量优先       
SDK_TRANSFER_POLICY_FLUENCY,		///< 流量优先       
SDK_TRANSFER_POLICY_TRANSMISSION,	///< 网传优先      
SDK_TRANSFER_POLICY_NR,
};


/// 网络传输协议类型     
enum SDK_NetTransProtocolType    
{
SDK_NET_TRANS_PRO_TCP = 0,    
SDK_NET_TRANS_PRO_UDP = 1,     
};


/// 编码功能    
enum SDK_EncodeFunctionTypes   
{
SDK_ENCODE_FUNCTION_TYPE_DOUBLE_STREAM,		///< 双码流功能      
SDK_ENCODE_FUNCTION_TYPE_COMBINE_STREAM,	    ///< 组合编码功能      
SDK_ENCODE_FUNCTION_TYPE_SNAP_STREAM,		///< 抓图功能      
SDK_ENCODE_FUNCTION_TYPE_WATER_MARK,		///< 水印功能      
SDK_ENCODE_FUNCTION_TYPE_IFRAME_RANGE,		///< I帧间隔      
SDK_ENCODE_FUNCTION_TYPE_LOW_BITRATE,   	    ///< 低码流      
SDK_ENCODE_FUNCTION_TYPE_SmartH264,		//H264+      
SDK_ENCODE_FUNCTION_TYPE_NR,   
};


/// 报警功能     
enum SDK_AlarmFucntionTypes   
{  
SDK_ALARM_FUNCTION_TYPE_MOTION_DETECT,		///< 动态检测     
SDK_ALARM_FUNCTION_TYPE_BLIND_DETECT,		///< 视屏遮挡       
SDK_ALARM_FUNCTION_TYPE_LOSS_DETECT,		///< 视屏丢失        
SDK_ALARM_FUNCTION_TYPE_LOCAL_ALARM,		///< 本地报警            
SDK_ALARM_FUNCTION_TYPE_NET_ALARM,		///< 网络报警            
SDK_ALARM_FUNCTION_TYPE_IP_CONFLICT,		///< IP地址冲突     
SDK_ALARM_FUNCTION_TYPE_NET_ABORT,		///< 网络异常                
SDK_ALARM_FUNCTION_TYPE_STORAGE_NOTEXIST,	    ///< 存储设备不存在              
SDK_ALARM_FUNCTION_TYPE_STORAGE_LOWSPACE,	    ///< 存储设备容量不足             
SDK_ALARM_FUNCTION_TYPE_STORAGE_FAILURE,	    ///< 存储设备访问失败            
SDK_ALARM_FUNCTION_TYPE_VIDEOANALYSE,		///< 视频分析             
SDK_ALARM_FUNCTION_TYPE_NET_ABORT_EXTEND,	    ///< 网络异常扩展             
SDK_ALARM_FUNCTION_TYPE_IPC_ALARM,		///< IPC报警             
SDK_ALARM_FUNCTION_TYPE_CONSUMER_433ALARM,	///< 家用产品433设备报警           
SDK_ALARM_FUNCTION_TYPE_CONSUMER_REMOTE, 	    ///< 家用产品2.4G 遥控器           
SDK_ALARM_FUNCTION_TYPE_NR          
};

/// 网络服务功能           
enum SDK_NetServerTypes         
{  
SDK_NET_SERVER_TYPES_IPFILTER,		///< 白黑名单             
SDK_NET_SERVER_TYPES_DHCP,		///< DHCP功能             
SDK_NET_SERVER_TYPES_DDNS,		///< DDNS功能              
SDK_NET_SERVER_TYPES_EMAIL,		///< Email功能              
SDK_NET_SERVER_TYPES_MULTICAST,		///< 多播功能                              
SDK_NET_SERVER_TYPES_NTP,			///< NTP功能                 
SDK_NET_SERVER_TYPES_PPPOE,               
SDK_NET_SERVER_TYPES_DNS,     
SDK_NET_SERVER_TYPES_ARSP,		///< 主动注册服务                   
SDK_NET_SERVER_TYPES_3G,            ///< 3G拨号                 
SDK_NET_SERVER_TYPES_MOBILE=10,     	///< 手机监控                    
SDK_NET_SERVER_TYPES_UPNP,		///< UPNP              
SDK_NET_SERVER_TYPES_FTP,			///< FTP                
SDK_NET_SERVER_TYPES_WIFI,          	///< WIFI                 
SDK_NET_SERVER_TYPES_ALARM_CENTER,  	///< 告警中心         
SDK_NET_SERVER_TYPES_NETPLAT_MEGA,  	///< 互信互通           
SDK_NET_SERVER_TYPES_NETPLAT_XINWANG,  	///< 星望            
SDK_NET_SERVER_TYPES_NETPLAT_SHISOU,  	///< 视搜              
SDK_NET_SERVER_TYPES_NETPLAT_VVEYE,  	///< 威威眼                
SDK_NET_SERVER_TYPES_RTSP,     		///< RTSP               
SDK_NET_SERVER_TYPES_PHONEMSG=20,     	///< 手机信息发送配置             
SDK_NET_SERVER_TYPES_PHONEMULTIMEDIAMSG, ///< 手机信息发送配置               
SDK_NET_SERVER_TYPES_DAS,          	///< 主动注册     
SDK_NET_SERVER_TYPES_LOCALSDK_PLATFORM,  ///< 网络平台信息设置       
SDK_NET_SERVER_TYPES_GOD_EYE,		///< 神眼接警中心系统      
SDK_NET_SERVER_TYPES_NAT,			///< NAT穿透，MTU配置      
SDK_NET_SERVER_TYPES_VPN,     		///< VPN       
SDK_NET_SERVER_TYPES_NET_KEYBOARD,	///< 网络键盘配置       
SDK_NET_SERVER_TYPES_SPVMN,		///< 28181协议配置     
SDK_NET_SERVER_TYPES_PMS,      	///< 手机服务      
SDK_NET_SERVER_TYPE_KAICONG,	    ///< 凯聪配置      
SDK_NET_SERVER_TYPE_PROTOCOL_MAC,		///< 支持MAC协议     
SDK_NET_SERVER_TYPE_XMHEARTBEAT, 		///< 雄迈心跳      
SDK_NET_SERVER_TYPES_MONITOR_PLATFORM, 	///< 神州数码监控平台       
SDK_NET_SERVER_TYPES_ANJUP2P,		///< P2P            
SDK_NET_SERVER_TYPES_TUTKIOTC,		///< TUTK IOTC平台            
SDK_NET_SERVER_TYPES_BAIDUCLOUD, 		///< 百度云              
SDK_NET_SERVER_TYPES_MOBILWATCH,		///< 手机看店            
SDK_NET_SERVER_TYPES_BJLTHY,		///< 北京龙腾访问服务器平台               
SDK_NET_SERVER_TYPES_OPENVPN,		///< openvpn配置               
SDK_NET_SERVER_TYPES_PROTOCOL_NAT,	///< 支持NAT协议              
SDK_NET_SERVER_TYPES_PLATFORM_GBEYES,	///< 支持环保数据叠加             
SDK_NET_SERVER_TYPES_GBEYES,		///< 信产全球眼平台          
SDK_NET_SERVER_TYPES_DATALINK,		///< DataLink客户网络服务中执行程序使能配置             
SDK_NET_SERVER_TYPES_WIFI_MODE,		///< 是否支持wifi模式相关配置           
SDK_NET_SERVER_TYPES_IPV6,		///< 支持ipv6             
SDK_NET_SERVER_TYPES_PMS_V2,		///< 新版PMS页面              
SDK_NET_SERVER_TYPES_4G,		    ///< 无线拨号的协议下拉框是否显示4G          
SDK_NET_SERVER_TYPES_SPVMN_SIP,		///< 28181配置显示SIP 板卡地址       
SDK_NET_SERVER_TYPES_RTMP,		///< RTMP协议       
SDK_NET_SERVER_TYPES_NR,           
};

/// 预览功能         
enum SDK_PreviewTypes          
{ 
   SDK_PREVIEW_TYPES_TOUR,		///< 轮巡            
   SDK_PREVIEW_TYPES_TALK,		///< GUI界面配置            
   SDK_PREVIEW_TYPES_NR              
};

///串口类型             
enum SDK_CommTypes           
{  
   SDK_COMM_TYPES_RS485,		///<485串口                 
   SDK_COMM_TYPES_RS232,		///<232串口         
   SDK_COMM_TYPES_NR       
};

//输入法限制        
enum SDK_InPutMethod         
{
SDK_NO_SUPPORT_CHINESE,		//不支持中文输入            
SDK_NO_SUPPORT_NR          
};

//报警中标签显示          
 
enum SDK_TipShow             
{
SDK_NO_BEEP_TIP_SHOW,  		//蜂鸣提示         
SDK_NO_FTP_TIP_SHOW,  		//FTP提示           
SDK_NO_EMAIL_TIP_SHOW,  	    //EMAIL提示              
SDK_NO_DISK_MANAGER_SHOW,     //不显示硬盘管理页面的分区和类型修改等按钮             
SDK_NO_TIP_SHOW_NR    

};

///车载功能            

enum SDK_MobileCar      
{
SDK_MOBILEDVR_STATUS_EXCHANGE,			//车辆状态             
SDK_MOBILEDVR_DELAY_SET,	 			//延时设置             
SDK_MOBILEDVR_CARPLATE_SET,            
SDK_MOBILEDVR_GPS_TIMING,	 			//GPS校时             
SDK_MOBILEDVR_DVR_BOOT_TYPE_SET,             
SDK_MOBILEDVR_NR          
};




///其他功能            

enum SDK_OtherFunction 
{  
<div style="margin-left:20px;">
SDK_OTHER_DOWNLOADPAUSE,				//录像下载暂停功能             
SDK_OTHER_USB_SUPPORT_RECORD,			//USB支持录像功能            
SDK_OTHER_SD_SUPPORT_RECORD,			//SD支持录像功能              
SDK_OTHER_ONVIF_CLIENT_SUPPORT,			//是否支持ONVIF客户端             
SDK_OTHER_NET_LOCALSEARCH_SUPPORT,		//是否支持远程搜索             
SDK_OTHER_MAXPLAYBACK_SUPPORT, 			//是否支持最大回放通道数显示                 
SDK_OTHER_NVR_SUPPORT, 				//是否是专业NVR             
SDK_OTHER_C7_PLATFORM_SUPPORT,			//支持C7平台            
SDK_OTHER_MAIL_TEST_SUPPORT,			//支持邮件测试            
SDK_OTHER_SHOW_OSD_INFO,            	//支持显示3行OSD信息               
SDK_OTHER_HIDE_DIGITAL, 				//通道模式屏蔽功能          
SDK_OTHER_ACUTANCE_HORIZONTAL,			//锐度           
SDK_OTHER_ACUTANCE_VERTIAL,            
SDK_OTHER_BROAD_TRENDS,				//宽动态功能         
SDK_OTHER_NO_TALK,				//对讲能力             
SDK_OTHER_ALTER_DIGITAL_NAME,			//修改数字通道名称            
SDK_OTHER_SHOW_CONNECT_STATUS,      	    //支持显示wifi 3G 主动注册等的连接状态         
SDK_OTHER_SUPPORT_ECACT_SEEK,			//支持回放精准定位              
SDK_OTHER_UPLOAD_TITLEANDSTATE,			//通道标题和数字通道状态上传能力集              
SDK_OTHER_NO_HDD_RECORD,				//无硬盘录像           
SDK_OTHER_MUSICFILE_PLAY,				//播放音频文件            
SDK_OTHER_SUPPORT_SET_DIG_IP,			//设置前端ip能力             
SDK_OTHER_VERSION_PRODUCT_TYPE,			//支持在版本信息里显示设备型号     
SDK_OTHER_SUPPORT_CAMERA_IMG_STYLE,		//支持摄像机图像风格     
SDK_OTHER_SUPPORT_TITLE_ABILITY,		    //支持修改onvif标题     
SDK_OTHER_SUPPORT_DIMEN_CODE,			//支持二维码     
SDK_OTHER_STORAGE_NAS_SUPPORT,			//是否支持NAS存储功能     
SDK_OTHER_SHOWFALSE_CHECKTIME,			//屏蔽解码器时间同步功能     
SDK_OTHER_SUPPORT_TIME_ZONE, 			//时区配置      
SDK_OTHER_SHOW_ALARM_LEVEL_REGION,		//显示数字通道报警功能的灵敏度和区域设置     
SDK_OTHER_SUPPORT_POS,				//支持POS      
SDK_OTHER_HDD_LOWSPACE_USE_MB,			//硬盘空间不足报警下限用MB      
SDK_OTHER_SUPPORT_CUSTOMIZE_OEMINFO,	    //定制OEM客户版本信息     
SDK_OTHER_DIGITAL_ENCODE,				//数字通道编码配置     
SDK_OTHER_RESUME_PTZ_STATE,			//开机恢复云台状态     
SDK_OTHER_SUPPORT_SNAP_CFG,			//支持抓图配置     
SDK_OTHER_ABNORMITY_SEND_EMAIL,			//存储设备存在及存储异常及存储空间不足发邮件     
SDK_OTHER_SUPPORT_DIGITAL_PRE,			//支持数字通道预录        
SDK_OTHER_SUPPORT_WRITE_LOG, 			//报警页面添加是否写日志勾选框     
SDK_OTHER_SUPPORT_CHANGE_ONVIF_PORT,	    //支持修改onvif端口     
SDK_OTHER_SUPPORT_COMM_DATA_UPLOAD,  	    //支持串口数据上传到指定服务器      
SDK_OTHER_SUPPORT_TEXT_PASSWORD,		    //记录明文密码     
SDK_OTHER_SUPPORT_CLOUD_UPGRADE,		    // 支持云升级     
SDK_OTHER_SUPPORT_USER_PROGRAM,			//支持启动客户小程序     
SDK_OTHER_SUPPORT_MODIFY_FRONT_CFG,		//支持修改前端配置     
SDK_OTHER_SUPPORT_FTP_TEST,    			//新程序支持FTP支持FTP测试，老程序不支持。      
SDK_OTHER_SUPPORT_PTZ_IDLE_STATE, 		//云台空闲时执行何种操作的配置    
SDK_OTHER_SUPPORT_IMP_RCD,			//web端是否提供关键录像搜索的选项	    
SDK_OTHER_SUPPORT_CAMERA_MOTOR_CTRL, 	    //支持机器人马达控制     
SDK_OTHER_SUPPORT_ENCODE_ADD_BEEP,		// 视频编码每隔30秒加入beep声    
SDK_OTHER_SUPPORT_FISH_EYE,	       	//鱼眼功能能力集     
SDK_OTHER_SUPPORT_SPVMN_NAS_SERVER,		//安徽超清客户的nas服务器配置     
SDK_OTHER_SUPPORT_SMALL_CHN_TITLE_FONT,      //IE端传12*18的通道标题点阵      
SDK_OTHER_SUPPORT_CFG_CLOUD_UPGRADE, 	    //支持新的云升级功能配置     
SDK_OTHER_SUPPORT_STORAGE_FAIL_REBOOT,	    //全部硬盘出错后自动重启      
SDK_OTHER_SUPPORT_SPLIT_CONTROL,		    //支持CMS客户端画面分割         
SDK_OTHER_RTSP_CLIENT_SUPPORT,			//数字通道是否支持通过RTSP连接前端设备       
SDK_OTHER_LOW_LUX_MODE,				//微光模式       
SDK_OTHER_SUPPORT_Switch_Resolution,	    //修改前端数字通道分辨率     
SDK_OTHER_LOW_MOTION,				//运动相机慢动作      
SDK_OTHER_SUPPORT_CORRIDOR_MODE,            //支持走廊模式     
SDK_OTHER_WIFINVR_SUPPORT,			//是否是WIFINVR     
SDK_OTHER_NR         
</div> 
};




///支持的系统功能    

typedef struct SDK\_SystemFunction 
{ 
<div style="margin-left:20px;">
bool vEncodeFunction[SDK_ENCODE_FUNCTION_TYPE_NR];	///< 编码功能 <a href="http://open.xmeye.net/zh/#EncodeFunctionTypes">SDK_EncodeFunctionTypes</a></br>

bool vAlarmFunction[SDK_ALARM_FUNCTION_TYPE_NR];	    ///< 报警功能 <a href="http://open.xmeye.net/zh/#AlarmFucntionTypes">AlarmFucntionTypes</a></br>

bool vNetServerFunction[SDK_NET_SERVER_TYPES_NR];	    ///< 网络服务功能<a href="http://open.xmeye.net/zh/#NetServerTypes">NetServerTypes</a></br>

bool vPreviewFunction[SDK_PREVIEW_TYPES_NR];		///< 预览功能<a href="http://open.xmeye.net/zh/#PreviewTypes">PreviewTypes</a></br>

bool vCommFunction[SDK_COMM_TYPES_NR];			///< 串口类型<a href="http://open.xmeye.net/zh/#CommTypes">SDK_CommTypes</a></br>

bool vInputMethodFunction[SDK_NO_SUPPORT_NR];  		///< 输入法限制<a href="http://open.xmeye.net/zh/#InPutMethod">SDK_InPutMethod</a></br>>

bool vTipShowFunction[SDK_NO_TIP_SHOW_NR];           ///< 报警标签显示<a href="http://open.xmeye.net/zh/#TipShow">SDK_TipShow></a></br>

bool vMobileCarFunction[SDK_MOBILEDVR_NR];		///< 车载功能

bool vOtherFunction[SDK_OTHER_NR];			///< 其他功能<a href="http://open.xmeye.net/zh/#OtherFunction">OtherFunction</a></br>
</div>
}<a href="http://open.xmeye.net/zh/#SystemFunction">SDK_SystemFunction</a></br>; 

/// 支持的DDNS类型

typedef struct <a href="http://open.xmeye.net/zh/#DDNSServiceFunction">SDK_DDNSServiceFunction</a></br> 
{ 
int  nTypeNum; 
char vDDNSType[<a href="http://open.xmeye.net/zh/#NET_MAX_DDNS_TYPE">NET\_MAX\_DDNS\_TYPE</a></br>][64]; 
}SDK_DDNSServiceFunction;

/// 区域遮挡能力集

typedef struct SDK\_BlindDetectFunction 
{ 
int iBlindConverNum;	///< 区域遮挡块数

}SDK_BlindDetectFunction;




/// 动检区域能力集

typedef struct SDK\_MotionDetectFunction 
{
int iGridRow;

int iGridColumn;

}SDK\_MotionDetectFunction; 




typedef struct SDK\_EncodeInfo 
{ 
bool bEnable;			///< 使能项

bool bHaveAudio;			///< 是否支持音频

int  iStreamType;		///< 码流类型，capture_channel_t

unsigned int uiCompression;	///< capture_comp_t的掩码

unsigned int uiResolution;	///< SDK_CAPTURE_SIZE_t的掩码

}SDK_EncodeInfo; 

/// 编码能力

typedef struct CONFIG\_EncodeAbility 
{ 
unsigned int iMaxEncodePower;				///< 支持的最大编码能力

int iChannelMaxSetSync;					///< 每个通道分辨率是否需要同步 0-不同步, 1 -同步

unsigned int nMaxPowerPerChannel[<a href="http://open.xmeye.net/zh/#NET_MAX_CHANNUM">NET_MAX_CHANNUM</a></br>];	///< 每个通道支持的最高编码能力

unsigned int ImageSizePerChannel[<a href="http://open.xmeye.net/zh/#NE_MA_CHANNUM">NE_MA_CHANNUM</a></br>];	///< 每个通道支持的图像分辨率

unsigned int ExImageSizePerChannel[<a href="http://open.xmeye.net/zh/#NE_MA_CHANNUM">NE_MA_CHANNUM</a></br>];	///< 每个通道支持的辅码流图像分辨率

unsigned int CompressionMask[<a href="http://open.xmeye.net/zh/#NET_MAX_CHANNUM">NET\_MAX\_CHANNUM</a></br>];		///< 编码模式capture\_comp\_t掩码

unsigned int ThridImageSize[<a href="http://open.xmeye.net/zh/#NET_MAX_CHANNUM">NET\_MAX\_CHANNUM</a></br>];		///< CHL\_3IRD\_T码流支持的图像分辨率

unsigned int FourthImageSize[<a href="http://open.xmeye.net/zh/#NET_MAX_CHANNUM">NET\_MAX\_CHANNUM</a></br>];		///< CHL\_4RTH\_T码流支持的图像分辨率

SDK_EncodeInfo vEncodeInfo[<a href="http://open.xmeye.net/zh/#CHL_FUNCTION">SDK\_CHL\_FUNCTION\_NUM</a></br>];		///< 编码信息,暂时最大就4中码流

SDK_EncodeInfo vCombEncInfo[<a href="http://open.xmeye.net/zh/#CHL_FUNCTION_NUM">SDK\_CHL\_FUNCTION\_NUM</a></br>];	///< 组合编码信息,暂时最大就4中码流

int	iMaxBps;					///< 最高码流Kbps

unsigned int ExImageSizePerChannelEx[<a href="http://open.xmeye.net/zh/#NET_MAX_CHANNUM">NET\_MAX\_CHANNUM</a></br>][<a href="http://open.xmeye.net/zh/#CAPTURE_SIZE_EXT_V3_NR">SDK\_CAPTURE\_SIZE\_EXT\_V3\_NR</a></br>];///< 每个通道支持的辅码流图像分辨率

}CONFIG_EncodeAbility; 

///< 自动维护设置

typedef struct SDK\_AutoMaintainConfig
{
int iAutoRebootDay;		///< 自动重启设置日期

int iAutoRebootHour;		///< 重启整点时间	[0, 23]

int iAutoDeleteFilesDays;		///< 自动删除文件时间[0, 30]

}SDK\_AutoMaintainConfig; 

// 云台联动类型

enum <a href="http://open.xmeye.net/zh/#PtzLinkTypes">PtzLinkTypes</a></br>
{
PTZ_LINK_NONE,		// 不需要联动 

PTZ_LINK_PRESET,	// 转至预置点 

PTZ_LINK_TOUR,		// 巡航 

PTZ_LINK_PATTERN	// 轨迹 

};




//  云台联动结构

typedef struct SDK\_PtzLinkConfig 
{ 

int iType;		// 联动的类型--对应结构体<a href="http://open.xmeye.net/zh/#PtzLinkTypes">PtzLinkTypes</a></br>

int iValue;		// 联动的类型对应的值

}SDK\_PtzLinkConfig;


 #define <a href="http://open.xmeye.net/zh/#CHANNELNAME_MAX_LEN">CHANNELNAME\_MAX\_LEN</a></br> 64  //通道名称最大长度

//由于要兼容多通道设备，所以需要修改结构体类型

typedef struct <a href="http://open.xmeye.net/zh/#EventHandler">SDK\_EventHandler</a></br> 
{ 
char	dwRecord[<a href="http://open.xmeye.net/zh/#NET_MAX_MSK_SIZE">NET\_MAX\_MSK\_SIZE</a></br>];		// 录象掩码 

int		iRecordLatch;			// 录像延时：10?300 sec

char	dwTour[<a href="http://open.xmeye.net/zh/#NET_MAX_MSK_SIZE">NET\_MAX\_MSK\_SIZE</a></br>];		// 轮巡掩码 	

char	dwSnapShot[<a href="http://open.xmeye.net/zh/#NET_MAX_MSK_SIZE">NET\_MAX\_MSK\_SIZE</a></br>];		// 抓图掩码 

char	dwAlarmOut[<a href="http://open.xmeye.net/zh/#NET_MAX_MSK_SIZE">NET\_MAX\_MSK\_SIZE</a></br>];		// 报警输出通道掩码 

char	dwMatrix[<a href="http://open.xmeye.net/zh/#NET_MAX_MSK_SIZE">NET\_MAX\_MSK\_SIZE</a></br>];		// 矩阵掩码 

int		iEventLatch;			// 联动开始延时时间，s为单位

int		iAOLatch;			// 报警输出延时：10?300 sec

<a href="http://open.xmeye.net/zh/#PtzLinkConfig PtzLink"> SDK\_PtzLinkConfig PtzLink[<a href="http://open.xmeye.net/zh/#NET_MAX_CHANNUM">NET\_MAX\_CHANNUM</a></br>];	// 云台联动项

<a href="http://open.xmeye.net/zh/#CONFIG_WORKSHEET">SDK\_CONFIG\_WORKSHEET</a></br> schedule;			// 录像时间段



bool	bRecordEn;				// 录像使能

bool	bTourEn;				// 轮巡使能

bool	bSnapEn;				// 抓图使能

bool	bAlarmOutEn;			    // 报警使能

bool	bPtzEn;



// 云台联动使能

bool	bTip;					// 屏幕提示使能

bool	bMail;					// 发送邮件

bool	bMessage;				// 发送消息到报警中心

bool	bBeep;					// 蜂鸣

bool	bVoice;					// 语音提示

bool	bFTP;					// 启动FTP传输

bool	bMatrixEn;				// 矩阵使能

bool	bLog;					// 日志使能

bool	bMessagetoNet;			    // 消息上传给网络使能



bool    bShowInfo;                    // 是否在GUI上和编码里显示报警信息

char    dwShowInfoMask[<a href="http://open.xmeye.net/zh/#NET_MAX_MSK_SIZE">NET\_MAX\_MSK\_SIZE</a></br>]; 	// 要联动显示报警信息的通道掩码

char    pAlarmInfo[<a href="http://open.xmeye.net/zh/#CHANNELNAME_MAX_LEN">CHANNELNAME\_MAX\_LEN</a></br>]; 	//要显示的报警信息



bool    bShortMsg;              //发送短信

bool    bMultimediaMsg;         //发送彩信

}SDK_EventHandler;

///< 动态检测设置

typedef struct SDK\_MOTIONCONFIG 
{ 

bool bEnable;				// 动态检测开启

int iLevel;				// 灵敏度

unsigned int mRegion[<a href="http://open.xmeye.net/zh/#NET_MD_REGION_ROW">NET\_MD\_REGION\_ROW</a></br>]; 	// 区域，每一行使用一个二进制串

<a href="http://open.xmeye.net/zh/#EventHandler">SDK\_EventHandler</a></br> hEvent</a></br>; 			// 动态检测联动

}SDK\_MOTIONCONFIG;




/// 全通道动态检测配置

typedef struct  SDK_MOTIONCONFIG_ALL 
{

<a href="http://open.xmeye.net/zh/#MOTIONCONFIG">SDK_MOTIONCONFIG</a></br> vMotionDetectAll[<a href="http://open.xmeye.net/zh/#EventHandler">NET_MAX_CHANNUM</a></br>];

}SDK_MOTIONCONFIG_ALL;

///< 遮挡检测配置

typedef struct  SDK_BLINDDETECTCONFIG 
{

bool	bEnable;	///< 遮挡检测开启

int		iLevel;	///< 灵敏度：1?6

<a href="http://open.xmeye.net/zh/#EventHandler">SDK_EventHandler</a></br> hEvent;	///< 遮挡检测联动

}SDK_BLINDDETECTCONFIG;




/// 全通道遮挡检测配置

typedef struct  SDK_BLINDDETECTCONFIG_ALL 
{
<a href="http://open.xmeye.net/zh/#BLINDDETECTCONFIG">SDK\_BLINDDETECTCONFIG</a></br> vBlindDetectAll[<a href="http://open.xmeye.net/zh/#MAX_CHANNUM">NET\_MAX\_CHANNUM</a></br>];

}SDK_BLINDDETECTCONFIG_ALL;

///< 基本事件结构 视频丢失

typedef struct SDK_VIDEOLOSSCONFIG 
{

bool bEnable;		///< 使能

<a href="http://open.xmeye.net/zh/#EventHandler">SDK\_EventHandler</a></br> hEvent;	///< 处理参数

}SDK\_VIDEOLOSSCONFIG;




/// 所有通道的基本时间结构

typedef struct SDK_VIDEOLOSSCONFIG_ALL 
{

<a href="http://open.xmeye.net/zh/#VIDEOLOSSCONFIG">SDK\_VIDEOLOSSCONFIG</a></br> vGenericEventConfig[<a href="http://open.xmeye.net/zh/#MAX_CHANNUM">NET\_MAX\_CHANNUM</a></br>];

}SDK\_VIDEOLOSSCONFIG_ALL;


///< 报警输入配置

typedef struct  SDK_ALARM_INPUTCONFIG 
{

bool	bEnable;		///< 报警输入开关

int		iSensorType;	///< 传感器类型常开 or 常闭

<a href="http://open.xmeye.net/zh/#EventHandler">SDK\_EventHandler</a></br> hEvent;	    ///< 报警联动

}SDK\_ALARM\_INPUTCONFIG;




///< 所有通道的报警输入配置

typedef struct  SDK_ALARM_INPUTCONFIG_ALL 
{

   <a href="http://open.xmeye.net/zh/#ALARM_INPUTCONFIG"> SDK\_ALARM\_INPUTCONFIG</a></br> vAlarmConfigAll[<a href="http://open.xmeye.net/zh/#MAX_CHANNUM">NET\_MAX\_CHANNUM</a></br>];

}SDK\_ALARM\_INPUTCONFIG_ALL;

///< 网路报警

typedef struct  SDK_NETALARMCONFIG 
{

bool bEnable;		///< 使能

<a href="http://open.xmeye.net/zh/#EventHandler">SDK\_EventHandler</a></br> hEvent;	///< 处理参数

}SDK\_NETALARMCONFIG;




/// 所有通道的网路报警结构

typedef struct  SDK\_NETALARMCONFIG\_ALL 
{

<a href="http://open.xmeye.net/zh/#NETALARMCONFIG">SDK\_NETALARMCONFIG</a></br> vNetAlarmConfig[<a href="http://open.xmeye.net/zh/#MAX_CHANNUM">NET\_MAX\_CHANNUM</a></br>];

}SDK\_NETALARMCONFIG\_ALL;




///< 本地报警输出配置

typedef struct  SDK\_AlarmOutConfig 
{

int nAlarmOutType;	///< 报警输出类型: 配置,手动,关闭

int nAlarmOutStatus;    ///< 报警状态: 0:打开 1;闭合

}SDK\_AlarmOutConfig;

///< 所有通道的报警输出配置

typedef struct  SDK_AlarmOutConfigAll 
{

<a href="http://open.xmeye.net/zh/#AlarmOutConfig">SDK\_AlarmOutConfig</a></br> vAlarmOutConfigAll[<a href="http://open.xmeye.net/zh/#MAX\CHANNUM">NET\_MAX\_CHANNUM</a></br>];

}SDK\_AlarmOutConfigAll;

/// 所有通道的解码器地址设置V2版本

typedef struct  SDK\_AbilitySerialNo 
{

char serialNo[<a href="http://open.xmeye.net/zh/#MAX_SERIALNO_LENGTH">NET\_MAX\_SERIALNO\_LENGTH</a></br>];

char productType[<a href="http://open.xmeye.net/zh/#MAX_SERIALNO_LENGTH">NET\_MAX\_SERIALNO\_LENGTH</a></br>];

}SDK\_AbilitySerialNo;




///< 驱动器信息结构

typedef struct  SDK\_DriverInformation 
{

int		iDriverType;		///< 驱动器类型

bool	    bIsCurrent;		///< 是否为当前工作盘

unsigned int	uiTotalSpace;		///< 总容量，MB为单位

unsigned int	uiRemainSpace;		///< 剩余容量，MB为单位

int		iStatus;		///< 错误标志，文件系统初始化时被设置

int		iLogicSerialNo;	    ///< 逻辑序号

<a href="http://open.xmeye.net/zh/#SYSTEM">SDK\_SYSTEM\_TIME</a></br>  tmStartTimeNew;	    ///< 新录像时间段的开始时间

<a href="http://open.xmeye.net/zh/#SYSTEM_TIME">SDK\_SYSTEM\_TIME</a></br>  tmEndTimeNew;		///< 新录像时间段的结束时间

<a href="http://open.xmeye.net/zh/#SYSTEM_TIME">SDK\_SYSTEM\_TIME</a></br>  tmStartTimeOld;	    ///< 老录像时间段的开始时间

<a href="http://open.xmeye.net/zh/#SYSTEM_TIME">SDK\_SYSTEM\_TIME</a></br>  tmEndTimeOld;		///< 老录像时间段的结束时间

char		fsType[<a href="http://open.xmeye.net/zh/#FSLEN">NET\_FSLEN</a></br>];	///<文件类型

}SDK\_DriverInformation;

/// 录像模式种类

enum  SDK\_RecordModeTypes 
{

SDK_RECORD_MODE_CLOSED,		///< 关闭录像

SDK_RECORD_MODE_MANUAL,		///< 手动录像

SDK_RECORD_MODE_CONFIG,		///< 按配置录像

SDK_RECORD_MODE_NR,

};

///< 录像设置

typedef struct  SDK\_RECORDCONFIG 
{

int iPreRecord;			        ///< 预录时间，为零时表示关闭

bool bRedundancy;			        ///< 冗余开关

 //bool bSnapShot;			       ///< 快照开关

int iPacketLength;		        ///< 录像打包长度（分钟）[1, 255]

int iRecordMode;				    ///< 录像模式，0 关闭，1 禁止 2 配置

<a href="http://open.xmeye.net/zh/#CONFIG_WORKSHEET">SDK\_CONFIG\_WORKSHEET</a></br> wcWorkSheet;		///< 录像时间段

unsigned int typeMask [<a href="http://open.xmeye.net/zh/#N_WEEKS">NET\_N\_WEEKS</a></br>][<a href="http://open.xmeye.net/zh/#N_TSECT">NET\_N\_TSECT</a></br>];	///< 录像类型掩码

}SDK_RECORDCONFIG;

//录像设置结构体

typedef struct  SDK_RECORDCONFIG_ALL 
{

<a href="http://open.xmeye.net/zh/#RECORDCONFIG">SDK\_RECORDCONFIG</a></br> vRecordConfigAll[<a href="http://open.xmeye.net/zh/#MAX_CHANNUM">NET\_MAX\_CHANNUM</a></br>];

}SDK_RECORDCONFIG_ALL;

///< 图片设置

typedef struct  SDK_SnapshotConfig 
{

int iPreSnap;			        ///< 预抓图片数

bool bRedundancy;					///< 冗余开关

int iSnapMode;					///< 录像模式，见<a href="http://open.xmeye.net/zh/#RecordModeTypes">RecordModeTypes</a></br>

<a href="http://open.xmeye.net/zh/#CONFIG_WORKSHEET">SDK\_CONFIG\_WORKSHEET</a></br> wcWorkSheet;			///< 录像时间段

unsigned int typeMask[<a href="http://open.xmeye.net/zh/#N_WEEKS">NET\_N\_WEEKS</a></br>][<a href="http://open.xmeye.net/zh/#N_TSECT">NET\_N\_TSECT</a></br>];	///< 录像类型掩码，见enum <a href="http://open.xmeye.net/zh/#RecordTypes">RecordTypes</a></br>

}SDK_SnapshotConfig;


typedef struct  SDK\_SnapshotConfigAll 
{

<a href="http://open.xmeye.net/zh/#SnapshotConfig">SDK\_SnapshotConfig</a></br> vSnapshotConfigAll[<a href="http://open.xmeye.net/zh/#MAX_CHANNUM">NET\_MAX\_CHANNUM</a></br>];

}SDK_SnapshotConfigAll;

//普通配置页结构体

typedef struct\_SDK\_CONFIG\_NORMAL 
{

<a href="http://open.xmeye.net/zh/#SYSTEM_TIME">SDK\_SYSTEM\_TIME</a></br> sysTime;	//系统时间


int  iLocalNo;			///< 本机编号:[0, 998] */

int  iOverWrite;		///< 硬盘满时处理 "OverWrite（iOverWrite=1）", "StopRecord（iOverWrite=0）" */		

char cIranCalendarEnable;	///< 是否启用伊朗日历，1表示启用，0表示不启用

char cFontSize;			///< 矢量字体大小

char reserved[2];

char sMachineName[64];		///< 机器名

int  iVideoStartOutPut;	///< 输出模式 */

int  iAutoLogout;		///< 本地菜单自动注销(分钟)	[0, 120]




int  iVideoFormat;		///< 视频制式:“PAL”:0, “NTSC”:1, “SECAM” */

int  iLanguage;		///< 语言选择:“English”, “SimpChinese”, “TradChinese”, “Italian”, “Spanish”, “Japanese”, “Russian”, “French”, “German” */	

int  iDateFormat;		///< 日期格式:“YYMMDD”, “MMDDYY”, “DDMMYY” */

int  iDateSeparator;		///< 日期分割符:“.”, “-”, “/” */

int  iTimeFormat;		///< 时间格式:“12”, “24” */

int  iDSTRule;			///< 夏令时规则 

int  iWorkDay;			///< 工作日

<a href="http://open.xmeye.net/zh/#DSTPoint">DSTPoint</a></br> dDSTStart;

<a href="http://open.xmeye.net/zh/#DSTPoint">DSTPoint</a></br> dDSTEnd;

}SDK\_CONFIG\_NORMAL;

//以下编码配置相关

// 编码设置

typedef struct  SDK\_CONFIG\_ENCODE
{

<a href="http://open.xmeye.net/zh/#MEDIA_FORMAT">SDK\_MEDIA\_FORMAT</a></br> dstMainFmt[<a href="http://open.xmeye.net/zh/#ENCODE_TYPE_NUM">SDK\_ENCODE\_TYPE\_NUM</a></br>];	//  主码流格式 	
 
 <a href="http://open.xmeye.net/zh/#MEDIA_FORMAT">SDK\_MEDIA\_FORMAT</a></br> dstExtraFmt[<a href="http://open.xmeye.net/zh/#EXTRATYPES">SDK\_EXTRATYPES</a></br>];		//  辅码流格式 

 <a href="http://open.xmeye.net/zh/#MEDIA_FORMAT">SDK\_MEDIA\_FORMAT</a></br> dstSnapFmt[<a href="http://open.xmeye.net/zh/#ENCODE_TYPE_NUM">SDK\_ENCODE\_TYPE\_NUM</a></br>];	//  抓图格式 

}SDK\_CONFIG\_ENCODE;

typedef struct  SDK\_EncodeConfigAll 
{

<a href="http://open.xmeye.net/zh/#CONFIG_ENCODE">SDK\_CONFIG\_ENCODE</a></br> vEncodeConfigAll[<a href="http://open.xmeye.net/zh/#MAX_CHANNUM">NET\_MAX\_CHANNUM</a></br>];

}SDK\_EncodeConfigAll;




// 简化版本编码配置

/// 媒体格式

typedef struct  SDK\_MEDIA\_FORMAT\_SIMPLIIFY 
{

<a href="http://open.xmeye.net/zh/#VIDEO_FORMAT">SDK\_VIDEO\_FORMAT</a></br> vfFormat;		//  视频格式定义 			

bool	bVideoEnable;			//  开启视频编码 

bool	bAudioEnable;			//  开启音频编码 	

}SDK\_MEDIA\_FORMAT\_SIMPLIIFY;




/// 编码设置

typedef struct  SDK\_CONFIG\_ENCODE\_SIMPLIIFY 
{

<a href="http://open.xmeye.net/zh/#MEDIA_FORMAT">SDK\_MEDIA\_FORMAT</a></br> dstMainFmt;	//  主码流格式 	

<a href="http://open.xmeye.net/zh/#MEDIA_FORMAT">SDK\_MEDIA\_FORMAT</a></br> dstExtraFmt;	//  辅码流格式 

}SDK\_CONFIG\_ENCODE\_SIMPLIIFY;




/// 全通道编码配置

typedef struct SDK\_EncodeConfigAll\_SIMPLIIFY 
{

<a href="http://open.xmeye.net/zh/#CONFIG_ENCODE_SIMPLIIFY">SDK\_CONFIG\_ENCODE\_SIMPLIIFY</a></br> vEncodeConfigAll[NET\_MAX\_CHANNUM];

}SDK\_EncodeConfigAll\_SIMPLIIFY;


typedef struct  SDK\_CombineEncodeConfigAll 
{

<a href="http://open.xmeye.net/zh/#CONFIG_ENCODE">SDK\_CONFIG\_ENCODE</a></br> vEncodeConfigAll[NET\_MAX\_COMBINE\_NUM];

}SDK_CombineEncodeConfigAll;




/// 组合编码模式

typedef struct  SDK\_CombEncodeParam 
{

int iEncodeMode;	//见<a href="http://open.xmeye.net/zh/#CombineEncodeMode">CombineEncodeMode</a></br>

}SDK\_CombEncodeParam;




typedef struct  SDK\_CombEncodeModeAll 
{

<a href="http://open.xmeye.net/zh/#CombEncodeParam">SDK\_CombEncodeParam</a></br> vEncodeParam[NET\_MAX\_COMBINE\_NUM];

}SDK\_CombEncodeModeAll;




//!视频物件结构

typedef struct   SDK\_VIDEO\_WIDGET 
{

unsigned int rgbaFrontground;	///< 物件的前景MakeRGB，和透明度	

unsigned int rgbaBackground;	///< 物件的后景MakeRGB，和透明度	

<a href="http://open.xmeye.net/zh/#sdkRect">sdkRect</a></br>	rcRelativePos;		///< 物件边距与整长的比例*8191

bool	bPreviewBlend;		///< 预览叠加,是否显示，1：显示 0：隐藏

bool	bEncodeBlend;		///< 编码叠加

}SDK\_VIDEO\_WIDGET;




//!视频物件设置

typedef struct  SDK\_CONFIG\_VIDEOWIDGET 
{

<a href="http://open.xmeye.net/zh/#VIDEO_WIDGET">SDK\_VIDEO\_WIDGET</a></br>	dstCovers[<a href="http://open.xmeye.net/zh/#EventHandler">NET\_COVERNUM</a></br>];

<a href="http://open.xmeye.net/zh/#VIDEO_WIDGET">SDK\_VIDEO\_WIDGET</a></br>	ChannelTitle;       //通道名称

<a href="http://open.xmeye.net/zh/#VIDEO_WIDGET">SDK\_VIDEO\_WIDGET</a></br>	TimeTitle;	     //设备时间

struct  
{

char strName[<a href="http://open.xmeye.net/zh/#NAME_PASSWORD_LEN">NET\_NAME\_PASSWORD\_LEN</a></br>];

__int64 iSerialNo;	

}ChannelName;			    ///< 通道名称

int		iCoverNum;		///< 当前该通道有几个叠加的区域 */

}SDK\_CONFIG\_VIDEOWIDGET;




/// 视频物件(输出模式对话框)

typedef struct  SDK\_VideoWidgetConfigAll 
{

<a href="http://open.xmeye.net/zh/#CONFIG_VIDEOWIDGET">SDK\_CONFIG\_VIDEOWIDGET</a></br> vVideoWidegetConfigAll[<a href="http://open.xmeye.net/zh/#MAX_CHANNUM">NET\_MAX\_CHANNUM</a></br>];

}SDK\_VideoWidgetConfigAll;

//视频颜色

typedef struct   SDK\_VIDEOCOLOR\_PARAM 
{

int	nBrightness;		///< 亮度	0-100

int	nContrast;		///< 对比度	0-100

int	nSaturation;		///< 饱和度	0-100

int	nHue;			///< 色度	0-100

int	mGain;			///< 增益	0-100 第７位置1表示自动增益		

int	mWhitebalance;		///< 自动白电平控制，bit7置位表示开启自动控制.0x0,0x1,0x2分别代表低,中,高等级

int nAcutance;            ///< 锐度   0-15

}SDK\_VIDEOCOLOR\_PARAM;

///< 视频颜色设置

typedef struct SDK\_VIDEOCOLOR 
{

<a href="http://open.xmeye.net/zh/#TIMESECTION">SDK\_TIMESECTION</a></br>		tsTimeSection;		/// 时间段

<a href="http://open.xmeye.net/zh/#VIDEOCOLOR_PARAM">SDK\_VIDEOCOLOR\_PARAM</a></br>	dstColor;		/// 颜色定义

int	iEnable;

}SDK\_VIDEOCOLOR;




typedef struct  SDK\_CONFIG\_VIDEOCOLOR 
{

<a href="http://open.xmeye.net/zh/#VIDEOCOLOR">SDK\_VIDEOCOLOR</a></br> dstVideoColor[<a href="http://open.xmeye.net/zh/#NET_N_MIN_TSECT">NET\_N\_MIN\_TSECT</a></br>];

}SDK\_CONFIG\_VIDEOCOLOR;




typedef struct  SDK\_VideoColorConfigAll 
{

<a href="http://open.xmeye.net/zh/#CONFIG_VIDEOCOLOR">SDK\_CONFIG\_VIDEOCOLOR</a></br> vVideoColorAll[<a href="http://open.xmeye.net/zh/#NET_MAX_CHANNUM">NET\_MAX\_CHANNUM</a></br>];

}SDK\_VideoColorConfigAll;

/// 所有通道名称标题

typedef struct SDK\_ChannelNameConfigAll 
{

char channelTitle[<a href="http://open.xmeye.net/zh/#NET_MAX_CHANNUM">NET\_MAX\_CHANNUM</a></br>][<a href="http://open.xmeye.net/zh/#NET_NAME_PASSWORD_LEN">NET\_NAME\_PASSWORD\_LEN</a></br>];

}SDK\_ChannelNameConfigAll;

///输出模式

typedef struct  SDK\_GUISetConfig 
{

int iWindowAlpha;		///< 窗口透明度	[128, 255]

bool bTimeTitleEn;		///< 时间标题显示使能

bool bChannelTitleEn;		///< 通道标题显示使能	

bool bAlarmStatus;		///< 报警状态

bool bRecordStatus;		///< 录像状态显示使能

bool bChanStateRecEn;		///< 录像标志显示使能

bool bChanStateVlsEn;		///< 视频丢失标志显示使能

bool bChanStateLckEn;		///< 通道锁定标志显示使能	

bool bChanStateMtdEn;		///< 动态检测标志显示使能

bool bBitRateEn;		///< 码流显示使能

bool bRemoteEnable;	///< 遥控器使能

bool bDeflick;			///< 抗抖动

}SDK\_GUISetConfig;

////!普通网络设置

typedef struct SDK\_CONFIG\_NET\_COMMON 
{

//!主机名

char HostName[<a href="http://open.xmeye.net/zh/#NET_NAME_PASSWORD_LEN">NET\_NAME\_PASSWORD\_LEN</a></br>]; 

//!主机IP

<a href="http://open.xmeye.net/zh/#CONFIG_IPAddress">CONFIG\_IPAddress</a></br> HostIP; 

//!子网掩码

<a href="http://open.xmeye.net/zh/#CONFIG_IPAddress">CONFIG\_IPAddress</a></br> Submask; 

//!网关IP

<a href="http://open.xmeye.net/zh/#CONFIG_IPAddress">CONFIG\_IPAddress</a></br> Gateway; 

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

//!监视协议 {"TCP","UDP","MCAST",…}

int MonMode; 

//!限定码流值

int MaxBps;  

//!传输策略

//char TransferPlan[<a href="http://open.xmeye.net/zh/#NET_NAME_PASSWORD_LEN">NET\_NAME\_PASSWORD\_LEN</a></br>]; 

int TransferPlan; 

//!是否启用高速录像下载测率

bool bUseHSDownLoad; 

//!MAC地址

char sMac[<a href="http://open.xmeye.net/zh/#NET_MAX_MAC_LEN">NET\_MAX\_MAC\_LEN</a></br>]; 

}SDK\_CONFIG\_NET\_COMMON;




typedef enum SDK\_DevType 
{

SDK\_DEV\_TYPE\_IPC,

SDK\_DEV\_TYPE\_DVR,

SDK\_DEV\_TYPE\_HVR,

SDK\_DEV\_TYPE\_POEIPC,

SDK\_DEV\_TYPE\_NVR,

SDK\_DEV\_TYPE\_RTSPIPC,

SDK\_DEV\_TYPE\_NR

 }SDK\_DevType;

////!普通网络设置

typedef struct SDK\_CONFIG\_NET\_COMMON\_V2 
{

//!主机名

char HostName[NET\_NAME\_PASSWORD\_LEN];

//!主机IPv

CONFIG_IPAddress HostIP;

//!子网掩码

CONFIG_IPAddress Submask;

//!网关IP

CONFIG_IPAddress Gateway;

char pLocalLinkAddr[32];	//本地链路地址

char pAddr[64];			//ipv6地址

char pGateway[64];

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

//!监视协议 {"TCP","UDP","MCAST",…}

int MonMode;

//!限定码流值

int MaxBps;

//!传输策略

//char TransferPlan[<a href="http://open.xmeye.net/zh/#NET_NAME_PASSWORD_LEN">NET\_NAME\_PASSWORD\_LEN</a></br>];

int  TransferPlan;				///传输策略

bool bUseHSDownLoad;				///是否启用高速录像下载测率

char sMac[<a href="http://open.xmeye.net/zh/#NET_MAX_MAC_LEN">NET\_MAX\_MAC\_LEN</a></br>];			///MAC地址

char sSn[<a href="http://open.xmeye.net/zh/#NET_MAX_MAC_LEN">NET\_MAX\_MAC\_LEN</a></br>]; 	        ///序列号(大华和中维设备搜索中用到，用来保存修改IP所需数据)

 #ifndef WIN32

int  DeviceType;   				///设备类型,手机区分是插座还是普通设备

 #endif

int ChannelNum;			        ///通道数

int	Device_Type;		        ///设备类型，见enum <a href="http://open.xmeye.net/zh/#DevType">SDK\_DevType</a></br>

 #ifdef OME

char Version[<a href="http://open.xmeye.net/zh/#NET_MAX_INFO_LEN">NET\_MAX\_INFO\_LEN</a></br>];           //版本信息

<a href="http://open.xmeye.net/zh/#SYSTEM_TIME">SDK\_SYSTEM\_TIME</a></br> BuildDate;  			//版本日期

 #endif

char OtherFunction[49];     ///用来保存修改其它厂家IP所需信息 

char Resume[7];			///保留


}SDK\_CONFIG\_NET\_COMMON\_V2;




////!跨网段设置IP需 --

typedef struct SDK\_CONFIG\_NET\_COMMON\_V3 
{

char HostName[<a href="http://open.xmeye.net/zh/#NET_NAME_PASSWORD_LEN">NET\_NAME\_PASSWORD\_LEN</a></br>];	    ///主机名 

<a href="http://open.xmeye.net/zh/#CONFIG_IPAddress">CONFIG\_IPAddress</a></br> HostIP;				///主机IP

<a href="http://open.xmeye.net/zh/#CONFIG_IPAddress">CONFIG\_IPAddress</a></br> Submask;			///子网掩码
<a href="http://open.xmeye.net/zh/#CONFIG_IPAddress">CONFIG\_IPAddress</a></br> Gateway;			///网关IP  

int  HttpPort;					///HTTP服务端口   

int  TCPPort;					///TCP侦听端口   

int  SSLPort;					///SSL侦听端口

int  UDPPort;					///UDP侦听端口  

int  MaxConn;					///最大连接数

int  MonMode;					///监视协议 {"TCP","UDP","MCAST",?}

int  MaxBps;					///限定码流值

//char TransferPlan[NET\_NAME\_PASSWORD\_LEN]; 

int  TransferPlan;				///传输策略

bool bUseHSDownLoad; 			    ///是否启用高速录像下载测率

char sMac[NET_MAX_MAC_LEN];			///MAC地址

char UserName[NET_NAME_PASSWORD_LEN];	    ///设备用户名

char Password[NET_NAME_PASSWORD_LEN];	    ///设备密码

char LocalMac[NET_MAX_MAC_LEN]; 

int  nPasswordType; 

char Resume[92];				    ///保留

}SDK\_CONFIG\_NET\_COMMON\_V3;




//DHCP

 #define <a href="http://open.xmeye.net/zh/#EventHandler">SDK_MAX_ETH_NUM</a></br> 4

typedef struct SDK\_NetDHCPConfig 
{
bool bEnable;

char ifName[32];

}SDK\_NetDHCPConfig;

/// 所有网卡的DHCP配置

typedef struct SDK\_NetDHCPConfigAll 
{
<a href="http://open.xmeye.net/zh/#NetDHCPConfig">SDK\_NetDHCPConfig</a></br> vNetDHCPConfig[<a href="http://open.xmeye.net/zh/#MAX_ETH_NUM">SDK\_MAX\_ETH\_NUM</a></br>];

}SDK_NetDHCPConfigAll;


///< DNS设置

typedef struct SDK\_NetDNSConfig 
{
<a href="http://open.xmeye.net/zh/#CONFIG_IPAddress">CONFIG\_IPAddress</a></br>	PrimaryDNS;

<a href="http://open.xmeye.net/zh/#CONFIG_IPAddress">CONFIG\_IPAddress</a></br>	SecondaryDNS;

}SDK\_NetDNSConfig;

///< 服务器结构定义

typedef struct SDK\_RemoteServerConfig 
{
char ServerName[<a href="http://open.xmeye.net/zh/#NET_NAME_PASSWORD_LEN">NET\_NAME\_PASSWORD\_LEN</a></br>];		///< 服务名

<a href="http://open.xmeye.net/zh/#CONFIG_IPAddress">CONFIG\_IPAddress</a></br> ip;				///< IP地址

int Port;						///< 端口号

char UserName[<a href="http://open.xmeye.net/zh/#NET_NAME_PASSWORD_LEN">NET\_NAME\_PASSWORD\_LEN</a></br>];		///< 用户名

char Password[<a href="http://open.xmeye.net/zh/#NET_NAME_PASSWORD_LEN">NET\_NAME\_PASSWORD\_LEN</a></br>];		///< 密码

bool Anonymity;					///< 是否匿名登录

}SDK\_RemoteServerConfig;

///< IP权限设置

typedef struct SDK\_NetIPFilterConfig 
{
bool Enable;					///< 是否开启

<a href="http://open.xmeye.net/zh/#CONFIG_IPAddress">CONFIG_IPAddress</a></br> BannedList[<a href="http://open.xmeye.net/zh/#NET_MAX_FILTERIP_NUM">NET_MAX_FILTERIP_NUM</a></br>];///< 黑名单列表

<a href="http://open.xmeye.net/zh/#CONFIG_IPAddress">CONFIG_IPAddress</a></br> TrustList[<a href="http://open.xmeye.net/zh/#NET_MAX_FILTERIP_NUM">NET_MAX_FILTERIP_NUM</a></br>];	///< 白名单列表

}SDK\_NetIPFilterConfig;


///< 组播设置

typedef struct SDK\_NetMultiCastConfig 
{
bool Enable;				///< 是否开启

<a href="http://open.xmeye.net/zh/#RemoteServerConfig">SDK\_RemoteServerConfig</a></br> Server;		///< 组播服务器

}SDK\_NetMultiCastConfig;


///< pppoe设置

typedef struct SDK_NetPPPoEConfig 
{
bool Enable;				///< 是否开启

<a href="http://open.xmeye.net/zh/#RemoteServerConfig">SDK\_RemoteServerConfig</a></br> Server;		///< PPPOE服务器

<a href="http://open.xmeye.net/zh/#CONFIG_IPAddress">CONFIG\_IPAddress</a></br> addr;			///< 拨号后获得的IP地址

}SDK\_NetPPPoEConfig;




///< DDNS设置

typedef struct SDK\_NetDDNSConfig 
{

bool Enable;				///< 是否开启 

bool Online;				///< 是否在线

char DDNSKey[<a href="http://open.xmeye.net/zh/#NET_NAME_PASSWORD_LEN">NET\_NAME\_PASSWORD\_LEN</a></br>];	///< DDNS类型名称, 目前有: JUFENG

char HostName[<a href="http://open.xmeye.net/zh/#NET_NAME_PASSWORD_LEN">NET\_NAME\_PASSWORD\_LEN</a></br>];	///< 主机名

<a href="http://open.xmeye.net/zh/#RemoteServerConfig">SDK\_RemoteServerConfig</a></br> Server;		///< DDNS服务器

}SDK\_NetDDNSConfig;




///< DDNS设置

typedef struct SDK\_NetDDNSConfigALL 
{

<a href="http://open.xmeye.net/zh/#NetDDNSConfig">SDK\_NetDDNSConfig</a></br> ddnsConfig[<a href="http://open.xmeye.net/zh/#NET_MAX_DDNS_TYPE">NET\_MAX\_DDNS\_TYPE</a></br>];

}SDK\_NetDDNSConfigALL;

///< FTP设置

typedef struct SDK\_FtpServerConfig 
{

bool bEnable;        			///< 服务器使能

SDK_RemoteServerConfig Server;		///< FTP服务器

char cRemoteDir[<a href="http://open.xmeye.net/zh/#NET_MAX_PATH_LENGTH">NET\_MAX\_PATH\_LENGTH</a></br>];	///< 远程目录

int  iMaxFileLen;			///< 文件最大长度

}SDK\_FtpServerConfig;

///< NTP设置

typedef struct SDK\_NetNTPConfig 
{

bool Enable;             ///< 是否开启

<a href="http://open.xmeye.net/zh/#RemoteServerConfig">SDK\_RemoteServerConfig</a></br> Server;     ///< PPPOE服务器

int  UpdatePeriod;          ///< 更新周期

int  TimeZone;            ///< 时区

}SDK\_NetNTPConfig;

 #define <a href="http://open.xmeye.net/zh/#NET_MAX_EMAIL_TITLE_LEN"> NET\_MAX\_EMAIL\_TITLE\_LEN</a></br> 64

 #define  <a href="http://open.xmeye.net/zh/#NET_MAX_EMAIL_RECIEVERS">NET\_MAX\_EMAIL\_RECIEVERS</a></br>  5

 #define  <a href="http://open.xmeye.net/zh/#NET_EMAIL_ADDR_LEN">NET\_EMAIL\_ADDR\_LEN</a></br>  64




///< EMAIL设置

typedef struct SDK\_NetEmailConfig 
{

///< 是否开启

bool Enable;

///< smtp 服务器地址使用字符串形式填充

///< 可以填ip,也可以填域名

<a href="http://open.xmeye.net/zh/#RemoteServerConfig">SDK\_RemoteServerConfig</a></br> Server;

bool bUseSSL;

///< 发送地址

char SendAddr[<a href="http://open.xmeye.net/zh/#NET_EMAIL_ADDR_LEN">NET\_EMAIL\_ADDR\_LEN</a></br>];

///< 接收人地址

char Recievers[<a href="http://open.xmeye.net/zh/#NET_MAX_EMAIL_RECIEVERS">NET\_MAX\_EMAIL\_RECIEVERS</a></br>][<a href="http://open.xmeye.net/zh/#NET_EMAIL_ADDR_LEN">NET\_EMAIL\_ADDR\_LEN</a></br>];

///< 邮件主题

char Title[<a href="http://open.xmeye.net/zh/#NET_MAX_EMAIL_TITLE_LEN">NET\_MAX\_EMAIL\_TITLE\_LEN</a></br>];

///< email有效时间

<a href="http://open.xmeye.net/zh/#TIMESECTION">SDK\_TIMESECTION</a></br> Schedule[<a href="http://open.xmeye.net/zh/#NET_N_MIN_TSECT">NET\_N\_MIN\_TSECT</a></br>];

}SDK_NetEmailConfig;




///< ARSP(主动注册服务器)设置

typedef struct SDK\_NetARSPConfig 
{

bool bEnable;				///< 是否开启

char sARSPKey[<a href="http://open.xmeye.net/zh/#NET_NAME_PASSWORD_LEN">NET\_NAME\_PASSWORD\_LEN</a></br>];	///< DNS类型名称

int  iInterval;				///< 保活间隔时间

char sURL[<a href="http://open.xmeye.net/zh/#NET_NAME_PASSWORD_LEN">NET\_NAME\_PASSWORD\_LEN</a></br>];    	///< 本机域名

<a href="http://open.xmeye.net/zh/#RemoteServerConfig">SDK\_RemoteServerConfig</a></br> Server;		///< DDNS服务器

int  nHttpPort;                 ///< 服务器HTTP端口

}SDK\_NetARSPConfig;




typedef struct SDK\_NetARSPConfigAll 
{

<a href="http://open.xmeye.net/zh/#NetARSPConfig">SDK\_NetARSPConfig</a></br> vNetARSPConfigAll[<a href="http://open.xmeye.net/zh/#NET_MAX_ARSP_TYPE">NET\_MAX\_ARSP\_TYPE</a></br>];

}SDK\_NetARSPConfigAll;




///< 解码器地址设置

typedef struct SDK\_NetDecoderConfig 
{

bool Enable;				///< 是否开启

char UserName[<a href="http://open.xmeye.net/zh/#NET_NAME_PASSWORD_LEN">NET\_NAME\_PASSWORD\_LEN</a></br>];	///< DDNS类型名称, 目前有: JUFENG

char PassWord[<a href="http://open.xmeye.net/zh/#NET_NAME_PASSWORD_LEN">NET\_NAME\_PASSWORD\_LEN</a></br>];	///< 主机名

char Address[<a href="http://open.xmeye.net/zh/#NET_NAME_PASSWORD_LEN">NET\_NAME\_PASSWORD\_LEN</a></br>];  

int  Protocol;

int  Port;				///< 解码器连接端口

int  Channel;				///< 解码器连接通道号

int  Interval;                  ///< 轮巡的间隔时间(s)

}SDK\_NetDecoderConfig;

/// 所有通道的解码器地址设置

typedef struct SDK\_NetDecoderConfigAll 
{

<a href="http://open.xmeye.net/zh/#NetDecoderConfig"> SDK\_NetDecoderConfig</a></br> vNetDecoderConfig[<a href="http://open.xmeye.net/zh/#NET_MAX_DECORDR_CH">NET\_MAX\_DECORDR_CH</a></br>];

}SDK\_NetDecoderConfigAll;

/// 解码器地址设置V2版本

typedef struct SDK\_NetDecoderConfig_V2 
{

int nTotalNum;     //有效的数组个数，最大为<a href="http://open.xmeye.net/zh/#NET_MAX_CHANNUM">NET\_MAX\_CHANNUM</a></br>

<a href="http://open.xmeye.net/zh/#NetDecoderConfig">SDK\_NetDecoderConfig</a></br> vNetDecoderConfig[<a href="http://open.xmeye.net/zh/#NET_MAX_CHANNUM">NET\_MAX\_CHANNUM</a></br>];

}SDK\_NetDecoderConfig\_V2;




/// 所有通道的解码器地址设置V2版本

typedef struct SDK\_NetDecoderConfigAll\_V2 
{

<a href="http://open.xmeye.net/zh/#NetDecoderConfig_V2">SDK\_NetDecoderConfig\_V2</a></br> vNetDecoderArray[<a href="http://open.xmeye.net/zh/#NET_MAX_DECORDR_CH">NET\_MAX\_DECORDR\_CH</a></br>];

}SDK\_NetDecoderConfigAll\_V2;




/// 捕获通道类型

enum SDK\_CaptureChannelTypes  
{

SDK\_CAPTURE\_CHN\_MAIN = 0,		///< 主通道	－	主码流1 

SDK\_CAPTURE\_CHN\_2END = 1,		///< 辅通道	－	出辅码流2 

SDK\_CAPTURE\_CHN\_3IRD = 2,		///< 辅通道	－	出辅码流3 

SDK\_CAPTURE\_CHN\_4RTH = 3,		///< 辅通道	－	出辅码流4 

SDK\_CAPTURE\_CHN\_JPEG = 4,		///< 辅通道	－	出JPEG抓图 

SDK\_CAPTURE\_CHN\_NR,

};




///< 解码器地址设置

typedef struct SDK\_NetDecorderConfigV3 
{

bool Enable;				///< 是否开启

char UserName[<a href="http://open.xmeye.net/zh/#NET_NAME_URL_LEN">NET\_NAME\_PASSWORD\_LEN</a></br>];	///< DDNS类型名称, 目前有: JUFENG

char PassWord[<a href="http://open.xmeye.net/zh/#NET_NAME_URL_LEN">NET\_NAME\_PASSWORD\_LEN</a></br>];	///< 主机名

char Address[<a href="http://open.xmeye.net/zh/#NET_NAME_URL_LEN">NET\_NAME\_URL\_LEN</a></br>]; 

int  Protocol;			    ///见enum <a href="http://open.xmeye.net/zh/#TransferProtocol_V2">SDK\_TransferProtocol_V2</a></br>

int  Port;				///< 解码器连接端口

int  Channel;				///< 解码器连接通道号

int  Interval;                  ///< 轮巡的间隔时间(s),0:表示永久

char ConfName[<a href="http://open.xmeye.net/zh/#NET_NAME_PASSWORD_LEN">NET\_NAME\_PASSWORD\_LEN</a></br>];	///<配置名称

int  DevType;				///<设备类型

int  StreamType;				///<连接的码流类型 见enum <a href="http://open.xmeye.net/zh/#CaptureChannelTypes">SDK\_CaptureChannelTypes</a></br>

char MainRtspUrl[<a href="http://open.xmeye.net/zh/#NET_NAME_URL_LEN">NET\_NAME\_URL\_LEN</a></br>];	///<rtsp协议时表示前端设备的主码流地址

char SubRtspUrl[<a href="http://open.xmeye.net/zh/#NET_NAME_URL_LEN">NET\_NAME\_URL\_LEN</a></br>];	///<rtsp协议时表示前端设备的辅码流地址

}SDK\_NetDecorderConfigV3;




/*解码器连接类型*/

enum SDK\_DecorderConnType 
{

SDK\_CONN\_SINGLE = 0, 	/*单连接*/

SDK\_CONN\_MULTI = 1,	/*多连接轮巡*/

SDK\_CONN\_TYPE\_NR, 

};




/*数字通道的配置*/

typedef struct SDK\_NetDigitChnConfig 
{

bool Enable;			    /*数字通道是否开启*/

int  ConnType;			    /*连接类型，取<a href="http://open.xmeye.net/zh/#DecoderConnectType">DecoderConnectType</a></br>的值*/

int  TourIntv;			    /*多连接时轮巡间隔*/

unsigned int SingleConnId;        /*单连接时的连接配置ID, 从1开始，0表示无效*/

bool EnCheckTime;			    /*开启对时*/

<a href="http://open.xmeye.net/zh/#NetDecorderConfigV3">SDK\_NetDecorderConfigV3</a></br> NetDecorderConf[32]; /*网络设备通道配置表*/

int  nNetDeorde; 			  /* 有多少个 */

bool EnSynchResolution;			  //同步分辨率使能开关,0表示打开，1表示关闭

}SDK\_NetDigitChnConfig;




/*所有数字通道的配置*/

typedef struct SDK\_NetDecorderConfigAll_V3 
{

<a href="http://open.xmeye.net/zh/#NetDigitChnConfig">SDK\_NetDigitChnConfig</a></br> DigitChnConf[<a href="http://open.xmeye.net/zh/#NET_MAX_DECORDR_CH">NET\_MAX\_DECORDR\_CH</a></br>];

}SDK\_NetDecorderConfigAll\_V3;




typedef struct SDK\_HVR\_CHNCAP 
{

int nD1Chn;			// 支持的D1路数

int n960HChn;			// 支持的960H路数

int n720PChn;			// 支持的720P路数

int n1080PChn;			// 支持的1080P路数

int nCIFChn;			//支持的CIF通道数

int nHD1Chn;			//支持的HD1通道数

unsigned char nPlayChn; 	    //支持回放路数

unsigned char nDigiTalChn; 	//支持最大数字通道路数

unsigned char n960PChn; 	    //支持的960P通道数

unsigned char n3MChn; 		//支持的3M通道数

unsigned char n5MChn; 		//支持的5M通道数

unsigned char nWUXGAChn; 	    //支持的WUXGA通道数

unsigned char n1080NChn;	    //支持1080N通道数

unsigned char n4MChn;		//支持4M通道数

//unsigned char nResChar[2];    //冗余

}SDK\_HVR\_CHNCAP, *SDK\_PHVR\_CHNCAP;




typedef struct SDK\_HVR\_CHNCAPV2 
{

unsigned char nD1Chn;		// 支持的D1路数

unsigned char n960HChn;		// 支持的960H路数

unsigned char n720PChn;		// 支持的720P路数

unsigned char n1080PChn;	    // 支持的1080P路数

unsigned char nCIFChn;		//支持的CIF通道数

unsigned char nHD1Chn;		//支持的HD1通道数

unsigned char nPlayChn; 	    //支持回放路数

unsigned char nDigiTalChn; 	//支持最大数字通道路数

unsigned char n960PChn; 	    //支持的960P通道数

unsigned char n3MChn; 		//支持的3M通道数

unsigned char n5MChn; 		//支持的5M通道数

unsigned char nWUXGAChn; 	    //支持的WUXGA通道数

unsigned char n1080NChn;	    //支持1080N通道数

unsigned char n4MChn;		//支持4M通道数

unsigned char n720NChn;		//支持720N通道数

unsigned char nWSVGAChn;	//支持WSVGA(1024*576)通道数

unsigned char n4KChn;		//支持的4K通道数

unsigned char n3M_NChn;		//支持的3M_N通道数

unsigned char n4M_NChn;		//支持的4M_N通道数

unsigned char n5M_NChn;		//支持的5M_N通道数

unsigned char n4K_NChn;		//支持的4K_N通道数

unsigned char nRes[11]; 

}SDK\_HVR\_CHNCAPV2, *SDK\_PHVR\_CHNCAPV2; 




typedef struct SDK\_CAPTURE\_HVRCAP  	//改用CAPTURE\_HVRCAPV2，为了兼容老的保留
{

<a href="http://open.xmeye.net/zh/#HVR_CHNCAP">SDK\_HVR\_CHNCAP</a></br> DigitalCap;	// 支持的数字通道信息

<a href="http://open.xmeye.net/zh/#HVR_CHNCAP">SDK\_HVR\_CHNCAP</a></br> AnalogCap;		// 支持的模拟通道信息

}SDK\_CAPTURE\_HVRCAP, *SDK\_PCAPTURE\_HVRCAP; 




typedef struct SDK\_CAPTURE\_HVRCAPV2 
{

<a href="http://open.xmeye.net/zh/#HVR_CHNCAPV2">SDK\_HVR\_CHNCAPV2</a></br> DigitalCap;	// 支持的数字通道信息

<a href="http://open.xmeye.net/zh/#HVR_CHNCAPV2">SDK\_HVR\_CHNCAPV2</a></br> AnalogCap;	// 支持的模拟通道信息

}SDK\_CAPTURE\_HVRCAPV2, *SDK\_PCAPTURE\_HVRCAPV2; 




typedef struct SDK\_CAPTURE\_TOTAL\_HVRCAP //改用CAPTURE\_TOTAL\_HVRCAPV2，为了兼容老的保留
{

int	nHVRCap;				// 实际支持的模式

<a href="http://open.xmeye.net/zh/#CAPTURE_HVRCAP">SDK\_CAPTURE\_HVRCAP</a></br> HVRCap[<a href="http://open.xmeye.net/zh/#MAX_HVR_CHNCAP_CHN">MAX\_HVR\_CHNCAP\_CHN</a></br>];	// 所有模式的汇总

}SDK\_CAPTURE\_TOTAL\_HVRCAP, *SDK\_PCAPTURE\_TOTAL\_HVRCAP; 




typedef struct SDK\_CAPTURE\_TOTAL\_HVRCAPV2 
{

int		nHVRCap;			// 实际支持的模式

<a href="http://open.xmeye.net/zh/#CAPTURE_HVRCAPV2">SDK\_CAPTURE\_HVRCAPV2</a></br> HVRCap[<a href="http://open.xmeye.net/zh/#MAX_HVR_CHNCAP_CHN">MAX\_HVR\_CHNCAP\_CHN</a></br>];	// 所有模式的汇总

}SDK\_CAPTURE\_TOTAL\_HVRCAPV2, *SDK\_PCAPTURE\_TOTAL\_HVRCAPV2;




//通道模式配置

typedef struct SDK\_NetDecorderChnModeConfig 
{

<a href="http://open.xmeye.net/zh/#CAPTURE_TOTAL_HVRCAPV2">SDK\_CAPTURE\_TOTAL\_HVRCAPV2</a></br>  HVRTotalCap;

int HVRCurCapMode;

}SDK\_NetDecorderChnModeConfig;




/* 数字通道状态 */

typedef struct SDK\_NetDecorderChnStatus 
{

char ChnName[<a href="http://open.xmeye.net/zh/#NET_NAME_PASSWORD_LEN">NET\_NAME\_PASSWORD\_LEN</a></br>];

char pMaxResName[50];

char pCurResName[50];

char pStatus[50];

}SDK\_NetDecorderChnStatus;




/*所有数字通道状态*/

typedef struct SDK\_NetDecorderChnStatusAll 
{

<a href="http://open.xmeye.net/zh/#NetDecorderChnStatus"> SDK\_NetDecorderChnStatus</a></br> ChnStatusAll[<a href="http://open.xmeye.net/zh/#NET_MAX_DECORDR_CH">NET\_MAX\_DECORDR\_CH</a></br>];

}SDK\_NetDecorderChnStatusAll;




//Pos设备类型

enum SDK\_PosDevType 
{

SDK\_POS\_TYPE\_MANY\_LINES, //计算完总金额后才把商品信息一起发送过来

SDK\_POS\_TYPE\_ONE\_LINE,   //每统计一件商品就把该商品的信息发送过来

SDK\_POS\_NR

};




//文字编码格式

enum SDK\_WordEncode 
{

SDK\_WORD\_ENCODE\_GB2312,   //汉字编码GB2312

SDK\_WORD\_ENCODE\_UNICODE,  //万国码 Unicode

SDK\_WORD\_ENCODE\_UTF8,    //UTF-8

};




 #define SDK\_MAX\_POS\_FUNC\_KEYWORDS 4

// pos相关配置

typedef struct SDK\_NetPosConfig 
{

bool Enable;		/*pos机通道使能*/

int  Devtype;		//pos机类型

int  Protocol;		//通信协议

int  Port;	    //协议端口号

bool SnapEnable;		//抓拍使能

int  StartLine;		//对收到的信息从多少行开始显示

int  WordEncodeType;	//文字编码格式，如枚举值 <a href="http://open.xmeye.net/zh/#WordEncodeType">WordEncodeType</a></br> 所示

bool KeyWordEnable; 	//关键字写日志功能使能

char SearchWrod[<a href="http://open.xmeye.net/zh/#MAX_POS_FUNC_KEYWORDS">SDK\_MAX\_POS\_FUNC\_KEYWORDS</a></br>][16]; //需要添加到日志里的单词

int  HideTime;        //隐藏通道显示的pos信息的时间,单位是秒，0表示不自动隐藏

int  res;		//保留

}SDK\_NetPosConfig;

//所有pos机相关配置

typedef struct SDK\_NetPosConfigAll 
{

<a href="http://open.xmeye.net/zh/#NetPosConfig">SDK\_NetPosConfig</a></br> PosConfig[<a href="http://open.xmeye.net/zh/#MAX_HVR_CHNCAP_CHN">MAX\_HVR\_CHNCAP\_CHN</a></br>];

}SDK\_NetPosConfigAll;




///< 3G拨号设置

typedef struct SDK\_Net3GConfig 
{

bool bEnable;			    ///< 无线模块使能标志

int  iNetType;			 	///< 无线网络类型

char sAPN[<a href="http://open.xmeye.net/zh/#NET_NAME_PASSWORD_LEN">NET\_NAME\_PASSWORD\_LEN</a></br>];		///< 接入点名称

char sDialNum[<a href="http://open.xmeye.net/zh/#NET_NAME_PASSWORD_LEN">NET\_NAME\_PASSWORD\_LEN</a></br>];    ///< 拨号号码

char sUserName[<a href="http://open.xmeye.net/zh/#NET_NAME_PASSWORD_LEN">NET\_NAME\_PASSWORD\_LEN</a></br>];   ///< 拨号用户名

char sPassword[<a href="http://open.xmeye.net/zh/#NET_NAME_PASSWORD_LEN">NET\_NAME\_PASSWORD\_LEN</a></br>];   ///< 拨号密码

<a href="http://open.xmeye.net/zh/#CONFIG_IPAddress">CONFIG_IPAddress</a></br> addr;			///< 拨号后获得的IP地址

char sOperators[<a href="http://open.xmeye.net/zh/#NET_NAME_PASSWORD_LEN">NET\_NAME\_PASSWORD\_LEN</a></br>];  ///< 运营商

}SDK\_Net3GConfig;




///< 手机监控设置包括

typedef struct SDK\_NetMoblieConfig 
{

bool bEnable;			///< 是否开启

<a href="http://open.xmeye.net/zh/#RemoteServerConfig">SDK\_RemoteServerConfig</a></br> Server;	///< 服务器

}SDK\_NetMoblieConfig;




//RTSP

typedef struct SDK\_NetRTSPConfig 
{

bool bServer;

bool bClient;

<a href="http://open.xmeye.net/zh/#RemoteServerConfig">SDK\_RemoteServerConfig</a></br> Server;	///< 服务器模式

<a href="http://open.xmeye.net/zh/#RemoteServerConfig">SDK\_RemoteServerConfig</a></br> Client;	///< 客户端模式

}SDK\_NetRTSPConfig;




///< UPNP设置

typedef struct SDK\_NetUPNPConfig 
{

bool bEnable;			///< 使能标志

bool bState;			///< 状态, 1: OK 0: NOK

int  iHTTPPort;			///< HTTP连接映射后的端口

int  iMediaPort;			///< 媒体连接映射后的端口

int  iMobliePort;		///< 手机监控映射后的端口

}SDK\_NetUPNPConfig;




///< WIFI设置

typedef struct SDK\_NetWifiConfig 
{

bool bEnable;

char sSSID[36];            	///< SSID Number

int  nChannel;             ///< channel

char sNetType[32];         	///< Infra, Adhoc

char sEncrypType[32];      	///< NONE, WEP, TKIP, AES

char sAuth[32];            	///< OPEN, SHARED, WEPAUTO, WPAPSK, WPA2PSK, WPANONE, WPA, WPA2

int  nKeyType;             ///< 0:Hex 1:ASCII

char sKeys[<a href="http://open.xmeye.net/zh/#NET_IW_ENCODING_TOKEN_MAX">NET\_IW\_ENCODING\_TOKEN\_MAX</a></br>]; 

<a href="http://open.xmeye.net/zh/#CONFIG_IPAddress">CONFIG\_IPAddress</a></br> HostIP;	   ///< host ip

CONFIG_IPAddress Submask;	    ///< netmask

CONFIG_IPAddress Gateway;	    ///< gateway

}SDK\_NetWifiConfig;




enum SDK\_RSSI\_SINGNAL 
{

SDK\_RSSI\_NO\_SIGNAL,    //<= -90db

SDK\_RSSI\_VERY\_LOW,     //<= -81db

SDK\_RSSI\_LOW,        //<= -71db

SDK\_RSSI\_GOOD,        //<= -67db

SDK\_RSSI\_VERY\_GOOD,    //<= -57db

SDK\_RSSI\_EXCELLENT     //<= -57db

};




typedef struct SDK\_NetWifiDevice 
{

char sSSID[36];           //SSID Number

int  nRSSI;             //SEE SDK\_RSSI\_SINGNAL

int  nChannel; 

char sNetType[32];         //Infra, Adhoc

char sEncrypType[32];       //NONE, WEP, TKIP, AES

char sAuth[32];           //OPEN, SHARED, WEPAUTO, WPAPSK, WPA2PSK, WPANONE, WPA, WPA2

}SDK\_NetWifiDevice;




typedef struct SDK\_NetWifiDeviceAll 
{

int nDevNumber;

<a href="http://open.xmeye.net/zh/#NetWifiDevice">SDK\_NetWifiDevice</a></br> vNetWifiDeviceAll[<a href="http://open.xmeye.net/zh/#NET_MAX_AP_NUMBER">NET\_MAX\_AP\_NUMBER</a></br>];

}SDK\_NetWifiDeviceAll;

/// 语音对讲格式

typedef struct SDK\_AudioInFormatConfigAll 
{

<a href="http://open.xmeye.net/zh/#AudioInFormatConfig">SDK\_AudioInFormatConfig</a></br> vAudioInFormatConfig[<a href="http://open.xmeye.net/zh/#AUDIO_ENCODE_TYPES_NR">SDK\_AUDIO\_ENCODE\_TYPES\_NR</a></br>];

}SDK\_AudioInFormatConfigAll;




/// 告警状态

typedef struct SDK\_DVR\_ALARMSTATE 
{

char iVideoMotion[NET\_MAX\_MSK\_SIZE];///< 移动侦测状态,用掩码表示通道号,byte0代表通道一,以此类推 1: 有告警 0: 无告警

char iVideoBlind[NET\_MAX\_MSK\_SIZE];///< 视频遮挡状态,用掩码表示通道号,byte0代表通道一,以此类推 1: 有告警 0: 无告警

char iVideoLoss[NET\_MAX\_MSK\_SIZE];///< 视频丢失状态,用掩码表示通道号,byte0代表通道一,以此类推 1: 有告警 0: 无告警

char iAlarmIn[NET\_MAX\_MSK\_SIZE];///< 告警输入状态,用掩码表示通道号,byte0代表通道一,以此类推 1: 有告警 0: 无告警

char iAlarmOut[NET\_MAX\_MSK\_SIZE];///< 告警输出状态,用掩码表示通道号,byte0代表通道一,以此类推 1: 有告警 0: 无告警

}SDK\_DVR\_ALARMSTATE;




// 通道状态

typedef struct SDK\_DVR\_CHANNELSTATE 
{

bool bRecord;   ///< 是否正在录像

int iBitrate;	///< 当前码率

}SDK\_DVR\_CHANNELSTATE;




// DVR工作状态

typedef struct SDK\_DVR\_WORKSTATE 
{

<a href="http://open.xmeye.net/zh/#DVR_CHANNELSTATE">SDK\_DVR_CHANNELSTATE</a></br> vChnState[<a href="http://open.xmeye.net/zh/#NET_MAX_CHANNUM">NET\_MAX\_CHANNUM</a></br>];

<a href="http://open.xmeye.net/zh/#DVR_ALARMSTATE">SDK\_DVR\_ALARMSTATE</a></br> vAlarmState;

}SDK\_DVR\_WORKSTATE;

/// 支持语言

typedef struct SDK\_MultiLangFunction 
{

 //每个协议最多由64个字符组成

int nLangNum;

char vLanguageName[128][64];

}SDK\_MultiLangFunction;




/// 支持的视频制式

typedef struct SDK\_MultiVstd 
{

//每个协议最多由3个字符组成

int nVstdNum;

char vVstdName[3][64];

}SDK\_MultiVstd;

/// 恢复的默认配置种类

typedef struct SDK\_SetDefaultConfigTypes 
{

bool vSetDefaultKinds[<a href="http://open.xmeye.net/zh/#DEFAULT_CFG_END">SDK\_DEFAULT\_CFG\_END</a></br>];

bool vDefaultFactory;		//恢复出厂设置配置

}SDK\_SetDefaultConfigTypes;

// 升级信息获取

typedef struct SDK\_UpgradeInfo 
{

char szSerial[64];

char szHardware[64];

char szVendor[64];

unsigned int uiLogoArea[2];

char szLogoPartType[64];

}SDK\_UpgradeInfo;




typedef struct  
{

int left;

int top;

int right;

int bottom;

}sdkRect;

/// 音频输入格式，语音对讲用

typedef struct SDK\_AudioInFormatConfig 
{

int iBitRate;	  ///< 码流大小，kbps为单位，比如192kbps，128kbps

int iSampleRate;   ///< 采样率，Hz为单位，比如44100Hz

int iSampleBit;    ///< 采样的位深

int iEncodeType;   ///< 编码方式，参照<a href="http://open.xmeye.net/zh/#AudioEncodeTypes">AudioEncodeTypes</a></br>定义

}SDK\_AudioInFormatConfig;




//语音对讲格式

typedef enum\_TALK\_CODING\_TYPE 
{

TALK\_DEFAULT = 0,

TALK\_PCM = 1,		//PCM

TALK\_G711a,		//G711a

TALK\_AMR,		//AMR

TALK\_G711u,		//G711u

TALK\_G726,		//G726

}TALK\_CODING\_TYPE;

//语音对讲

typedef struct H264\_DVR\_TALKDECODE\_INFO 
{

<a href="http://open.xmeye.net/zh/#TALK_CODING_TYPE">TALK\_CODING\_TYPE</a></br>	encodeType;	//编码类型

int	nAudioBit;	//用实际的值表示，如8位 则填值为8

unsigned int dwSampleRate;//采样率，如16k 则填值为16000

char reserved[64]; 

}H264\_DVR\_TALKDECODE\_INFO;

typedef struct SDK\_VIDEO\_FORMAT 
{

int		iCompression;	//  压缩模式(视频格式) 参照<a href="http://open.xmeye.net/zh/#CAPTURE_COMP_t">enum SDK\_CAPTURE\_COMP\_t</a></br> 	

int		iResolution;	//  分辨率 参照枚举<a href="http://open.xmeye.net/zh/#CAPTURE_SIZE_t">SDK\_CAPTURE\_SIZE\_t</a></br>

int		iBitRateControl;//  码流控制 参照枚举<a href="http://open.xmeye.net/zh/#capture_brc_t">SDK\_capture\_brc\_t</a></br>

int		iQuality;	//  码流的画质 档次1-6		

int		nFPS;		//  帧率值，NTSC/PAL不区分,负数表示多秒一帧		

int		nBitRate;	//  0-4096k,该列表主要由客户端保存，设备只接收实际的码流值而不是下标。

int		iGOP;		//  描述两个I帧之间的间隔时间，2-12 

} SDK\_VIDEO\_FORMAT;




typedef struct  SDK\_AUDIO\_FORMAT 
{

int		nBitRate;	//  码流kbps	

int		nFrequency;	//  采样频率	

int		nMaxVolume;	//  最大音量阈值

}SDK\_AUDIO\_FORMAT;




// 媒体格式

typedef struct SDK\_MEDIA\_FORMAT 
{

<a href="http://open.xmeye.net/zh/#VIDEO_FORMAT">SDK\_VIDEO\_FORMAT</a></br> vfFormat;	//  视频格式定义 			

<a href="http://open.xmeye.net/zh/#AUDIO_FORMAT">SDK\_AUDIO\_FORMAT</a></br> afFormat;	//  音频格式定义 

bool	bVideoEnable;		//  开启视频编码 

bool	bAudioEnable;		//  开启音频编码 	

} SDK\_MEDIA\_FORMAT;




typedef union {//IP addr 

unsigned char	c[4]; 

unsigned short	s[2]; 

unsigned int 	l; 

}CONFIG\_IPAddress; 

//短信配置

typedef struct SDK\_NetShortMsgCfg 
{

bool bEnable;       //发送手机短信的功能是否启用

char pDesPhoneNum[<a href="http://open.xmeye.net/zh/#NET_MAX_RECIVE_MSG_PHONE_COUNT">NET\_MAX\_RECIVE\_MSG\_PHONE\_COUNT</a></br>][16]; 

int  sendTimes;     //需要向每个手机发送多少次短信

}SDK\_NetShortMsgCfg;

//手机彩信配置

typedef struct SDK\_NetMultimediaMsgCfg 
{

bool bEnable;				// 发送手机彩信的功能是否启用

char pDesPhoneNum[<a href="http://open.xmeye.net/zh/#NET_MAX_RECIVE_MSG_PHONE_COUNT">NET\_MAX\_RECIVE\_MSG\_PHONE\_COUNT</a></br>][16]; //接收彩信的手机号，现支持3个手机号

char pGateWayDomain[40];	        // 网关地址，域名或IP

int  gateWayPort;			// 网关端口

char pMmscDomain[40];		    // 彩信服务器地址，IP或域名

int  mmscPort;				// 彩信服务器端口号

}SDK\_NetMultimediaMsgCfg;

//鱼眼镜头类型枚举

typedef enum SDK\_E\_FISH\_LENS\_TYPE 
{

SDK\_FISH\_LENS\_NORMAL,  //普通镜头，不用app端做图像校正

SDK\_FISH\_LENS\_360VR,

SDK\_FISH\_LENS\_360LVR,

SDK\_FISH\_LENS\_180VR,

SDK\_FISH\_LENS\_DUAL\_360VR,

SDK\_FISH\_LENS\_DUAL\_180VR,

SDK\_FISH\_LENS\_NR,

}SDK\_E\_FISH\_LENS\_TYPE;




//鱼眼镜头配置参数

typedef struct SDK\_FishLensParam 
{

char  version;		//结构体的版本号(如果修改下面的成员导致app需要对新老程序分开处理时，则需要让扩展部将参数设置工具中的版本号加1，并修改设备上的默认配置)

char  lensType;      //镜头类型，如枚举<a href="http://open.xmeye.net/zh/#E_FISH_LENS_TYPE">SDK\_E\_FISH\_LENS\_TYPE</a></br>

short centerOffsetX;   //圆心偏差横坐标  单位:像素点

short centerOffsetY;   //圆心偏差纵坐标  单位:像素点

short radius;        //半径  单位:像素点

short imageWidth;      //圆心校正时的图像宽度  单位:像素点

short imageHeight;	//圆心校正时的图像高度  单位:像素点

char  viewAngle;	//视角  0:俯视   1:平视

char  viewMode;      //显示模式   0:360VR

short zoom;		 //缩放比例。为了传输方便，这里将原值放大了100倍

char  resv[8];	

} SDK\_FishLensParam;




//所有通道的鱼眼镜头参数配置

typedef struct SDK\_FishLensParamAll 
{

<a href="http://open.xmeye.net/zh/#FishLensParamv">SDK\_FishLensParamv</a></br> vLensParamAll[<a href="http://open.xmeye.net/zh/#NET_MAX_CHANNUM">NET\_MAX\_CHANNUM</a></br>];

}SDK\_FishLensParamAll;




//云台配置的控制方式设置

typedef enum SDK\_PTZ\_CTRL\_TYPE 
{

PTZ\_CTRL\_COAX = 0,//通过同轴线

PTZ\_CTRL\_RS485,   //通过485线

PTZ\_CTRL\_BOTH,    //同轴线和485线都发送控制命令

}SDK\_PTZ\_CTRL\_TYPE;




typedef struct SDK\_PTZControlMode 
{
int ctrlMode;			//云台控制的方式【<a href="http://open.xmeye.net/zh/#PTZ_CTRL_TYPE">PTZ\_CTRL\_TYPE</a></br> 三个枚举值】

} SDK\_PTZControlMode;




typedef struct SDK\_PTZControlModeAll 
{
<a href="http://open.xmeye.net/zh/#PTZControlMode">SDK\_PTZControlMode</a></br> CtrlModeAll[<a href="http://open.xmeye.net/zh/#NET_MAX_CHANNUM">NET\_MAX\_CHANNUM</a></br>];

}SDK\_PTZControlModeAll;




typedef struct SDK\_SmartH264Param 
{

bool SmartH264;

}SDK\_SmartH264Param;




typedef struct SDK\_SmartH264ParamAll 
{

<a href="http://open.xmeye.net/zh/#SmartH264Param">SDK\_SmartH264Param</a></br> SmartH264All[<a href="http://open.xmeye.net/zh/#NET_MAX_CHANNUM">NET\_MAX\_CHANNUM</a></br>];

}SDK\_SmartH264ParamAll;




typedef struct SDK\_WifiInfo 
{

char ssid[32];		//无线SSID信息

char wifiVersion[32];	//无线模块的版本信息

int advance;		//性能增强模式

}SDK\_WifiInfo;




///< 按间隔抓图

struct SDK\_IntervalSnapMode 
{

int iFTPTime;

int iEmailTime;

int iStorageTime;

};

///< 按定时抓图

struct SDK\_TriggerSnapMode 
{

SDK\_SYSTEM\_TIME TriggerTime;

bool bFTP;

bool bEmail;

bool bStorage;

};

///< 抓图计划

struct SDK\_SnapSchedule 
{

int iSnapType;		// 0:间隔抓图；1:定时抓图 2:关闭

<a href="http://open.xmeye.net/zh/#IntervalSnapMode">SDK\_IntervalSnapMode</a></br> intervalMode; 

<a href="http://open.xmeye.net/zh/#TriggerSnapMode">SDK\_TriggerSnapMode</a></br> vTriggerMode[256]; 

};




//所有通道的计划抓图配置

struct SDK\_SnapScheduleAll 
{  

<a href="http://open.xmeye.net/zh/#SnapSchedule">SDK\_SnapSchedule</a></br> vSnapScheduleAll[<a href="http://open.xmeye.net/zh/#NET_MAX_CHANNUM">NET\_MAX\_CHANNUM</a></br>];

};




网络键盘键值定义


/// 按键值, 不能随便更改

enum SDK\_NetKeyBoardValue 
{

SDK\_NET\_KEY\_0, SDK\_NET\_KEY\_1, SDK\_NET\_KEY\_2, SDK\_NET\_KEY\_3, SDK\_NET\_KEY\_4, SDK\_NET\_KEY\_5, SDK\_NET\_KEY\_6, SDK_NET_KEY_7, SDK_NET_KEY_8, SDK\_NET\_KEY\_9, 

SDK\_NET\_KEY\_10, SDK\_NET\_KEY\_11, SDK\_NET\_KEY\_12, SDK\_NET\_KEY\_13, SDK\_NET\_KEY\_14, SDK\_NET\_KEY\_15, SDK\_NET\_KEY\_16, SDK\_NET\_KEY\_10PLUS,SDK\_NET\_KEY\_DIGIT, 

SDK\_NET\_KEY\_UP = 20,     // 上或者云台向上

SDK\_NET\_KEY\_DOWN,        // 下或者云台向下

SDK\_NET\_KEY\_LEFT,        // 左或者云台向左

SDK\_NET\_KEY\_RIGHT,       // 右或者云台向右

SDK\_NET\_KEY\_SHIFT, 

SDK\_NET\_KEY\_PGUP,        // 上一页

SDK\_NET\_KEY\_PGDN,        // 下一页

SDK\_NET\_KEY\_RET,         // 确认

SDK\_NET\_KEY\_ESC,         // 取消或退出

SDK\_NET\_KEY\_FUNC,        // 切换输入法

SDK\_NET\_KEY\_PLAY,        // 播放/暂停

SDK\_NET\_KEY\_BACK,        // 倒放

SDK\_NET\_KEY\_STOP,        // 停止

SDK\_NET\_KEY\_FAST,        // 快放

SDK\_NET\_KEY\_SLOW,        // 慢放

SDK\_NET\_KEY\_NEXT,        // 下一个文件

SDK\_NET\_KEY\_PREV,        // 上一个文件

SDK\_NET\_KEY\_PAUSE,      // 暂停

SDK\_NET\_KEY\_FUNC\_A,	  // 功能键A

SDK\_NET\_KEY\_FUNC\_B,	  // 功能键B(在消费类产品上，A和B的功能会根据设备的不同而有不同的表现)

SDK\_NET\_KEY\_REC = 40,    // 录像设置

SDK\_NET\_KEY\_SEARCH,      // 录像查询

SDK\_NET\_KEY\_INFO,        // 系统信息

SDK\_NET\_KEY\_ALARM,       // 告警输出

SDK\_NET\_KEY\_ADDR,        // 遥控器地址设置

SDK\_NET\_KEY\_BACKUP,      // 备份

SDK\_NET\_KEY\_SPLIT,       // 画面分割模式切换，每按一次切换到下一个风格模式

SDK\_NET\_KEY\_SPLIT1,      // 单画面

SDK\_NET\_KEY\_SPLIT4,      // 四画面

SDK\_NET\_KEY\_SPLIT8,      // 八画面

SDK\_NET\_KEY\_SPLIT9,      // 九画面

SDK\_NET\_KEY\_SPLIT16,     // 16画面

SDK\_NET\_KEY\_SHUT,        // 关机

SDK\_NET\_KEY\_MENU,        // 菜单

SDK\_NET\_KEY\_SPLIT25,	// 25画面

SDK\_NET\_KEY\_SPLIT36,     // 36画面

SDK\_NET\_KEY\_PTZ = 60,    // 进入云台控制模式

SDK\_NET\_KEY\_TELE,        // 变倍减

SDK\_NET\_KEY\_WIDE,        // 变倍加

SDK\_NET\_KEY\_IRIS\_SMALL,  // 光圈增

SDK\_NET\_KEY\_IRIS\_LARGE,  // 光圈减

SDK\_NET\_KEY\_FOCUS\_NEAR,  // 聚焦远

SDK\_NET\_KEY\_FOCUS\_FAR,   // 聚焦近

SDK\_NET\_KEY\_BRUSH,       // 雨刷

SDK\_NET\_KEY\_LIGHT,       // 灯光

SDK\_NET\_KEY\_SPRESET,     // 设置预置点

SDK\_NET\_KEY\_GPRESET,     // 转至预置点

SDK\_NET\_KEY\_DPRESET,     // 清除预置点

SDK\_NET\_KEY\_PATTERN,     // 模式

SDK\_NET\_KEY\_AUTOSCAN,    // 自动扫描开始结束

SDK\_NET\_KEY\_AUTOTOUR,    // 自动巡航

SDK\_NET\_KEY\_AUTOPAN,     // 线扫开始/结束

};




/// 按键状态

enum SDK\_NetKeyBoardState 
{

SDK\_NET\_KEYBOARD\_KEYDOWN,	 // 按键按下

SDK\_NET\_KEYBOARD\_KEYUP,	 // 按键松开

};




typedef struct SDK_NetKeyBoardData 
{

int iValue; //枚举<a href="http://open.xmeye.net/zh/#NetKeyBoardValue">SDK\_NetKeyBoardValue</a></br>

int iState; //枚举<a href="http://open.xmeye.net/zh/#NetKeyBoardState">SDK\_NetKeyBoardState</a></br>

}SDK_NetKeyBoardData;


## 结构体定义

### 设备信息H264\_DVR\_DEVICEINFO结构体

typedef struct \_H264\_DVR\_DEVICEINFO
{

char sSoftWareVersion[64];	///< 软件版本信息

char sHardWareVersion[64];	///< 硬件版本信息

char sEncryptVersion[64];	    ///< 加密版本信息

<a href="http://open.xmeye.net/zh/#SYSTEM_TIME">SDK\_SYSTEM\_TIME </a></br>tmBuildTime;   ///< 软件创建时间

char sSerialNumber[64];		///< 设备序列号

int byChanNum;			///< 视频输入通道数

int iVideoOutChannel;		///< 视频输出通道数

int byAlarmInPortNum;		///< 报警输入通道数

int byAlarmOutPortNum;		///< 报警输出通道数

int iTalkInChannel;		///< 对讲输入通道数

int iTalkOutChannel;		///< 对讲输出通道数

int iExtraChannel;		///< 扩展通道数

int iAudioInChannel;		///< 音频输入通道数

int iCombineSwitch;		///< 组合编码通道分割模式是否支持切换

int iDigChannel;			///<数字通道数

unsigned int uiDeviceRunTime;  ///<系统运行时间

<a href="http://open.xmeye.net/zh/#DeviceType">SDK\_DeviceType </a></br>deviceTye;	///设备类型

char sHardWare[64];		///<设备型号

char uUpdataTime[20];		///<更新日期 例如 2013-09-03 14:15:13

unsigned int uUpdataType;	    ///<更新内容

int nLanguage;//国家的语言ID,0英语 1中文 2中文繁体 3韩语 4德语 5葡萄牙语 6俄语

char sCloudErrCode[<a href="http://open.xmeye.net/zh/#NET_MAX_PATH_LENGTH">NET\_MAX\_PATH\_LENGTH</a></br>];//云登陆具体错误内容

int status[32];

//判断新过来的连接是不是通过代理转发的，如果是那么按照服务器3

//返回的限制条件来限制。

//status[0] 路数限制:0代表不限制， n代表限制n路

//status[1]码流限制。0 :不限制。1限制不能观看主码流。

//status[2]限制时间。0:不限制。n:限制n分钟。

//status[3]限制码率，目前分为四档。0:不限制。1:限制为CIF 6帧 100K ，后续待定

//status[4]保留位，后续扩充。

//其中status[0]和status[1]在此处体现。

//status[2]和status[3]在传输码流的过程中体现

}H264\_DVR\_DEVICEINFO,*LPH264\_DVR\_DEVICEINFO;

### 时间信息SDK_SYSTEM_TIME结构体

/// 系统时间结构

typedef struct SDK\_SYSTEM\_TIME
{

int  year;		///< 年。   

int  month;		///< 月，January = 1, February = 2, and so on.   

int  day;		///< 日。   

int  wday;		///< 星期，Sunday = 0, Monday = 1, and so on   

int  hour;		///< 时。   

int  minute;	    ///< 分。   

int  second;	    ///< 秒。   

int  isdst;		///< 夏令时标识。   

}SDK\_SYSTEM\_TIME;




//录像设置相关结构体

typedef struct SDK\_TIMESECTION

{

//!使能

int enable;

//!开始时间:小时

int startHour;

//!开始时间:分钟

int	startMinute;

//!开始时间:秒钟

int	startSecond;

//!结束时间:小时

int	endHour;

//!结束时间:分钟

int	endMinute;

//!结束时间:秒钟

int	endSecond;

}SDK\_TIMESECTION;




typedef struct
{

int dwYear;	//年

int dwMonth;	//月

int dwDay;	//日

int dwHour;	//时

int dwMinute;	//分

int dwSecond;	//秒

}H264\_DVR\_TIME,*LPH264\_DVR\_TIME;




//时间结构

typedef struct\_NEW\_NET\_TIME
{

unsigned int second		:6;		//	秒	1-60		

unsigned int minute		:6;		//	分	1-60		

unsigned int hour		:5;		//	时	1-24		

unsigned int day		:5;		//	日	1-31		

unsigned int month		:4;		//	月	1-12		

unsigned int year		:6;		//	年	2000-2063	

}NEW\_NET\_TIME, *LPNET\_TIME;

///< 夏令时结构

typedef struct DSTPoint
{

int	iYear;

int	iMonth;

int	iWeek;		///<周1:first  to2 3 4 -1:last one   0:表示使用按日计算的方法[-1,4]

int	iWeekDay;	///<weekday from sunday=0	[0, 6]

int Hour;

int Minute;

}DSTPoint;


### 录像文件信息H264\_DVR\_FINDINFO结构体

typedef struct H264\_DVR\_FINDINFO

{

int nChannelN0;		//通道号

int nFileType;		//文件类型, 见<a href="http://open.xmeye.net/zh/#File_Type">SDK\_File\_Type</a></br>

<a href="http://open.xmeye.net/zh/#TIME">H264\_DVR\_TIME</a></br> startTime; //开始时间

<a href="http://open.xmeye.net/zh/#TIME">H264\_DVR\_TIME</a></br> endTime;	//结束时间

char szFileName[32];	//文件名，为空的话，系统处理，有值，系统采用

void *hWnd;        //窗口句柄

int  StreamType;		//查询的码流类型,主码流:0,辅码流:1

}H264\_DVR\_FINDINFO;




//录像文件返回结构体

typedef struct H264_DVR_FILE_DATA
{

int ch;				//通道号

int size;				//文件大小

char sFileName[108];		//文件名

<a href="http://open.xmeye.net/zh/#SYSTEM_TIME">SDK\_SYSTEM\_TIME</a></br> stBeginTime;   //文件开始时间

<a href="http://open.xmeye.net/zh/#SYSTEM_TIME">SDK\_SYSTEM\_TIME</a></br> stEndTime;	//文件结束时间

void *hWnd;			//窗口句柄

int StreamType;			//码流类型是回放主码流（0）还是辅助码流（1）

}H264\_DVR\_FILE\_DATA;




//按时间段查询

typedef struct SDK\_SearchByTime
{

int nHighChannel;			///< 33~64录像通道号掩码

int nLowChannel;			///< 1~32录像通道号掩码

int nFileType;             ///< 文件类型, 见<a href="http://open.xmeye.net/zh/#File_Type">SDK\_File\_Type</a></br>

<a href="http://open.xmeye.net/zh/#SYSTEM_TIME">SDK\_SYSTEM\_TIME</a></br> stBeginTime;   ///< 查询开始时间

<a href="http://open.xmeye.net/zh/#SYSTEM_TIME">SDK\_SYSTEM\_TIME </a></br>stEndTime;	///< 查询结束时间

int    iSync;             ///< 是否需要同步

unsigned int nHighStreamType;  ///< 33~64录像的码流类型,二进制位为0代表主码流，1代表辅码流

unsigned int nLowStreamType;   ///< 1~32录像的码流类型,二进制位为0代表主码流，1代表辅码流

}SDK\_SearchByTime;




//每个通道的录像信息

typedef struct SDK\_SearchByTimeInfo
{

int iChannel;			///< 录像通道号

///< 录像记录用720个字节的5760位来表示一天中的1440分钟

 ///< 0000:无录像 0001:F\_COMMON 0002:F\_ALERT 0003:F\_DYNAMIC 0004:F\_CARD 0005:F_HAND

unsigned char cRecordBitMap[720];

}SDK\_SearchByTimeInfo;




typedef struct SDK\_SearchByTimeResult
{

int nInfoNum;	  ///< 通道的录像记录信息个数

<a href="http://open.xmeye.net/zh/#SearchByTimeInfo">SDK\_SearchByTimeInfo</a></br> ByTimeInfo[<a href="http://open.xmeye.net/zh/#NET_MAX_CHANNUM">NET\_MAX\_CHANNUM</a></br>];    ///< 通道的录像记录信息

}SDK\_SearchByTimeResult;

<a href="http://open.xmeye.net/zh/#3.3.1">串口协议信息</a></br>



typedef struct SDK\_COMMATTRI
{

int	iDataBits;	// 数据位取值为5,6,7,8

int	iStopBits;	// 停止位

int	iParity;	// 校验位

int	iBaudRate;	// 实际波特率

}SDK\_COMMATTRI;

// 串口协议

enum SDK\_CommProtocol
{

SDK_CONSOLE = 0,

SDK_KEYBOARD,

SDK_COM_TYPES,

};

/// 串口协议

typedef struct SDK\_COMMFUNC
{

//每个协议最多由64个字符组成

int nProNum;

char vCommProtocol[100][32];

}SDK\_COMMFUNC;

// 串口配置

typedef struct SDK\_CONFIG\_COMM\_X
{

char iProtocolName[32];	// 串口协议:“Console”

int iPortNo;		// 端口号

<a href="http://open.xmeye.net/zh/#COMMATTRI>SDK\_COMMATTRI</a></br> aCommAttri;	// 串口属性

}SDK\_CONFIG\_COMM\_X;

云台协议


typedef struct SDK\_STR\_CONFIG_PTZ
{

char sProtocolName[<a href="http://open.xmeye.net/zh/#NET_MAX_PTZ_PROTOCOL_LENGTH>NET\_MAX\_PTZ\_PROTOCOL\_LENGTH</a></br>];	// 协议名称

int	ideviceNo;				// 云台设备地址编号

int	iNumberInMatrixs;			// 在矩阵中的统一编号

int iPortNo;					// 串口端口号	[1, 4]

<a href="http://open.xmeye.net/zh/#COMMATTRI>SDK\_COMMATTRI</a></br> dstComm;
	// 串口属性

}SDK\_STR\_CONFIG\_PTZ;

/// 云台协议

typedef struct SDK\_PTZPROTOCOLFUNC
{

//每个协议最多由64个字符组成

int nProNum;

char vPTZProtocol[100][<a href="http://open.xmeye.net/zh/#NET_MAX_PTZ_PROTOCOL_LENGTH>NET\_MAX\_PTZ\_PROTOCOL\_LENGTH</a></br>];

}SDK\_PTZPROTOCOLFUNC;

//所有通道云台协议

typedef struct SDK\_STR\_PTZCONFIG\_ALL
{

<a href="http://open.xmeye.net/zh/#STR_CONFIG_PTZ>SDK\_STR\_CONFIG\_PTZ</a></br> ptzAll[<a href="http://open.xmeye.net/zh/#NET_MAX_CHANNUM>NET\_MAX\_CHANNUM</a></br>];

}SDK\_STR\_PTZCONFIG\_ALL;




//RS485

typedef struct SDK\_STR\_RS485CONFIG\_ALL
{

<a href="http://open.xmeye.net/zh/#STR_CONFIG_PTZ>SDK\_STR\_CONFIG\_PTZ</a></br> ptzAll[<a href="http://open.xmeye.net/zh/#NET_MAX_CHANNUM>NET\_MAX\_CHANNUM</a></br>];

}SDK\_STR\_RS485CONFIG_ALL;

用户管理功能数据结构体


typedef struct\_OPR\_RIGHT
{

char name[<a href="http://open.xmeye.net/zh/#NET_MAX_USER_LENGTH">NET\_MAX\_USER\_LENGTH</a></br>];

}OPR\_RIGHT;




typedef struct\ _USER\_INFO
{

int rigthNum;

char rights[<a href="http://open.xmeye.net/zh/#NET_MAX_RIGTH_NUM">NET\_MAX\_RIGTH\_NUM][<a href="http://open.xmeye.net/zh/#NET_MAX_USER_LENGTH">NET\_MAX\_USER\_LENGTH</a></br>];

char Groupname[<a href="http://open.xmeye.net/zh/#NET_MAX_USER_LENGTH">NET\_MAX\_USER\_LENGTH</a></br>];

char memo[<a href="http://open.xmeye.net/zh/#NET_MAX_USER_LENGTH">NET\_MAX\_USER\_LENGTH</a></br>];

char name[<a href="http://open.xmeye.net/zh/#NET_MAX_USER_LENGTH">NET\_MAX\_USER\_LENGTH</a></br>];

char passWord[<a href="http://open.xmeye.net/zh/#NET_MAX_USER_LENGTH">NET\_MAX\_USER\_LENGTH</a></br>];

bool reserved; //是否保留

bool shareable; //本用户是否允许复用 1-复用，0-不复用

}USER\_INFO;




typedef struct \_USER\_GROUP\_INFO
{

int rigthNum;

char memo[<a href="http://open.xmeye.net/zh/#NET_MAX_USER_LENGTH">NET\_MAX\_USER\_LENGTH</a></br>]; 

char name[<a href="http://open.xmeye.net/zh/#NET_MAX_USER_LENGTH">NET\_MAX\_USER\_LENGTH</a></br>];

char rights[<a href="http://open.xmeye.net/zh/#NET_MAX_RIGTH_NUM">NET\_MAX\_RIGTH\_NUM][<a href="http://open.xmeye.net/zh/#NET_MAX_USER_LENGTH">NET\_MAX\_USER\_LENGTH];  //权限列表

}USER\_GROUP\_INFO;




//用户信息配置结构

typedef struct\_USER\_MANAGE\_INFO
{

int rigthNum;

<a href="http://open.xmeye.net/zh/#OPR_RIGHT">OPR\_RIGHT</a></br> rightList[<a href="http://open.xmeye.net/zh/#NET_MAX_RIGTH_NUM">NET\_MAX\_RIGTH\_NUM</a></br>];

int groupNum;

<a href="http://open.xmeye.net/zh/#USER_GROUP_INFO">USER\_GROUP\_INFO groupList[<a href="http://open.xmeye.net/zh/#NET_MAX_GROUP_NUM">NET\_MAX\_GROUP\_NUM</a></br>];

int userNum;

<a href="http://open.xmeye.net/zh/#USER_INFO">USER_INFO</a></br> userList[<a href="http://open.xmeye.net/zh/#NET_MAX_USER_NUM">NET\_MAX\_USER\_NUM</a></br>];

}<a href="http://open.xmeye.net/zh/#USER_MANAGE_INFO">USER\_MANAGE\_INFO</a></br>;




//修改用户

typedef struct\_CONF\_MODIFYUSER
{

char UserName[<a href="http://open.xmeye.net/zh/#NET_MAX_USER_LENGTH">NET\_MAX\_USER\_LENGTH</a></br>];

<a href="http://open.xmeye.net/zh/#USER_INFO">USER\_INFO</a></br> User;

}<a href="http://open.xmeye.net/zh/#CONF_MODIFYUSER">CONF\_MODIFYUSER</a></br>;




//修改组

typedef struct\_CONF\_MODIFYGROUP
{

char GroupName[<a href="http://open.xmeye.net/zh/#NET_MAX_USER_LENGTH">NET\_MAX\_USER\_LENGTH</a></br>];

<a href="http://open.xmeye.net/zh/#USER_GROUP_INFO">USER\_GROUP\_INFO </a></br>Group;

}<a href="http://open.xmeye.net/zh/#CONF_MODIFYGROUP">CONF_MODIFYGROUP;




/// 修改用户密码请求

struct\_CONF\_MODIFY\_PSW
{

char sUserName[<a href="http://open.xmeye.net/zh/#NET_MAX_USER_LENGTH">NET\_MAX\_USER\_LENGTH</a></br>];

char Password[<a href="http://open.xmeye.net/zh/#NET_MAX_USER_LENGTH">NET\_MAX\_USER\_LENGTH</a></br>];

char NewPassword[<a href="http://open.xmeye.net/zh/#NET_MAX_USER_LENGTH">NET\_MAX\_USER\_LENGTH</a></br>];

};

日志信息


 #define <a href="http://open.xmeye.net/zh/#NET_MAX_RETURNED_LOGLIST">NET\_MAX\_RETURNED\_LOGLIST</a></br>   1024       //最多日志条数

/// 日志查询条件

struct <a href="http://open.xmeye.net/zh/#LogSearchCondition">SDK\_LogSearchCondition</a></br>
{

int nType;    ///< 日志类型

 int iLogPosition;            ///< 从上次查询的结束时的日志指针

<a href="http://open.xmeye.net/zh/#SYSTEM_TIME">SDK\_SYSTEM\_TIME </a></br>stBeginTime;    ///< 查询日志开始时间

<a href="http://open.xmeye.net/zh/#SYSTEM_TIME">SDK\_SYSTEM\_TIME</a></br> stEndTime;      ///< 查询日志结束时间

};

struct <a href="http://open.xmeye.net/zh/#LogItem">SDK\_LogItem</a></br>
{

 char sType[24];    ///< 日志类型

 char sUser[32];    ///< 日志用户

 char sData[68];    ///< 日志数据

 <a href="http://open.xmeye.net/zh/#SYSTEM_TIME">SDK\_SYSTEM\_TIME </a></br>stLogTime;  ///< 日志时间

 int iLogPosition;        ///< 从上次查询的结束时的日志指针

};

//日志返回信息

struct <a href="http://open.xmeye.net/zh/#LogList">SDK\_LogList</a></br>
{

 int iNumLog;

 <a href="http://open.xmeye.net/zh/#LogItem">SDK\_LogItem</a></br> Logs[<a href="http://open.xmeye.net/zh/#NET_MAX_RETURNED_LOGLIST">NET\_MAX\_RETURNED\_LOGLIST</a></br>];

};

查询硬盘信息的返回数据结构
enum
{

SDK_MAX_DRIVER_PER_DISK = 4,		///< 每个磁盘最多的分区数

SDK_MAX_DISK_PER_MACHINE = 8,		///< 最多支持8块硬盘

};

//硬盘管理

typedef struct <a href="http://open.xmeye.net/zh/#STORAGEDISK">SDK\_STORAGEDISK</a></br>
{

int		iPhysicalNo;

int		iPartNumber;		// 分区数

<a href="http://open.xmeye.net/zh/#DriverInformation">SDK\_DriverInformation</a></br> diPartitions[<a href="http://open.xmeye.net/zh/#MAX_DRIVER_PER_DISK">SDK\_MAX\_DRIVER\_PER\_DISK</a></br>];

}SDK\_STORAGEDISK;




typedef struct <a href="http://open.xmeye.net/zh/#StorageDeviceInformationAll">SDK\_StorageDeviceInformationAll</a></br>
{

int iDiskNumber;

<a href="http://open.xmeye.net/zh/#STORAGEDISK">SDK\_STORAGEDISK </a></br>vStorageDeviceInfoAll[<a href="http://open.xmeye.net/zh/#MAX_DISK_PER_MACHINE">SDK\_MAX\_DISK\_PER\_MACHINE</a></br>];

}SDK\_StorageDeviceInformationAll;

网络监视

typedef struct <a href="http://open.xmeye.net/zh/#CLIENTINFO">H264\_DVR\_CLIENTINFO</a></br>
{

int nChannel;	//通道号

int nStream;	//0表示主码流，为1表示子码流

int nMode;	//0：TCP方式,1：UDP方式,2：多播方式,3 - RTP方式，4-音视频分开(TCP)

int nComType;	//只对组合编码通道有效, 组合编码通道的拼图模式

  void* hWnd;     //预览输出窗口句柄（为NULL时候，网络数据与解码播放分开处理）

}*LPH264\_DVR\_CLIENTINFO;

### 网络报警信息

typedef struct <a href="http://open.xmeye.net/zh/#NetAlarmInfo">SDK\_NetAlarmInfo</a></br>
{

int iEvent;   //目前未使用

int iState;   //每bit表示一个通道,bit0:第一通道,0-无报警 1-有报警, 依次类推

}SDK\_NetAlarmInfo;





///< 报警中心设置

typedef struct <a href="http://open.xmeye.net/zh/#NetAlarmCenterConfig">SDK\_NetAlarmCenterConfig</a></br>
{

bool bEnable;	///< 是否开启

char sAlarmServerKey[<a href="http://open.xmeye.net/zh/#NET_NAME_PASSWORD_LEN">NET\_NAME\_PASSWORD\_LEN</a></br>];	///< 报警中心协议类型名称,

<a href="http://open.xmeye.net/zh/#RemoteServerConfig">SDK\_RemoteServerConfig</a></br> Server;			///< 报警中心服务器

bool bAlarm;

bool bLog;

}SDK\_NetAlarmCenterConfig;




typedef struct <a href="http://open.xmeye.net/zh/#NetAlarmServerConfigAll">SDK\_NetAlarmServerConfigAll</a></br>
{

<a href="http://open.xmeye.net/zh/#NetAlarmCenterConfig">SDK\_NetAlarmCenterConfig</a></br> vAlarmServerConfigAll[<a href="http://open.xmeye.net/zh/#NET_MAX_ALARMSERVER_TYPE">NET\_MAX\_ALARMSERVER\_TYPE</a></br>];

}SDK\_NetAlarmServerConfigAll;




// 报警中心消息类型

enum <a href="http://open.xmeye.net/zh/#AlarmCenterMsgType">SDK\_AlarmCenterMsgType</a></br>
{

SDK\_ALARMCENTER\_ALARM,

SDK\_ALARMCENTER\_LOG,

};




// 报警中心消息类型

enum <a href="http://open.xmeye.net/zh/#AlarmCenterStatus">SDK\_AlarmCenterStatus</a></br>
{

SDK\_AC\_START,

SDK\_AC\_STOP,

};




// 告警中心消息内容

typedef struct <a href="http://open.xmeye.net/zh/#NetAlarmCenterMsg">SDK\_NetAlarmCenterMsg</a></br>
{

CONFIG_IPAddress HostIP;		///< 设备IP

int  nChannel;             ///< 通道

int  nType;               ///< 类型 见AlarmCenterMsgTypev

int  nStatus;              ///< 状态 见AlarmCenterStatus

<a href="http://open.xmeye.net/zh/#SYSTEM_TIME">SDK\_SYSTEM_TIME</a></br> Time;         ///< 发生时间

char sEvent[<a href="http://open.xmeye.net/zh/#NET_MAX_INFO_LEN">NET\_MAX\_INFO\_LEN</a></br>];  	///< 事件

char sSerialID[<a href="http://open.xmeye.net/zh/#NET_MAX_MAC_LEN">NET\_MAX\_MAC\_LEN</a></br>]; 	///< 设备序列号

char sDescrip[<a href="http://open.xmeye.net/zh/#NET_MAX_INFO_LEN">NET\_MAX\_INFO\_LEN</a></br>];  ///< 描述

}SDK\_NetAlarmCenterMsg;

### 存储设备控制信息

enum <a href="http://open.xmeye.net/zh/#StorageDeviceControlTypes">SDK\_StorageDeviceControlTypes</a></br>
{

SDK\_STORAGE\_DEVICE\_CONTROL\_SETTYPE,	///< 设置类型

SDK\_STORAGE\_DEVICE\_CONTROL\_RECOVER,	///< 恢复错误

SDK\_STORAGE\_DEVICE\_CONTROL\_PARTITIONS,	///< 分区操作

SDK\_STORAGE\_DEVICE\_CONTROL\_CLEAR,		///< 清除操作



SDK\_STORAGE\_DEVICE\_CONTROL\_ADDNAS,	///<添加NAS

SDK\_STORAGE\_DEVICE\_CONTROL\_CHANGENAS,	///修改NAS

SDK\_STORAGE\_DEVICE\_CONTROL\_DELNAS,	///<删除NAS

SDK_STORAGE\_DEVICE\_CONTROL\_NR,

};

### RTSP信息

typedef struct <a href="http://open.xmeye.net/zh/#NetRTSPConfig">SDK\_NetRTSPConfig</a></br>
{

bool bServer;

bool bClient;

<a href="http://open.xmeye.net/zh/#RemoteServerConfig">SDK\_RemoteServerConfig </a></br>Server;		///< 服务器模式

<a href="http://open.xmeye.net/zh/#RemoteServerConfig">SDK\_RemoteServerConfig</a></br> Client;		///< 客户端模式

}SDK\_NetRTSPConfig;

### 互信互通

typedef struct <a href="http://open.xmeye.net/zh/#CONFIG_NET_MEGA">SDK\_CONFIG\_NET\_MEGA</a></br>
{

bool bEnable;

bool bNetManEnable;

CONFIG_IPAddress ServerIP;

int  iServerPort;

char sDeviceId[32];

char sUserName[24];

char sPasswd[32];

int  iMaxCon;

int  iVideoPort;

int  iAudioPort;

int  iMsgPort;

int  iUpdatePort;

}SDK\_CONFIG\_NET\_MEGA;

### 新望平台

typedef struct <a href="http://open.xmeye.net/zh/#CONFIG_NET_XINGWANG">SDK\_CONFIG\_NET\_XINGWANG</a></br>
{

bool bEnable;

bool bSyncTime;

bool bSubStream;

CONFIG_IPAddress ServerIP;

int  iServerPort;

int  iDownLoadPort;

char sPasswd[32];

char szSID[32];

}SDK\_CONFIG\_NET\_XINGWANG;

### 视搜平台

typedef struct <a href="http://open.xmeye.net/zh/#CONFIG_NET_SHISOU">SDK\_CONFIG\_NET\_SHISOU</a></br>
{

bool bEnable;

SDK_RemoteServerConfig Server;

char szSID[<a href="http://open.xmeye.net/zh/#NET_MAX_USERNAME\_LENGTH">NET\_MAX\_USERNAME\_LENGTH</a></br>];

}SDK\_CONFIG\_NET\_SHISOU;

### VVEYE平台

typedef struct <a href="http://open.xmeye.net/zh/#CONFIG">SDK\_CONFIG\_NET\_VVEYE</a></br>
{

bool bEnable;

bool bCorpEnable;        //只有在使用企业服务器时才需要设置Server

<a href="http://open.xmeye.net/zh/#RemoteServerConfig">SDK\_RemoteServerConfig </a></br>Server;

char szDeviceName[<a href="http://open.xmeye.net/zh/#NET_MAX_USERNAME_LENGTH">NET\_MAX\_USERNAME\_LENGTH</a></br>];

}SDK\_CONFIG\_NET\_VVEYE;

### 媒体包以及包信息

typedef enum <a href="http://open.xmeye.net/zh/#SERIAL_TYPE">SERIAL\_TYPE</a></br>
{

RS232 = 0,

RS485 = 1,

}SERIAL\_TYPE;

enum <a href="http://open.xmeye.net/zh/#MEDIA_PACK_TYPE">MEDIA\_PACK\_TYPE</a></br>
{

FILE\_HEAD =	0,	   	// 文件头

VIDEO\_I\_FRAME = 1,		// 视频I帧

VIDEO\_B\_FRAME =	2,		// 视频B帧

VIDEO\_P\_FRAME = 3,		// 视频P帧

VIDEO\_BP\_FRAME = 4,		// 视频BP帧

VIDEO\_BBP\_FRAME	= 5,		// 视频B帧B帧P帧

VIDEO\_J\_FRAME = 6,		// 图片帧

AUDIO\_PACKET = 10,		// 音频包

};




typedef struct
{

int	   nPacketType;	// 包类型,见MEDIA\_PACK\_TYPE

char*	    pPacketBuffer;	// 缓存区地址

unsigned int   dwPacketSize;	// 包的大小



// 绝对时标

int	   nYear;	    // 时标:年

int	   nMonth;	    // 时标:月

int	   nDay;	    // 时标:日

int	   nHour;	    // 时标:时

int	   nMinute;	    // 时标:分

int       nSecond;	    // 时标:秒

unsigned int   dwTimeStamp;	// 相对时标低位，单位为毫秒

unsigned int   dwTimeStampHigh; //相对时标高位，单位为毫秒

unsigned int   dwFrameNum;     //帧序号

unsigned int   dwFrameRate;    //帧率

unsigned short  uWidth;       //图像宽度

unsigned short  uHeight;      //图像高度

unsigned int   Reserved[6];    //保留

} <a href="http://open.xmeye.net/zh/#PACKET_INFO_EX">PACKET\_INFO\_EX</a></br>;


typedef struct <a href="http://open.xmeye.net/zh/#OEMInfo">SDK\_OEMInfo</a></br>
{

int nOEMID;    //OEM ID

char sCompanyName[<a href="http://open.xmeye.net/zh/#NET_MAX_USERNAME_LENGTH">NET\_MAX\_USERNAME\_LENGTH</a></br>]; //公司名

char sTel[<a href="http://open.xmeye.net/zh/#NET_MAX_USERNAME_LENGTH">NET\_MAX\_USERNAME\_LENGTH</a></br>];      //电话

char sAddr[<a href="http://open.xmeye.net/zh/#NET_MAX_USERNAME_LENGTH">NET\_MAX\_USERNAME\_LENGTH</a></br>];      //地址

}SDK\_OEMInfo;


typedef struct\_TransComChannel  //透明窗口
{

<a href="http://open.xmeye.net/zh/#SERIAL_TYPE">SERIAL\_TYPE</a></br> TransComType;	//SERIAL\_TYPE

unsigned int baudrate;

unsigned int databits;

unsigned int stopbits;

unsigned int parity;

} <a href="http://open.xmeye.net/zh/#TransComChannel">TransComChannel</a></br>;

typedef enum <a href="http://open.xmeye.net/zh/#State_Type">SDK\_State\_Type</a></br>
{

DEV\_STATE\_DDNS=0,

}SDK\_State\_Type;




//摄象机参数.....

//曝光配置

typedef struct <a href="http://open.xmeye.net/zh/#ExposureCfg">SDK\_ExposureCfg</a></br>
{

int  level;    	//曝光等级

unsigned int leastTime;	//自动曝光时间下限或手动曝光时间，单位微秒

unsigned int mostTime; 	//自动曝光时间上限，单位微秒

}SDK\_ExposureCfg;




 //增益配置

typedef struct <a href="http://open.xmeye.net/zh/#GainCfg">SDK\_GainCfg</a></br>
{

int gain;    //自动增益上限(自动增益启用)或固定增益值

int autoGain;//自动增益是否启用，0:不开启  1:开启

}SDK\_GainCfg;




 //网络摄像机配置

typedef struct <a href="http://open.xmeye.net/zh/#CameraParam">SDK\_CameraParam</a></br>
{

unsigned int whiteBalance;      //白平衡

unsigned int dayNightColor;     //日夜模式，取值有彩色、自动切换和黑白

int elecLevel;             	//参考电平值

unsigned int apertureMode;      //自动光圈模式

unsigned int BLCMode;          //背光补偿模式

<a href="http://open.xmeye.net/zh/#ExposureCfg">SDK\_ExposureCfg </a></br>exposureConfig;	 //曝光配置

<a href="http://open.xmeye.net/zh/#GainCfg">SDK\_GainCfg</a></br>     gainConfig;    //增益配置

unsigned int PictureFlip;		//图片上下翻转

unsigned int PictureMirror;	//图片左右翻转(镜像)

unsigned int RejectFlicker;	//日光灯防闪功能

unsigned int EsShutter;		//电子慢快门功能

int ircut_mode;		//IR-CUT切换 0 = 红外灯同步切换 1 = 自动切换

int dnc_thr;		//日夜转换阈值

int ae_sensitivity;	//ae灵敏度配置

int Day_nfLevel;	//noise filter 等级，0-5,0不滤波，1-5 值越大滤波效果越明显

int Night_nfLevel;

int Ircut_swap;		//ircut 正常序= 0   反序= 1

int high_light;     //强光抑制功能 0~255,默认是16

}SDK\_CameraParam;




//所有摄象机配置

typedef struct <a href="http://open.xmeye.net/zh/#AllCameraParam">SDK\_AllCameraParam</a></br>
{

SDK\_CameraParam vCameraParamAll[<a href="http://open.xmeye.net/zh/#NET_MAX_CHANNUM">NET\_MAX\_CHANNUM</a></br>];   //所有的通道

}SDK\_AllCameraParam;




//曝光能力级

typedef struct <a href="http://open.xmeye.net/zh/#CameraAbility">SDK\_CameraAbility</a></br>
{

int  count;      			//支持曝光速度数量

unsigned int speeds[<a href="http://open.xmeye.net/zh/#CAMERAPARA_MAXNUM">CAMERAPARA_MAXNUM</a></br>];  //曝光速度

int  status;     		    //工作状态  >= 0 正常  < 0 异常

int  elecLevel;  			//参考电平值

int  luminance;  			//平均亮度

char pVersion[64];			//xm 2a版本

char isFishLens; //是否是鱼眼镜头，如果是，则需要app和PC端做图像校正

char resv1[3];   //保留，如果增加char型的成员先用这里的

char reserve[28];//保留，如果增加int型的成员用这里

}SDK\_CameraAbility;

### 本地播放控制

enum <a href="http://open.xmeye.net/zh/#LoalPlayAction">SDK\_LoalPlayAction</a></br>
{

SDK\_Local\_PLAY\_PAUSE,	/*<! 暂停播放 */

SDK\_Local\_PLAY\_CONTINUE,	/*<! 继续正常播放 */

SDK\_Local\_PLAY\_FAST,	/*<! 加速播放 */

SDK\_Local\_PLAY\_SLOW,	/*<! 减速播放 */
};

### 主动服务

//主动服务回调数据

typedef struct <a href="http://open.xmeye.net/zh/#ACTIVEREG_INFO">H264\_DVR\_ACTIVEREG\_INFO</a></br>
{

char deviceSarialID[64];		//设备序列号，如果大于64位则赋值0

<a href="http://open.xmeye.net/zh/#DEVICEINFO">H264\_DVR\_DEVICEINFO </a></br>deviceInfo;	//设备信息

char IP[<a href="http://open.xmeye.net/zh/#IP_SIZE">IP\_SIZE</a></br>];   		//外网IP

}H264\_DVR\_ACTIVEREG\_INFO;

### 子连接类型

typedef enum <a href="http://open.xmeye.net/zh/#SubConnType">SubConnType</a></br>
{

conn\_realTimePlay=1,

conn\_talk,

conn\_playback

}SubConnType;

### 连接类型

//向设备注册

enum <a href="http://open.xmeye.net/zh/#SocketStyle">SocketStyle</a></br>
{

TCPSOCKET=0,

UDPSOCKET,	

PLUGLANSOCKET=4,		//插座局域网登陆

PLUGOUTERSOCKET,		//插座外网登陆

P2P\_TUTKSOCKET,			//TUTK P2P

 SOCKETNR

};

### 搜索协议类型

typedef enum <a href="http://open.xmeye.net/zh/#TransferProtocol_V2">SDK\_TransferProtocol\_V2</a></br>
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

### 搜索在线设备的基本类型

typedef struct <a href="http://open.xmeye.net/zh/#SDevicesState">SDK\_SDevicesState</a></br>
{

int 	num;	 	//设备数量

char uuid[32][32];	//最大32个序列号

int state[32];    	//0:不在线，1:在线

}SDK\_SDevicesState;

### 密码找回

//安全问题配置

struct SDK_PwdPresetQsPair 
{

int questionIndex;				//问题序号

char strAnswer[256];			//答案

};

struct SDK_PasswordSafety 
{

bool bTipPageHide;				//是否隐藏密码为空时的提示页面

SDK_PwdPresetQsPair PwdResetQs[4];	//安全问题和答案

char resv[20];

};




//获取找回密码的问题

struct SDK_QuestionDelivery
{

int  nStrNum;		//问题个数

char vQuestionStr[7][256];

};

### 车牌识别及人脸识别

typedef struct SDK\_PlateDetectWhiteList
{ 

int iAddrCount;			   //车牌个数

char vWhiteListAddr[256][256]; // 车牌白名单地址

}SDK\_PlateDetectWhiteList;




//车牌侦测升降杆控制

typedef struct SDK\_PlateDetectLiftBar
{ 

bool bLiftBarCmd;

int	iChannel;

}SDK\_PlateDetectLiftBar;




//报警回调类型

enum 
{ 

ALARM\_TYPE = 1,

PUSH\_TYPE,

};




enum SDK_INTEL_PUSH_TYPE
{ 

SDK\_INTEL\_PUSH\_TYPE\_CAR_PLATE = 0,	//表示车牌类型

SDK\_INTEL\_PUSH\_TYPE\_FACE      = 1,	//表示人脸类型

SDK\_INTEL\_PUSH\_TYPE\_ALL       = 255,//表示全部类型

};

enum SDK\_INTEL\_PUSH\_IMG\_TYPE
{ 

SDK\_INTEL\_PUSH\_IMG\_TYPE\_FULL   = 1,	//表示只要大图

SDK\_INTEL\_PUSH\_IMG\_TYPE\_TARGET = 2,	//表示只要小图

SDK\_INTEL\_PUSH\_IMG\_TYPE\_NR			//表示两种图都要

};




//车牌区域

typedef struct SDK\_RECT\_S
{ 

int leftX;

int topY;

int width;

int height;

} SDK\_RECT\_S;




typedef struct SDK\_PLATE\_DETECT
{

char acPlateCode[20];	//车牌号码，尾部有字符串结束符"\0" 

char acPlateColor[4];	//车牌颜色，黄蓝黑白或"无"代表未知，字符串结束符"\0"，字符编码格式为

}SDK\_PLATE\_DETECT;




typedef struct SDK\_FACE\_DETECT
{ 

char sex;            //性别

char age;            //年龄

char resv[20];

}SDK\_FACE\_DETECT;




typedef struct SDK\_IA\_LPR\_TARGET\_INFO
{

SDK\_RECT\_S stRect;

union
{

SDK\_FACE\_DETECT face;

SDK\_PLATE\_DETECT plate;

}DETECT;

char resv[16];

}SDK\_IA\_LPR\_TARGET\_INFO;




typedef struct SDK\_IA\_LPR\_REC\_S
{

unsigned short resultType; //识别类型类型  0:车牌  1:人脸识别  

unsigned short picSubType; //0:大图  1:小图

unsigned short picFormat;  //0:jpg  1:bmp   2:yuv

unsigned short tagNum;		//目标个数

SDK\_IA\_LPR\_TARGET\_INFO pTargetInfo[8]; //最多支持8个目标

char resv[32];

}SDK\_IA\_LPR\_REC\_S;




typedef struct SDK\_PushRetData
{

SDK\_IA\_LPR\_REC\_S iaLprRecs;	

int nChannel;				//通道号

int nLenSize;				//图片大小

unsigned char* pBuffer;		//图片数据

}SDK\_PushRetData;




typedef struct SDK\_PlateDetectCfg
{

int iDefaultL;//默认字母，比如"A" 

int iDefaultP;// 默认汉字，比如"浙" ,采用gb2312编码

int resv;

SDK\_RECT\_S astLpRect[7];

int iMaxWidth;

int iMinWidth;

}SDK\_PlateDetectCfg;




//车牌检测

typedef struct SDK\_PlateDetect
{

bool	bEnable;				//true:开启,false:关闭

SDK\_PlateDetectCfg stPlateParam;//车牌检测参数设置

SDK\_EventHandler hEvent;			//车牌检测联动参数

}SDK\_PlateDetect;




//全通道车牌检测

typedef struct SDK_PlateDetectAll
{

SDK\_PlateDetect vPlateDetect[NET\_MAX\_CHANNUM];

}SDK\_PlateDetectAll;




//人脸相关结构体：

typedef struct SDK\_FaceRect
{
int s32X;
int s32Y;
int u32Width;
int u32Height;
}SDK\_FaceRect;




//人脸检测

typedef struct SDK\_FaceDetect
{

bool	bEnable;			//true:开启,false:关闭

SDK\_FaceRect stFaceParam;	//人脸检测参数设置

SDK\_EventHandler hEvent;	//人脸检测联动参数

}SDK\_FaceDetect;




//全通道人脸检测

typedef struct SDK\_FaceDetectAll
{

SDK\_FaceDetect vFaceDetect[NET\_MAX\_CHANNUM];

}SDK\_FaceDetectAll;



 
​