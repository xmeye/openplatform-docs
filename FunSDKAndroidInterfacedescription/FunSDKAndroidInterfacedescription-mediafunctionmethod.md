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
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int MediaRealPlay(int hUser, String devId, int  nChnIndex, int  nStreamType, Object hWnd, int  nSeq)</td></tr>
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


## 播放远程录像

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int MediaNetRecordPlay(int hUser, String devId, byte []sPlayBackFile, Object hWnd,   int  nSeq);</td></tr>
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
</td><td>消息值：EUIMSG   .EMSG_START_PLAY
回放过程中的信息通过“EUIMSG   .EMSG_ON_PLAY_INFO”消息定时通知
回放结束时通过消息“EUIMSG   .EMSG_ON_PLAY_END”通知
</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>==EE_OK：成功；<0：失败，详见错误码说明</td></tr>
</table>


## 播放远程录像—按时间

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int   MediaNetRecordPlayByTime(int hUser,String szDevId, byte[] pH264_DVR_FINDINFO,   Object hWnd, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">播放远程录像—按时间</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>设备序列号</td></tr>
<tr><td style="text-align:center">pH264_DVR_FINDINFO
</td><td>录像信息结构体对像H264_DVR_FILE_DATA字节流</td></tr>
<tr><td  style="text-align:center">hWnd</td>
<td>显示窗口GLSurfaceView20对象</td></tr>
<tr><td  style="background-color:#ccc;text-align:center">返回</td>
<td colspan="2">视频播放对象句柄，可用来实现本视频的开始、抓图、录像等操作</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：EUIMSG   .EMSG_START_PLAY
回放过程中的信息通过“EUIMSG   .EMSG_ON_PLAY_INFO”消息定时通知
回放结束时通过消息“EUIMSG   .EMSG_ON_PLAY_END”通知
</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>==EE_OK：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 播放本地录像

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">INT  MediaLocRecordPlay(int   hUser, String szFileName, Object hWnd, int    nSeq);</td></tr>
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
</td><td>消息值：EUIMSG   .EMSG_START_PLAY
回放过程中的信息通过“EUIMSG   .EMSG_ON_PLAY_INFO”消息定时通知
回放结束时通过消息“EUIMSG   .EMSG_ON_PLAY_END”通知
</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>==EE_OK：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 云播放录像

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int   MediaCloudRecordPlay(int hUser, String szFileName,int nType, int nStartTime,   Object hWnd, int nSeq);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">云播放录像</td></tr>
<tr><td rowspan="5" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">szFileName</td>
<td>本地文件路径及名称</td></tr>
<tr><td style="text-align:center">nType</td>
<td>类型</td></tr>
<tr><td style="text-align:center">nStartTime</td>
<td>开始时间</td></tr>
<tr><td style="text-align:center">hWnd</td>
<td>显示窗口GLSurfaceView20对象</td></tr>
<tr><td  style="background-color:#ccc;text-align:center">返回</td>
<td colspan="2">视频播放对象句柄，可用来实现本视频的开始、抓图、录像等操作</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：EUIMSG   .EMSG_START_PLAY
回放过程中的信息通过“EUIMSG   .EMSG_ON_PLAY_INFO”消息定时通知
回放结束时通过消息“EUIMSG   .EMSG_ON_PLAY_END”通知
</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>==EE_OK：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 播放实时流录像

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int   MediaRtspPlay(int hUser, String uuid, int mediaId,String sUrl, Object hWnd,   int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">云播放录像</td></tr>
<tr><td rowspan="5" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">uuid</td>
<td>唯一标识符</td></tr>
<tr><td style="text-align:center">mediaId</td>
<td>码流ID</td></tr>
<tr><td style="text-align:center">sUrl</td>
<td>URL</td></tr>
<tr><td style="text-align:center">hWnd</td>
<td>显示窗口GLSurfaceView20对象</td></tr>
<tr><td  style="background-color:#ccc;text-align:center">返回</td>
<td colspan="2">视频播放对象句柄，可用来实现本视频的开始、抓图、录像等操作</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：EUIMSG   .EMSG_START_PLAY
回放过程中的信息通过“EUIMSG   .EMSG_ON_PLAY_INFO”消息定时通知
回放结束时通过消息“EUIMSG   .EMSG_ON_PLAY_END”通知
</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>==EE_OK：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 播放视频—视频ID

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int   MediaByVideoId(int hUser, String szVideoId, Object hWnd,int nSeq);</td></tr>
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
</td><td>消息值：EUIMSG   .EMSG_START_PLAY
回放过程中的信息通过“EUIMSG   .EMSG_ON_PLAY_INFO”消息定时通知
回放结束时通过消息“EUIMSG   .EMSG_ON_PLAY_END”通知
</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>==EE_OK：成功；<0：失败，详见错误码说明</td></tr>
</table>

## 视频控制-播放/暂停

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int  MediaPause(INT  hPlayer, int  bPause, int    nSeq = 0);</td></tr>
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
</td><td>消息值：EUIMSG   .EMSG_PAUSE_PLAY</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>当前状态；1：正在播放；0：暂停状态</td></tr>
</table>

## 视频控制-停止

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int  MediaStop(INT  hPlayer, int  nSeq = 0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">视频控制—停止</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">hPlayer</td>
<td>视频控制句柄—视频播放的返回值</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：EUIMSG   .EMSG_STOP_PLAY</td></tr>
</table>

## 视频控制-定位播放位置

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int   MediaSeekToPos(int hPlayer, int nPos, int nSeq);</td></tr>
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
</td><td>消息值：EUIMSG   .EMSG_ SEEK_TO_POS</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>0</td></tr>
</table>

## 视频控制-定位播放时间

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int   MediaSeekToTime(int hPlayer, int nAddTime,   int nAbsTime, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">视频控制—定位播放时间</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">hPlayer</td>
<td>视频控制句柄—视频播放的返回值</td></tr>
<tr><td style="text-align:center">nAddTime</td>
<td>总的时间</td></tr>
<tr><td style="text-align:center">nAbsTime</td>
<td>绝对时间</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td  style="text-align:center">id
</td><td>消息值：EUIMSG .EMSG_ SEEK_TO_TIME</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>0</td></tr>
</table>

## 视频控制—设置声音

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int   MediaSetSound(int hPlayer, int nSound, int nSeq);</td></tr>
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
</td><td>消息值：EUIMSG   .EMSG_ SET_SOUND</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>无</td></tr>
</table>

## 播放速度控制

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int  MediaSetPlaySpeed(INT  hPlayer, int  nSpeed, int  nSeq = 0);</td></tr>
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
</td><td>消息值：EUIMSG   .EMSG_SET_PLAY_SPEED</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>当前速度值</td></tr>
</table>

## 开始录像

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int  MediaStartRecord(INT  hPlayer, const char *szFileName, int  nSeq = 0);</td></tr>
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
</td><td>消息值：EUIMSG   .EMSG_START_SAVE_MEDIA_FILE</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>==EE_OK：成功；<0：失败，详见错误码说明</td></tr>
<tr><td  style="text-align:center">szStr</td>
<td>保存文件名称</td></tr>
</table>

## 停止录像

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int  MediaStopRecord (int  hPlayer, int  nSeq = 0);
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
</td><td>消息值：EUIMSG   .EMSG_STOP_SAVE_MEDIA_FILE</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>==EE_OK：成功；<0：失败，详见错误码说明</td></tr>
<tr><td  style="text-align:center">szStr</td>
<td>保存文件名称</td></tr>
</table>

## 视频抓图

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int  MediaSnapImage(HANDLE hPlayer, const char   *szFileName, int  nSeq = 0);</td></tr>
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
</td><td>消息值：EUIMSG   .EMSG_SAVE_IMAGE_FILE</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>==EE_OK：成功；<0：失败，详见错误码说明</td></tr>
<tr><td  style="text-align:center">szStr</td>
<td>保存文件名称</td></tr>
</table>





