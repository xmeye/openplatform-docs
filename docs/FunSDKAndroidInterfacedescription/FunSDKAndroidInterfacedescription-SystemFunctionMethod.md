## 获取设备列表

<style>
	table{
		border-collapse:collapse;
		width:100%;
	}
	table tr td{
		border:1px solid #000;
	}
</style>
<table >
<tr><td style="background-color:#ccc;text-align:center;width:100px;">定义</td><td colspan="2">int SysGetDevList(int hUser, String szUser, String password, int nSeq );</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">获取设备列表</td></tr>
<tr><td rowspan="5" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">hUser
</td><td>结果接收者<label style="color:red">（其它方法此参数的意义相同）</label></td></tr>
<tr><td style="text-align:center">szUser
</td><td>用户名（本地登录方式暂时验证）</td></tr>
<tr><td style="text-align:center">password</td><td>密码（本地登录方式暂时验证）</td></tr>
<tr><td style="text-align:center">nSeq
</td><td>消息回调的seq值<label style="color:red">（其它方法此参数的意义相同）</label>
</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id</td>
<td>消息值：EUIMSG.SYS_GET_DEV_INFO_BY_USER
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>>=0：设备条数；<0：失败，详见错误码说明</td></tr>
<tr><td style="text-align:center">pData
</td><td>指向SDBDeviceInfo数组的字节流（可使用G.BytesToObj转换字节流与对象之间的）</td></tr>
</table>

## 获取设备列表(第三方获取)

