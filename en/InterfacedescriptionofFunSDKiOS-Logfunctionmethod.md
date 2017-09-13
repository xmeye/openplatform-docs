
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
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">void Fun_LogInit(UI_HANDLE hUser, const char *szServerIP, int nServerPort, const char *szLogFile, int nLogLevel = 0x3);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">日志初始化</td></tr>
<tr><td rowspan="5" style="background-color:#ccc;text-align:center">参数<br/>说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">szServerIP</td>
<td>服务IP</td></tr>
<tr><td style="text-align:center">nServerPort</td>
<td>端口号</td></tr>
<tr><td style="text-align:center">szLogFile</td>
<td>日志文件</td></tr>
<tr><td style="text-align:center">nLogLevel</td>
<td>
日志级别：LOG_UI_MSG ：通过EUIMSG .EMSG_APP_ON_MSG_LOG消息发给hUser<br/>
<div style="margin-left:40px;">
LOG_FILE    ：发送文件<br/>
LOG_NET_MSG ：发送网络<br/>
</div>
<label style="color:red">注：参数可以使用“｜”，多重输出</label><br/><br/>

#define   LOG_UI_MSG  1<br/>
#define   LOG_FILE    2<br/>
#define   LOG_NET_MSG 4<br/><br/>

如果日志级别包含LOG_UI_MSG   用户通过EUIMSG .EMSG_APP_ON_MSG_LOG消息接收打印信息，打印信息在字符串参数中获取；接收对象为LogInit中的hUser
</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果<br/>消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id</td>
<td>消息值：EUIMSG   .EMSG_START_PLAY</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==EE_OK：成功；<0：失败，详见错误码说明</td></tr>
</table>
<br/>

<div name="dayin" id="dayin" style="font-size:20px;"><b>6.2 Print log</b></div>
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">void Fun_Log(char *szLog);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">打印日志：输出的位置根据初始化中日志级别和服务信息以及文件信息等参数来确定</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数<br/>说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">szLog</td>
<td>日志信息</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">结果<br/>消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id</td>
<td>消息值：EUIMSG   .EMSG_APP_ON_MSG_LOG，日志信息在字符串参数中获取
</td></tr>
</table>
<br/>

<div name="fasong" id="fasong" style="font-size:20px;"><b>6.3Send log</b></div>
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">void Fun_SendLogFile(const char *szFile);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">发送日志</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数<br/>说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">szFile</td>
<td>日志文件</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果<br/>消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id</td>
<td>消息值：EUIMSG   . ELOG_MSG_SEND_FILE</td></tr>
<tr><td style="text-align:center">arg1</td>
<td>==EE_OK：成功；<0：失败，详见错误码说明</td></tr>
</table>
<br/>

<div name="yichang" id="yichang" style="font-size:20px;"><b>6.4Catch exception</b></div> 
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">void Fun_Crash(char *crashInfo);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">发送捕获到的异常信息至服务器</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数<br/>说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">crashInfo</td>
<td>异常信息</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果<br/>消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id</td>
<td>消息值：EUIMSG   . ELOG_APP_CRASH</td></tr>
<tr><td style="text-align:center">arg1</td>
<td>==EE_OK：成功；<0：失败，详见错误码说明</td></tr>
</table>
<br/>














