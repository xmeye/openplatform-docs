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
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int   DevGetChnName(int hUser, String devId, String szUser, String password,   int  nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">获取通道名称</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">devId</td><td>设备序列号</td></tr>
<tr><td style="text-align:center">szUser
</td><td>设备登录用户名；为空时，使用默认用户名（默认为添加设备时的用户名）</td></tr>
<tr><td style="text-align:center">password</td><td>设备登录密码；</td></tr>
<tr><td rowspan="7" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id</td>
<td>消息值：EUIMSG  . DEV_GET_CHN_NAME</td></tr>
<tr><td style="text-align:center">arg1
</td><td>>0：通道个数；<0：失败，详见错误码说明</td></tr>
<tr><td style="text-align:center">arg2
</td><td>Net类型：0:p2p连接，1转发模式 2:IP地址直连</td></tr>
<tr><td style="text-align:center">arg1
</td><td>"ChannelTitle"信息大小</td></tr>
<tr><td style="text-align:center">arg1
</td><td>设备id</td></tr>
<tr><td style="text-align:center">pData
</td><td>指向SDK_ChannelNameConfigAll对象字节流</td></tr>
</table>

## 查询录像

<table >
<tr><td style="background-color:#ccc;text-align:center;width:100px;">定义</td><td colspan="2">int  DevFindFile(int hUser, String devId, byte   []pH264_DVR_FINDINFO, int  nMaxCount,   int  waittime, int  nSeq);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">查询录像</td></tr>
<tr><td rowspan="5" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">devId</td>
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
</td><td>消息值：EUIMSG   . DEV_FIND_FILE</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>>0：结果条数；<0：失败，详见错误码说明</td></tr>
<tr><td  style="text-align:center">pData</td>
<td>指向H264_DVR_FILE_DATA对象数组字节流</td></tr>
</table>

## 查询录像(按时间)

<table >
<tr><td style="background-color:#ccc;text-align:center;width:50px;">定义</td><td colspan="2">int  DevFindFileByTime (int hUser, String devId,   byte []pSDK_SearchByTime, int    waittime, int  nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">查询录像
</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">devId</td>
<td>设备序列号</td></tr>
<tr><td style="text-align:center">pSDK_SearchByTime
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
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int   DevDowonLoadByFile(int hUser, String szDevId, byte []pH264_DVR_FILE_DATA,   String szFileName, int nSeq)</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">按文件下载录像</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">devId</td>
<td>设备序列号</td></tr>
<tr><td style="text-align:center">pH264_DVR_FILE_DATA
</td><td>查询条件。H264_DVR_FILE_DATA对象字节流</td></tr>
<tr><td  style="text-align:center">szFileName</td><td>保存文件路径+文件名</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG  . ON_FILE_DOWNLOAD:下载函数调用结果<br>
EUIMSG  . ON_FILE_DLD_COMPLETE:下载完成消息回调<br>
EUIMSG  . ON_FILE_DLD_POS:下载进度消息回调<br>
</td></tr>
<tr><td style="text-align:center">arg1
</td><td><0：失败，详见错误码说明</td></tr>
</table>

## 按时间录像下载

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int   DevDowonLoadByTime(int hUser, String szDevId, byte []pH264_DVR_FINDINFO,   String szFileName, int nSeq)</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">按文件下载录像</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">devIds</td>
<td>设备序列号</td></tr>
<tr><td style="text-align:center">pH264_DVR_FINDINFO
</td><td>查询条件。H264_DVR_FINDINFO对象字节流</td></tr>
<tr><td  style="text-align:center">szFileName</td><td>保存文件路径+文件名</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：EUIMSG . ON_FILE_DOWNLOAD:下载函数调用结果<br>
EUIMSG  .  ON_FILE_DLD_COMPLETE:下载完成消息回调<br>
EUIMSG  .  ON_FILE_DLD_POS:下载进度消息回调<br>
</td></tr>
<tr><td style="text-align:center">arg1
</td><td><0：失败，详见错误码说明</td></tr>
</table>

## 图像列表下载

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int DevImgListDowonLoadM(int userId, String devId, byte[] pData, String fileName, int chnId, String fileTypeMask, int seq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">图像列表下载</td></tr>
<tr><td rowspan="6" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">devId</td>
<td>设备序列号</td></tr>
<tr><td style="text-align:center">pData</td>
<td>图片下载信息</td></tr>
<tr><td style="text-align:center">fileName</td>
<td>文件名</td></tr>
<tr><td style="text-align:center">chnId
</td><td>通道号</td></tr>
<tr><td  style="text-align:center">fileTypeMask</td><td>掩码（下载序列）</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：EUIMSG . ON_FILE_DOWNLOAD:下载函数调用结果<br>
EUIMSG  .  ON_FILE_DLD_COMPLETE:下载完成消息回调<br>
EUIMSG  .  ON_FILE_DLD_POS:下载进度消息回调<br>
</td></tr>
<tr><td style="text-align:center">arg1
</td><td><0：失败，详见错误码说明</td></tr>
</table>

## 设备停止下载

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int   DevStopDownLoad(int hDownload);</td></tr>
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
</td><td>消息值：EUIMSG . Stop_DownLoad . 5530</td></tr>
<tr><td style="text-align:center">arg1
</td><td><0：失败，详见错误码说明</td></tr>
</table>

## 云台控制

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int   DevPTZControl(int hUser, String devId, int nChnIndex, int nPTZCommand, int   bStop, int nSpeed, int nSeq)</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">云台控制
</td></tr>
<tr><td rowspan="6" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">devId</td><td>设备序列号</td></tr>
<tr><td style="text-align:center">nChnIndex</td>
<td>通道号（从0开始）</td></tr>
<tr><td style="text-align:center">nPTZCommand</td>
<td>云台命令（详见EPTZCMD）</td></tr>
<tr><td style="text-align:center">bStop</td>
<td>0:stop 1:start</td></tr>
<tr><td style="text-align:center">nSpeed</td>
<td>默认值4</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id</td>
<td>消息值：EUIMSG  . DEV_PTZ_CONTROL</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td></tr>
<tr><td style="text-align:center">pData
</td><td>指向结果对象字节流</td></tr>
</table>

## 语音对讲-开始

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int   DevStarTalk(int hUser, String devId, int nSeq);</td></tr>
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
</td><td>消息值：EUIMSG . DEV_START_TALK
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 语音对讲-停止

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">void   DevStopTalk(int hTalker);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">停止语音对讲</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">hTalker</td>
<td>语音对讲对象操作句柄</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG  . DEV_STOP_TALK</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 语音对讲-发送数据

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int DevSendTalkData(String szDevId, byte[] pPCMData, int nDataLen);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">发送语音对讲客户端的数据</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>设备序列号</td></tr>
<tr><td style="text-align:center">pPCMData</td>
<td>PCM格式数据</td></tr>
<tr><td style="text-align:center">nDataLen</td>
<td>PCM格式数据大小</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG  . DEV_SEND_MEDIA_DATA</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 设备搜索

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int   DevSearchDevice(int hUser, int nTimeout, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">设备搜索
</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">nTimeout</td>
<td>超时时间</td></tr>
<tr><td rowspan="5" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG   . EMSG_DEV_SEARCH_DEVICES
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td></tr>
<tr><td style="text-align:center">arg2
</td><td>消息长度</td></tr>
<tr><td style="text-align:center">pData
</td><td>指向结果对象字节流SDK_CONFIG_NET_COMMON_V2</td></tr>
</table>


## 参数配置-获取配置(Json)

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int DevGetConfigByJson(int   hUser, String szDevId,String szCommand,int nOutBufLen,int nChannelNO,int   nTimeout,int nSeq);</td></tr>
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
<tr><td rowspan="6" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG . DEV_GET_JSON 5128
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td></tr>
<tr><td style="text-align:center">arg2
</td><td>通道号（从0开始）；配置命令字是"SystemInfo"的时候->NetType; //0:p2p连接，1转发模式 2:IP地址直连</td></tr>
<tr><td style="text-align:center">str
</td><td>配置命令字</td></tr>
<tr><td style="text-align:center">pData
</td><td>指向结果对象字节流</td></tr>
</table>

## 参数配置-获取配置(Json2)

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int DevGetConfigJson (int hUser, String szDevId, String szCommand, String pConfig, int nChannelNO, int nCmdReq, int nCmdRes, int nTimeout, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">获取设备配置(Json)</td></tr>
<tr><td rowspan="8" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr style="text-align:center"><td>szDevId
</td><td>设备序列号</td></tr>
<tr style="text-align:center"><td>szCommand
</td><td>配置命令字（详见EConfigCmd）</td></tr>
<tr style="text-align:center"><td>pConfig
</td><td>配置对象字节流</td></tr>
<tr style="text-align:center"><td>nChannelNO
</td><td>通道号（从0开始）</td></tr>
<tr style="text-align:center"><td>nCmdReq
</td><td>命令ID</td></tr>
<tr style="text-align:center"><td>nCmdRes
</td><td>暂时未使用</td></tr>
<tr style="text-align:center"><td>nTimeout
</td><td>超时时间</td></tr>
<tr><td rowspan="6" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG . DEV_GET_JSON 5128
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td></tr>
<tr><td style="text-align:center">arg2
</td><td>通道号（从0开始）；配置命令字是"SystemInfo"的时候->NetType; //0:p2p连接，1转发模式 2:IP地址直连</td></tr>
<tr><td style="text-align:center">str
</td><td>配置命令字</td></tr>
<tr><td style="text-align:center">pData
</td><td>指向结果对象字节流</td></tr>
</table>

## 参数配置-保存配置(Json)

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int DevSetConfigByJson(int   hUser, String szDevId,String szCommand,String pConfig,int nChannelNO,int   nTimeout,int   nSeq);</td></tr>
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
<tr><td rowspan="6" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG   . DEV_SET_JSON 5129
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明
</td></tr>
<tr><td style="text-align:center">arg2
</td><td>通道号（从0开始）；配置命令字是"SystemInfo"的时候->NetType; //0:p2p连接，1转发模式 2:IP地址直连
</td></tr>
<tr><td style="text-align:center">str
</td><td>配置命令字
</td></tr>
<tr><td style="text-align:center">pData
</td><td>指向结果对象字节流
</td></tr>
</table>

## 参数配置-保存配置(Json2)

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int DevSetConfigJson(int hUser, String szDevId, String szCommand, String pConfig, int nChannelNO, int nCmdReq, int nCmdRes, int nTimeout, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">获取设备配置(Json)</td></tr>
<tr><td rowspan="8" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr style="text-align:center"><td>szDevId
</td><td>设备序列号</td></tr>
<tr style="text-align:center"><td>szCommand
</td><td>配置命令字（详见EConfigCmd）</td></tr>
<tr style="text-align:center"><td>pConfig
</td><td>配置对象字节流</td></tr>
<tr style="text-align:center"><td>nChannelNO
</td><td>通道号（从0开始）</td></tr>
<tr style="text-align:center"><td>nCmdReq
</td><td>命令ID</td></tr>
<tr style="text-align:center"><td>nCmdRes
</td><td>暂时未使用</td></tr>
<tr style="text-align:center"><td>nTimeout
</td><td>超时时间</td></tr>
<tr><td rowspan="6" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG . DEV_SET_JSON 5129
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td></tr>
<tr><td style="text-align:center">arg2
</td><td>通道号（从0开始）；配置命令字是"SystemInfo"的时候->NetType; //0:p2p连接，1转发模式 2:IP地址直连</td></tr>
<tr><td style="text-align:center">str
</td><td>配置命令字</td></tr>
<tr><td style="text-align:center">pData
</td><td>指向结果对象字节流</td></tr>
</table>

## 参数配置-获取设备属性

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int   DevGetAttr(int hUser, String devId, int nCommand, int nOutBufLen, int   nChannelNO, int nTimeout, int nSeq);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
 获取设备属性</td></tr>
<tr><td rowspan="6" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">devId</td>
<td>设备序列号</td></tr>
<tr><td style="text-align:center">nCommand</td>
<td>配置命令字（详见EConfigCmd/EDEV_ATTR）</td></tr>
<tr><td style="text-align:center">nOutBufLen
</td><td>结果长度</td></tr>
<tr><td style="text-align:center">nChannelNO</td>
<td>通道号（从0开始）</td></tr>
<tr><td style="text-align:center">nTimeout
</td><td>超时时间</td></tr>
<tr><td rowspan="6" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG   . DEV_GET_ATTR
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td>
<tr><td style="text-align:center">arg2
</td><td>NetType; //0:p2p连接，1转发模式 2:IP地址直连</td>
<tr><td style="text-align:center">arg1
</td><td>arg1 < 0的时候返回错误信息，否则返回设备序列号</td>
<tr><td style="text-align:center">pData
</td><td>结果返回字节流</td>
</tr>
</table>

## 参数配置-设置设备属性

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int   DevSetAttr(int hUser, String devId, int nCommand, byte []pConfig, int   nChannelNO, int nTimeout, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
 设置设备属性--EDA_OPT_ALARM（EDEV_ATTR）现在只能配置报警功能</td></tr>
<tr><td rowspan="6" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">devId</td>
<td>设备序列号</td></tr>
<tr><td style="text-align:center">nCommand</td>
<td>配置命令字（详见EConfigCmd/EDEV_ATTR）</td></tr>
<tr><td style="text-align:center">pConfig
</td><td>配置对象字节流</td></tr>
<tr><td style="text-align:center">nChannelNO</td>
<td>通道号（从0开始）</td></tr>
<tr><td style="text-align:center">nTimeout
</td><td>超时时间</td></tr>
<tr><td rowspan="6" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG   . DEV_SET_ATTR</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td>
<tr><td style="text-align:center">arg2
</td><td>控制开关 本地报警推送0:开启, 1:关闭</td>
<tr><td style="text-align:center">str
</td><td>配置命令字（详见EDEV_ATTR）</td>
<tr><td style="text-align:center">pData
</td><td>arg1 < 0的时候返回错误信息</td>
</tr>
</table>

## 快速配置开启

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int   DevStartAPConfig(int hUser, int nGetRetType,String ssid, String data, String   info, String ipaddr, int type,int   isbroad, String mac,  int nTimeout);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
 快速配置开启</td></tr>
<tr><td rowspan="10" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">nGetRetType</td>
<td>获取网络类型1:外网;2:内网 0x3:一起</td></tr>
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
<tr><td style="text-align:center">mac</td>
<td>mac：以“：”分隔的16进制形式</td></tr>
<tr><td style="text-align:center">nTimeout</td>
<td>超时时间</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG   . EMSG_DEV_AP_CONFIG
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td>
</tr>
<tr><td style="text-align:center">pData
</td><td>网络设置，指向SDK_CONFIG_NET_COMMON_V2字节流</td>
</tr>
</table>

## 快速配置关闭

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">void   DevStopAPConfig();</td></tr>
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

## WIFI配置-手机APP通过局域网登录时

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">	int DevStartWifiConfig(int hUser, String szDevId, String szSSID, String szPassword, int nTimeout);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
WIFI配置配置接口（这种方式需要可以登录设备，通过协议把SSID和密码发给设备<br>
手机APP通过局域网登录时（过程：调用接口->回调返回结果）
</td></tr>
<tr><td rowspan="5" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>序列号</td></tr>
<tr><td style="text-align:center">szSSID</td>
<td>SSID</td></tr>
<tr><td style="text-align:center">szPassword</td>
<td>密码</td></tr>
<tr><td style="text-align:center">nTimeout</td>
<td>超时时间,默认值120s</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：消息值：EUIMSG . DEV_SET_WIFI_CFG</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td>
</tr>
</table>

## WIFI配置-手机APP通过设备热点连接时

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">	int DevStartWifiConfig(int hUser, String szDevId, String szSSID, String szPassword, int nTimeout);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
手机APP通过设备热点连接时（过程：手机连接设备热点->调用接口->返回1->切换到家里的WIFI->返回结果）/td></tr>
<tr><td rowspan="5" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>序列号</td></tr>
<tr><td style="text-align:center">szSSID</td>
<td>SSID</td></tr>
<tr><td style="text-align:center">szPassword</td>
<td>密码</td></tr>
<tr><td style="text-align:center">nTimeout</td>
<td>超时时间,默认值120s</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：消息值：EUIMSG . DEV_SET_WIFI_CFG</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td>
</tr>
</table>

## 结束WIFI配置

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int DevStopWifiConfig();</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
 结束WIFI配置</td></tr>
</table>


## 设备登录

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int DevLogin(int hUser, String szDevId, String szUser, String szPwd, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
 设备登录，如果本地数据库中没有此设备，则创建</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>设备序列号</td></tr>
<tr><td style="text-align:center">szUser</td>
<td>用户名</td></tr>
<tr><td style="text-align:center">szPwd</td>
<td>密码</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG . DEV_LOGIN 5139</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td>
<tr><td style="text-align:center">str
</td><td>正确时返回””，错误的时候返回错误信息</td>
</tr>
</table>

## 设备退出登录

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int   DevLogout(int hUser, String szDevId, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
 设备退出登录</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>设备序列号</td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>==0：成功；<0：失败，详见错误码说明
</td><tr>
</table>

## 设备选项

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int   DevOption(int hUser, String szDevId, int nOptId,byte[] pData, int nDataLen,   int param1, int param2, int param3,String szStr, int seq);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
设备选项</td></tr>
<tr><td rowspan="9" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>设备序列号</td></tr>
<tr><td style="text-align:center">nOptId</td>
<td>选项ID，详见FunSDK; enum EDEV_OPTERATE</td></tr>
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
</td><td>消息值：EUIMSG.DEV_OPTION</td></tr>
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
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int   DevCheckUpgrade(int hUser, String szDevId, int nSeq);
</td></tr>
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
</td><td>0：当前为最新程序<br>1：支持云升级<br>2：本地或服务器升级<br><0：失败，详见错误码说明
</td></tr>
</table>

## 子设备检查升级

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int DevCheckUpgradeEx(int hUser, String szDevId, byte[] pSDK_SubDevInfo, int nSeq);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
智联中心检查子设备升级</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr style="text-align:center"><td>szDevId</td>
<td>设备序列号</td></tr>
<tr style="text-align:center"><td>pSDK_SubDevInfo</td>
<td>子设备信息，检查更新时，Type可选， 默认“IPC”，其它需赋值；<br>开始升级时，暂时只需要SN、 SoftWareVer，其它可选</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id</td>
<td>消息值：EUIMSG   . DEV_CHECK_UPGRADE</td></tr>
<tr ><td style="text-align:center">arg1
</td><td>0：当前为最新程序<br>1：支持云升级<br>2：本地或服务器升级<br><0：失败，详见错误码说明
</td></tr>
</table>

## 设备开始升级

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int   DevStartUpgrade(int hUser, String szDevId, int nType, int nSeq);
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
</td><td>消息值：EUIMSG  . DEV_START_UPGRADE<br>
升级中升级文件下载情况通过消息”   EUIMSG . CHECK_FILE_COMPLETE”处理<br>
升级文件下载进度情况通过消息” EUIMSG . DEV_ON_UPGRADE_PROGRESS”处理
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td>
</tr>
</table>

## 子设备开始升级

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int DevStartUpgradeEx(int hUser, String szDevId, byte[] pSDK_SubDevInfo, int nType, int nSeq);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
子设备开始升级-智联中心子设备升级接口</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>设备序列号</td></tr>
<tr><td style="text-align:center">pSDK_SubDevInfo</td>
<td>子设备信息， 检查更新时，Type可选， 默认“IPC”，其它需赋值；<br>开始升级时，暂时只需要SN、 SoftWareVer，其它可选</td></tr>
<tr><td style="text-align:center">nType</td>
<td>升级类型</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG  . DEV_START_UPGRADE<br>
升级中升级文件下载情况通过消息”   EUIMSG . CHECK_FILE_COMPLETE”处理<br>
升级文件下载进度情况通过消息” EUIMSG . DEV_ON_UPGRADE_PROGRESS”处理
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td>
</tr>
</table>

## 通过文件升级

<table >
<tr><td style="background-color:#ccc;text-align:center;width:100px;">定义</td><td colspan="2">int   DevStartUpgradeByFile(int hUser, String szDevId, String sFileName, int nSeq);</td></tr>
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
</td><td>消息值：EUIMSG 同上  .</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>==0：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 子设备通过文件升级

<table >
<tr><td style="background-color:#ccc;text-align:center;width:100px;">定义</td><td colspan="2">int DevStartUpgradeByFileEx(UI_HANDLE hUser, String szDevId, String szSubDevId, String szFileName, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">子设备通过文件升级-智联中心子设备本地升级接口</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td  style="text-align:center">szDevId
</td><td>设备序列号</td></tr>
<tr><td  style="text-align:center">szSubDevId
</td><td>子设备序列号</td></tr>
<tr><td  style="text-align:center">szFileName</td>
<td>升级文件名称</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：EUIMSG 同上  .</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>==0：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 设备停止升级

<table >
<tr><td style="background-color:#ccc;text-align:center;width:50px;">定义</td><td colspan="2">int   DevStopUpgrade(int hUser, String szDevId, int nSeq);
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
</td><td>消息值：EUIMSG  . DEV_STOP_UPGRADE
</td></tr>
<tr><td  style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 设备检查升级—云升级

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int SysCloudUpGradeCheck (int hUser, String szDevId, int nSeq);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
设备检查升级—云升级</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>设备序列号</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG . SYS_CLOUDUPGRADE_CHECK
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>0：当前为最新程序，1：设备连接升级服务器升级，2：本地升级,但升级文件还没有下载下来；3：本地升级,升级文件已经下载下来了  <0：失败，详见错误码说明
</td></tr>
<tr><td style="text-align:center">str
</td><td>日志信息，新版本的日志信息也要返回
</td></tr>
</table>

## 下载升级文件—云升级

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int SysCloudUpGradeDownLoad (int hUser, String szDevId, int nSeq);
</td></tr>
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
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int SysStopCloudUpGradeDownLoad (int hUser, String szDevId, int nSeq);
</td></tr>
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

## 获取推荐码流值

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int GetDefaultBitRate(int nEncType, int iResolution,int iQuality, int iGOP, int nFrameRate, int nVideoStd, int nDevType);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
获取推荐码流值</td></tr>
<tr><td rowspan="8" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td  style="text-align:center">szDevId</td>
<td>编码方式 详见SDK_CAPTURE_COMP_t 7:h264 8:H265</td></tr>
<tr><td  style="text-align:center">szDevId</td>
<td>分辨率 详见SDK_CAPTURE_SIZE_t</td></tr>
<tr><td  style="text-align:center">szDevId</td>
<td>图像质量 1~6</td></tr>
<tr><td  style="text-align:center">szDevId</td>
<td>帧之间的间隔时间，1-12</td></tr>
<tr><td  style="text-align:center">szDevId</td>
<td>帧率</td></tr>
<tr><td  style="text-align:center">szDevId</td>
<td>视频制式 0 : P 1 : N</td></tr><tr><td  style="text-align:center">szDevId</td>
<td>设备类型 详见EFUN_DEV_TYPE</td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>获取到的推荐码流值
</td><tr>
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
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int   CSSAPICommandCFS(int hUser, String szDevId, String cmd, String param, String   date, int nSeq);</td></tr>
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
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">iint DevSetAttrAlarm(int hUser, String szDevId, int nCommand, byte[] pConfig,int nChannelNO, int nTimeout, int nSeq);
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
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int DevSetAlarmListener(int hUser, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">局域网报警功能,设置实时报警消息的接收者,所有设备的报警信息均由此接收,设置一次即可<br>设置本地报警接受者,不再使用FUN_DevGetAlarmState(此名字含义不明显)， 使用FUN_DevSetAlarmListener
注调用此接口前必须先调用一次DevSetAttrAlarm开启局域网报警功能
</td></tr>
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

### 1、录像日历查询

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int   DevCmdGeneral(int hUser, String szDevId,int nCmdReq, String szCmd, int   nRetSize, int nTimeout,byte[] pInParam, int nCmdRes, int nSeq);
</td></tr>
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

### 2、透明传输

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

### 3、查询月份录像或图片信息

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int DevCmdGeneral(int hUser, String szDevId,int nCmdReq, String szCmd, int nRetSize, int nTimeout,byte[] pInParam, int nCmdRes, int nSeq)</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">查询一个月中的录像或图片信息</td></tr>
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
{
    "Name":   "OPSCalendar",
      "OPSCalendar": {
        "Event":   "*",
          "FileType": "h264", //录像为“h264"，图片为“jpg”
        "Month":   8,
        "Rev":   "",
        "Year":   2016
    },
    "SessionID":   "0x00000001"
}
</td></tr>
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
说明：Mask为一个二进制32位的数，从第一位开始判断:
<br/>
0：没有录像;
1：有录像，直到整个月判断完毕
</td></tr>
</table>

## 查询设备缩略图

<table >
<tr><td style="background-color:#ccc;text-align:center;width:20px;">定义</td><td colspan="2">int   DevSearchPicture(int hUser, String szDevId,int nCmdReq, int nRetSize, int   nTimeout,byte[] pInParam, int   nCount, int nCmdRes, String szFileName, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
查询、下载设备缩略图  （该接口只适用于部分设备）</td></tr>
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

## 停止查询缩略图
<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int StopDevSearchPic (int hUser, String szDevId, int nSeq);

</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
 停止查询，下载缩略图</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>设备序列号</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG   . DEV_SEARCH_PIC_STOP
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>无</td></tr>
</table>

## 录像缩略图下载-单张图片

<table >
<tr><td style="background-color:#ccc;text-align:center;width:20px;">定义</td><td colspan="2">int DownloadRecordBImage(int hUser, String szDevId, int nChannel, int nTime, String szFileName, int nTypeMask, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
录像缩略图下载（最新固件才会支持2017.07.19）</td></tr>
<tr><td rowspan="7" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>序列号</td></tr>
<tr><td style="text-align:center">nChannel</td>
<td>设备能力级-详见EDEV_STREM_TYPE
</td></tr>
<tr><td style="text-align:center">nTime</td>
<td>图片时间点</td></tr>
<tr><td style="text-align:center">szFileName</td>
<td>文件存放路径</td></tr>
<tr><td style="text-align:center">nTypeMask</td>
<td>掩码  默认-1全部类型</td></tr>
<tr><td style="text-align:center">szFileName</td>
<td>图片文件名</td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>nDownId：可用于FUN_CancelDownloadRecordImage，取消下载用
</td><tr>
<tr><td rowspan="6" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：异步消息EUIMSG . DOWN_RECODE_BPIC_START =  5534,    //录像缩略图下载开始<br>DOWN_RECODE_BPIC_FILE  =  5535,    //录像缩略图下载--文件下载结果返回<br>DOWN_RECODE_BPIC_COMPLETE =  5536, //录像缩略图下载-下载完成（结束）
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td></tr>
<tr><td style="text-align:center">arg2
</td><td>图片总个数</td></tr>
<tr><td style="text-align:center">arg3
</td><td>下载个数</td></tr>
<tr><td style="text-align:center">str
</td><td>图片名称</td></tr>
</table>

## 录像缩略图下载-多张图片

<table >
<tr><td style="background-color:#ccc;text-align:center;width:20px;">定义</td><td colspan="2">int DownloadRecordBImages(int hUser, String szDevId, int nChannel, int nStartTime, int nEndTime, String szFilePath, int nTypeMask, int nSeq, int nMaxPicCount);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
录像缩略图下载（最新固件才会支持2017.07.19）</td></tr>
<tr><td rowspan="9" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>序列号</td></tr>
<tr><td style="text-align:center">nChannel</td>
<td>设备能力级-详见EDEV_STREM_TYPE
</td></tr>
<tr><td style="text-align:center">nStartTime</td>
<td>开始时间</td></tr>
<tr><td style="text-align:center">nEndTime</td>
<td>结束时间</td></tr>
<tr><td style="text-align:center">szFileName</td>
<td>文件存放路径</td></tr>
<tr><td style="text-align:center">nTypeMask</td>
<td>掩码  默认-1全部类型</td></tr>
<tr><td style="text-align:center">szFileName</td>
<td>图片文件名</td></tr>
<tr><td style="text-align:center">nMaxPicCount</td>
<td>最大下载个数 默认值: 0x7fffffff</td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>nDownId：可用于FUN_CancelDownloadRecordImage，取消下载用
</td><tr>
<tr><td rowspan="6" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：异步消息EUIMSG . DOWN_RECODE_BPIC_START =  5534,    //录像缩略图下载开始<br>DOWN_RECODE_BPIC_FILE  =  5535,    //录像缩略图下载--文件下载结果返回<br>DOWN_RECODE_BPIC_COMPLETE =  5536, //录像缩略图下载-下载完成（结束）
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：成功；<0：失败，详见错误码说明</td></tr>
<tr><td style="text-align:center">arg2
</td><td>图片总个数</td></tr>
<tr><td style="text-align:center">arg3
</td><td>下载个数</td></tr>
<tr><td style="text-align:center">str
</td><td>图片名称</td></tr>
</table>

## 取消录像缩略图下载

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int CancelDownloadRecordImage(String szDevId, int nDownId);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
 取消录像缩略图下载</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>设备序列号</td></tr>
<tr><td style="text-align:center">nDownId</td>
<td>录像下载开始的返回值，如果==0表示全部停止</td></tr>
</table>

## 设置设备下载队列最多任务数

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int SetDownRBImageQueueSize(String szDevId, int nMaxSize);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
 设置设备下载队列最多任务数</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>设备序列号</td></tr>
<tr><td style="text-align:center">nMaxSize</td>
<td>下载队列最多任务数: nMaxSize == 0取消限制； nMaxSize > 0：下载最大排队任务数</td></tr>
</table>

## 获取掩码设置

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">boolean IsSelectHex(String szHex, int nIndex);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
 获取掩码设置-获取设置 0xffffffff ffffffff ffffffff: 31~0 63~32 95~64...</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">szHex</td>
<td>掩码相关参数</td></tr>
<tr><td style="text-align:center">nIndex</td>
<td>掩码相关参数</td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>False失败 
</td><tr>
</table>

## 设置掩码设置

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">String SetSelectHex(String szHex, int nIndex, boolean bSelected);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
 设置掩码设置</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">szHex</td>
<td>掩码相关参数</td></tr>
<tr><td style="text-align:center">nIndex</td>
<td>掩码相关参数</td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>修改的掩码 
</td><tr>
</table>

## 通过SSID获取设备类型

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">int CheckDevType(String szDevSSID);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
 通过SSID获取设备类型</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">szDevSSID</td>
<td>设备的SSID</td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>设备类型枚举值
</td><tr>
</table>

## 获取设备运行状态

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">String SMGetObjRunState(String sFun, String sObjId);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
 获取设备运行状态</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">sFun</td>
<td></td></tr>
<tr><td style="text-align:center">sObjId</td>
<td></td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>获取到的设备运行状态字节流
</td><tr>
</table>

## 设置设备运行使能

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">定义</td><td colspan="2">void SMEnable(int hUser, String sFun, String sObjId, boolean bEnable);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">
 设置设备运行使能</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">sFun</td>
<td></td></tr>
<tr><td style="text-align:center">sObjId</td>
<td></td></tr>
<tr><td style="text-align:center">bEnable</td>
<td></td></tr>
</td><tr>
</table>

## 使设备进入休眠状态(门铃)

<table >
<tr><td style="background-color:#ccc;text-align:center;width:50px;">定义</td><td colspan="2">int DevSleep(int hUser, String szDevId, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">使设备进入休眠状态(门铃)
</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">devId</td>
<td>设备序列号</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：EUIMSG . DEV_SLEEP 5141
</td></tr>
<tr><td  style="text-align:center">arg1
</td><td>==EE_OK：成功；ps：不再等结果，默认总会成功，就算失败，过15秒，设备也会自动休眠</td></tr>
</table>

## 唤醒设备(门铃)

<table >
<tr><td style="background-color:#ccc;text-align:center;width:50px;">定义</td><td colspan="2">int DevSleep(int hUser, String szDevId, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">唤醒设备，使之进入唤醒状态(适用于门铃)<br>
注意：调用唤醒接口后，不管当前状态，执行唤醒操作，成功后马上返回结果并后台登录，15秒超时
</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">devId</td>
<td>设备序列号</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：EUIMSG . DEV_WAKE_UP
</td></tr>
<tr><td  style="text-align:center">arg1
</td><td>==EE_OK：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 获取DSS支持的能力级

<table >
<tr><td style="background-color:#ccc;text-align:center;width:50px;">定义</td><td colspan="2">int GetDSSAbility(String szDevId, int nChannel);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">获取DSS支持的能力级
</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>设备序列号</td></tr>
<tr><td style="text-align:center">nChannel</td>
<td>设备能力级-详见EDEV_STREM_TYPE</td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>返回是否支持 > 0表示有此功能能力  <=0表示无
</td><tr>
</table>

## 设置本地保存密码/用户名

<table >
<tr><td style="background-color:#ccc;text-align:center;width:50px;">定义</td><td colspan="2">int DevSetLocalPwd(String szDevId, String szUser, String szPwd);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">设置本地保存密码/用户名
</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>设备序列号</td></tr>
<tr><td style="text-align:center">szUser</td>
<td>用户名</td></tr>
<tr><td style="text-align:center">szPwd</td>
<td>密码</td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>成功返回0，参数传递错误返回-1；
</td><tr>
</table>

## 获取本地保存密码

<table >
<tr><td style="background-color:#ccc;text-align:center;width:50px;">定义</td><td colspan="2">String DevGetLocalPwd(String szDevId);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">获取本地保存密码
</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>设备序列号</td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>获取到的密码
</td><tr>
</table>

## 获取本地保存用户名

<table >
<tr><td style="background-color:#ccc;text-align:center;width:50px;">定义</td><td colspan="2">String DevGetLocalUserName(String szDevId);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">获取本地保存用户名
</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>设备序列号</td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>获取到的用户名
</td><tr>
</table>

## 获取设备能力级

<table >
<tr><td style="background-color:#ccc;text-align:center;width:50px;">定义</td><td colspan="2">int GetDevAbility(String devId, String ability);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">获取设备能力级
</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">devId</td>
<td>设备序列号</td></tr>
<tr><td style="text-align:center">ability</td>
<td>获取设备什么能力级参数<br>
例：智能录像放回能力 "OtherFunction/SupportIntelligentPlayBack"<br>
是否开通云存储 "XXXAbillity/CloudStore"</td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>正常情况下返回 > 0表示有此功能能力 <=0表示无<br>是否开通云存储返回：-1：未知；0（不支持）、 1（支持已开通，正常使用）、2（支持已开通，服务到期） 、3（支持未开通）
</td><tr>
</table>

## 设备是否处于局域网中

<table >
<tr><td style="background-color:#ccc;text-align:center;width:50px;">定义</td><td colspan="2">int DevIsSearched(String szDevId, byte[] devInfo);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">设备是否处于局域网中
</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>设备序列号</td></tr>
<tr><td style="text-align:center">devInfo</td>
<td>设备信息,需分配对象空间new byte[244];详见SDK_CONFIG_NET_COMMON_V2</td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>返回值<=0,未搜到; 1,搜到
</td><tr>
</table>

## 获取通道个数

<table >
<tr><td style="background-color:#ccc;text-align:center;width:50px;">定义</td><td colspan="2">int GetDevChannelCount(String szDevId);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">获取通道个数，该接口支持DSS的设备可用
</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>设备序列号</td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>通道个数，不在线返回0
</td><tr>
</table>

## 通过SN获取对应的外网IP地址

<table >
<tr><td style="background-color:#ccc;text-align:center;width:50px;">定义</td><td colspan="2">String DevGetNetIPBySN(String uuid)</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">通过SN获取对应的外网IP地址
</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">uuid</td>
<td>设备唯一标示符</td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>获取到的ip地址
</td><tr>
</table>

## 跨网段设置设备配置

<table >
<tr><td style="background-color:#ccc;text-align:center;width:50px;">定义</td><td colspan="2">int DevSetNetCfgOverUDP(int hUser, int bTempCfg, byte []pNetCfg, String szDeviceMac, String szDeviceSN, String szDevUserName, String szDevPassword, int nTimeout, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">跨网段设置设备配置，目前只支持对有线网络配置进行设置
</td></tr>
<tr><td rowspan="8" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">bTempCfg</td>
<td>存储标识：1临时保存,其他为永久保存</td></tr>
<tr><td style="text-align:center">pNetCfg</td>
<td>SNetCFG结构体地址</td></tr>
<tr><td style="text-align:center">szDeviceMac</td>
<td>设备Mac地址</td></tr>
<tr><td style="text-align:center">szDeviceSN</td>
<td>设备序列号</td></tr>
<tr><td style="text-align:center">szDevUserName</td>
<td>设备登录用户名</td></tr>
<tr><td style="text-align:center">szDevPassword</td>
<td>设备登录密码</td></tr>
<tr><td style="text-align:center">nTimeout</td>
<td>等待超时时间,单位毫秒</td></tr>
</td><tr>
tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>异步返回，EUIMSG . DEV_SET_NET_IP_BY_UDP
</td></tr>
<tr><td  style="text-align:center">arg1
</td><td>==EE_OK：成功；<0：失败，详见错误码说明</td></tr>
<tr><td  style="text-align:center">arg1
</td><td>设备Mac地址</td></tr>
</table>
