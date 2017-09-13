
<div name="chushihua" id="chushihua" style="font-size:20px;"><b>6.1 Log initialization</b></div>
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
<tr><td style="background-color:#ccc;text-align:center;width:35px;">Definition</td><td colspan="2">void Fun_LogInit(UI_HANDLE hUser, const char *szServerIP, int nServerPort, const char *szLogFile, int nLogLevel = 0x3);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Log initialization</td></tr>
<tr><td rowspan="5" style="background-color:#ccc;text-align:center">Parameters <br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr><td style="text-align:center">szServerIP</td>
<td>Server IP</td></tr>
<tr><td style="text-align:center">nServerPort</td>
<td>Port number</td></tr>
<tr><td style="text-align:center">szLogFile</td>
<td>Log file</td></tr>
<tr><td style="text-align:center">nLogLevel</td>
<td>
Log level: LOG_UI_MSG: send message to hUser via EUIMSG .EMSG_APP_ON_MSG_LOG<br/>
<div style="margin-left:40px;">
LOG_FILE    ：send file<br/>
LOG_NET_MSG ：send network<br/>
</div>
<label style="color:red">Note: parameters can use “｜”, multiple output</label><br/><br/>

#define   LOG_UI_MSG  1<br/>
#define   LOG_FILE    2<br/>
#define   LOG_NET_MSG 4<br/><br/>

If log level contains LOG_UI_MSG, users receive print  information via EUIMSG .EMSG_APP_ON_MSG_LOG, print information is obtained in string parameters; receiving object is hUser in LogInit. 
</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result  <br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id</td>
<td>Message value：EUIMSG   .EMSG_START_PLAY</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==EE_OK：success; <0: fail, for details, see error code   description</td></tr>
</table>
<br/>

<div name="dayin" id="dayin" style="font-size:20px;"><b>6.2 Print log</b></div> 
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">Definition</td><td colspan="2">void Fun_Log(char *szLog);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Print log: the output location is determined by the log level, service   
information and file information in the initialization and other parameters、</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr><td style="text-align:center">szLog</td>
<td>Log information</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">结果<br/>消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id</td>
<td>Message value:EUIMSG   .EMSG_APP_ON_MSG_LOG，log information is obtained in string paremeters
</td></tr>
</table>
<br/>

<div name="fasong" id="fasong" style="font-size:20px;"><b>6.3Send log</b></div> 
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">Definition</td><td colspan="2">void Fun_SendLogFile(const char *szFile);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Send log</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">Parameters <br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr><td style="text-align:center">szFile</td>
<td>Log file</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result   <br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id</td>
<td>Message value：EUIMSG   . ELOG_MSG_SEND_FILE</td></tr>
<tr><td style="text-align:center">arg1</td>
<td>==EE_OK：success; <0: fail, for details, see error code description</td></tr>
</table>
<br/>

<div name="yichang" id="yichang" style="font-size:20px;"><b>6.4Catch exception</b></div>  
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">Definition</td><td colspan="2">void Fun_Crash(char *crashInfo);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Send captured exception information to server</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">Parameters <br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr><td style="text-align:center">crashInfo</td>
<td>Exception information</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result   <br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id</td>
<td>Message value：EUIMSG   . ELOG_APP_CRASH</td></tr>
<tr><td style="text-align:center">arg1</td>
<td>==EE_OK：success; <0: fail, for details, see error code description</td></tr>
</table>
<br/>














