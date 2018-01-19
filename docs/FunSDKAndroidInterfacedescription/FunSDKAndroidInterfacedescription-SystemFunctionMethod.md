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
</td><td>指向SDBDeviceInfo数组的字节流（可使用G.BytesToObj函数转换字节流与对象）</td></tr>
</table>

## 添加设备

<table >
<tr><td style="background-color:#ccc;text-align:center;width:100px;">定义</td><td colspan="2">int SysAddDevice(int hUser, SDBDeviceInfo *pDevInfo, String userName="",String password="", int nSeq=0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">添加设备</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">pDevInfo</td>
<td>
设备信息对象字节流
typedef struct SDBDeviceInfo

{
   char Devmac[64]; // DEV_SN / IP / DNS
   char Devname[128]; // 名称
   char devIP[64]; // 名称
   char loginName[16]; // 用户名
   char loginPsw[16]; // 密码
   int nPort; // 端口映射端口
   int nType; // --设备类型 1:插座
   int nID; // --本设备ID,内部使用
}SDBDeviceInfo;
</td></tr>
<tr><td  style="text-align:center">userName
</td><td>系统用户名；为空时表示与调用SysGetDevList使用的用户名相同</td></tr>
<tr><td  style="text-align:center">password</td><td>系统密码；为空时表示与调用SysGetDevList使用密码相同</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：EUIMSG . SYS_ADD_DEVICE</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>==0：成功；<0：失败，详见错误码说明</td></tr>
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
</td><td>消息值：EUIMSG   . EMSG_SYS_DELETE_DEV
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

## 获取手机验证码

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int SysSendPhoneMsg(int hUser, String userName, String phoneNO, int nSeq = 0);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">获取手机验证码</td></tr>
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
</td><td>消息值：EUIMSG   . EMSG_SYS_GET_PHONE_CHECK_CODE</td></tr>
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
<td>消息值：EUIMSG   . EMSG_SYS_REGISER_USER_XM
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
<td>密码</td></tr>
<tr><td style="text-align:center">newPwd
</td><td>新密码</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG   . EMSG_SYS_EDIT_PWD_XM
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 忘记登录密码

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int SysForgetPwdXM(int hUser, String phone, int nSeq)</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">忘记登录密码
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

## 验证验证码（手机）

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int CheckResetCodeXM(int hUser, String phone, String checkNum, int nSeq);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">验证修改密码的验证码是否正确</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">phone</td>
<td>手机号码</td></tr>
<tr><td style="text-align:center">checkNum</td>
<td>验证码</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG   . EMSG_SYS_REST_PWD_CHECK_XM</td></tr>
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
<td>手机号码</td></tr>
<tr><td style="text-align:center">newPwd</td>
<td>新密码</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG   . EMSG_SYS_RESET_PWD_XM
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
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG   . SYS_CHECK_DEVICE_REAL
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td>
</tr>
</table>

## 获取邮箱验证码

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int SysSendEmailCode(int hUser, String email, int nSeq);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
 获取邮箱验证码</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">email</td>
<td>邮箱账号</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>
 消息值：EUIMSG   . SYS_SEND_EMAIL_CODE</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td>
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
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG   . SYS_REGISTE_BY_EMAIL
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td>
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

<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG   . SYS_SEND_EMAIL_FOR_CODE</td></tr>
<tr><td style="text-align:center">arg1</td>
<td>==0：成功；<0：失败，详见错误码说明</td></tr>
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
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG   . SYS_CHECK_CODE_FOR_EMAIL</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td>
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
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int SysCheckUserRegiste(int hUser, String userName, int nSeq =0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
检查用户是否已被注册</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">userName</td>
<td>用户名</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG   . EMSG_SYS_CHECK_USER_REGISTE</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td>
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
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG   . EMSG_SYS_GET_USER_INFO
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td>
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
<td>上报数据类型：
VEHICLE =   0;// 车载信息
SDK_RECORD_STATE   = 1;// 录像状态
SDK_DIGITCHN_STATE   = 2; // 数字通道连接状态
SDK_TITLE_INFO   = 3; // 通道标题
SDK_FUNCTION_STATE   = 4;// 功能状态   如：运动相机
// 录像状态、延时拍状态等
SDK_ELECT_STATE   = 5;// 电量状态
</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id</td>
<td>消息值：EUIMSG   . EMSG_DEV_START_UPLOAD_DATA
EMSG_DEV_ON_UPLOAD_DATA   回调中返回 上报数据、进度、数据类型
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












