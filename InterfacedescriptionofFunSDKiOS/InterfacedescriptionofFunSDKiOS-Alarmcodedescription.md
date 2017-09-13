本文为报警接口说明。Android和IOS，在调用接口方面，差异不大，但在报警推送方面有很大不同。IOS需要有报警功能的证书，并把证书提供给我们一份（我们报警服务器给苹果服务器推送消息用），也要把发布app的id告诉我们；Android不需要。下面将对提供的接口做一说明，说明接口使用的Android。

## 初始化

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
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int MC_Init(int hUser, SMCInitInfo pInfo,  int nSeq)
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">初始化相关参数。使用报警功能，需首先调用此方法。</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">pSMCInitInfo</td>
<td>输入参数，指向SMCInitInfo 的字节流</td></tr>
<tr><td style="text-align:center">hUser</td>
<td>用于接收本次回调消息。同时，Android也用来接收订阅后的实时报警消息。
</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id</td>
<td>MC_INIT_INFO </td></tr>
<tr><td style="text-align:center">arg1
</td><td>= 0: 成功; < 0失败</td></tr>
<tr><td style="background-color:#ccc;text-align:center;">说明</td>
<td colspan="2">

typedef struct SMCInitInfo
{
<div style="margin-left:20px;">
    char user[64];
    char password[64];
    char token[128];       // IOS:每台设备的token；Android：需自己组，保证唯一性
    int language;         //   EMSGLANGUAGE
    int appType;          //   EAPPTYPE
    char szAppType[64];   // IOS:XXXXXX APP-ID程序唯一标识; Android:暂不需要
</div>
}SMCInitInfo;
</td></tr>
</table>


## 报警订阅

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int MC_LinkDev(int hUser, const char* uuid, const char* devUserName, const char* devPassword, int nSeq)</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">订阅实时报警消息。只需订阅一次即可，直到取消订阅，一直有效。</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">hUser</td>
<td>用于接收本次回调消息</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id</td>
<td>MC_LinkDev</td></tr>
<tr><td style="text-align:center">arg1
</td><td>>=0：成功；<0：失败</td></tr>
<tr><td style="background-color:#ccc;text-align:center">备注
</td><td colspan="2">Android: 实时报警消息 id: MC_ON_AlarmCb;  arg1: pData字节流长度;  pData: 实时报警信息，json格式;  str: 设备序列号
IOS: 报警消息由苹果服务器推送
</td></tr>
</table>


## 取消报警订阅

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int MC_UnlinkDev(int hUser, const char* uuid, int   nSeq)</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">取消订阅</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center"></td><td></td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id</td>
<td>MC_UnlinkDev</td></tr>
<tr><td style="text-align:center">arg1
</td><td>>=0：成功； <0：失败</td></tr>
</table>


## 查询历史报警信息

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int MC_SearchAlarmInfo(int hUser,  XPMS_SEARCH_ALARMINFO_REQ *pXPMS_SEARCH_ALARMINFO_REQ,  int nSeq)
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">查询历史报警信息</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td>pXPMS_SEARCH_ALARMINFO_REQ</td>
<td>输入参数，指向XPMS_SEARCH_ALARMINFO_REQ的字节流</td></tr>
<tr><td rowspan="6" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id</td>
<td>MC_SearchAlarmInfo</td></tr>
<tr><td style="text-align:center">arg1
</td><td>>= 0  pData字节流长度; <0失败</td></tr>
<tr><td style="text-align:center">arg3
</td><td>报警消息个数</td></tr>
<tr><td style="text-align:center">str
</td><td>设备序列号</td></tr>
<tr><td style="text-align:center">pData
</td><td>指向报警信息的字节流，json格式</td></tr>
</table>


## 下载报警图片

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int MC_SearchAlarmPic(int hUser,  const char* fileName, XPMS_SEARCH_ALARMPIC_REQ *pXPMS_SEARCH_ALARMPIC_REQ,  int nSeq)
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">下载报警图片</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">fileName</td><td>图片名，绝对路径</td></tr>
<tr><td>pXPMS_SEARCH_ALARMPIC_REQ</td>
<td>指向XPMS_SEARCH_ALARMPIC_REQ的字节流</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id</td>
<td>MC_SearchAlarmPic</td></tr>
<tr><td style="text-align:center">arg1
</td><td>>=0 成功; <0 失败</td></tr>
<tr><td style="text-align:center">str</td>
<td>图片名</td></tr>
</table>


## 获取图片URL

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">char *MC_GetAlarmPicURL(char   *strDNSPicURL, char strPicURL[512]);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">获取图片URL</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">strDNSPicURL</td>
<td>带有域名的URL</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center"> </td>
<td>解析IP后的URL</td></tr>
</table>


## 收不到报警可能原因

```
1、设备要支持新的报警。例如，软件版本：V4.02.R12.。。。，其中，R12发布日期在2016年3月15号之后，R11是2015年12月25号之后，支持新的报警。
2、设备需连接外网，报警功能要打开，并向服务器订阅。
3、检查设备DNS设置，国内(中国大陆)一般首选：114.114.114.114，备选：8.8.8.8; 其它地区，一般配置为：8.8.8.8。
```
