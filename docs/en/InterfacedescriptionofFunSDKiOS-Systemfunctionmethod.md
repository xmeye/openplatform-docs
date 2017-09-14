

<div name="huoqu" id="huoqu" style="font-size:20px;"><b>3.1 Get device list</b></div> 
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">Definition</td><td colspan="2">int FUN_SysGetDevList(UI_HANDLE hUser, const char *szUser, const char *szPwd, int nSeq );</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description
</td><td colspan="2">Get device list</td></tr>
<tr><td rowspan="5" style="background-color:#ccc;text-align:center">Parameters<br/> 
description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr><td style="text-align:center">hUser
</td><td>Result receiver(The significance of this parameter is the same in other methods)</label></td></tr>
<tr><td style="text-align:center">szUser
</td><td>Username (temporary verification in local login method)</td></tr>
<tr><td style="text-align:center">password</td><td>Password (temporary verification in local login  method)</td></tr>
<tr><td style="text-align:center">nSeq
</td><td>SEQ value of message callback (The significance of this parameter is the same in other methods)</label>
</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">Result<br/> 
message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id</td>
<td>Message value：EUIMSG.SYS_GET_DEV_INFO_BY_USER
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>>=0：number of devices；<0：fail, for details, see error code description</td></tr>
<tr><td style="text-align:center">pData
</td><td>Byte stream pointing to the SDBDeviceInfo array（Use G.BytesToObj to convert byte 
streams and objects</td></tr>
</table>
<br/>

<div name="tianjia" id="tianjia" style="font-size:20px;"><b>3.2 Add device</b></div> 
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">Definition</td><td colspan="2">int FUN_SysAddDevice(UI_HANDLE hUser, SDBDeviceInfo *pDevInfo, const char *UserName="",const char*Psw="", int nSeq=0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Add device</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr><td style="text-align:center">pDevInfo</td>
<td>
Device information object byte stream<br/><br/>
typedef struct SDBDeviceInfo<br>

{<br>
char Devmac[64]; // DEV_SN / IP / DNS<br/>
char Devname[128]; // Name<br/>
char devIP[64]; // Name<br/>
char loginName[16]; // username<br/>
char loginPsw[16]; //  password<br/>
int nPort; //  port mapping port<br/><br/>
int nType; // --device type 1: socket<br/>
int nID; // --device ID, internal use<br/>
}SDBDeviceInfo;<br>
</td></tr>
<tr><td  style="text-align:center">userName
</td><td>System username; when it is empty, that means it is the same as the username used 
by calling SysGetDevList</td></tr>
<tr><td  style="text-align:center">password</td><td>System password; when it is empty, that means it is the same as the password used by 
calling SysGetDevList</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result<br/> 
message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td  style="text-align:center">id
</td><td>Message value: EUIMSG . SYS_ADD_DEVICE</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>==0：success；<0: fail, for details, see error code  description</td></tr>
</table>
<br/>

<div name="shanchu" id="shanchu" style="font-size:20px;"><b>3.3 Delete device</b></div>
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:50px;">Definition</td><td colspan="2">int FUN_SysDelete_Dev(UI_HANDLE hUser, const char *Delete_DevMac,const char *UserName,const char *Psw, int nSeq = 0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Delete device</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr><td style="text-align:center">Delete_DevMac</td>
<td>	Device serial number</td></tr>
<tr><td style="text-align:center">userName
</td><td>System username; when it is empty, that means it isthe same as the username used by calling  SysGetDevList</td></tr>
<tr><td  style="text-align:center">password</td><td>System password; when it is empty, that means it is the same as the password used by calling   SysGetDevList</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name
</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td  style="text-align:center">id
</td><td>Message value：EUIMSG   . EMSG_SYS_DELETE_DEV
</td></tr>
<tr><td  style="text-align:center">arg1
</td><td>==0：success；<0:  fail, for details, see error code  
description</td></tr>
</table>
<br/>

<div name="xiugai" id="xiugai" style="font-size:20px;"><b>3.4  Modify device</b></div> 
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">Definition</td><td colspan="2">int FUN_SysChangeDevInfo(UI_HANDLE hUser, struct SDBDeviceInfo *ChangeDevInfor,const char *UserName,const char *Psw, int nSeq = 0);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description

