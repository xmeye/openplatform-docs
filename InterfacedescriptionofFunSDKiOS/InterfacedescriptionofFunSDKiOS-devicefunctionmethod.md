## 获取通道名称

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
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int FUN_DevGetChnName(UI_HANDLE hUser, const char *szDevId, const char *szUser, const char *szPwd, int nSeq = 0);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">获取通道名称</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>设备序列号</td></tr>
<tr><td style="text-align:center">szUser
</td><td>设备登录用户名；为空时，使用默认用户名（默认为添加设备时的用户名）</td></tr>
<tr><td style="text-align:center">szPwd</td>
<td>设备登录密码；</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id</td>
<td>消息值：EUIMSG   .EMSG_DEV_GET_CHN_NAME</td></tr>
<tr><td style="text-align:center">arg1
</td><td>>0：通道个数；<0：失败，详见错误码说明</td></tr>
<tr><td style="text-align:center">pData
</td><td>指向SDK_ChannelNameConfigAll对象字节流</td></tr>
</table>

## 查询录像

<table >
<tr><td style="background-color:#ccc;text-align:center;width:100px;">定义</td><td colspan="2">int FUN_DevFindFile(UI_HANDLE hUser, const char *szDevId, H264_DVR_FINDINFO* lpFindInfo, int nMaxCount, int waittime = 10000, int nSeq = 0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">查询录像</td></tr>
<tr><td rowspan="5" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>设备序列号</td></tr>
<tr><td style="text-align:center">pH264_DVR_FINDINFO</td>
<td>查询条件。H264_DVR_FINDINFO对象字节流</td></tr>
<tr><td  style="text-align:center">nMaxCount
</td><td>返回最大条数</td></tr>
<tr><td  style="text-align:center">waittime</td><td>超时时间</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：EUIMSG   . EMSG_DEV_FIND_FILE</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>>0：结果条数；<0：失败，详见错误码说明</td></tr>
<tr><td  style="text-align:center">pData</td>
<td>指向H264_DVR_FILE_DATA对象数组字节流</td></tr>
</table>

## 查询录像(按时间)

<table >
<tr><td style="background-color:#ccc;text-align:center;width:50px;">定义</td><td colspan="2">int FUN_DevFindFileByTime(UI_HANDLE hUser, const char *szDevId, SDK_SearchByTime* lpFindInfo, int waittime = 2000, int nSeq = 0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">查询录像
</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>设备序列号</td></tr>
<tr><td style="text-align:center">lpFindInfo
</td><td>查询条件。SDK_SearchByTime对象字节流</td></tr>
<tr><td  style="text-align:center">waittime</td><td>超时时间</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：EUIMSG   . DEV_FIND_FILE_BY_TIME
</td></tr>
<tr><td  style="text-align:center">arg1
</td><td>>0：结果条数；<0：失败，详见错误码说明</td></tr>
<tr><td  style="text-align:center">pData
</td><td>指向SDK_SearchByTimeResult对象字节流</td></tr>
</table>

## 按文件录像下载

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">FUN_HANDLE FUN_DevDowonLoadByFile(UI_HANDLE hUser, const char *szDevId, H264_DVR_FILE_DATA *pH264_DVR_FILE_DATA, const char *szFileName, int nSeq = 0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">按文件下载录像</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>设备序列号</td></tr>
<tr><td style="text-align:center">pH264_DVR_FILE_DATA
</td><td>查询条件。H264_DVR_FILE_DATA对象字节流</td></tr>
<tr><td  style="text-align:center">szFileName</td><td>保存文件路径+文件名</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG   . EMSG_ON_FILE_DOWNLOAD:下载函数调用结果
EUIMSG   . EMSG_ON_FILE_DLD_COMPLETE:下载完成消息回调
EUIMSG   . EMSG_ON_FILE_DLD_POS:下载进度消息回调
</td></tr>
<tr><td style="text-align:center">arg1
</td><td><0：失败，详见错误码说明</td></tr>
</table>

## 按时间录像下载

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">FUN_HANDLE FUN_DevDowonLoadByTime(UI_HANDLE hUser, const char *szDevId, H264_DVR_FINDINFO *pH264_DVR_FINDINFO, const char *szFileName, int nSeq = 0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">按文件下载录像</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>设备序列号</td></tr>
<tr><td style="text-align:center">pH264_DVR_FINDINFO
</td><td>查询条件。H264_DVR_FINDINFO对象字节流</td></tr>
<tr><td  style="text-align:center">szFileName</td><td>保存文件路径+文件名</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：EUIMSG   .EMSG_ON_FILE_DOWNLOAD:下载函数调用结果
EUIMSG   . EMSG_ON_FILE_DLD_COMPLETE:下载完成消息回调
EUIMSG   . EMSG_ON_FILE_DLD_POS:下载进度消息回调
</td></tr>
<tr><td style="text-align:center">arg1
</td><td><0：失败，详见错误码说明</td></tr>
</table>

## 设备停止下载

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int FUN_DevStopDownLoad(FUN_HANDLE hDownload);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">设备停止下载
</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td  style="text-align:center">hDownload</td>
<td>下载操作对象句柄</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：无</td></tr>
<tr><td style="text-align:center">arg1
</td><td><0：失败，详见错误码说明</td></tr>
</table>

## 4.7 云台控制

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int FUN_DevPTZControl(UI_HANDLE hUser, const char *szDevId, int nChnIndex, int nPTZCommand, bool bStop = false, int nSpeed = 4, int nSeq = 0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">云台控制
</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>设备序列号</td></tr>
<tr><td style="text-align:center">nChnIndex</td>
<td>通道号（从0开始）</td></tr>
<tr><td style="text-align:center">nPTZCommand</td>
<td>云台命令（详见EPTZCMD）</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id</td>
<td>消息值：EUIMSG   . EMSG_DEV_PTZ_CONTROL</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 语音对讲-开始

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">FUN_HANDLE FUN_DevStarTalk(UI_HANDLE hUser, const char *szDevId, int nSeq = 0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">开始语音对讲
</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">devId</td>
<td>设备序列号</td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td>
<td colspan="2">语音对讲对象句柄，可用来实现停止对讲功能</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG   . EMSG_DEV_START_TALK
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 语音对讲-停止

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">void FUN_DevStopTalk(FUN_HANDLE hPlayer);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">停止语音对讲</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">hTalker</td>
<td>语音对讲对象操作句柄</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG   . EMSG_DEV_STOP_TALK</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 语音对讲-发送数据

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int   FUN_DevSendTalkData(const char *szDevId, const char *pPCMData, int nDataLen);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">发送语音对讲客户端的数据</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>设备序列号</td></tr>
<tr><td style="text-align:center">pPCMData</td>
<td>PCM格式数据</td></tr>
<tr><td style="text-align:center">nDataLen</td>
<td>PCM数据长度</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG   . EMSG_DEV_SEND_MEDIA_DATA</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 设备搜索

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int FUN_DevSearchDevice(UI_HANDLE hUser, int nTimeout, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">设备搜索
</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">nTimeout</td>
<td>超时时间</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG   . EMSG_DEV_SEARCH_DEVICES
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 参数配置-获取配置

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int FUN_DevGetConfig(UI_HANDLE hUser, const char *szDevId, int nCommand, int nOutBufLen, int nChannelNO = -1, int nTimeout = 5000, int nSeq = 0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">获取设备配置</td></tr>
<tr><td rowspan="6" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">szDevId
</td><td>设备序列号</td></tr>
<tr><td style="text-align:center">nCommand</td>
<td>配置命令字（详见EConfigCmd）</td></tr>
<tr><td style="text-align:center">nOutBufLen
</td><td>结果长度</td></tr>
<tr><td style="text-align:center">nChannelNO</td>
<td>通道号（从0开始）</td></tr>
<tr><td style="text-align:center">nTimeout
</td><td>超时时间</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG   . EMSG_DEV_GET_CONFIG
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td></tr>
<tr><td style="text-align:center">pData
</td><td>指向结果对象字节流</td></tr>
</table>

## 参数配置-获取配置(Json)

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int FUN_DevGetConfig_Json(UI_HANDLE hUser, const char *szDevId, const char *szCommand, int nOutBufLen, int nChannelNO = -1, int nTimeout = 5000, int nSeq = 0);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">获取设备配置(Json)</td></tr>
<tr><td rowspan="6" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr style="text-align:center"><td>szDevId
</td><td>设备序列号</td></tr>
<tr style="text-align:center"><td>szCommand
</td><td>配置命令字（详见EConfigCmd）</td></tr>
<tr style="text-align:center"><td>nOutBufLen
</td><td>结果长度</td></tr>
<tr style="text-align:center"><td>nChannelNO
</td><td>通道号（从0开始）</td></tr>
<tr style="text-align:center"><td>nTimeout
</td><td>超时时间</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG   . EMSG_DEV_GET_CONFIG_JSON
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td></tr>
<tr><td style="text-align:center">pData
</td><td>指向结果对象字节流</td></tr>
</table>

## 参数配置-保存配置

<table >
<tr><td style="background-color:#ccc;text-align:center;width:20px;">定义</td><td colspan="2">int FUN_DevSetConfig(UI_HANDLE hUser, const char *szDevId, int nCommand, const void *pConfig, int nConfigLen, int nChannelNO = -1, int nTimeout = 5000, int nSeq = 0);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">保存设备配置</td></tr>
<tr><td rowspan="6" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>设备序列号</td></tr>
<tr><td style="text-align:center">nCommand</td>
<td>配置命令字（详见EConfigCmd）</td></tr>
<tr><td style="text-align:center">pConfig
</td><td>配置对象字节流</td></tr>
<tr><td style="text-align:center">nChannelNO
</td><td>通道号（从0开始）</td></tr>
<tr><td style="text-align:center">nTimeout
</td><td>超时时间</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG   . EMSG_DEV_SET_CONFIG
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明
</td></tr>
</table>

## 参数配置-保存配置(Json)

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int FUN_DevSetConfig_Json(UI_HANDLE hUser, const char *szDevId, const char *szCommand, const void *pConfig, int nConfigLen, int nChannelNO = -1, int nTimeout = 5000, int nSeq = 0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">保存设备配置(Json)</td></tr>
<tr><td rowspan="6" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>设备序列号</td></tr>
<tr><td style="text-align:center">szCommand</td>
<td>配置命令字（详见EConfigCmd）</td></tr>
<tr><td style="text-align:center">pConfig
</td><td>配置对象字节流</td></tr>
<tr><td style="text-align:center">nChannelNO</td>
<td>通道号（从0开始）</td></tr>
<tr><td style="text-align:center">nTimeout
</td><td>超时时间</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG   . EMSG_DEV_SET_CONFIG_JSON
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明
</td></tr>
</table>

## 参数配置-获取设备属性

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int FUN_DevGetAttr(UI_HANDLE hUser, const char *szDevId, int nCommand, int nOutBufLen, int nChannelNO = -1, int nTimeout = 5000, int nSeq = 0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
 获取设备属性</td></tr>
<tr><td rowspan="6" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>设备序列号</td></tr>
<tr><td style="text-align:center">nCommand</td>
<td>配置命令字（详见EConfigCmd）</td></tr>
<tr><td style="text-align:center">nOutBufLen
</td><td>结果长度</td></tr>
<tr><td style="text-align:center">nChannelNO</td>
<td>通道号（从0开始）</td></tr>
<tr><td style="text-align:center">nTimeout
</td><td>超时时间</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG   . EMSG_DEV_GET_ATTR
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td>
<tr><td style="text-align:center">pData
</td><td>结果返回字节流</td>
</tr>
</table>

## 参数配置-设置设备属性

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int FUN_DevSetAttr(UI_HANDLE hUser, const char *szDevId, int nCommand, const void *pConfig, int nConfigLen, int nChannelNO = -1, int nTimeout = 5000, int nSeq = 0);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
 设置设备属性</td></tr>
<tr><td rowspan="6" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>设备序列号</td></tr>
<tr><td style="text-align:center">nCommand</td>
<td>配置命令字（详见EConfigCmd）</td></tr>
<tr><td style="text-align:center">pConfig
</td><td>配置对象字节流</td></tr>
<tr><td style="text-align:center">nChannelNO</td>
<td>通道号（从0开始）</td></tr>
<tr><td style="text-align:center">nTimeout
</td><td>超时时间</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG   . EMSG_DEV_SET_ATTR</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td>
</tr>
</table>

## 快速配置开启

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int FUN_DevStartAPConfig(UI_HANDLE hUser, int nGetRetType, const char *ssid, const char *data, const char *info, const char *ipaddr, int type, int isbroad, const unsigned char wifiMac[6], int nTimeout = 10000);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
 快速配置开启</td></tr>
<tr><td rowspan="9" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">nGetRetType</td>
<td>获取网络类型</td></tr>
<tr><td style="text-align:center">ssid</td>
<td>id</td></tr>
<tr><td style="text-align:center">data</td>
<td>数据</td></tr>
<tr><td style="text-align:center">info</td>
<td>信息</td></tr>
<tr><td style="text-align:center">ipaddr</td>
<td>IP地址</td></tr>
<tr><td style="text-align:center">type</td>
<td>类型</td></tr>
<tr><td style="text-align:center">isbroad</td>
<td>范围</td></tr>
<tr><td style="text-align:center">nTimeout</td>
<td>超时时间</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG   . EMSG_DEV_AP_CONFIG
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td>
</tr>
</table>

## 快速配置关闭

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">void FUN_DevStopAPConfig(int nStopType = 0x3);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
 快速配置关闭</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">无  </td>
<td>无  </td></tr>

<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：</td></tr>
<tr><td style="text-align:center">arg1</td>
<td>无 </td></tr>
</table>

## 设置WIFI配置

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int   FUN_DevSetWIFIConfig(UI_HANDLE hUser, const char *pCfg, int nCfgLen, const   char *szUser, const char *szPwd, int nTimeout, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
 设置WIFI配置</td></tr>
<tr><td rowspan="6" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">pCfg</td>
<td>网络配置</td></tr>
<tr><td style="text-align:center">nCfgLen</td>
<td>长度</td></tr>
<tr><td style="text-align:center">szUser</td>
<td>用户名</td></tr>
<tr><td style="text-align:center">szPwd</td>
<td>密码</td></tr>
<tr><td style="text-align:center">nTimeout</td>
<td>超时时间</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG   . EMSG_DEV_SET_WIFI_CFG</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td>
</tr>
</table>

## 设备退出登录

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int FUN_DevLogout(UI_HANDLE hUser, const char *szDevId);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
 设置退出登录</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>设备序列号</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：无</td></tr>
<tr><td style="text-align:center">arg1
</td><td>无</td>
</tr>
</table>

## 设备选项

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int FUN_DevOption(UI_HANDLE hUser, const char *szDevId, int nOptId, void *pData = NULL, int nDataLen = 0, int param1 = 0, int param2 = 0, int param3 = 0, const char *szStr = "", int seq = 0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
设备选项</td></tr>
<tr><td rowspan="9" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>设备序列号</td></tr>
<tr><td style="text-align:center">nOptId</td>
<td>选项ID</td></tr>
<tr><td style="text-align:center">pData</td>
<td>数据</td></tr>
<tr><td style="text-align:center">nDataLen</td>
<td>数据长度</td></tr>
<tr><td style="text-align:center">param1</td>
<td>参数1</td></tr>
<tr><td style="text-align:center">param2</td>
<td>参数2</td></tr>
<tr><td style="text-align:center">param3</td>
<td>参数3</td></tr>
<tr><td style="text-align:center">szStr</td>
<td>字符串</td></tr>
<tr><td rowspan="5" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG.EMSG_DEV_OPTION</td></tr>
<tr><td style="text-align:center">arg1
</td><td>>=0：成功；<0：失败，详见错误码说明</td>
</tr>
<tr><td style="text-align:center">arg3
</td><td>上面参数中选项ID</td>
</tr>
<tr><td style="text-align:center">pData
</td><td>如果有返回数据，即为设备返回的数据。注意：可能为空</td>
</tr>
</table>

### 透明串口

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int DevOption(int hUser, String szDevId, int nOptId,byte[] pData, int   nDataLen, int param1, int param2, int param3,String szStr, int seq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
透明串口提供三个操作：打开串口、写串口、关闭串口</td></tr>
<tr><td rowspan="7" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>设备序列号</td></tr>
<tr><td style="text-align:center">nOptId</td>
<td>可选：
打开：EDOPT_DEV_OPEN_TANSPORT_COM (5)
写：EDOPT_DEV_TANSPORT_COM_WRITE（8）
关闭：EDA_DEV_CLOSE_TANSPORT_COM(6)
</td></tr>
<tr><td style="text-align:center">pData</td>
<td>写串口时有效，要写的数据</td></tr>
<tr><td style="text-align:center">nDataLen</td>
<td>数据长度</td></tr>
<tr><td style="text-align:center">param1</td>
<td>为串口类型： 0:  RS232; 1: RS485</td></tr>
<tr><td style="text-align:center">param2</td>
<td>设备返回有效数据的接收者；若打开时已设，写时再设置（param2 >0 ）会覆盖之前的。（接收者句柄）
</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG.EMSG_DEV_OPTION
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>>=0：成功；<0：失败，详见错误码说明</td>
</tr>
<tr><td style="text-align:center">arg3
</td><td>参数中的nOptId</td>
</tr>
<tr><td style="background-color:#ccc;text-align:center">说明
</td><td colspan="2">设备返回数据：id: EMSG_DEV_ON_TRANSPORT_COM_DATA（5130）；arg1: 数据长度；pData: 数据内容
</td>
</tr>
</table>

## 设备设置用户数据

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int   DevSetUserData(int nType, byte[] pData);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
设备设置用户数据</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">nType</td>
<td>类型</td></tr>
<tr><td style="text-align:center">pData</td>
<td>用户数据</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：无
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>无</td>
</tr>
</table>

## 设备检查升级

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int FUN_DevCheckUpgrade(UI_HANDLE hUser, const char *szDevId, int nSeq = 0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
设备检查升级</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr style="text-align:center"><td>szDevId</td>
<td>设备序列号</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id</td>
<td>消息值：EUIMSG   . EMSG_DEV_CHECK_UPGRADE</td></tr>
<tr ><td style="text-align:center">arg1
</td><td>0：当前为最新程序，1：支持云升级，2：本地或服务器升级；<0：失败，详见错误码说明
</td></tr>
</table>

## 设备开始升级

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int FUN_DevStartUpgrade(UI_HANDLE hUser, const char *szDevId, int nType, int nSeq = 0);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
设备开始升级</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>设备序列号</td></tr>
<tr><td style="text-align:center">nType</td>
<td>升级类型</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG   . EMSG_DEV_START_UPGRADE
升级中升级文件下载情况通过消息”   EUIMSG . EMSG_CHECK_FILE_COMPLETE”处理
升级文件下载进度情况通过消息” EUIMSG .EMSG_DEV_ON_UPGRADE_PROGRESS”处理
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td>
</tr>
</table>

## 通过文件升级

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int FUN_DevStartUpgradeByFile(UI_HANDLE hUser, const char *szDevId, const char *szFileName, int nSeq = 0);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">通过文件升级</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td  style="text-align:center">szDevId
</td><td>设备序列号</td></tr>
<tr><td  style="text-align:center">sFileName</td>
<td>升级文件名称</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：EUIMSG   .</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>==0：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 设备停止升级

<table >
<tr><td style="background-color:#ccc;text-align:center;width:50px;">定义</td><td colspan="2">int FUN_DevStopUpgrade(const char *szDevId, int nSeq = 0);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">设备停止升级</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>设备序列号</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：EUIMSG   . EMSG_DEV_STOP_UPGRADE
</td></tr>
<tr><td  style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 设备检查升级—云升级

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int Fun_SysCloudUpGradeCheck (UI_HANDLE hUser, const char *szDevId, int nSeq =0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
设备检查升级—云升级</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>设备序列号</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG . SYS_CLOUDUPGRADE_CHECK
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>0：当前为最新程序，1：设备连接升级服务器升级，2：本地升级,但升级文件还没有下载下来；3：本地升级,升级文件已经下载下来了  <0：失败，详见错误码说明
</td></tr>
</table>

## 下载升级文件—云升级

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int Fun_SysCloudUpGradeDownLoad (UI_HANDLE hUser, const char *szDevId, int nSeq=0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
通过文件升级—云升级</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>设备序列号</td></tr>

<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：EUIMSG . SYS_CLOUDUPGRADE_DOWNLOAD
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明
</td></tr>
</table>

## 停止下载升级文件—云升级

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int Fun_SysStopCloudUpGradeDownLoad (UI_HANDLE hUser, const char *szDevId, int nSeq =0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
通过文件升级</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td  style="text-align:center">szDevId</td>
<td>设备序列号</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG . STOP_CLOUDUPGRADE_DOWNLOAD</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 其它方法

<table >
<tr><td style="background-color:#ccc;text-align:center;width:16%;">定义</td><td colspan="5">GetObjHandle(EOOBJECT_ID.EOOBJECT_USER_SERVER)   + SendMsg</td></tr>
<tr><td style="background-color:#ccc;text-align:center;width:16%;">描述</td><td colspan="5">使用GetObjHandle获得对象ID,通过SendMsg完成发送消息处理功能</td></tr>
<tr style="background-color:#69c;"><td style="text-align:center;width:16%;">名称+消息ID\参数</td><td>nParam1</td><td>nParam2</td><td>nParam3</td><td>szParam
</td><td>pData</td></tr>
<tr style="background-color:#ccc;"><td style="text-align:center;width:16%;">获取公开设备列表</td><td></td><td></td><td></td><td></td><td></td></tr>
<tr><td style="text-align:center;width:16%;">GetPublicDevList</td><td>详见错误码
</td><td></td><td></td><td>JSON格式</td><td></td></tr>
<tr style="background-color:#ccc;"><td style="text-align:center;width:16%;">公开设备
</td><td></td><td></td><td></td><td>设备序列号</td><td></td></tr>
<tr><td style="text-align:center;width:16%;">SetDevPublic</td><td>详见错误码</td><td></td><td></td><td></td><td></td></tr>
<tr style="background-color:#ccc;"><td style="text-align:center;width:16%;">取消公开设备
</td><td></td><td></td><td></td><td>设备序列号</td><td></td></tr>
<tr><td style="text-align:center;width:16%;">CancelDevPublic</td><td>详见错误码</td><td></td><td></td><td></td><td></td></tr>
<tr style="background-color:#ccc;"><td style="text-align:center;width:16%;">分享设备</td><td></td><td></td><td></td><td>设备序列号</td><td></td></tr>
<tr><td style="text-align:center;width:16%;">ShareDevVideo</td><td>详见错误码</td><td></td><td></td><td>媒体URL</td><td></td></tr>
<tr style="background-color:#ccc;"><td style="text-align:center;width:16%;">取消分享</td><td></td><td></td><td></td><td>设备序列号</td><td></td></tr>
<tr><td style="text-align:center;width:16%;">CancelShareDevVideo</td><td>详见错误码</td><td></td><td></td><td></td><td></td></tr>
<tr style="background-color:#ccc;"><td style="text-align:center;width:16%;">获取共享设备列表</td><td></td><td></td><td></td><td></td><td></td></tr>
<tr><td style="text-align:center;width:16%;">GetShareDevList</td><td>详见错误码</td><td></td><td></td><td>JSON格式</td><td></td></tr>
<tr style="background-color:#ccc;"><td style="text-align:center;width:16%;">设备注册</td><td></td><td></td><td></td><td></td><td></td></tr>
<tr><td style="text-align:center;width:16%;">DevRegister</td><td>详见错误码</td><td></td><td></td><td>JSON格式</td><td></td></tr>
<tr style="background-color:#ccc;"><td style="text-align:center;width:16%;">发表评论</td><td></td><td></td><td></td><td></td><td></td></tr>
<tr><td style="text-align:center;width:16%;">SendComment</td><td>详见错误码</td><td></td><td></td><td>JSON格式</td><td></td></tr>
<tr style="background-color:#ccc;"><td style="text-align:center;width:16%;">获取评论列表
</td><td></td><td></td><td></td><td></td><td></td></tr>
<tr><td style="text-align:center;width:16%;">GetCommentList</td><td>详见错误码</td><td></td><td></td><td>JSON格式</td><td></td></tr>
<tr style="background-color:#ccc;"><td style="text-align:center;width:16%;">获取视频信息
</td><td></td><td></td><td></td><td></td><td></td></tr>
<tr><td style="text-align:center;width:16%;">GetVideoInfo</td><td>详见错误码</td><td></td><td></td><td>JSON格式</td><td></td></tr>
<tr style="background-color:#ccc;"><td style="text-align:center;width:16%;">获取用户相册列表</td><td></td><td></td><td></td><td></td><td></td></tr>
<tr><td style="text-align:center;width:16%;">GetUserPhotosList</td><td>详见错误码</td><td></td><td></td><td>JSON格式</td><td></td></tr>
<tr style="background-color:#ccc;"><td style="text-align:center;width:16%;">创建用户相册
</td><td></td><td></td><td></td><td></td><td></td></tr>
<tr><td style="text-align:center;width:16%;">UpLoadPhoto</td><td>详见错误码</td><td></td><td></td><td>JSON格式</td><td></td></tr>
<tr style="background-color:#ccc;"><td style="text-align:center;width:16%;">上传图片
</td><td></td><td></td><td></td><td></td><td></td></tr>
<tr><td style="text-align:center;width:16%;">UpLoadPhoto</td><td>详见错误码</td><td></td><td></td><td>JSON格式</td><td></td></tr>
<tr style="background-color:#ccc;"><td style="text-align:center;width:16%;">编辑图片信息
</td><td></td><td></td><td></td><td></td><td></td></tr>
<tr><td style="text-align:center;width:16%;">EditPhotoInfo</td><td>详见错误码</td><td></td><td></td><td>JSON格式</td><td></td></tr>
<tr style="background-color:#ccc;"><td style="text-align:center;width:16%;">获取图片列表
</td><td></td><td></td><td></td><td></td><td></td></tr>
<tr><td style="text-align:center;width:16%;">GetPhotoList</td><td>详见错误码</td><td></td><td></td><td>JSON格式</td><td></td></tr>
<tr style="background-color:#ccc;"><td style="text-align:center;width:16%;">编辑短片视频信息</td><td></td><td></td><td></td><td></td><td></td></tr>
<tr><td style="text-align:center;width:16%;">EditShortVideoInfo</td><td>详见错误码
</td><td></td><td></td><td>JSON格式</td><td></td></tr>
<tr style="background-color:#ccc;"><td style="text-align:center;width:16%;">获取短片视频列表</td><td></td><td></td><td></td><td></td><td></td></tr>
<tr><td style="text-align:center;width:16%;">GetShortVideoList</td><td>详见错误码
</td><td></td><td></td><td>JSON格式</td><td></td></tr>
<tr style="background-color:#ccc;"><td style="text-align:center;width:16%;">上传视频至金山云</td><td></td><td></td><td></td><td></td><td></td></tr>
<tr><td style="text-align:center;width:16%;">KSSAPIUpLoadVideo</td><td>详见错误码</td><td></td><td></td><td>JSON格式</td><td></td></tr>
</table>

## 获取KSS授权信息

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">FUN_HANDLE FUN_CSSAPICommandCFS(UI_HANDLE hUser, const char *szDevId, const char *cmd, const char *param, const char *date, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">开启/关闭局域网报警</td></tr>
<tr><td rowspan="5" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">szDevId
</td><td>设备序列号</td></tr>
<tr><td style="text-align:center">cmd
</td><td>命令字符：cfs_info（获取bucket、accesskey等信息）、cfs_sig（获取签名）</td></tr>
<tr><td style="text-align:center">param
</td><td>具体请求内容json格式：
当cmd为cfs_info：
{"sigstring":"GET\n\n\n<label style="color:red">Wed,30 Sep 2015 09:08:03 GMT</label>\n/xmcfs/"}
当cdm为cfs_sig:
<pre>
{"sigstring":
<b>
 "{     

    "expiration":   "2015-01-01T12:00:00.000Z",

    "conditions": 

      [

        {"acl": "public-read"   },

        {"bucket":   "mybucket" },

        ["starts-with",   "$key", "2015/01/"]

      ]

  }"
</b>
}
</pre>
*加粗的部分需要使用base64进行编码
</td></tr>
<tr><td style="text-align:center">date</td><td>日期</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG. CSS_API_CMD_CFS</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 设置开启/关闭局域网报警

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int DevSetAttrAlarmByInt(int hUser, String szDevId, int nCommand, int nValue, int nSeq)
int DevSetAttrAlarmByInt(int hUser, String szDevId, int nCommand, int nValue, int nChannelNO, int nTimeout, int nSeq)
int DevSetAttrAlarmByString(int hUser, String szDevId, int nCommand, String sValue, int nChannelNO, int nTimeout, int nSeq)
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">开启/关闭局域网报警</td></tr>
<tr><td rowspan="6" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>设备序列号</td></tr>
<tr><td style="text-align:center">nCommand</td>
<td>属性名称：使用EDEV_ATTR.EDA_OPT_ALARM（2）</td></tr>
<tr><td style="text-align:center">nValue</td>
<td>配置信息：0为关闭 ，非0为开启（建议赋1）</td></tr>
<tr><td style="text-align:center">nChannelNO</td>
<td>暂时无用</td></tr>
<tr><td style="text-align:center">nTimeout</td>
<td>超时时间，默认5s</td></tr>
<tr><td rowspan="5" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG.DEV_SET_AT(5110)
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td></tr>
<tr><td style="text-align:center">arg2
</td><td>配置信息：0为关闭 ,1为开启</td></tr>
<tr><td style="text-align:center">arg3
</td><td>属性名称：EDEV_ATTR.EDA_OPT_ALARM（2）</td></tr>
<tr><td style="text-align:center">备注
</td><td colspan="2">Android: 建议使用第一个函数；
IOS: 使用FUN_DevSetAttr (UI_HANDLE hUser, const char *szDevId, int nCommand, const void *pConfig, int nConfigLen, int nChannelNO = -1, int nTimeout = 15000, int nSeq = 0);
注意：调用此函数前，确保已调用 DevSetAlarmListener(int hUser, int nSeq)，否则接收不到实时报警消息
</td></tr>
</table>

## 局域网报警功能

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">FUN_HANDLE FUN_DevGetAlarmState(UI_HANDLE hUser, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">局域网报警功能,设置实时报警消息的接收者,所有设备的报警信息均由此接收,设置一次即可<label style="color:red">注调用此接口前必须先调用一次DevSetAttrAlarm开启局域网报警功能
</label></td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center"> </td>
<td></td></tr>
<tr><td rowspan="5" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG .DEV_GET_LAN_ALARM（5132）</td></tr>
<tr><td style="text-align:center">arg1
</td><td>>0：成功（报警信息长度）；<=0：失败，详见错误码说明</td></tr>
<tr><td style="text-align:center">pData
</td><td>返回报警信息字节流(json 格式)</td></tr>
<tr><td style="text-align:center">str
</td><td>设备序列号或ip</td></tr>
</table>

## 通用命令接口

<table >
<tr><td style="background-color:#ccc;text-align:center;width:20px;">定义</td><td colspan="2">int   DevCmdGeneral(int hUser, String szDevId,int nCmdReq, String szCmd, int   nRetSize, int nTimeout,byte[] pInParam, int nCmdRes, int nSeq);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">本接口为通用接口，大多数的命令都可调用此接口实现</td></tr>
<tr><td rowspan="8" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>序列号</td></tr>
<tr><td style="text-align:center">nCmdReq</td>
<td>命令ID</td></tr>
<tr><td style="text-align:center">szCmd</td>
<td>命令字符串，不要为空。没有该字段时，随便赋一字符串</td></tr>
<tr><td style="text-align:center">nRetSize</td>
<td>pInParam为json格式内容时，赋0；为字符串时，赋1024即可</td></tr>
<tr><td style="text-align:center">nTimeout</td>
<td>超时时间(单位: ms)，一般5000~8000即可</td></tr>
<tr><td style="text-align:center">pInParam</td>
<td>请求信息</td></tr>
<tr><td style="text-align:center">nCmdRes</td>
<td>暂时无用</td></tr>
<tr><td rowspan="7" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG   . DEV_CMD_EN</td></tr>
<tr><td style="text-align:center">arg1
</td><td>>=0：成功；<0：失败，详见错误码说明</td></tr>
<tr><td style="text-align:center">arg2
</td><td>返回数据的长度</td></tr>
<tr><td style="text-align:center">arg3
</td><td>命令ID，即参数中的命令ID</td></tr>
<tr><td style="text-align:center">str
</td><td>命令字符串, 即参数中的命令字符串</td></tr>
<tr><td style="text-align:center">pData
</td><td>返回的字节流</td></tr>
</table>

### 录像日历查询

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int FUN_DevCmdGeneral(UI_HANDLE hUser, const char *szDevId, int nCmdReq, const char *szCmd, int nRetSize, int nTimeout, char *pInParam = NULL, int nInParamLen = 0, int nCmdRes = -1, int nSeq = 0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">录像日历查询</td></tr>
<tr><td rowspan="8" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>序列号</td></tr>
<tr><td style="text-align:center">nCmdReq</td>
<td>命令ID:
请求：FILESEARCH_CALENDAR_REQ   = 1446, 
反馈：FILESEARCH_CALENDAR_RSP = 1447,
</td></tr>
<tr><td style="text-align:center">szCmd</td>
<td>操作命令</td></tr>
<tr><td style="text-align:center">nRetSize</td>
<td>0</td></tr>
<tr><td style="text-align:center">nTimeout</td>
<td>超时时间(单位: ms)</td></tr>
<tr><td style="text-align:center">pInParam</td>
<td>请求信息</td></tr>
<tr><td style="text-align:center">nCmdRes</td>
<td>暂时无用</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG   .DEV_CMD_EN
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>>=0：成功；  <0：失败，详见错误码说明</td></tr>
<tr><td style="text-align:center">备注
</td><td colspan="2">其它信息可参考4.35</td></tr>
</table>

### 透明传输

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int   DevCmdGeneral(int hUser, String szDevId,int nCmdReq, String szCmd, int   nRetSize, int nTimeout,byte[] pInParam, int nCmdRes, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">数据透明传输</td></tr>
<tr><td rowspan="8" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>序列号</td></tr>
<tr><td style="text-align:center">nCmdReq</td>
<td>命令ID</td></tr>
<tr><td style="text-align:center">szCmd</td>
<td>示例“hello”</td></tr>
<tr><td style="text-align:center">nRetSize</td>
<td>1024</td></tr>
<tr><td style="text-align:center">nTimeout</td>
<td>超时时间(单位: ms),建议5000ms</td></tr>
<tr><td style="text-align:center">pInParam</td>
<td>数据信息</td></tr>
<tr><td style="text-align:center">nCmdRes</td>
<td>暂时无用</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG.DEV_CMD_EN
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>>=0：成功；   <0：失败，详见错误码说明</td></tr>
<tr><td style="text-align:center">备注
</td><td colspan="2">其它信息可参考4.35</td></tr>
</table>

### 查询月份录像或图片信息

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int  DevCmdGeneral(int hUser, String szDevId,int   nCmdReq, String szCmd, int   nRetSize, int nTimeout,byte[] pInParam, int   nCmdRes, int nSeq)
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
查询一个月中的录像或图片信息</td></tr>
<tr><td rowspan="8" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>序列号</td></tr>
<tr><td style="text-align:center">nCmdReq</td>
<td>1446</td></tr>
<tr><td style="text-align:center">szCmd</td>
<td>“OPSCalendar”</td></tr>
<tr><td style="text-align:center">nRetSize</td>
<td>0</td></tr>
<tr><td style="text-align:center">nTimeout</td>
<td>超时时间(单位: ms),建议5000ms</td></tr>
<tr><td style="text-align:center">pInParam</td>
<td>
<pre>
{
    "Name":   "OPSCalendar",
      "OPSCalendar": {
        "Event":   "*",
          "FileType": "h264",     //录像为“h264"，图片为“jpg”
        "Month":   8,
        "Rev":   "",
        "Year":   2016
    },
    "SessionID":   "0x00000001"

}
</pre></td></tr>
<tr><td style="text-align:center">nCmdRes</td>
<td>暂时无用</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG.DEV_CMD_EN
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>>=0：成功； <0：失败，详见错误码说明</td></tr>
<tr><td style="text-align:center">pData
</td><td colspan="2">
<pre>
{
      "Name": "OPSCalendar",
      "OPSCalendar": {
        "Mask": 0
      },
      "Ret": 100,
      "SessionID": "0x1c"
}
</pre>
说明：Mask为一个二进制32位的数，从第一位开始判断，0：没有录像，1：有录像，直到整个月判断完毕
</td></tr>
</table>

## 查询设备缩略图

<table >
<tr><td style="background-color:#ccc;text-align:center;width:20px;">定义</td><td colspan="2">int FUN_DevSearchPic(UI_HANDLE hUser, const char *szDevId, int nCmdReq, int nRetSize, int nTimeout, char *pInParam, int nInParamLen, int nCount, int nCmdRes = -1, const char * szFileName = NULL, int nSeq = 0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
查询设备缩略图  （该接口只适用于部分设备）</td></tr>
<tr><td rowspan="9" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>序列号</td></tr>
<tr><td style="text-align:center">nCmdReq</td>
<td>命令ID:
请求：COMPRESS_PICTURE_REQ   = 1448, 
反馈：COMPRESS_PICTURE_RSP = 1449,
</td></tr>
<tr><td style="text-align:center">nRetSize</td>
<td>返回大小</td></tr>
<tr><td style="text-align:center">nTimeout</td>
<td>超时</td></tr>
<tr><td style="text-align:center">pInParam</td>
<td>请求信息</td></tr>
<tr><td style="text-align:center">nCount</td>
<td>最大下载量</td></tr>
<tr><td style="text-align:center">nCmdRes</td>
<td>命令匹配：
-1：不匹配
其他：匹配
</td></tr>
<tr><td style="text-align:center">szFileName</td>
<td>图片文件名</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG   . DEV_SEARCH_PIC
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 保存设备实时流

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int DevSaveRealTimeStream (int hUser, String szDevId, int nChannel,   int nStreamType, String szFileName, int nSeq)</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
开始保存实时流</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">nChannel</td>
<td>通道号</td></tr>
<tr><td style="text-align:center">nStreamType</td>
<td>码流类型</td></tr>
<tr><td style="text-align:center">szFileName
</td><td>保存的文件名（绝对路径），如xx/xx/xx.mp4</td></tr>
<tr><td rowspan="5" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td rowspan="3" style="text-align:center">id
</td><td>START_PLAY(5501),打开视频</td></tr>
<tr><td>EMSG_ON_MediaData_Save（5528，新加），开始保存数据</td></tr>
<tr><td>EMSG_MediaData_Save_Process（5529， 新加），已保存数据的大小，每2s发送一次
</td></tr>
<tr><td style="text-align:center">arg1
</td><td><0：失败，详见错误码说明；>=0：成功，在id = EMSG_MediaData_Save_Process时，为保存数据的大小</td></tr>
<tr><td style="background-color:#ccc;text-align:center">说明</td>
<td colspan="2">如果返回失败，不需调用DevCloseRealTimeStream</td></tr>
</table>

## 停止保存实时流

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int DevCloseRealTimeStream(<label
style="color:red">int</label> <label style="color:#f63">hSaveObj<label>)

</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
 停止保存实时流</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">hSaveObj</td>
<td>DevSaveRealTimeStream的返回值</td></tr>
</table>