<table >
<tr><td style="background-color:#ccc;text-align:center;width:100px;">定义</td><td colspan="2">int SysGetDevListEx(int hUser, const char *unionId, const char *szType, int nApptype, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">第三方获取列表接口（微信、QQ、微博等）</td></tr>
<tr><td rowspan="5" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">unionId
</td><td>唯一ID</td></tr>
<tr><td style="text-align:center">szType
</td><td>第三方类型(例:微信“wx”)</td></tr>
<tr><td style="text-align:center">password</td><td>密码（本地登录方式暂时验证）</td></tr>
<tr><td style="text-align:center">nApptype
</td><td>app类型
</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id</td>
<td>消息值：EUIMSG.SYS_GET_DEV_INFO_BY_USER
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>>=0：设备条数；<0：失败，详见错误码说明</td></tr>
<tr><td style="text-align:center">pData
</td><td>指向SDBDeviceInfo数组的字节流（可使用G.BytesToObj转换字节流与对象之间的）</td></tr>
</table>
unionId	
	
	

## 添加设备

<table >
<tr><td style="background-color:#ccc;text-align:center;width:100px;">定义</td><td colspan="2">int SysAddDevice(int hUser, byte[] pSDBDeviceInfo, String sUser, String sPwd, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">添加设备</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">pSDBDeviceInfo</td>
<td>
设备信息对象字节流<br>
typedef struct SDBDeviceInfo<br>
{<br>
   &nbsp char Devmac[64]; //DEV_SN/IP/DNS<br>
   &nbsp char Devname[128]; //名称<br>
   &nbsp char devIP[64]; //设备ip<br>
   &nbsp char loginName[16]; //用户名<br>
   &nbsp char loginPsw[16]; //密码<br>
   &nbsp int nPort; //端口映射端口<br>
   &nbsp int nType; //--设备类型 1:插座<br>
   &nbsp int nID; //--本设备ID,内部使用<br>
}SDBDeviceInfo;
</td></tr>
<tr><td  style="text-align:center">sUser
</td><td>系统用户名；为空时表示与调用SysGetDevList使用的用户名相同<br>格式:param1=value1&param2=value2<br>
其中“ma=true&delOth=true”设置此帐户为此设备的主帐户<br>
其中“ext=XXXXXXXX”设置设备的用户自定义信息</td></tr>
<tr><td  style="text-align:center">sPwd</td><td>系统密码；为空时表示与调用SysGetDevList使用密码相同</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：EUIMSG . SYS_ADD_DEVICE</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>==0：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 通过文件添加设备

<table >
<tr><td style="background-color:#ccc;text-align:center;width:50px;">定义</td><td colspan="2">int SysAddDevByFile(int hUser, String szPath, int nSeq)</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">通过文件添加设备</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">szPath</td>
<td>设备信息文件（含路径）</td></tr>

<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：EUIMSG  . SYS_ADD_DEVICE_BY_FILE
</td></tr>
<tr><td  style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 删除设备

<table >
<tr><td style="background-color:#ccc;text-align:center;width:50px;">定义</td><td colspan="2">int SysDelete_Dev(int hUser, String devId,String userName,String password, int nSeq = 0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">删除设备</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">Delete_DevMac</td>
<td>设备序列号</td></tr>
<tr><td style="text-align:center">userName
</td><td>系统用户名；为空时表示与调用SysGetDevList使用的用户名相同</td></tr>
<tr><td  style="text-align:center">password</td><td>系统密码；为空时表示与调用SysGetDevList使用密码相同</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：EUIMSG  . SYS_DELETE_DEV
</td></tr>
<tr><td  style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 修改设备

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int SysChangeDevInfo(int hUser, struct SDBDeviceInfo *ChangeDevInfor,String userName,String password, int nSeq = 0);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">修改设备</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">ChangeDevInfor
</td>
<td>设备信息：SDBDeviceInfo 参考上面下定义
</td></tr>
<tr><td style="text-align:center">userName
</td><td>系统用户名；为空时表示与调用SysGetDevList使用的用户名相同</td></tr>
<tr><td  style="text-align:center">Psw</td><td>系统密码；为空时表示与调用SysGetDevList使用密码相同</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG.   EMSG_SYS_CHANGEDEVINFO
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 加密设备序列号

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">string EncDevInfo (string szDevId, string szUser, string szPwd, int nType);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">加密设备序列号</td></tr>
<tr><td rowspan="5" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">szDevId</td><td>设备序列号</td></tr>
<tr><td style="text-align:center">userName
</td><td>系统用户名；为空时表示与调用SysGetDevList使用的用户名相同</td></tr>
<tr><td  style="text-align:center">Psw</td><td>系统密码；为空时表示与调用SysGetDevList使用密码相同</td></tr>
<tr><td style="text-align:center">nType</td>
<td>类型
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>加密过后的设备序列号
</td><tr>
</table>

## 解密设备序列号

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">string DecDevInfo(string szDevInfo);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">解密设备序列号</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">szDevInfo</td><td>需要解密的设备信息</td></tr>

<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>解密过后的设备序列号
</td><tr>
</table>

## 修改密码

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int SysPswChange (int hUser, String userName,String old_Psw,String new_Psw, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">修改密码</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">userName</td>
<td>用户名</td></tr>
<tr><td style="text-align:center">old_Psw</td>
<td>老密码</td></tr>
<tr><td style="text-align:center">new_Psw</td>
<td>新密码</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：EUIMSG . SYS_PSW_CHANGE
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>> ==0：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 恢复密码

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int SysPswRestore(int hUser, String UserName,String new_Psw, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">用户密码恢复</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">UserName</td>
<td>用户名</td></tr>
<tr><td style="text-align:center">new_Psw</td>
<td>密码</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：EUIMSG . SYS_PSW_RESTORE
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>> ==0：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 通过邮箱找密码

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int SysGetPWByEmail(int hUser, String UserName, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">找回密码，会向注册邮箱里发送修改密码的链接。</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">UserName</td>
<td>用户名</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：EUIMSG . SYS_GETPWBYEMAIL
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>> ==0：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 获取设备状态

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int SysGetDevState(int hUser, String devId, int nSeq = 0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">获取设备状态，可多个一起查询，以；分割</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">devIds</td>
<td>设备序列号</td></tr>

<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：EUIMSG   . EMSG_SYS_GET_DEV_STATE
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>> 0：在线</td></tr>
<tr><td style="text-align:center">str
</td><td>单个设备序列号</td></tr>
<tr><td>备注</td><td colspan="2">若多个设备一起查询，设备状态会分开返回</td></tr>
</table>

## 分类型获取设备状态
<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int GetDevState(String szDevId, int nType);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">分类型获取设备状态（直接获取缓存中的状态）</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">nType</td>
<td>设备类型，详见枚举EFunDevStateType</td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>返回值见枚举EFunDevState
</td><tr>
</table>

## 用户账号绑定

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int SysBindingAccount(int hUser, String name, String pwd, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">name，pwd不为空时，绑定现有的帐户和密码<br>
name，pwd为空时，自动生成一个用户名和密码
</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">name</td>
<td>用户名</td></tr>
<tr><td style="text-align:center">pwd</td>
<td>密码</td></tr>

<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：EUIMSG . SYS_BINDING_ACCOUNT
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td></tr>
<tr><td style="text-align:center">str
</td><td>绑定的用户名和密码组成的字符串</td></tr>
</table>

## 获取手机验证码

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int SysSendPhoneMsg(int hUser, String userName, String phoneNO, int nSeq = 0);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">获取手机验证码(用户注册)</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td  style="text-align:center">userName</td>
<td>用户名</td></tr>
<tr><td style="text-align:center">phoneNO</td>
<td>手机号码</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG  . SYS_GET_PHONE_CHECK_CODE</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 用户注册（手机号）

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int SysRegUserToXM(int  hUser, String userName, String pwd, String checkCode,String phoneNO, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">用户注册(手机号)</td></tr>
<tr><td rowspan="5" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">userName
</td><td>用户名。用户名要求长度4~15位，可用中文、英文、数字和“_”组成 </td></tr>
<tr><td style="text-align:center">pwd</td>
<td>密码</td></tr>
<tr><td style="text-align:center">checkCode
</td><td>验证码</td></tr>
<tr><td style="text-align:center">phoneNO</td>
<td>手机号码</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id</td>
<td>消息值：EUIMSG  . SYS_REGISER_USER_XM
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 用户注册（手机号-扩展参数）

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">iint SysRegUserToXMExtend(int hUser, String UserName,String pwd, String checkCode, String phoneNO, String source, String country, String city, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">用户注册(手机号-扩展参数)</td></tr>
<tr><td rowspan="8" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">userName
</td><td>用户名。用户名要求长度4~15位，可用中文、英文、数字和“_”组成 </td></tr>
<tr><td style="text-align:center">pwd</td>
<td>密码</td></tr>
<tr><td style="text-align:center">checkCode
</td><td>验证码</td></tr>
<tr><td style="text-align:center">phoneNO</td>
<td>手机号码</td></tr>
<tr><td style="text-align:center">source</td>
<td>注册来源</td></tr>
<tr><td style="text-align:center">country</td>
<td>国家</td></tr>
<tr><td style="text-align:center">city</td>
<td>城市</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id</td>
<td>消息值：EUIMSG  . SYS_REGISER_USER_XM_EXTEND
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 修改用户密码

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int SysEditPwdXM(int hUser, String userName, String oldPwd, String newPwd, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">修改用户密码
</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">userName
</td><td>用户名</td></tr>
<tr><td style="text-align:center">oldPwd</td>
<td>旧密码</td></tr>
<tr><td style="text-align:center">newPwd
</td><td>新密码</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG  . SYS_EDIT_PWD_XM
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 忘记登录密码

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int SysForgetPwdXM(int hUser, String phone, int nSeq)</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">忘记登录密码(获取验证码)
</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">phone</td>
<td>手机号码</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG   . EMSG_SYS_FORGET_PWD_XM
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 验证验证码（手机或邮箱）

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int CheckResetCodeXM(int hUser, String phone, String checkNum, int nSeq);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">验证修改密码的验证码是否正确</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">phone</td>
<td>手机号码或者邮箱</td></tr>
<tr><td style="text-align:center">checkNum</td>
<td>验证码</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG  . SYS_REST_PWD_CHECK_XM</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 重置登录密码

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int ResetPwdXM(int hUser, String phone, String newPwd, int nSeq);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">验证修改密码的验证码是否正确</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">phone</td>
<td>手机号码或者邮箱</td></tr>
<tr><td style="text-align:center">newPwd</td>
<td>新密码</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG  . SYS_RESET_PWD_XM
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 同步登录

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int SysLoginToXM(int hUser, String UserName, String pwd, int nSeq);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">同步登录
</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">UserName
</td><td>用户名</td></tr>
<tr><td style="text-align:center">pwd</td>
<td>密码</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG   . EMSG_ SYS_GET_DEV_INFO_BY_USER_XM
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 同步退出

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int SysLogout(int hUser, int nSeq = 0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">同步退出
</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr style="text-align:center"><td>无
</td><td>   </td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG   . SYS_LOGOUT_TO_XM
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 视频广场登陆

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int XMVideoLogin(int hUser, String userName, String passWord, int nSeq);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">视频广场登陆
</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">UserName
</td><td>用户名</td></tr>
<tr><td style="text-align:center">passWord</td>
<td>密码</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG . XM030_VIDEO_LOGIN
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 视频广场退出

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int XMVideoLogout(int hUser, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">视频广场退出
</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr style="text-align:center"><td>无
</td><td>   </td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：消息值：EUIMSG . XM030_VIDEO_LOGOUT
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 上传本地视频文件

<table >
<tr><td style="background-color:#ccc;text-align:center;width:20px;">定义</td><td colspan="2">int   UpLoadLocalVideo(int hUser, String title, String location, String   description, String catagroyId, String videoFileName, String pictureFileName,   int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">上传本地视频文件、标题、描述、地址、类别
</td></tr>
<tr><td rowspan="7" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">title</td>
<td>标题</td></tr>
<tr><td style="text-align:center">location</td>
<td>地址</td></tr>
<tr><td style="text-align:center">description
</td><td>描述</td></tr>
<tr><td style="text-align:center">catagroyId
</td><td>分类id</td></tr>
<tr><td style="text-align:center">videoFileName
</td><td>视频本地路径</td></tr>
<tr><td style="text-align:center">pictureFileName
</td><td>视频缩略图本地路径</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG   . SYS_DEV_UPLOAD_VIDEO
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；>   0 是进度 <0：失败，详见错误码说明</td></tr>
</table>

## 删除目录下文件

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int GN_DeleteFiles(const char *szDir, long nDaysAgo, const char *szType);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">删除指定目录上，指定日期之前，指定后缀名的文件</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">szDir</td>
<td>目录</td></tr>
<tr><td style="text-align:center">nDaysAgo</td>
<td>日期</td></tr>
<tr><td style="text-align:center">szType
</td><td>后缀名</td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>>=0 返回删除文件数  <0删除失败
</td><tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：无</td></tr>
<tr><td style="text-align:center">arg1
</td><td>>=0   返回删除文件数  <0删除失败</td></tr>
</table>

## 检查产品真伪

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int SysCheckDeviceReal(int hUser, String twoDimensionCode, int nSeq = 0);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
 检查产品真伪</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">twoDimensionCode</td>
<td>设备二维码</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG   . SYS_CHECK_DEVIDE_REAL 5040
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td>
</tr>
<tr><td style="text-align:center">str
</td><td>获取到的josn数据</td>
</tr>
</table>

## 检查密码合法性和强度

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int SysCheckPwdStrength(int hUser, String pwd, int nSeq);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
 检查密码合法性和强度</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">pwd</td>
<td>密码</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG . SYS_CHECK_PWD_STRENGTH
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td>
</tr>
<tr><td style="text-align:center">str
</td><td>获取到的josn数据</td>
</tr>
</table>

## 获取邮箱验证码

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int SysSendEmailCode(int hUser, String email, int nSeq);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
 获取邮箱验证码(用户注册)</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">email</td>
<td>邮箱账号</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>
 消息值：EUIMSG   . SYS_SEND_EMAIL_CODE</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td>
</tr>
<tr><td style="text-align:center">str
</td><td>获取到的josn数据</td>
</tr>
</table>

## 获取邮箱验证码-扩展

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int SysSendEmailCodeEx(int hUser, String email, String username, int nSeq);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
 获取邮箱验证码(用户注册-扩展)</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">email</td>
<td>邮箱账号</td></tr>
<tr><td style="text-align:center">username</td>
<td>用户名</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>
 消息值：EUIMSG . SYS_SEND_EMAIL_CODE</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td>
</tr>
<tr><td style="text-align:center">str
</td><td>获取到的josn数据</td>
</tr>
</table>

## 用户注册（邮箱）

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int SysRegisteByEmail(int hUser, String userName, String password, String email, String code, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
 用户注册（邮箱）</td></tr>
<tr><td rowspan="5" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">userName</td>
<td>用户名。用户名要求长度4~15位，可用中文、英文、数字和“_”组成 </td></tr>
<tr><td style="text-align:center">password</td>
<td>密码</td></tr>
<tr><td style="text-align:center">email</td>
<td>邮箱</td></tr>
<tr><td style="text-align:center">code</td>
<td>验证码</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG   . SYS_REGISTE_BY_EMAIL
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td>
</tr>
<tr><td style="text-align:center">str
</td><td>获取到的josn数据</td>
</tr>
</table>

## 用户注册（邮箱-扩展）

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int SysRegisteByEmailExtend(int hUser, String userName, String pwd, String email, String code, String source, String country, String city,int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
 用户注册（邮箱-扩展）</td></tr>
<tr><td rowspan="8" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">userName</td>
<td>用户名。用户名要求长度4~15位，可用中文、英文、数字和“_”组成 </td></tr>
<tr><td style="text-align:center">password</td>
<td>密码</td></tr>
<tr><td style="text-align:center">email</td>
<td>邮箱</td></tr>
<tr><td style="text-align:center">code</td>
<td>验证码</td></tr>
<tr><td style="text-align:center">source</td>
<td>注册来源</td></tr>
<tr><td style="text-align:center">country</td>
<td>国家</td></tr>
<tr><td style="text-align:center">city</td>
<td>城市</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG . SYS_REGISTE_BY_EMAIL_EXTEND
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td>
</tr>
<tr><td style="text-align:center">str
</td><td>获取到的josn数据</td>
</tr>
</table>

## 找回密码 （重置）- 发送邮箱验证码

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int SysSendCodeForEmail(int hUser, String email, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
 获取邮箱验证码（修改密码）</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">email</td>
<td>邮箱账号</td></tr>

<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG   . SYS_SEND_EMAIL_FOR_CODE</td></tr>
<tr><td style="text-align:center">arg1</td>
<td>==0：成功；<0：失败，详见错误码说明</td></tr>
<tr><td style="text-align:center">str
</td><td>获取到的josn数据</td>
</tr>
</table>

## 找回密码 （重置）-扩展 发送邮箱验证码

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int SysSendCodeForEmailEx(int hUser, String email, String username, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
 获取邮箱验证码（修改密码）</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">email</td>
<td>邮箱账号</td></tr>
<tr><td style="text-align:center">username</td>
<td>用户名</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG   . SYS_SEND_EMAIL_FOR_CODE</td></tr>
<tr><td style="text-align:center">arg1</td>
<td>==0：成功；<0：失败，详见错误码说明</td></tr>
<tr><td style="text-align:center">str
</td><td>获取到的josn数据</td>
</tr>
</table>

## 找回密码 （重置） – 验证邮箱验证码

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int SysCheckCodeForEmail(int hUser, String email, String code, int nSeq);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
 验证找回密码的验证码是否正确</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">email</td>
<td>邮箱</td></tr>
<tr><td style="text-align:center">code</td>
<td>邮箱验证码</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG   . SYS_CHECK_CODE_FOR_EMAIL</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td>
</tr>
<tr><td style="text-align:center">str
</td><td>获取到的josn数据</td>
</tr>
</table>

## 邮箱找回密码 （重置）

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int SysChangePwdByEmail(int hUser, String email, String newpwd, int nSeq);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
 找回密码（邮箱）</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">email</td>
<td>邮箱</td></tr>
<tr><td style="text-align:center">newpwd</td>
<td>新密码</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG   . SYS_PSW_CHANGE_BY_EMAIL</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td>
</tr>
</table>

## 检查用户是否已被注册

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int SysCheckUserRegiste(int hUser, String userName, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
检查用户是否已被注册</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">userName</td>
<td>用户名</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG   . SYS_CHECK_USER_REGISTE</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td>
</tr>
<tr><td style="text-align:center">str
</td><td>获取到的josn数据</td>
</tr>
</table>

## 检查用户手机号是否已被注册

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int CheckUserPhone (int hUser, String phone, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
检查用户手机号是否已被注册</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">phone</td>
<td>手机号码</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG   . SYS_CHECK_USER_PHONE</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td>
</tr>
<tr><td style="text-align:center">str
</td><td>获取到的josn数据</td>
</tr>
</table>

## 检查用户邮箱是否已被注册

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int CheckUserMail(int hUser, String mail, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
检查用户邮箱是否已被注册</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">mail</td>
<td>邮箱</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG   . SYS_CHECK_USER_MAIL</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td>
</tr>
<tr><td style="text-align:center">str
</td><td>获取到的josn数据</td>
</tr>
</table>

## 获取用户信息

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int SysGetUerInfo(int hUser, String userName, String pwd, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
获取用户信息</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">userName</td>
<td>用户名</td></tr>
<tr><td style="text-align:center">pwd</td>
<td>密码</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG  . SYS_GET_USER_INFO
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td>
</tr>
<tr><td style="text-align:center">str
</td><td>获取到的josn数据</td>
</tr>
</table>

## 绑定安全手机(1)—发送验证码 

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int SysSendBindingPhoneCode(int hUser, String phone, String userName, String pwd, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
发送验证码到手机 </td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">phone</td>
<td>手机号码</td></tr>
<tr><td style="text-align:center">userName</td>
<td>用户名</td></tr>
<tr><td style="text-align:center">pwd</td>
<td>密码</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG  . SYS_SEND_BINDING_PHONE_CODE
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td>
</tr>
<tr><td style="text-align:center">str
</td><td>获取到的josn数据</td>
</tr>
</table>

## 绑定安全手机(2)—验证code并绑定 

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int SysBindingPhone(int hUser, String userName, String pwd, String phone, String code, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
绑定手机号 </td></tr>
<tr><td rowspan="5" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">userName</td>
<td>用户名</td></tr>
<tr><td style="text-align:center">pwd</td>
<td>密码</td></tr>
<tr><td style="text-align:center">phone</td>
<td>手机号</td></tr>
<tr><td style="text-align:center">code</td>
<td>验证码</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG  . SYS_BINDING_PHONE
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td>
</tr>
<tr><td style="text-align:center">str
</td><td>获取到的josn数据</td>
</tr>
</table>

## 绑定安全邮箱(1)—发送验证码 

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int SysSendBindingEmailCode (int hUser, String email, String userName, String pwd, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
发送验证码到邮箱 </td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">email</td>
<td>邮箱账户</td></tr>
<tr><td style="text-align:center">userName</td>
<td>用户名</td></tr>
<tr><td style="text-align:center">pwd</td>
<td>密码</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG  . SYS_SEND_BINDING_EMAIL_CODE
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td>
</tr>
<tr><td style="text-align:center">str
</td><td>获取到的josn数据</td>
</tr>
</table>

## 绑定安全邮箱(2)—验证code并绑定 

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int SysBindingEmail (int hUser, String userName, String pwd, String email, String code, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
绑定邮箱 </td></tr>
<tr><td rowspan="5" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">userName</td>
<td>用户名</td></tr>
<tr><td style="text-align:center">pwd</td>
<td>密码</td></tr>
<tr><td style="text-align:center">email</td>
<td>邮箱账户</td></tr>
<tr><td style="text-align:center">code</td>
<td>验证码</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG  . SYS_BINDING_EMAIL
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td>
</tr>
<tr><td style="text-align:center">str
</td><td>获取到的josn数据</td>
</tr>
</table>

## 检查APP更新

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int FirLatest(int hUser, String appId, String appToken, int nSeq = 0);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
检查APP更新</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">appToken</td>
<td>包名</td></tr>
<tr><td style="text-align:center">appId</td>
<td>App Id</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG   . FIR_IM_CHECK_LATEST
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td>
</tr>
<tr><td style="text-align:center">str
</td><td>获取到的josn数据</td>
</tr>
</table>

## 开启上报数据

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int DevStartUploadData(int hUser, String szDevId,int nUploadDataType, int nSeq);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
开启上报数据</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr style="text-align:center"><td>szDevId</td>
<td>设备序列号</td></tr>
<tr><td style="text-align:center">nUploadDataType
</td>
<td>上报数据类型：<br>
VEHICLE =   0;// 车载信息<br>
SDK_RECORD_STATE   = 1;// 录像状态<br>
SDK_DIGITCHN_STATE   = 2; // 数字通道连接状态<br>
SDK_TITLE_INFO   = 3; // 通道标题<br>
SDK_FUNCTION_STATE   = 4;// 功能状态   如：运动相机
// 录像状态、延时拍状态等<br>
SDK_ELECT_STATE   = 5;// 电量状态
</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id</td>
<td>消息值：EUIMSG   . DEV_START_UPLOAD_DATA<br>
DEV_ON_UPLOAD_DATA   回调中返回 上报数据、进度、数据类型
</td></tr>
<tr ><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 关闭上报数据

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int DevStopUploadData(int hUser, String szDevId,int nUploadDataType, int nSeq);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
关闭上报数据</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>设备序列号</td></tr>
<tr><td style="text-align:center">nUploadDataType</td>
<td>上报数据类型：类型说明同上</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG   . FIR_IM_CHECK_LATEST
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td>
</tr>
</table>

## 返回设备是否开启了微信报警推送

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int SysDevWXPMS(const char *szDeviceSN);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
返回设备是否开启了微信报警推送</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">szDeviceSN</td>
<td>设备序列号</td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>返回是否开启int；>=0开启
</td><tr>
</table>

## 返回设备登录帐户是否是主帐户

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int SysDevIsMasterAccount(String szDeviceSN);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
返回设备登录帐户是否是主帐户</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">szDeviceSN</td>
<td>设备序列号</td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>返回是否开启int；>=0开启
</td><tr>
</table>

## 获取设备的备注信息

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int SysGetDevComment(String szDeviceSN);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
获取设备的备注信息</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">szDeviceSN</td>
<td>设备序列号</td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>返回获取到的备注信息
</td><tr>
</table>

## 开启微信报警监听

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int SysOpenWXAlarmListen(int hUser, String sDevId, int nSeq);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
开启微信报警监听</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">sDevId</td>
<td>设备序列号</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG . SYS_WX_ALARM_LISTEN_OPEN
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td>
</tr>
<tr><td style="text-align:center">str
</td><td>返回的josn数据</td>
</tr>
</table>

## 关闭微信报警监听

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int SysCloseWXAlarmListen(int hUser, String sDevId, int nSeq);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
关闭微信报警监听</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">sDevId</td>
<td>设备序列号</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG . SYS_WX_ALARM_LISTEN_CLOSE
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td>
</tr>
<tr><td style="text-align:center">str
</td><td>返回的josn数据</td>
</tr>
</table>

## 微信报警状态查询

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int SysWXAlarmStateCheck(int hUser, String sDevId, int nSeq);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
微信报警状态查询</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">sDevId</td>
<td>设备序列号</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG . SYS_WX_ALARM_WXPMSCHECK
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td>
</tr>
<tr><td style="text-align:center">str
</td><td>返回的josn数据</td>
</tr>
</table>

## 查询云存储状态

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int SysGetDevsCSStatus(int hUser, String szDevices, int nSeq);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
实时从服务器上查询云存储状态</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">szDevices</td>
<td>设备序列号，多个设备用","号分隔</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG . SYS_CHECK_CS_STATUS(5067)
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td>
</tr>
<tr><td style="text-align:center">str
</td><td>josn数据</td>
</tr>
</table>

## 获取设备所在的帐户信息

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int SysGetDevUserInfo(int hUser, String szDevice, int nSeq);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
获取设备所在的帐户信息</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">szDevice</td>
<td>设备序列号</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG . SYS_DULIST(5068)
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td>
</tr>
<tr><td style="text-align:center">str
</td><td>返回的josn数据</td>
</tr>
</table>

## 指定设备的主帐户

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int SysSetDevMasterAccount(int hUser, String szDevice,  String szMAUserId, int nSeq);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
指定设备的主帐户</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">szDevice</td>
<td>设备序列号</td></tr>
<tr><td style="text-align:center">szMAUserId</td>
<td>主帐户ID</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG . SYS_MDSETMA(5069)
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td>
</tr>
<tr><td style="text-align:center">str
</td><td>返回的josn数据</td>
</tr>
</table>

## 修改登录用户名

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int SysModifyUserName(int hUser, String szNewUserName, int nSeq);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
修改登录用户名（只能修改微信等绑定帐户自动生成）</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">szNewUserName</td>
<td>新的用户名</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG. SYS_MODIFY_USERNAME(5070)
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td>
</tr>
</table>

## 添加设备状态到Listener

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int SysAddDevStateListener(int hUser);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
添加设备状态到Listener</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">hUser</td>
<td>消息结果接收者</td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>0
</td><tr>
</table>

## 从Listener删除设备状态

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int SysRemoveDevStateListener(int hUser);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
从Listener删除设备状态</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">hUser</td>
<td>消息结果接收者</td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>0
</td><tr>
</table>

## 从服务器端更新当前账号是否为该设备的主账号

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int SysIsDevMasterAccountFromServer(int hUser, String szDevice, int nSeq);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
从服务器端更新当前账号是否为该设备的主账号</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">szDevice</td>
<td>设备序列号</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG. SYS_IS_MASTERMA
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>1：主账号 0：不是主账号</td>
</tr>
<tr><td style="text-align:center">str
</td><td>返回的json信息</td>
</tr>
</table>

## 前后台切换函数

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">void SetActive(int nActive);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
APP前后台切换</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">nActive</td>
<td>切换标识</td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>详见错误码说明
</td><tr>
</table>








