## 播放设备实时视频
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
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">FUN_HANDLE FUN_MediaRealPlay(UI_HANDLE hUser, const char *szDevId, int nChnIndex, int nStreamType, LP_WND_OBJ hWnd, MEDIA_EX_PARAM int nSeq = 0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">播放设备通道实时视频</td></tr>
<tr><td rowspan="6" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明</td></tr>
<tr><td style="text-align:center">devId</td><td>设备序列号</td></tr>
<tr><td style="text-align:center">nChnIndex</td>
<td>通道号（从0开始）</td></tr>
<tr><td style="text-align:center">nStreamType</td>
<td>码流类型；0：主码流；1：子码流1</td></tr>
<tr><td style="text-align:center">hWnd</td>
<td>显示窗口GLSurfaceView20对象</td></tr>
<tr><td style="text-align:center">nSeq</td>
<td>操作序列号（用户自定义）</td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td>
<td colspan="2">视频播放对象句柄，可用来实现本视频的开始、抓图、录像等操作</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id</td>
<td>消息值：EUIMSG   .EMSG_START_PLAY</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==EE_OK：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 通过URL链接播放视频

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">FUN_HANDLE Fun_MediaPlayByURL(UI_HANDLE hUser, const char* strUrl, LP_WND_OBJ hWnd, MEDIA_EX_PARAM int nSeq = 0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">通过URL链接播放视频</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">参数<br>说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">strUrl</td>
<td>视频Url链接</td></tr>
<tr><td style="text-align:center">hWnd</td>
<td>显示窗口GLSurfaceView20对象</td></tr>
<tr><td  style="text-align:center">nSeq
</td><td>操作序列号（用户自定义）</td></tr>
<tr><td  style="background-color:#ccc;text-align:center">返回</td>
<td colspan="2">视频播放对象句柄，可用来实现本视频的开始、抓图、录像等操作</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：EUIMSG .EMSG_ START_PLAY<br>
缓存结束，开始播放:EUIMSG . ON_PLAY_BUFFER_END
</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>==EE_OK：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 通过URL链接播放视频- -播放国标Rtsp流

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">FUN_HANDLE Fun_MediaPlayByURLEx(UI_HANDLE hUser, const char *szUrl, int nType, LP_WND_OBJ hWnd, MEDIA_EX_PARAM int nSeq = 0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">通过URL链接播放视频- -播放国标Rtsp流</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">参数<br>说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">strUrl</td>
<td>视频Url链接</td></tr>
<tr><td style="text-align:center">nType</td>
<td>流类型nType == 0时同MediaPlayByURL; 100:GB-Rtsp</td></tr>
<tr><td  style="text-align:center">hWnd
</td><td>显示窗口GLSurfaceView20对象</td></tr>
<tr><td  style="background-color:#ccc;text-align:center">返回</td>
<td colspan="2">视频播放对象句柄，可用来实现本视频的开始、抓图、录像等操作</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：EUIMSG . EMSG_START_PLAY<br>
缓存结束，开始播放:EUIMSG . EMSG_ON_PLAY_BUFFER_END
</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>==EE_OK：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 播放远程录像

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">FUN_HANDLE FUN_MediaNetRecordPlay(UI_HANDLE hUser, const char *szDevId, H264_DVR_FILE_DATA *sPlayBackFile, LP_WND_OBJ hWnd, MEDIA_EX_PARAM int nSeq = 0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">播放远程录像</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">参数<br>说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">devId</td>
<td>设备序列号</td></tr>
<tr><td style="text-align:center">sPlayBackFile</td>
<td>录像信息结构体对像H264_DVR_FILE_DATA字节流</td></tr>
<tr><td  style="text-align:center">hWnd
</td><td>显示窗口GLSurfaceView20对象</td></tr>
<tr><td  style="background-color:#ccc;text-align:center">返回</td>
<td colspan="2">视频播放对象句柄，可用来实现本视频的开始、抓图、录像等操作</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：EUIMSG .EMSG_START_PLAY<br>
回放过程中的信息通过“EUIMSG .EMSG_ON_PLAY_INFO”消息定时通知<br>
回放结束时通过消息“EUIMSG . EMSG_ON_PLAY_END”通知
</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>==EE_OK：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 播放远程录像—按时间

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">FUN_HANDLE FUN_MediaNetRecordPlayByTime(UI_HANDLE hUser, const char *szDevId, H264_DVR_FINDINFO *sPlayBackFile, LP_WND_OBJ hWnd, MEDIA_EX_PARAM int nSeq = 0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">播放远程录像—按时间</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>设备序列号</td></tr>
<tr><td style="text-align:center">pH264_DVR_FINDINFO
</td><td>录像信息结构体对像H264_DVR_FINDINFO字节流</td></tr>
<tr><td  style="text-align:center">hWnd</td>
<td>显示窗口GLSurfaceView20对象</td></tr>
<tr><td  style="background-color:#ccc;text-align:center">返回</td>
<td colspan="2">视频播放对象句柄，可用来实现本视频的开始、抓图、录像等操作</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：EUIMSG . EMSG_START_PLAY<br>
回放过程中的信息通过“EUIMSG . EMSG_ON_PLAY_INFO”消息定时通知<br>
回放结束时通过消息“EUIMSG . EMSG_ON_PLAY_END”通知
</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>==EE_OK：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 播放本地录像

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">FUN_HANDLE FUN_MediaLocRecordPlay(UI_HANDLE hUser, const char *szFileName, LP_WND_OBJ hWnd, MEDIA_EX_PARAM int nSeq = 0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">播放本地录像</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">szFileName</td>
<td>本地文件路径及名称</td></tr>
<tr><td  style="text-align:center">hWnd</td>
<td>显示窗口GLSurfaceView20对象</td></tr>
<tr><td  style="background-color:#ccc;text-align:center">返回</td>
<td colspan="2">视频播放对象句柄，可用来实现本视频的开始、抓图、录像等操作</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：EUIMSG . EMSG_START_PLAY<br>
回放过程中的信息通过“EUIMSG . EMSG_ON_PLAY_INFO”消息定时通知<br>
回放结束时通过消息“EUIMSG . EMSG_ON_PLAY_END”通知
</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>==EE_OK：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 播放本地录像-通过url播放录像

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">FUN_HANDLE FUN_MediaRecordPlay(UI_HANDLE hUser, const char *szRecord, LP_WND_OBJ hWnd, MEDIA_EX_PARAM int nSeq = 0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">播放本地录像-通过url播放录像</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">sRecord</td>
<td>本地文件路径及名称/url及名称</td></tr>
<tr><td  style="text-align:center">hWnd</td>
<td>显示窗口GLSurfaceView20对象</td></tr>
<tr><td  style="background-color:#ccc;text-align:center">返回</td>
<td colspan="2">视频播放对象句柄，可用来实现本视频的开始、抓图、录像等操作</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：EUIMSG . EMSG_START_PLAY<br>
回放过程中的信息通过“EUIMSG . EMSG_ON_PLAY_INFO”消息定时通知<br>
回放结束时通过消息“EUIMSG . EMSG_ON_PLAY_END”通知
</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>==EE_OK：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 云录像播放

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">FUN_HANDLE FUN_MediaCloudRecordPlay(UI_HANDLE hUser, const char *szDevId, int nChannel, const char *szStreamType, int nStartTime, int nEndTime, LP_WND_OBJ hWnd, MEDIA_EX_PARAM int nSeq = 0);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">云播放录像</td></tr>
<tr><td rowspan="7" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>设备序列号</td></tr>
<tr><td style="text-align:center">nChannel</td>
<td>通道号</td></tr>
<tr><td style="text-align:center">sStreamType</td>
<td>类型</td></tr>
<tr><td style="text-align:center">nStartTime</td>
<td>开始时间</td></tr>
<tr><td style="text-align:center">nEndTime</td>
<td>结束时间</td></tr>
<tr><td style="text-align:center">hWnd</td>
<td>显示窗口GLSurfaceView20对象</td></tr>
<tr><td  style="background-color:#ccc;text-align:center">返回</td>
<td colspan="2">视频播放对象句柄，可用来实现本视频的开始、抓图、录像等操作</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：EUIMSG . EMSG_START_PLAY<br>
回放过程中的信息通过“EUIMSG . EMSG_ON_PLAY_INFO”消息定时通知<br>
回放结束时通过消息“EUIMSG . EMSG_ON_PLAY_END”通知
</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>==EE_OK：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 云录像下载

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">FUN_HANDLE FUN_MediaCloudRecordDownload(UI_HANDLE hUser, const char *szDeviceId, int nChannel, const char *szStreamType, int nStartTime, int nEndTime, const char *szFileName, int nSeq);