</td><td colspan="2">Modify device</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name
</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr><td style="text-align:center">ChangeDevInfor
</td>
<td>Device information:SDBDeviceInfo reference above to 
define</td></tr>
<tr><td style="text-align:center">userName
</td><td>System username; when it is empty, that means it is the 
same as the username used by calling  SysGetDevList</td></tr>
<tr><td  style="text-align:center">Psw</td><td>System password; when it is empty, that means it is the same as the password used by calling  SysGetDevList</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result <br/>message</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value：EUIMSG.   EMSG_SYS_CHANGEDEVINFO
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：success; <0: fail, for details, see error code   description
</td></tr>
</table>
<br/>

<div name="yonghu" id="yonghu" style="font-size:20px;"><b>3.5 Add user</b></div> 
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">Definition</td><td colspan="2">int FUN_SysUser_Register(UI_HANDLE hUser, const char *UserName,const char *Psw,const char *email, int nSeq = 0);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description
</td><td colspan="2">Add user </td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name
</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr><td style="text-align:center">UserName
</td><td>Add username</td></tr>
<tr><td style="text-align:center">password
</td><td>Add password</td></tr>
<tr><td  style="text-align:center">email</td><td>Mailbox account</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result <br/>message</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value:EUIMSG   . EMSG_SYS_USER_REGISTER
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：success; <0: fail, for details, see error code   description
</td></tr>
</table>
<br/>

<div name="mima" id="mima" style="font-size:20px;"><b>3.6  Modify password</b></div> 
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">Definition</td><td colspan="2">int FUN_SysPsw_Change(UI_HANDLE hUser, const char *UserName,const char *old_Psw,const char *new_Psw, int nSeq = 0);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description

</td><td colspan="2">Modify password </td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name
</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr><td style="text-align:center">UserName
</td><td>UserName</td></tr>
<tr><td style="text-align:center">old_Psw
</td><td>Old password</td></tr>
<tr><td  style="text-align:center">new_Psw</td><td>New password</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result <br/>message</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value:EUIMSG   . EMSG_SYS_PSW_CHANGE
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：success; <0: fail, for details, see error code   description
</td></tr>
</table>
<br/>

<div name="chongzhi" id="chongzhi" style="font-size:20px;"><b>3.7 Restore password</b></div> 
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">Definition</td><td colspan="2">int FUN_SysPsw_Restore(UI_HANDLE hUser, const char *UserName,const char *new_Psw, int nSeq = 0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description

</td><td colspan="2">User password recovery</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name
</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr><td style="text-align:center">userName
</td><td>Username</td></tr>
<tr><td  style="text-align:center">new_Psw
</td><td>New password</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result <br/>message</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value: EUIMSG   . EMSG_SYS_PSW_RESTORE
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：success; <0: fail, for details, see error code   description
</td></tr>
</table>
<br/>

<div name="zhaohui" id="zhaohui" style="font-size:20px;"><b>3.8 Find back password via mailbox</b></div>
<br/>


<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">Definition</td><td colspan="2">int Fun_SysGetPWByEmail(UI_HANDLE hUser, const char* UserName, int nSeq = 0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Find back password, it will send the link that can modify the password to the registered mailbox </td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr><td style="text-align:center">userName</td>
<td>Username</td></tr>

<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td  style="text-align:center">id
</td><td>Message value:（FunSDK）
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>0: success; -213000: no this user name; -213001 send failed; other: see error code description
</td></tr>	
</table>
<br/>


<div name="huoqu1" id="huoqu1" style="font-size:20px;"><b>3.9 Get device status</b></div> 
<br/>
<br/>


<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">Definition</td><td colspan="2">int FUN_SysGetDevState(UI_HANDLE hUser, const char *devId, int nSeq = 0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Get device status, can use more than one to query, separated by “;”</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr><td style="text-align:center">devIds</td>
<td>Device serial number</td></tr>

