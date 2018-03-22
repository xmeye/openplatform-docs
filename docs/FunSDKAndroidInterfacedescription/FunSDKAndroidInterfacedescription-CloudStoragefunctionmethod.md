## 查询Media通过指定日期

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
<tr><td style="background-color:#ccc;text-align:center;width:80px;">定义</td><td colspan="2"><b>int SearchMediaByMoth(int hUser, String devId, int nChannel, String  sStreamType, int nDate, int nSeq);
</b></td><tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">查询Media通过指定日期
</td></tr>
<tr><td rowspan="5" style="background-color:#ccc;text-align:center;">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr style="text-align:center"><td>devId</td><td>序列号</td>
<tr style="text-align:center"><td>nChannel</td><td>通道号</td>
<tr style="text-align:center"><td>sStreamType</td><td>码流类型</td>
<tr style="text-align:center"><td>nDate</td><td>日期</td>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";></td><tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG . MC_SearchMediaByMoth
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>返回结果 < 0失败 >=0成功 详见详见错误码说明
</td></tr>
</table>

## 查询Media通过指定时间

</style>
<table >
<tr><td style="background-color:#ccc;text-align:center;width:80px;">定义</td><td colspan="2"><b>int SearchMediaByTime(int hUser, String devId, int nChannel, String  sStreamType, int nStartTime, int nEndTime, int nSeq);
</b></td><tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">查询Media通过指定时间
</td></tr>
<tr><td rowspan="6" style="background-color:#ccc;text-align:center;">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr style="text-align:center"><td>devId</td><td>序列号</td>
<tr style="text-align:center"><td>nChannel</td><td>通道号</td>
<tr style="text-align:center"><td>sStreamType</td><td>码流类型</td>
<tr style="text-align:center"><td>nStartTime</td><td>开始时间</td>
<tr style="text-align:center"><td>nEndTime</td><td>结束时间</td>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG . MC_SearchMediaByTime
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>返回结果 < 0失败 >=0成功 详见详见错误码说明
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>获取到的信息 Json格式数据
</td></tr>
</table>

## 下载录像等媒体的缩略图

</style>
<table >
<tr><td style="background-color:#ccc;text-align:center;width:80px;">定义</td><td colspan="2"><b>int DownloadThumbnail(int hUser, String devId, String szJson, String szFileName, int nWidth, int nHeight, int nSeq);
</b></td><tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">下载录像等媒体的缩略图
</td></tr>
<tr><td rowspan="6" style="background-color:#ccc;text-align:center;">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr style="text-align:center"><td>devId</td><td>序列号</td>
<tr style="text-align:center"><td>szJson</td><td>获取到的josn信息</td>
<tr style="text-align:center"><td>szFileName</td><td>文件名</td>
<tr style="text-align:center"><td>nWidth</td><td>宽</td>
<tr style="text-align:center"><td>nHeight</td><td>高//可以指定宽和高，等于0时默认为原始大小</td>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>消息签名 //内部使用，用来判断此消息是否有效
</td><tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG . MC_DownloadMediaThumbnail
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>返回结果 < 0失败 >=0成功 详见详见错误码说明
</td></tr>
<tr><td style="text-align:center">str
</td><td>缩略图文件路径
</td></tr>
</table>

## 设置下载列表中的任务数量

</style>
<table >
<tr><td style="background-color:#ccc;text-align:center;width:80px;">定义</td><td colspan="2"><b>int SetDownloadThumbnailMaxQueue(int nMaxQueueSize);
</b></td><tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">设置下载列表中的任务数量
</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center;">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr style="text-align:center"><td>nMaxQueueSize</td><td>任务最大数量//默认值#define N_MAX_DOWNLOAD_QUEUE_SIZE 32</td>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>0
</td><tr>
</table>

## 取消全部缩略图下载任务

</style>
<table >
<tr><td style="background-color:#ccc;text-align:center;width:80px;">定义</td><td colspan="2"><b>void StopDownloadThumbnail();
</b></td><tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">取消全部缩略图下载任务
</td></tr>
</table>