</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">云播放下载</td></tr>
<tr><td rowspan="7" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>设备序列号</td></tr>
<tr><td style="text-align:center">nChannel</td>
<td>通道号</td></tr>
<tr><td style="text-align:center">sStreamType</td>
<td>类型</td></tr>
<tr><td style="text-align:center">nStartTime</td>
<td>开始时间</td></tr>
<tr><td style="text-align:center">nEndTime</td>
<td>结束时间</td></tr>
<tr><td style="text-align:center">sFileName</td>
<td>下载的文件名</td></tr>
<tr><td  style="background-color:#ccc;text-align:center">返回</td>
<td colspan="2">视频播放对象句柄，可用来实现本视频的开始、抓图、录像等操作</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：EUIMSG . EMSG_ON_FILE_DOWNLOAD:下载函数调用结果<br>
EUIMSG . EMSG_ON_FILE_DLD_COMPLETE:下载完成消息回调<br>
EUIMSG . EMSG_ON_FILE_DLD_POS:下载进度消息回调<br>
</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>==EE_OK：成功；<0：失败，详见错误码说明</td></tr>
<tr><td  style="text-align:center">str</td>
<td>码流类型</td></tr>
</table>

## 播放视频—视频ID

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">FUN_HANDLE FUN_MediaByVideoId(UI_HANDLE hUser, const char *szVideoId, LP_WND_OBJ hWnd, MEDIA_EX_PARAM int nSeq = 0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">播放视频</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">szVideoId</td>
<td>视频ID</td></tr>
<tr><td style="text-align:center">hWnd</td>
<td>显示窗口GLSurfaceView20对象</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：消息值：EUIMSG . EMSG_START_PLAY<br>
回放过程中的信息通过“EUIMSG . EMSG_ON_PLAY_INFO”消息定时通知<br>
回放结束时通过消息“EUIMSG . EMSG_ON_PLAY_END”通知
</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>==EE_OK：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 视频控制-播放/暂停

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int FUN_MediaPause(FUN_HANDLE hPlayer, int bPause, int nSeq = 0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">视频控制-开始/暂停</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">hPlayer</td>
<td>视频控制句柄—视频播放的返回值</td></tr>
<tr><td style="text-align:center">bPause</td>
<td> 0：播放；1：暂停；-1：两者切换</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：EUIMSG . EMSG_PAUSE_PLAY</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>当前状态；1：正在播放；0：暂停状态</td></tr>
</table>

## 视频控制-刷新

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int FUN_MediaRefresh(FUN_HANDLE hPlayer, int nSeq = 0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">视频控制-刷新</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">hPlayer</td>
<td>视频控制句柄—视频播放的返回值</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：EUIMSG . EMSG_REFRESH_PLAY</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>=EE_OK：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 视频控制-停止

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int FUN_MediaStop(FUN_HANDLE hPlayer, void *env = NULL);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">视频控制—停止</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">hPlayer</td>
<td>视频控制句柄—视频播放的返回值</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：无</td></tr>
</table>

## 视频控制-定位播放位置

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int FUN_MediaSeekToPos(FUN_HANDLE hPlayer, int nPos, int nSeq = 0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">视频控制—定位播放位置</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">hPlayer</td>
<td>视频控制句柄—视频播放的返回值</td></tr>
<tr><td style="text-align:center">nPos</td>
<td>位置</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：EUIMSG . EMSG_SEEK_TO_POS</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>0</td></tr>
</table>

## 视频控制-定位播放时间

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int FUN_MediaSeekToTime(FUN_HANDLE hPlayer, int nAddTime, int nAbsTime, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">视频控制—定位播放时间</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">hPlayer</td>
<td>视频控制句柄—视频播放的返回值</td></tr>
<tr><td style="text-align:center">nAddTime</td>
<td>总的时间</td></tr>
<tr><td style="text-align:center">nAbsTime</td>
<td>绝对时间time_t的值 
两者二选一，如果nAbsTime不为-1，则使用nAbsTime<br>
nAbsTime后面不再支持,替换为MediaSeekToMSTime
</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：EUIMSG . EMSG_SEEK_TO_TIME</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>0</td></tr>
</table>

## 视频控制—-定位绝对播放时间

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int FUN_MediaSeekToMSTime(FUN_HANDLE hPlayer, uint64 nMSecond, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">视频控制—-定位绝对播放时间</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">hPlayer</td>
<td>视频控制句柄—视频播放的返回值</td></tr>
<tr><td style="text-align:center">nMSecond</td>
<td>绝对时间time_t的值</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：EUIMSG . EMSG_SEEK_TO_TIME</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>无</td></tr>
</table>

## 视频控制—设置声音

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int FUN_MediaSetSound(FUN_HANDLE hPlayer, int nSound, int nSeq = 0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">视频控制—设置声音</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">hPlayer</td>
<td>视频控制句柄—视频播放的返回值</td></tr>
<tr><td style="text-align:center">nSound</td>
<td>声音数值</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：EUIMSG . EMSG_SET_SOUND</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>无</td></tr>
</table>

## 视频控制-设置大小

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int FUN_MediaSetPlaySize(FUN_HANDLE hPlayer, int nType, int nSeq = 0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">视频控制-设置大小 实时播放/云存储播放有效</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">hPlayer</td>
<td>视频控制句柄—视频播放的返回值</td></tr>
<tr><td style="text-align:center">nType</td>
<td>播放类型 0:高清 1:标清 2:高清/标清 3:流畅(实时视频有效)</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：EUIMSG . EMSG_ON_MEDIA_SET_PLAY_SIZE</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>无</td></tr>
</table>

## 视频控制-获取当前播放时间

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">uint64 FUN_MediaGetCurTime(FUN_HANDLE hPlayer);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">视频控制-获取当前播放时间 ms</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">hPlayer</td>
<td>视频控制句柄—视频播放的返回值</td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>当前播放时间
</td><tr>
</table>

## 视频控制-调整显示
<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int FUN_MediaSetDisplayBCSG(FUN_HANDLE hPlayer, int nBrightness, int nContrast, int nSaturation, int nGray);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">视频控制—调整显示的亮度(brightness)\对比度(contrast)\饱合度(saturation)\灰度(gray)<br>
(只影响显示，对原始视频数据无影响)
</td></tr>
<tr><td rowspan="6" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">hPlayer</td>
<td>视频控制句柄—视频播放的返回值</td></tr>
<tr><td style="text-align:center">nBrightness</td>
<td>亮度</td></tr>
<tr><td style="text-align:center">nContrast</td>
<td>对比度</td></tr>
<tr><td style="text-align:center">nSaturation</td>
<td>饱和度</td></tr>
<tr><td style="text-align:center">nGray</td>
<td>灰度</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：EUIMSG .  EMSG_SET_MEDIA_DISPLAY_BCSG</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>无</td></tr>
</table>

## 视频控制-智能回放
<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int Fun_MediaSetIntellPlay(FUN_HANDLE hPlayer, unsigned int nTypeMask, int nSpeed, int nSeq = 0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">视频控制—智能回放
</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">hPlayer</td>
<td>视频控制句柄—视频播放的返回值</td></tr>
<tr><td style="text-align:center">nValue</td>
<td>类型 <pre>
以“|”分隔各类型 详见EMSSubType
空：取消
ALL：全部录像包括普通
ALLALARM：全部报警录像
COMMON：普通报警
LOCALALARM：本地报警
NETALARM：网络报警
NETABORT：断网报警
IPC：PC报警
SPEED：超速报警
GSENSOR：SENSOR报警
SERIAL：串口报警
MOTION：移动侦测	
LOSS：视频丢失
BLIND：视频遮挡	
PIR：红外检测
CARDNUMBER：卡号录像	
PERIMETER：周界检测
TRIPWIRE：单绊线检测	
ABANDUM：物品遗留
STOLEN：物品被盗	
CHANGE：场景变换
</pre></td></tr>
<tr><td style="text-align:center">nSpeed</td>
<td>播放速度。取值-3~3分别代表-8、-4、-2、1、2、4、8倍速 ==0:取消智能快放</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：EUIMSG . EMSG_SET_INTELL_PLAY</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>==EE_OK：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 视频控制-改变播放显示窗口
<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int FUN_MediaSetPlayView(FUN_HANDLE hPlayer, LP_WND_OBJ hWnd, MEDIA_EX_PARAM int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">视频控制—改变播放显示窗口
</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">hPlayer</td>
<td>视频控制句柄—视频播放的返回值</td></tr>
<tr><td style="text-align:center">hWnd</td>
<td>显示窗口GLSurfaceView20对象</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：EUIMSG . EMSG_MEDIA_SETPLAYVIEW</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>无</td></tr>
</table>

## 视频控制-设置视频流畅度等级
<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int FUN_MediaSetFluency(FUN_HANDLE hPlayer, int nLevel, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">视频控制—设置视频流畅度等级
</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">hPlayer</td>
<td>视频控制句柄—视频播放的返回值</td></tr>
<tr><td style="text-align:center">nLevel</td>
<td>流畅度等级 详见EDECODE_TYPE</td></tr>
</table>

## 视频控制-抓取缩略图
<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int FUN_MediaGetThumbnail(FUN_HANDLE hPlayer, const char *szOutFileName, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">视频控制—抓取缩略图
</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">hPlayer</td>
<td>视频控制句柄—视频播放的返回值</td></tr>
<tr><td style="text-align:center">szOutFileName</td>
<td>保存的文件名称</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：消息值：EUIMSG . EMSG_ON_Media_Thumbnail</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>==EE_OK：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 视频控制-抓取*.私有码流缩略图
<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int FUN_GetMediaThumbnail(const char *szInFileName, const char *szOutFileName);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">视频控制—抓取*.私有码流缩略图
</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">strInFileName</td>
<td>视频文件路径</td></tr>
<tr><td style="text-align:center">strOutFileName</td>
<td>获取的缩略图路径</td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>==EE_OK：成功；<0：失败，详见错误码说明
</td><tr>
</table>

## 视频控制-获取解码参数
<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int FUN_MediaGetDecParam(const char *szFilePath, unsigned char *pOutBuffer, int nBufMaxSize);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">视频控制—获取解码参数
</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">szFilePath</td>
<td>w文件路径</td></tr>
</td></tr>
<tr><td style="text-align:center">pOutBuffer</td>
<td>获取到的解码参数</td></tr>
</td></tr>
<tr><td style="text-align:center">nBufMaxSize</td>
<td>最大值</td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>0：解码参数的大小；<0：失败，详见错误码说明
</td><tr>
</table>

## 视频控制-获取鱼眼解码参数
<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int FUN_MediaGetFishParam(const char * szFilePath, FishEyeFrameParam * pInfo);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">视频控制—获取鱼眼解码参数
</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">szFilePath</td>
<td>文件名</td></tr>
<tr><td style="text-align:center">pInfo</td>
<td>获取到的解码参数</td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>0：解码参数的大小；<0：失败，详见错误码说明
</td><tr>
</table>

## 实时流的保存
<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">FUN_HANDLE FUN_DevSaveRealTimeStream(UI_HANDLE hUser, const char *szDevId, int nChannel, int nStreamType, const char *szFileName, int nSeq = 0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">实时流的保存
</td></tr>
<tr><td rowspan="5" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>序列号</td></tr>
<tr><td style="text-align:center">nChannel</td>
<td>通道号</td></tr>
<tr><td style="text-align:center">nStreamType</td>
<td>码流类型</td></tr>
<tr><td style="text-align:center">szFileName</td>
<td>保存的文件名称</td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>视频播放对象句柄，可用来实现本视频的开始、抓图等操作 
</td><tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：EUIMSG . EMSG_START_PLAY保存数据开始<br>
EUIMSG . EMSG_ON_MediaData_Save<br>
已保存数据大小，单位kB  EUIMSG . EMSG_MediaData_Save_Process 
</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>==EE_OK：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 关闭实时流的保存
<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int FUN_DevCloseRealTimeStream(FUN_HANDLE hSaveObj);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">关闭实时流的保存
</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">hSaveObj</td>
<td>实时流保存返回的值</td></tr>

<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：EUIMSG .EMSG_STOP_PLAY 
</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>无</td></tr>
</table>

## 播放速度控制

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int FUN_MediaSetPlaySpeed(FUN_HANDLE hPlayer, int nSpeed, int nSeq = 0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">设置播放速度</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">hPlayer</td>
<td>视频控制句柄—视频播放的返回值</td></tr>
<tr><td style="text-align:center">nSpeed</td>
<td>播放速度。取值-3~3分别代表-8、-4、-2、1、2、4、8倍速</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：EUIMSG  . EMSG_SET_PLAY_SPEED</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>当前速度值</td></tr>
</table>

## 开始录像

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int FUN_MediaStartRecord(FUN_HANDLE hPlayer, const char *szFileName, int nSeq = 0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">开始录像</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">hPlayer</td>
<td>视频控制句柄—视频播放的返回值</td></tr>
<tr><td style="text-align:center">szFileName</td>
<td>保存录像文件名称；文件格式以后缀名表示；“.H264”；私有格式；其它有AVI等
</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：EUIMSG . EMSG_START_SAVE_MEDIA_FILE</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>==EE_OK：成功；<0：失败，详见错误码说明</td></tr>
<tr><td  style="text-align:center">szStr</td>
<td>保存文件名称</td></tr>
</table>

## 停止录像

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int  MediaStop(int  hPlayer, int  nSeq);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">停止录像</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">hPlayer</td>
<td>视频控制句柄—视频播放的返回值</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：EUIMSG . EMSG_STOP_SAVE_MEDIA_FILE</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>==EE_OK：成功；<0：失败，详见错误码说明</td></tr>
<tr><td  style="text-align:center">szStr</td>
<td>保存文件名称</td></tr>
</table>

## 视频抓图

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int FUN_MediaSnapImage(FUN_HANDLE hPlayer, const char *szFileName, int nSeq = 0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">视频抓图</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">hPlayer</td>
<td>视频控制句柄—视频播放的返回值</td></tr>
<tr><td style="text-align:center">szFileName</td>
<td>保存录像文件名称；文件格式以后缀名表示；“.H264”；私有格式；其它有AVI等
</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：EUIMSG   .EMSG_EMSG_SAVE_IMAGE_FILE</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>==EE_OK：成功；<0：失败，详见错误码说明</td></tr>
<tr><td  style="text-align:center">szStr</td>
<td>保存文件名称</td></tr>
</table>


## 播放视频XMp4

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">FUN_HANDLE Fun_MediaPlayXMp4(UI_HANDLE hUser, int hMp4File, LP_WND_OBJ hWnd, MEDIA_EX_PARAM int nSeq = 0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">播放视频XMp4</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">hXMp4</td>
<td>mp4文件</td></tr>
<tr><td style="text-align:center">hWnd</td>
<td>显示窗口GLSurfaceView20对象
</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：EUIMSG . EMSG_START_PLAY<br>
回放过程中的信息通过“EUIMSG . EMSG_ON_PLAY_INFO”消息定时通知<br>
回放结束时通过消息“EUIMSG . EMSG_ON_PLAY_END”通知
</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>==EE_OK：成功；<0：失败，详见错误码说明</td></tr>
<tr><td  style="text-align:center">szStr</td>
<td>保存文件名称</td></tr>
</table>

## 播放视频

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int FUN_MediaPlay(FUN_HANDLE hPlayer, int nSeq = 0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">播放视频</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">hPlayer</td>
<td>视频控制句柄—视频播放的返回值</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：EUIMSG . EMSG_START_PLAY<br>
回放过程中的信息通过“EUIMSG . EMSG_ON_PLAY_INFO”消息定时通知<br>
回放结束时通过消息“EUIMSG . EMSG_ON_PLAY_END”通知
</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>==EE_OK：成功；<0：失败，详见错误码说明</td></tr>
<tr><td  style="text-align:center">szStr</td>
<td>保存文件名称</td></tr>
</table>

## 视频缓存时间设置

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int MediaSetBufferByTime(int hPlayer,int nMaxBufferTime, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">视频缓存时间设置</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">hPlayer</td>
<td>视频控制句柄—视频播放的返回值</td></tr>
<tr><td style="text-align:center">nMaxBufferTime</td>
<td>最大缓存时间</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>
</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>==EE_OK：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 获取媒体文件信息

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">byte[]GetMediaFileInfo(String sFile)</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">获取媒体文件信息</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">sFile</td>
<td>视频文件路径</td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>视频文件信息结构体的byte数组
</td><tr>

<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>
</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>==EE_OK：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 转时间类型

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int ToTimeType(int time[]);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">转时间类型</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">time</td>
<td>时间</td></tr>
</table>

## 转时间

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">ToTime(int time_t, int time[]);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">转时间</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">time_t</td>
<td>秒级时间</td></tr>
<tr><td style="text-align:center">time</td>
<td>时间</td></tr>
</table>

## 加密MD5

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">String DevMD5Encrypt(String strInput);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">加密MD5</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">strInput</td>
<td>明文</td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>密文
</td><tr>

</table>