<tr><td rowspan="4" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td  style="text-align:center">id
</td><td>Message value：EUIMSG   . EMSG_SYS_GET_DEV_STATE
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>> 0： online</td></tr>
<tr><td style="text-align:center">str
</td><td>	
Single device serial number</td></tr>
<tr><td>Note</td><td colspan="2">If multiple devices query together, device status will be returned separately
</td></tr>
</table>
<br/>


<div name="yanzhengma" id="yanzhengma" style="font-size:20px;"><b>3.10  Get the phone verification code</b></div> 
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">Definition</td><td colspan="2">int FUN_SysSendPhoneMsg(UI_HANDLE hUser, const char *UserName, const char *phoneNO, int nSeq = 0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Get the phone verification code</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Parameters<br/>description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">description
</td></tr>
<tr><td  style="text-align:center">userName</td>
<td>Username</td></tr>
<tr><td style="text-align:center">phoneNO</td>
<td>Phone number</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result <br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value：EUIMSG   . EMSG_SYS_GET_PHONE_CHECK_CODE</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：success; <0: fail, for details, see error code   description</td></tr>
</table>
<br/>

<div name="zhuce" id="zhuce" style="font-size:20px;"><b>3.11 User register (cell-phone number)</b></div> 
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">Definition</td><td colspan="2">int FUN_SysRegUserToXM(UI_HANDLE hUser, const char *UserName, const char *pwd, const char *checkCode,const char *phoneNO, int nSeq);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description
</td><td colspan="2">User register (cell-phone number)</td></tr>
<tr><td rowspan="5" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description

</td></tr>
<tr><td style="text-align:center">userName
</td><td>Username. The length of username requires 4~15 characters, includes Chinese, letters, digital and "_"</td></tr>
<tr><td style="text-align:center">pwd</td>
<td>Password</td></tr>
<tr><td style="text-align:center">checkCode
</td><td>Verification Code</td></tr>
<tr><td style="text-align:center">phoneNO</td>
<td>Phone number</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result <br/>message</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id</td>
<td>Message value：EUIMSG   . EMSG_SYS_REGISER_USER_XM
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0： success; <0: fail, for details, see error code  description</td></tr>
</table>
<br/>

<div name="xiugaimima" id="xiugaimima" style="font-size:20px;"><b>3.12 Modify user password</b></div>
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">Definition</td><td colspan="2">int FUN_SysEditPwdXM(UI_HANDLE hUser, const char *UserName, const char *oldPwd, const char *newPwd, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description
</td><td colspan="2">Modify user password
</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">Parameters<br/>Description
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr><td style="text-align:center">userName
</td><td>Username</td></tr>
<tr><td style="text-align:center">oldPwd</td>
<td>Password</td></tr>
<tr><td style="text-align:center">newPwd
</td><td>newPassword</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value：EUIMSG   . EMSG_SYS_EDIT_PWD_XM
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：success; <0: fail, for details, see error code description</td></tr>
</table>
<br/>

<div name="wangji" id="wangji" style="font-size:20px;"><b>3.13 Forget login password</b></div> 
<br/>
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">Definition</td><td colspan="2">int FUN_SysForgetPwdXM(UI_HANDLE hUser, const char *phone, int nSeq)</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Forget login password
</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name

</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr><td style="text-align:center">phone</td>
<td>Phone number</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result <br/>message</td><td style="background-color:#ccc;text-align:center;width:20%;">Name
</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value: EUIMSG   . EMSG_SYS_FORGET_PWD_XM
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0： success; <0: fail, for details, see error code description</td></tr>
</table>
<br/>

<div name="yanzheng" id="yanzheng" style="font-size:20px;"><b>3.14 Verify verification code (mobile phone) </b></div> 
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">Definition</td><td colspan="2">int FUN_CheckResetCodeXM(UI_HANDLE hUser, const char *phone, const char *checkNum, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Check whether the verification code of modifing password is correct</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr><td style="text-align:center">phone</td>
<td>Phone number</td></tr>
<tr><td style="text-align:center">checkNum</td>
<td>Verification code</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result <br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value：EUIMSG   . EMSG_SYS_REST_PWD_CHECK_XM</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：success; <0: fail, for details, see error code description</td></tr>
</table>
<br/>

