<pre>
<label style="color:green">////////////////////////General and common used error definitions/////////////////////////////</label>
    EE_OK = 0,
    EE_OBJ_NOT_EXIST = -1239510,
    EE_ERROR = -100000,
    EE_PARAM_ERROR = -99999,
    EE_CREATE_FILE = -99998,
    EE_OPEN_FILE = -99997,
    EE_WRITE_FILE = -99996,
    EE_READ_FILE = -99995,
    EE_NO_SUPPORTED = -99994,
    EE_NET = -99993,                    // Network error

    
    <label style="color:green">/// Enumeration of error values used in this interface</label>
    EE_DVR_SDK_NOTVALID            = -10000,            // Illegal request 
    EE_DVR_NO_INIT                = -10001,            // SDK without initialization
    EE_DVR_ILLEGAL_PARAM        = -10002,            // User parameter is invalid
    EE_DVR_INVALID_HANDLE        = -10003,            // Invalid handle
    EE_DVR_SDK_UNINIT_ERROR        = -10004,            // SDK cleanup error
    EE_DVR_SDK_TIMEOUT            = -10005,            // Wait timeout
    EE_DVR_SDK_MEMORY_ERROR        = -10006,            // Memory error, create memory failed
    EE_DVR_SDK_NET_ERROR        = -10007,            // Network error
    EE_DVR_SDK_OPEN_FILE_ERROR    = -10008,            // Open file failed
    EE_DVR_SDK_UNKNOWNERROR        = -10009,            // Unknown error
    EE_DVR_DEV_VER_NOMATCH        = -11000,            // Received data is incorrect, the version may not match
    EE_DVR_SDK_NOTSUPPORT        = -11001,            // Version is not supported    
    
    EE_DVR_OPEN_CHANNEL_ERROR    = -11200,            // Open channel failed
    EE_DVR_CLOSE_CHANNEL_ERROR    = -11201,            // Close channel failed
    EE_DVR_SUB_CONNECT_ERROR    = -11202,            // Establish media sub connections failed
    EE_DVR_SUB_CONNECT_SEND_ERROR = -11203,            // Media sub connection communication failure
    EE_DVR_NATCONNET_REACHED_MAX  = -11204,         // Nat video link reaches the maximum and do not allow the new Nat video link
    
    <label style="color:green">/// User management section error code</label>
    EE_DVR_NOPOWER                    = -11300,            // No permission
    EE_DVR_PASSWORD_NOT_VALID        = -11301,            // Incorrect account and password
    EE_DVR_LOGIN_USER_NOEXIST        = -11302,            // User does not exist
    EE_DVR_USER_LOCKED                = -11303,            // User is locked
    EE_DVR_USER_IN_BLACKLIST        = -11304,            // User is not allowed to visit (in the black list)
    EE_DVR_USER_HAS_USED            = -11305,            // User is logged in
    EE_DVR_USER_NOT_LOGIN            = -11306,            // User is not logged in
    EE_DVR_CONNECT_DEVICE_ERROR    = -11307,            // Device may not exist
    EE_DVR_ACCOUNT_INPUT_NOT_VALID = -11308,            // User management input is invalid
    EE_DVR_ACCOUNT_OVERLAP            = -11309,            // Index overlap
    EE_DVR_ACCOUNT_OBJECT_NONE        = -11310,            // There is no object, used for query
    EE_DVR_ACCOUNT_OBJECT_NOT_VALID= -11311,            // There is no object, used for query
    EE_DVR_ACCOUNT_OBJECT_IN_USE    = -11312,            // Object is being used
    EE_DVR_ACCOUNT_SUBSET_OVERLAP    = -11313,            // Subset exceeds range (for example, the permissions of group exceed permissions table, user rights exceed the scope of the permissions range of group etc.
    EE_DVR_ACCOUNT_PWD_NOT_VALID    = -11314,            // Incorrect password
    EE_DVR_ACCOUNT_PWD_NOT_MATCH    = -11315,            // Passwords do not match
    EE_DVR_ACCOUNT_RESERVED            = -11316,            // Keep account   

   

    <label style="color:green">/// Configuration management related error code</label>
    EE_DVR_OPT_RESTART                = -11400,            // After saving the configuration, need to restart the application
    EE_DVR_OPT_REBOOT                = -11401,            // Need to reboot the system
    EE_DVR_OPT_FILE_ERROR            = -11402,            // Writing file error
    EE_DVR_OPT_CAPS_ERROR            = -11403,            // Configuration properties are not supported
    EE_DVR_OPT_VALIDATE_ERROR        = -11404,            // Configuration check failed
    EE_DVR_OPT_CONFIG_NOT_EXIST        = -11405,            // Requested or setting configuration does not exist
     EE_DVR_OPT_CONFIG_PARSE_ERROR   = -11406,           // Configuration parse error

    <label style="color:green">/// </label>
    EE_DVR_CTRL_PAUSE_ERROR        = -11500,              // Pause failed
    EE_DVR_SDK_NOTFOUND            = -11501,              // Find failed, not find the corresponding file
    EE_DVR_CFG_NOT_ENABLE       = -11502,             // Configuration not enabled
    EE_DVR_DECORD_FAIL          = -11503,             // Decode failed
    
    <label style="color:green">//DNS protocol parse return error code</label>
    EE_DVR_SOCKET_ERROR             = -11600,         // Create socket failed
    EE_DVR_SOCKET_CONNECT           = -11601,         // Connect socket failed
    EE_DVR_SOCKET_DOMAIN            = -11602,         // Domain name resolution failed
    EE_DVR_SOCKET_SEND              = -11603,         // Send data failed
    EE_DVR_ARSP_NO_DEVICE           = -11604,         // Not get to device information, device should not be online
    EE_DVR_ARSP_BUSING              = -11605,         // ARSPserver is busy
    EE_DVR_ARSP_BUSING_SELECT       = -11606,         // ARSP server is busy, select failed
    EE_DVR_ARSP_BUSING_RECVICE        = -11607,         // ARSP server is busy, recvice failed
    EE_DVR_CONNECTSERVER_ERROR      = -11608,         // Connect to server failed
    EE_DVR_ARSP_USER_NOEXIST        = -11609,        // User does not exist 
    EE_DVR_ARSP_PASSWORD_ERROR        = -11610,          // Incorrect account and password
    EE_DVR_ARSP_QUERY_ERROR            = -11611,          // Search failed
    EE_DVR_CONNECT_FULL            = -11612,       // Numbers of server connection are full
    
    <label style="color:green">//Copyright related</label>
    EE_DVR_PIRATESOFTWARE           =-11700,         // Device piracy
    
    EE_ILLEGAL_PARAM = -200000,        // Invalid parameters
    EE_USER_NOEXIST = -200001, // User does not exist
    EE_SQL_ERROR = -200002, // sql failure
    EE_PASSWORD_NOT_VALID = -200003, // Incorrect password
    EE_USER_NO_DEV = -200004, // User does not have the device
    EE_DEV_NOT_LOGIN = -200005, // Login failed
    EE_FUN_BEEN_START = -200006,
    EE_USER_EXSIT = -200007,        // Username has been registered
    EE_DSS_NOT_SUP_MAIN = -210008,   // DSSdoes not support HD mode
    EE_TPS_NOT_SUP_MAIN = -210009,   // Transmitting mode does not support HD mode
    <label style="color:green">//Public command word</label>
    EE_MC_UNKNOWNERROR = -201101, /// Unknown error
    EE_MC_NOTVALID = -201102, /// Illegal request
    EE_MC_MSGFORMATERR = -201103, /// Message format error
    EE_MC_LOGINED = -201104, /// User has logged in
    EE_MC_UNLOGINED = -201105, /// User is not logged in
    EE_MC_USERORPWDERROR = -201106, /// Incorrect username and password
    EE_MC_NOPOWER = -201107, /// No permissions
    EE_MC_NOTSUPPORT = -201108, /// Version is not supported
    EE_MC_TIMEOUT = -201109, /// Timeout
    EE_MC_NOTFOUND = -201110, /// Find failed, did not find the corresponding file
    EE_MC_FOUND = -201111, /// Find success, return all files
    EE_MC_FOUNDPART = -201112, /// Find success, return some files
    EE_MC_PIRATESOFTWARE = -201113, /// Pirated software
    EE_MC_FILE_NOT_FOUND = -201114, /// Not query file
    EE_MC_PEER_ONLINE = -201115,   /// Peer online
    EE_MC_PEER_NOT_ONLINE = -201116, /// Peer not online
    EE_MC_PEERCONNET_REACHED_MAX = -201117, /// Peer connection numbers have reached the upper limit
    EE_MC_LINK_SERVER_ERROR = -201118, ///Connect server failed
    EE_MC_APP_TYPE_ERROR = -201119, ///App type error
    EE_MC_SEND_DATA_ERROR = -201120, ///Send data error
    EE_MC_AUTHCODE_ERROR = -201121, ///Get AUTHCODE error
    EE_MC_XPMS_UNINIT = -201122, ///Uninitialized


    
    EE_AS_PHONE_CODE0 =-210002, //Interface validation failed
    EE_AS_PHONE_CODE1 =-210003, //Parameters error
    EE_AS_PHONE_CODE2 =-210004, //Mobile phone number has been registered
    EE_AS_PHONE_CODE3 =-210005, //Exceed the number of sending message everyday (each phone number can only send registration validation information for three times everyday)
    EE_AS_PHONE_CODE4 =-210010, //Send failed
    EE_AS_PHONE_CODE5 =-210017, // It can only be sent once within 120 seconds.
    
    
    EE_AS_REGISTER_CODE0 =-210102, //Interface validation failed
    EE_AS_REGISTER_CODE1 =-210103, //Parameters error 
    EE_AS_REGISTER_CODE2 =-210104, //Phone number has been registered
    EE_AS_REGISTER_CODE3 =-210106, //Username has been registered
    EE_AS_REGISTER_CODE4 =-210107, //Registration code validation error
    EE_AS_REGISTER_CODE5 =-210110, //Register failed (there is specific information about failure in msg)
    
    EE_AS_LOGIN_CODE1 =-210202, //Interface validation failed
    EE_AS_LOGIN_CODE2 =-210203, //Parameters error
    EE_AS_LOGIN_CODE3 =-210210, //Login failed
    
    EE_AS_EIDIT_PWD_CODE1 =-210302, // Interface validation failed
    EE_AS_EIDIT_PWD_CODE2 =-210303, // Parameters error
    EE_AS_EIDIT_PWD_CODE3 =-210311, // The new password does not meet the requirements
    EE_AS_EIDIT_PWD_CODE4 =-210313, // Original password error
    EE_AS_EIDIT_PWD_CODE5 =-210315, // Please input a new password that is different from the original password 
    
    EE_AS_FORGET_PWD_CODE1 =-210402, // Interface validation failed
    EE_AS_FORGET_PWD_CODE2 =-210403, // Parameters error
    EE_AS_FORGET_PWD_CODE3 =-210405, // Exceed the number of sending message everyday (each phone number can only send registration validation information for three times everyday.
    EE_AS_FORGET_PWD_CODE4 =-210410, // Send failed (there is specific information about failure in msg)
    EE_AS_FORGET_PWD_CODE5 =-210414, // Phone number does not exist
    
    EE_AS_RESET_PWD_CODE1 =-210502, //Interface validation failed
    EE_AS_RESET_PWD_CODE2 =-210503, //Parameters error
    EE_AS_RESET_PWD_CODE3 =-210511, //The new password does not meet the requirements
    EE_AS_RESET_PWD_CODE4 =-210512, //Two new passwords are not the same
    EE_AS_RESET_PWD_CODE5 =-210514, //Phone number does not exist
    EE_AS_CHECK_PWD_CODE1 =-210602, //Interface validation failed
    EE_AS_CHECK_PWD_CODE2 =-210603, //Parameters error
    EE_AS_CHECK_PWD_CODE3 =-210607, //Verification code error
    EE_AS_CHECK_PWD_CODE4 =-210614, //Phone number does not exist
    

    <label style="color:green">//Video Square related</label>
    EE_AS_GET_PUBLIC_DEV_LIST_CODE = -210700, // Server response failed
    
    EE_AS_GET_SHARE_DEV_LIST_CODE = -210800, // Server response failed
    
    EE_AS_SET_DEV_PUBLIC_CODE = -210900, // Server response failed
    
    EE_AS_SHARE_DEV_VIDEO_CODE = -211000, // Server response failed
    
    EE_AS_CANCEL_DEV_PUBLIC_CODE = -211100, // Server response failed
    
    EE_AS_CANCEL_SHARE_VIDEO_CODE = -211200, // Server response failed
    
    EE_AS_DEV_REGISTER_CODE = -211300, // Server response failed
    
    EE_AS_SEND_COMMNET_CODE  = -211400, // Server response failed
    
    EE_AS_GET_COMMENT_LIST_CODE = -211500, // Server response failed
    
    EE_AS_GET_VIDEO_INFO_CODE = -211600, // Server response failed
    
    EE_AS_UPLOAD_LOCAL_VIDEO_CODE = -211700, // Server response failed
    EE_AS_UPLOAD_LOCAL_VIDEO_CODE1 = -211703, // Lack upload file
    
    EE_AS_GET_SHORT_VIDEO_LIST_CODE = -211800, // Server response failed
    
    EE_AS_EDIT_SHORT_VIDEO_INFO_CODE = -211900, // Server response failed
    
    EE_AS_DELETE_SHORT_VIDEO_CODE = -212000, // Server response failed
    
    EE_AS_SELECT_AUTHCODE_CDOE =  -212100, // Server response failed
    EE_AS_SELECT_AUTHCODE_CDOE1 =  -212104, // Server query failed
    
    EE_AS_GET_USER_PHOTOS_LIST_CODE = -212200, // Server response failed
    
    EE_AS_CREATE_USER_PHOTOS_CODE = -212300, // Server response failed
    
    EE_AS_UPLOAD_PHOTO_CODE = -212400, // Server response failed
    EE_AS_UPLOAD_PHOTO_CODE1 = -212402, // Uploaded file is not received
    
    EE_AS_EDIT_PHOTO_INFO_CODE = -212500, // Server response failed
    
    EE_AS_GET_PHOTO_LIST_CODE = -212600, // Server response failed
    
    EE_AS_DELETE_PHOTO_CODE = -212700, // Server response failed
    
    EE_AS_DELETE_PHOTOS_CODE = -212800, //Server response failed
    
    EE_AS_CHECK_PWD_STRENGTH_CODE = -212900, //Server response failed
    EE_AS_CHECK_PWD_STRENGTH_CODE1 = -212902, //Interface validation failed
    EE_AS_CHECK_PWD_STRENGTH_CODE2 = -212903, //Parameters error
    EE_AS_CHECK_PWD_STRENGTH_CODE3 = -212910, //Password not qualified
    
    <label style="color:green">//Cloud services retrieve password via mailbox return error</label>
    EE_HTTP_PWBYEMAIL_UNFINDNAME = -213000,  //No this user name
    EE_HTTP_PWBYEMAIL_FAILURE = -213001,    //Send failed
    
    EE_AS_SEND_EMAIL_CODE = -213100,    // Server response failed
    EE_AS_SEND_EMAIL_CODE1 = -213102,   // Interface validation failed
    EE_AS_SEND_EMAIL_CODE2 = -213103,   //Parameters error
    EE_AS_SEND_EMAIL_CODE3 = -213108,   //Mailbox has been registered
    EE_AS_SEND_EMAIL_CODE4 = -213110,   //Send failed
    
    EE_AS_REGISTE_BY_EMAIL_CODE = -213200,    // Server response failed
    EE_AS_REGISTE_BY_EMAIL_CODE1 = -213202,    // Interface validation failed
    EE_AS_REGISTE_BY_EMAIL_CODE2 = -213203,    // Parameters error
    EE_AS_REGISTE_BY_EMAIL_CODE3 = -213206,    // Send failed
    EE_AS_REGISTE_BY_EMAIL_CODE4 = -213207,    // Registration code validation error
    EE_AS_REGISTE_BY_EMAIL_CODE5 = -213208,    // Mailbox has been registered
    EE_AS_REGISTE_BY_EMAIL_CODE6 = -213210,    // Register failed
    
    EE_AS_SEND_EMAIL_FOR_CODE = -213300,    // Server response failed
    EE_AS_SEND_EMAIL_FOR_CODE1 = -213302,    // Interface validation failed
    EE_AS_SEND_EMAIL_FOR_CODE3 = -213303,    // Parameters error
    EE_AS_SEND_EMAIL_FOR_CODE4 = -213310,    // Send failed
    EE_AS_SEND_EMAIL_FOR_CODE5 = -213314,    // Mailbox does not exist
    EE_AS_SEND_EMAIL_FOR_CODE6 = -213316,    // Mailbox and username do not match
    
    EE_AS_CHECK_CODE_FOR_EMAIL = -213400,    // Server response failed
    EE_AS_CHECK_CODE_FOR_EMAIL1 = -213402,    // Interface validation failed
    EE_AS_CHECK_CODE_FOR_EMAIL2 = -213403,    // Parameters error
    EE_AS_CHECK_CODE_FOR_EMAIL3 = -213407,    // Verification code error
    EE_AS_CHECK_CODE_FOR_EMAIL4 = -213414,    // Mailbox does not exist
    
    EE_AS_RESET_PWD_BY_EMAIL = -213500,   // Server response failed
    EE_AS_RESET_PWD_BY_EMAIL1 = -213502,   // Interface validation failed
    EE_AS_RESET_PWD_BY_EMAIL2 = -213503,   // Parameters error
    EE_AS_RESET_PWD_BY_EMAIL3 = -213513,   // Reset failed
    EE_AS_RESET_PWD_BY_EMAIL4 = -213514,   //Phone number or mailbox does not exist
    
    EE_CLOUD_DEV_MAC_BACKLIST = -213600,   //101://In the black list (mac)
    EE_CLOUD_DEV_MAC_EXSIT = -213601,    //102://Already exist
    EE_CLOUD_DEV_MAC_EMPTY = -213602,     //104: //mac value is null
    EE_CLOUD_DEV_MAC_INVALID = -213603,     //105: //Incorrect format (the length of the MAC address is not 16 characters or there is a keyword)
    EE_CLOUD_DEV_MAC_UNREDLIST = -213604,     //107:  //White list does not exist
    EE_CLOUD_DEV_NAME_EMPTY = -213605,     //109: //Device name cannot be empty
    EE_CLOUD_DEV_USERNAME_INVALID = -213606, //111: //Device username format is not correct, keywords containing
    EE_CLOUD_DEV_PASSWORD_INVALID = -213607,  //112: //Device username format is not correct, keywords containing
    EE_CLOUD_DEV_NAME_INVALID = -213608,     //113: //Device username format is not correct, keywords containing
    
    EE_CLOUD_PARAM_INVALID = -213610,      //10003: //Abnormal parameters (parameters incoming by dev.mac is incorrect)
    EE_CLOUD_USERNAME_NOTEXIST = -213611, //41001: //Username does not exist (get device list)
    EE_CLOUD_CHANGEDEVINFO = -213612,     //Edit device information failed
    
    EE_CLOUD_SERVICE_ACTIVATE = -213620,      //10002://Open failed
    EE_CLOUD_SERVICE_UNAVAILABLE = -213621,    //40001: //Abnormal parameters (parameters incoming by dev.mac is incorrect)
    
    EE_CLOUD_AUTHENTICATION_FAILURE = -213630 ,    //150000: //Validation authorization failed (username or password error)
    
    EE_AS_CHECK_USER_REGISTE_CODE = -213700,    // Server response failed
    EE_AS_CHECK_USER_REGISTE_CODE1 = -213702,    // Interface validation failed
    EE_AS_CHECK_USER_REGISTE_CODE2 = -213703,    // Parameters error
    EE_AS_CHECK_USER_REGISTE_CODE3 = -213706,    // Username has been registered
    
    EE_CLOUD_UPGRADE_UPDATE = -213800, //Success, need to update
    EE_CLOUD_UPGRADE_LASTEST = -213801, //Success, the latest, no need to update
    EE_CLOUD_UPGRADE_INVALIDREQ = -213802,//Fail, invalid request
    EE_CLOUD_UPGRADE_UNFINDRES = -213803,   //Fail, resource not found
    EE_CLOUD_UPGRADE_SERVER = -213804,     //Failed, server internal error
    EE_CLOUD_UPGRADE_SERVER_UNAVAIL = -213805,  //Fail, the server is temporarily unavailable. At this time, Retry-After specifies the time for the next request.
    
    EE_AS_SYS_LOGOUT_CODE = -214100, // Server response failed
    EE_AS_SYS_LOGOUT_CODE1 = -214102, // Server response failed
    EE_AS_SYS_LOGOUT_CODE2 = -214103, // Parameters error
    
    EE_AS_SYS_NO_VALIDATED_REGISTER_CODE = -214200, // Server response failed
    EE_AS_SYS_NO_VALIDATED_REGISTER_CODE1 = -214202, // Interface validation failed
    EE_AS_SYS_NO_VALIDATED_REGISTER_CODE2 = -214203, // Parameters error
    EE_AS_SYS_NO_VALIDATED_REGISTER_CODE3 = -214206, // Username has been registered
    EE_AS_SYS_NO_VALIDATED_REGISTER_CODE4 = -214210, // Register failed
    
    EE_AS_SYS_GET_USER_INFO_CODE = -214300, // Server response failed
    EE_AS_SYS_GET_USER_INFO_CODE1 = -214302, // Interface validation failed
    EE_AS_SYS_GET_USER_INFO_CODE2 = -214303, // Parameters error
    EE_AS_SYS_GET_USER_INFO_CODE3 = -214306, // Username does not exist
    EE_AS_SYS_GET_USER_INFO_CODE4 = -214310, // Get failed
    EE_AS_SYS_GET_USER_INFO_CODE5 = -214313, // User password error
    
    EE_AS_SYS_SEND_BINDING_PHONE_CODE = -214400, // Server response failed
    EE_AS_SYS_SEND_BINDING_PHONE_CODE1 = -214402, // Interface validation failed
    EE_AS_SYS_SEND_BINDING_PHONE_CODE2 = -214403, // Parameters error
    EE_AS_SYS_SEND_BINDING_PHONE_CODE3 = -214404, // Phone number has been bound
    EE_AS_SYS_SEND_BINDING_PHONE_CODE4 = -214405, // Exceed the number of sending message everyday
    EE_AS_SYS_SEND_BINDING_PHONE_CODE5 = -214406, // Username does not exist
    EE_AS_SYS_SEND_BINDING_PHONE_CODE6 = -214410, // Send failed
    EE_AS_SYS_SEND_BINDING_PHONE_CODE7 = -214413, // User password error
    EE_AS_SYS_SEND_BINDING_PHONE_CODE8 = -214417, // It can only be sent once within 120 seconds.
    
    EE_AS_SYS_BINDING_PHONE_CODE = -214500, // Server response failed
    EE_AS_SYS_BINDING_PHONE_CODE1 = -214502, // Interface validation failed
    EE_AS_SYS_BINDING_PHONE_CODE2 = -214503, // Parameters error
    EE_AS_SYS_BINDING_PHONE_CODE3 = -214504, // Phone number has been bound
    EE_AS_SYS_BINDING_PHONE_CODE4 = -214506, // Username does not exist
    EE_AS_SYS_BINDING_PHONE_CODE5 = -214507, // Verification code error
    EE_AS_SYS_BINDING_PHONE_CODE6 = -214510, // Bind failed
    EE_AS_SYS_BINDING_PHONE_CODE7 = -214513, // User password error
    
    EE_AS_REGISTER_EXTEND_CODE0 =-214802; //Interface validation failed
    EE_AS_REGISTER_EXTEND_CODE1 =-214803; //Parameters error
    EE_AS_REGISTER_EXTEND_CODE2 =-214804; //Phone number has been registered
    EE_AS_REGISTER_EXTEND_CODE3 =-214806; //Username has been registered
    EE_AS_REGISTER_EXTEND_CODE4 =-214807; //Registration code validation error
    EE_AS_REGISTER_EXTEND_CODE5 =-214810; //Register failed (there is specific information about failure in msg)
    
    EE_AS_REGISTE_BY_EMAIL_EXTEND_CODE = -214900;    // Server response failed
    EE_AS_REGISTE_BY_EMAIL_EXTEND_CODE1 = -214902;    // Interface validation failed
    EE_AS_REGISTE_BY_EMAIL_EXTEND_CODE2 = -214903;    // Parameters error
    EE_AS_REGISTE_BY_EMAIL_EXTEND_CODE3 = -214906;    // Username has been registered
    EE_AS_REGISTE_BY_EMAIL_EXTEND_CODE4 = -214907;    // Registration code validation error
    EE_AS_REGISTE_BY_EMAIL_EXTEND_CODE5 = -214908;    // Mailbox has been registered
    EE_AS_REGISTE_BY_EMAIL_EXTEND_CODE6 = -214910;    // Register failed
    
    EE_AS_SYS_NO_VALIDATED_REGISTER_EXTEND_CODE = -215000; // Server response failed
    EE_AS_SYS_NO_VALIDATED_REGISTER_EXTEND_CODE1 = -215002; // Interface validation failed
    EE_AS_SYS_NO_VALIDATED_REGISTER_EXTEND_CODE2 = -215003; // Parameters error
    EE_AS_SYS_NO_VALIDATED_REGISTER_EXTEND_CODE3 = -215006; // Username has been registered
    EE_AS_SYS_NO_VALIDATED_REGISTER_EXTEND_CODE4 = -215010; // Register failed



    EE_DSS_XMCloud_InvalidParam = -215100,    //Gey device DSS information via XMCloud
    EE_DSS_XMCloud_ConnectHls = -215101,
    EE_DSS_XMCloud_InvalidStream= -215102,
    EE_DSS_XMCloud_Request = -215103,
    EE_DSS_XMCloud_StreamInterrupt = -215104,

    EE_DSS_SQUARE_PARSE_URL = -215110,      //Fail to parse video square url of XMCloud return

    EE_DSS_MINOR_STREAM_DISABLE = -215120,   //DSS The server prohibits sub stream
    EE_DSS_NO_DEVICE = -215121,              //NVR   Front-end does not connect video source

    EE_ALARM_SELECT_NO_RECORD = -222400; ////No alarm history is queried

    EE_SYS_GET_AUTH_CODE = -300000,  // Get Auth Error


    EE_MNETSDK_HEARTBEAT_TIMEOUT = -400000, //The errors between -400000 and -500000 stem from libMNetSDK.so
    EE_MNETSDK_FILE_NOTEXIST = -400001,
    EE_MNETSDK_IS_UPGRADING = -400002,
    EE_MNETSDK_SERVER_STATUS_ERROR = -400003,
    EE_MNETSDK_GETCONNECT_TYPE_ERROR = -400004,
    EE_MNETSDK_QUERY_SERVER_FAIL = -400005,
    EE_MNETSDK_HAS_CONNECTED = -400006,
    EE_MNETSDK_IS_LOGINING = -400007,
    EE_MNETSDK_DEV_IS_OFFLINE = -400008,
    EE_MNETSDK_NOTSUPPORT = -400009,
    EE_MENTSDK_NOFILEFOUND = -400010,
    EE_MNETSDK_DISCONNECT_ERROR = -400011,
    EE_MNETSDK_TALK_ALAREADY_START = -400012,   //Talk-back is open
    EE_MNETSDK_DEV_PTL = -400013,           //DevPTL NULL
    EE_MNETSDK_BACKUP_FAILURE = -400014,    //Backup to disk failed
    EE_MNETSDK_NODEVICE = -400015,           //No storage devices (USB disk) or the device is not recorded

    EE_MNETSDK_USEREXIST = -400016,
    EE_MNETSDK_CAPTURE_PIC_FAILURE = -400017,        //Capture image failed


    EE_MNETSDK_TALK_NOT_START = -400100,   //Device error code write behind
    EE_MNETSDK_STORAGE_IS_FULL = -400101,  //The device storage is full


    EE_ACCOUNT_HTTP_USERNAME_PWD_ERROR = -604000;     //4000 : Username or password error
    EE_ACCOUNT_VERIFICATION_CODE_ERROR = -604010;     //4010 : Verification code error
    EE_ACCOUNT_PASSWORD_NOT_SAME = -604011;           //4011 : Two passwords are not the same
    EE_ACCOUNT_USERNAME_HAS_BEEN_REGISTERED = -604012;//4012 : Username has been registered
    EE_ACCOUNT_USERNAME_IS_EMPTY = -604013;           //4013 : Username is empty
    EE_ACCOUNT_PASSWORD_IS_EMPTY = -604014;                    //4014 : Password is empty
    EE_ACCOUNT_COMFIRMPWD_IS_EMPTY = -604015;                  //4015 : Confirm password is empty
    EE_ACCOUNT_PHONE_IS_EMPTY = -604016;                       //4016 : Cell-phone number is empty
    EE_ACCOUNT_USERNAME_FORMAT_NOT_CORRECT = -604017;          //4017 : Incorrect username format
    EE_ACCOUNT_PASSWORD_FORMAT_NOT_CORRECT = -604018;          //4018 : Incorrect password format
    EE_ACCOUNT_COMFIRMPWD_FORMAT_NOT_CORRECT = -604019;        //4019 : Confirm incorrect password format
    EE_ACCOUNT_PHONE_FORMAT_NOT_CORRECT = -604020;             //4020 : Incorrect cell-phone number format
    EE_ACCOUNT_PHONE_IS_EXIST = -604021;                       //4021 : Cell-phone number already exists
    EE_ACCOUNT_PHONE_NOT_EXSIT = -604022;                      //4022 : Cell-phone number does not exist
    EE_ACCOUNT_EMAIL_IS_EXIST = -604023;                       //4023 : Mailbox already exists
    EE_ACCOUNT_EMAIL_NOT_EXIST = -604024;                      //4024 : Mailbox does not exist
    //EE_ACCOUNT_USER_NOT_EXSIT = -604025;                       //4025 : User does not exist
    EE_ACCOUNT_OLD_PASSWORD_ERROR = -604026;                   //4026 : Original password error
    EE_ACCOUNT_MODIFY_PASSWORD_ERROR = -604027;                //4027 : Modify password failed
    
    EE_ACCOUNT_USERID_IS_EMPTY = -604029;               //4029 : User ID is empty
    EE_ACCOUNT_VERIFICATION_CODE_IS_EMPTY = -604030;           //4030 : Modify password failed
    EE_ACCOUNT_EMAIL_IS_EMPTY = -604031;                       //4031 : Mailbox is empty
    EE_ACCOUNT_EMAIL_FORMATE_NOT_CORRECT = -604032;            //4032 : Incorrect mailbox format

    
    EE_ACCOUNT_DEVICE_ILLEGAL_NOT_ADD = -604100;        //4100 : Illegal device is not allowed to add
    EE_ACCOUNT_DEVICE_ALREADY_EXSIT = -604101;                 //4101 : Device already exists
    EE_ACCOUNT_DEVICE_CHANGE_IFNO_FAIL = -604103;       //4103 : Device information modify failed
    EE_ACCOUNT_DEVICE_UUID_ILLEGAL = -604104,   //4104 : Abnormal device uuid parameters
    EE_ACCOUNT_DEVICE_USERNAME_ILLEGAL = -604105,  //4105 : Abnormal device username parameters
    EE_ACCOUNT_DEVICE_PASSWORD_ILLEGAL = -604106,  //4106 : Abnormal device password parameters

 

    EE_ACCOUNT_SEND_CODE_FAIL  = -604300;                //4300 : Send failed
    
    EE_ACCOUNT_MESSAGE_INTERFACE_CHECK_ERROR  = -604400; //4400 : Message interface verification failed, please contact us.
    EE_ACCOUNT_MESSAGE_INTERFACE_PARM_ERROR = -604401;         //4401 : Message interface verification failed, please contact us.
    EE_ACCOUNT_MESSAGE_TIME_MORE_THAN_THREE = -604402;         //4402 : Exceed the times of sending message, each cell-phone number can only send three times a day.
    EE_ACCOUNT_MESSAGE_SEND_ERROR = -604403;                   //4403 : Send failed, please try again later
    EE_ACCOUNT_MESSAGE_SEND_OFTEN = -604404;                   //4404 : Send too often, please wait 120 seconds.
    
    EE_ACCOUNT_HTTP_SERVER_ERROR = -600500 ;            //5000 : Server failure
    EE_ACCOUNT_CERTIFICATE_NOT_EXIST = -605001;                //5001 : Certificate does not exist
    EE_ACCOUNT_HTTP_HEADER_ERROR = -605002;                    //5002 : Request header information error
    EE_ACCOUNT_CERTIFICATE_FAILURE = -605003;                  //5003 : Certificate is invalid
    EE_ACCOUNT_ENCRYPT_CHECK_FAILURE = -605004;                //5004 : Generating key checking error
    EE_ACCOUNT_PARMA_ABNORMAL = -605005;                       //5005 : Abnormal parameters
</pre>

