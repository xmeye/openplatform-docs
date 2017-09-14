<br/>

<div>
This text is an alarm interface description. The difference between Android and IOS is not big in the respect of calling interface, but there are a lot of differences in the alarm push. IOS need to have a certificate of alarm function, provide a certificate to us (our alarm server will push message to the Apple server) and tell us theid of releasing APP; Android does not need. The following will make a description of provided interfaces, and explain the usage of Android interface used .
</div>
#### Initialization ####
<br/>

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
<tr><td style="background-color:#ccc;text-align:center;width:35px;">Definition
</td><td colspan="2">int Init(int hUser, byte []pSMCInitInfo,  int nSeq)</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description
</td><td colspan="2">Initialize related parameters. Use alarm function, need to call this method first.</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr><td style="text-align:center">pSMCInitInfo</td>
<td>Input parameters, point to SMCInitInfo byte stream
</td></tr>
<tr><td style="text-align:center">hUser</td>
<td>Used to receive the callback message of this time. At the same time, Android is also used to receive the real-time alarm message after the subscription.
</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result <br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id</td>
<td>MC_INIT_INFO </td></tr>
<tr><td style="text-align:center">arg1
</td><td>= 0:success; < 0：fail</td></tr>
<tr><td style="background-color:#ccc;text-align:center;">Description
</td>
<td colspan="2">

typedef struct SMCInitInfo<br/>
{<br/>
<div style="margin-left:20px;">
    char user[64];<br/>
    char password[64];<br/>
    char token[128];       // IOS:each device's token; Android: need to combine by yourself to ensure uniqueness<br/>
    int language;         //   EMSGLANGUAGE<br/>
    int appType;          //   EAPPTYPE<br/>
    char szAppType[64];   // IOS:XXXXXX APP-IDprogram unique identifier; Android:temporarily not required<br/><br/>
</div>
}SMCInitInfo;<br/>
</td></tr>
</table>
<br/>

#### Alarm subscription ####
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">Definition
</td><td colspan="2">int LinkDev(int hUser, String uuid, String   devUserName, String devPassword, int nSeq)</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description
</td><td colspan="2">Subscribe real-time alarm message. Just need to subscribe once and it is always effective until cancel the subscription.</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr><td style="text-align:center">hUser</td>
<td>Used to receive the callback message of this time.</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result <br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id</td>
<td>MC_LinkDev</td></tr>
<tr><td style="text-align:center">arg1
</td><td>>=0：success；<0：fail
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Note
</td><td colspan="2">Android: real-time alarm message id: MC_ON_AlarmCb;  arg1: pData byte stream length; pData: real-time alarm message, json format; str: device serial number <br/>
</td></tr>
</table>
<br/>

#### Cancel alarm subscription ####
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">Definition
</td><td colspan="2">int UnlinkDev(int hUser, String uuid, int   nSeq)</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description
</td><td colspan="2">Cancel the subscription</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr><td style="text-align:center">&#160</td><td>&#160</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result <br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id</td>
<td>MC_UnlinkDev</td></tr>
<tr><td style="text-align:center">arg1
</td><td>>=0：success； <0：fail</td></tr>
</table>
<br/>

#### Query history alarm information ####
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">Definition
</td><td colspan="2">int SearchAlarmInfo(int hUser,  byte []pXPMS_SEARCH_ALARMINFO_REQ,  int nSeq)</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description
</td><td colspan="2">Query history alarm information</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr><td>pXPMS_SEARCH_ALARM<br/>INFO_REQ</td>
<td>Input parameters, point to XPMS_SEARCH_ALARMINFO_REQ byte stream</td></tr>
<tr><td rowspan="6" style="background-color:#ccc;text-align:center">Result <br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id</td>
<td>MC_SearchAlarmInfo</td></tr>
<tr><td style="text-align:center">arg1
</td><td>>= 0  pData byte stream length；<0 fail</td></tr>
<tr><td style="text-align:center">arg3
</td><td>Number of alarm messages</td></tr>
<tr><td style="text-align:center">str
</td><td>Device serial number</td></tr>
<tr><td style="text-align:center">pData
</td><td>Byte stream pointing to alarm information, json format</td></tr>
</table>
<br/>

#### Download alarm images ####
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">Definition
</td><td colspan="2">int SearchAlarmPic(int hUser,  String fileName, byte   []pXPMS_SEARCH_ALARMPIC_REQ,  int nSeq)</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description
</td><td colspan="2">Download alarm images</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr><td style="text-align:center">fileName</td><td>Image name, absolute path
</td></tr>
<tr><td>pXPMS_SEARCH_ALAR<br/>MPIC_REQ</td>
<td>Point to XPMS_SEARCH_ALARMPIC_REQ byte stream</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">Result <br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id</td>
<td>MC_SearchAlarmPic</td></tr>
<tr><td style="text-align:center">arg1
</td><td>>=0 success; <0fail</td></tr>
<tr><td style="text-align:center">str</td>
<td>Image name</td></tr>
</table>
<br/>

#### Get images URL ####
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">Definition
</td><td colspan="2">int SearchAlarmPic(int hUser,  String fileName, byte []pXPMS_SEARCH_ALARMPIC_REQ,  int nSeq)</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description
</td><td colspan="2">Get images URL</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr><td style="text-align:center">strDNSPicURL</td>
<td>URL with domain name</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">Result <br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center"> </td>
<td>UPL after resolving IP</td></tr>
</table>
<br/>

#### The possible reasons why can not receive the alarm: ####
1、Device needs to support the new alarm. For example, software version: V4.02.R12. The release date of R12 is after March 15, 2016; R11 is after December 25, 2015, support for the new alarm.<br/>
2、The device is needed to connect extranet. The alarm function is needed to open and subscribe to the server.<br/>
3、Check device DNS settings, domestic (Chinese Mainland) is generally considered the preferred: 114.114.114.114, alternative: 8.8.8.8; other areas, general configuration is: 8.8.8.8.