<div name="reset" id="reset" style="font-size:20px;"><b>3.15 Reset login password</b></div> 
<br/>
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">Definition</td><td colspan="2">int FUN_ResetPwdXM(UI_HANDLE hUser, const char *phone, const char *newPwd, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description
</td><td colspan="2">Check whether the verification code of modifing password is correct</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Parameters<br/>Description
</td><td style="background-color:#ccc;text-align:center;width:20%;">	
Name</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr><td style="text-align:center">phone</td>
<td>Phone number</td></tr>
<tr><td style="text-align:center">newPwd</td>
<td>New password</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result <br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">	
Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value：EUIMSG   . EMSG_SYS_RESET_PWD_XM
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：success; <0: fail, for details, see error code description
</td></tr>
</table>
<br/>

<div name="tongbu1" id="tongbu1" style="font-size:20px;"><b>3.16 Sync login</b></div>
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">Definition</td><td colspan="2">int FUN_SysLoginToXM(UI_HANDLE hUser, const char *UserName, const char *pwd, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Sync login
</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Parameters
<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr><td style="text-align:center">UserName
</td><td>Username</td></tr>
<tr><td style="text-align:center">pwd</td>
<td>Password</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result <br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value:EUIMSG   . EMSG_ SYS_GET_DEV_INFO_BY_USER_XM
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：success; <0: fail, for details, see error code</td></tr>
</table>
<br/>

<div name="tongbu2" id="tongbu2" style="font-size:20px;"><b>3.17  Sync logout</b></div> 
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">Definition</td><td colspan="2">int FUN_SysLogout(UI_HANDLE hUser, int nSeq = 0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2"> Sync logout
</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr style="text-align:center"><td>/
</td><td>  / </td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result <br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value：EUIMSG   . SYS_LOGOUT_TO_XM
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：success; <0: fail, for details, see error code description
</td></tr>
</table>
<br/>

<div name="shangchuan" id="shangchuan" style="font-size:20px;"><b>3.18 Upload local video files</b></div>
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:20px;">Definition</td><td colspan="2">int   UpLoadLocalVideo(int hUser, String title, String location, String   description, String catagroyId, String videoFileName, String pictureFileName,   int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Upload local video files, title, description, location, category
</td></tr>
<tr><td rowspan="7" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr><td style="text-align:center">title</td>
<td>Title</td></tr>
<tr><td style="text-align:center">location</td>
<td>Location</td></tr>
<tr><td style="text-align:center">description
</td><td>Description</td></tr>
<tr><td style="text-align:center">catagroyId
</td><td>CategoryId</td></tr>
<tr><td style="text-align:center">videoFileName
</td><td>Video local path</td></tr>
<tr><td style="text-align:center">pictureFileName
</td><td>Video thumbnail local path</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value：EUIMSG   . SYS_DEV_UPLOAD_VIDEO
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：success; > 0: progress; <0: fail, for details, see error code description</td></tr>
</table>
<br/>

<div name="wenjian" id="wenjian" style="font-size:20px;"><b>3.19 Delete the file under the directory</b></div> 
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">Definition</td><td colspan="2">int GN_DeleteFiles(const char *szDir, long nDaysAgo, const char *szType);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Delete the files that on the specified directory, before the specified date and the specified suffix</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr><td style="text-align:center">szDir</td>
<td>Catalog</td></tr>
<tr><td style="text-align:center">nDaysAgo</td>
<td>Date</td></tr>
<tr><td style="text-align:center">szType
</td><td>Suffix</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value：无</td></tr>
<tr><td style="text-align:center">arg1
</td><td>>=0return the number of deleted files <0 delete failed</td></tr>
</table>
<br/>


<div name="zhenwei" id="zhenwei" style="font-size:20px;"><b>3.20 Check the authenticity of products</b></div> 
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">Definition</td><td colspan="2">int FUN_SysCheckDeviceReal(UI_HANDLE hUser, const char *twoDimensionCode, int nSeq = 0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Check the authenticity of products</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr><td style="text-align:center">twoDimensionCode</td>
<td>Device two-dimensional code</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result <br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value：EUIMSG   . SYS_CHECK_DEVICE_REAL
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：success; <0: fail, for details, see error code description
</td>
</tr>
</table>
<br/>

<div name="validity" id="validity" style="font-size:20px;"><b>3.21 Check the validity and strength of the password</b></div> 
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">Definition</td><td colspan="2">int FUN_CheckPwdStrength(UI_HANDLE hUser, const char *newPwd, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description
</td><td colspan="2">Check the validity and strength of the password</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">Parameters<br/>Description
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr><td style="text-align:center">email</td>
<td>Password</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result <br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>
 Message value：EUIMSG   . SYS_SEND_EMAIL_CODE</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：success; <0: fail, for details, see error code description
</td>
</tr>
</table>
<br/>

<div name="youxiang" id="youxiang" style="font-size:20px;"><b>3.22 Gets mailbox validation code</b></div> 
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">Definition</td><td colspan="2">int SysSendEmailCode(int hUser, String email, int nSeq);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">
 Gets mailbox validation code</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr><td style="text-align:center">email</td>
<td>Mailbox account</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>
 essage value：EUIMSG   . SYS_SEND_EMAIL_CODE</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：success; <0: fail, for details, see error code description</td>
</tr>
</table>
<br/>

<div name="yongzhu" id="yongzhu" style="font-size:20px;"><b>3.23 User register (mailbox)</b></div>
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">Definition</td><td colspan="2">int FUN_SysRegisteByEmail(UI_HANDLE hUser, const char *userName, const char *password, const char *email, const char *code, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">
 User register (mailbox)</td></tr>
<tr><td rowspan="5" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr><td style="text-align:center">userName</td>
<td>Username. The length of username requires 4~15 characters, includes Chinese, letters, digital and "_" </td></tr>
<tr><td style="text-align:center">password</td>
<td>Password</td></tr>
<tr><td style="text-align:center">email</td>
<td>Mailbox</td></tr>
<tr><td style="text-align:center">code</td>
<td>Verification code</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value：EUIMSG   . SYS_REGISTE_BY_EMAIL
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：success; <0: fail, for details, see error code   description
</td>
</tr>
</table>
<br/>

<div name="zhaohui1" id="zhaohui1" style="font-size:20px;"><b>3.24 Find back password (reset) - send mailbox verification code</b></div>
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">Definition</td><td colspan="2">int FUN_SysSendCodeForEmail(UI_HANDLE hUser, const char *email, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Get mailbox verification code (modify password)</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr><td style="text-align:center">email</td>
<td>E-mail account</td></tr>

<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result<br/>Message 
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value：EUIMSG   . SYS_SEND_EMAIL_FOR_CODE</td></tr>
<tr><td style="text-align:center">arg1</td>
<td>==0：success; <0: fail, for details, see error code  description
</td></tr>
</table>
<br/>

<div name="zhaohui2" id="zhaohui2" style="font-size:20px;"><b>3.25 Find back password (reset) - verify mailbox verification code</b></div>
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">Definition</td><td colspan="2">int FUN_SysCheckCodeForEmail(UI_HANDLE hUser, const char *email, const char *code, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description
</td><td colspan="2">
 Check whether the verification code of finding back password is correct</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr><td style="text-align:center">email</td>
<td>Mailbox</td></tr>
<tr><td style="text-align:center">code</td>
<td>Mailbox verification code</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value：EUIMSG   . SYS_CHECK_CODE_FOR_EMAIL</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：success; <0: fail, for details, see error code   description</td>
</tr>
</table>
<br/>

<div name="zhaohui3" id="zhaohui3" style="font-size:20px;"><b>3.26 Find back password via mailbox (reset)</b></div>
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">Definition</td><td colspan="2">int FUN_SysChangePwdByEmail(UI_HANDLE hUser, const char *email, const char *newpwd, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">
 Find back password (mailbox)</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr><td style="text-align:center">email</td>
<td>Mailbox</td></tr>
<tr><td style="text-align:center">newpwd</td>
<td>New password</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value：EUIMSG   . SYS_PSW_CHANGE_BY_EMAIL</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：success; <0: fail, for details, see error code  description</td>
</tr>
</table>
<br/>

<div name="yibei" id="yibei" style="font-size:20px;"><b>3.27 Check if the user has been registered</b></div>
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">Definition</td><td colspan="2">int FUN_SysCheckUserRegiste(UI_HANDLE hUser, const char *userName, int nSeq =0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">
Check if the user has been registered</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr><td style="text-align:center">userName</td>
<td>Username</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value：EUIMSG   . EMSG_SYS_CHECK_USER_REGISTE</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：success; <0: fail, for details, see error code  description
</td>
</tr>
</table>
<br/>

<div name="Noneed" id="Noneed" style="font-size:20px;"><b>3.28 No need to verify the registration</b></div> 
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">Definition</td><td colspan="2">int FUN_SysNoValidatedRegister(UI_HANDLE hUser, const char *userName, const char *pwd, int nSeq  =0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">No need to verify the registration</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr><td style="text-align:center">userName</td>
<td>Username. The length of username requires 4~15  characters, includes Chinese, letters, digital and "_"</td></tr>
<tr><td style="text-align:center">pwd</td>
<td>Password</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value：EUIMSG   . EMSG_SYS_NO_VALIDATED_REGISTER
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：success; <0: fail, for details, see error code  description</td>
</tr>
</table>
<br/>

<div name="yongxin" id="yongxin" style="font-size:20px;"><b>3.29 Get user information</b></div>
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">Definition</td><td colspan="2">int SysGetUerInfo(int hUser, String userName, String pwd, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Get user information</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr><td style="text-align:center">userName</td>
<td>Username</td></tr>
<tr><td style="text-align:center">pwd</td>
<td>Password</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value：EUIMSG   . EMSG_SYS_GET_USER_INFO
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：success; <0: fail, for details, see error code  description</td>
</tr>
</table>
<br/>

<div name="gengxin" id="gengxin" style="font-size:20px;"><b>3.30 Check APP update</b></div>
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">Definition</td><td colspan="2">int Fun_FirLatest(UI_HANDLE hUser, const char *appId, const char *appToken, int nSeq = 0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Check APP update</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr><td style="text-align:center">appToken</td>
<td>Package name</td></tr>
<tr><td style="text-align:center">appId</td>
<td>App Id</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value：EUIMSG   . FIR_IM_CHECK_LATEST
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：success; <0: fail, for details, see error code description
</td>
</tr>
</table>
<br/>

<div name="shuju1" id="shuju1" style="font-size:20px;"><b>3.31 Open reported data</b></div>
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">Definition</td><td colspan="2">int Fun_DevStartUploadData(UI_HANDLE hUser, const char *szDevId,int nUploadDataType, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">
Open reported data</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr style="text-align:center"><td>szDevId</td>
<td>Device serial number</td></tr>
<tr><td style="text-align:center">nUploadDataType
</td>
<td>Report data type:<br/>
VEHICLE =   0;// vehicle information<br/>
SDK_RECORD_STATE   = 1;// record state<br/>
SDK_DIGITCHN_STATE   = 2; // digital channel connection state<br/>
SDK_TITLE_INFO   = 3; // Channel title<br/>
SDK_FUNCTION_STATE   = 4;// functional state for example:sports action camera<br/>
// record status, time-lapse state, etc<br/>
SDK_ELECT_STATE   = 5;// electricity state<br/>
</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result <br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id</td>
<td>Message value：EUIMSG   . EMSG_DEV_START_UPLOAD_DATA<br/>
EMSG_DEV_ON_UPLOAD_DATA   return the reported data, progress, data type in calling
</td></tr>
<tr ><td style="text-align:center">arg1
</td><td>==0：success; <0: fail, for details, see error code  description</td></tr>
</table>
<br/>

<div name="shuju2" id="shuju2" style="font-size:20px;"><b>3.32 Close reported data</b></div>
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">Definition</td><td colspan="2">int Fun_DevStopUploadData(UI_HANDLE hUser, const char *szDevId,int nUploadDataType, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">
Close reported data</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>Device serial number</td></tr>
<tr><td style="text-align:center">nUploadDataType</td>
<td>Report data type: type description is same as above</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value：EUIMSG   . FIR_IM_CHECK_LATEST
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：success; <0: fail, for details, see error code  description</td>
</tr>
</table>
<br/>











