## 剪切媒体文件

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
<tr><td style="background-color:#ccc;text-align:center;width:80px;">定义</td><td colspan="2"><b>int MP4_SubFile(UI_HANDLE hUser, const char *szSrcFile, const char *szDesFile, int nTimeBegin, int nTimeEnd, int nSeq = 0);
</b></td><tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">剪切指定的视频文件（目前支持MP4格式文件）//配置或更改工作目录后，必须调用该接口开启工作目录
</td></tr>
<tr><td rowspan="6" style="background-color:#ccc;text-align:center;">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr style="text-align:center"><td>hUser</td><td>接收分割进度及结果回调</td></tr>
<tr style="text-align:center"><td>szSrcFile</td><td>被分割的源文件路径</td></tr>
<tr style="text-align:center"><td>szDesFile</td><td>被分割的目标文件路径</td></tr>
<tr style="text-align:center"><td>nTimeBegin</td><td>被分割的源文件的开始时间(单位)</td></tr>
<tr style="text-align:center"><td>nTimeEnd</td><td>被分割的源文件的结束时间(单位耗秒)</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息ID EUIMSG.EMSG_MF_ON_SUB_FILE_PROGRESS:进度及结果 
EUIMSG.MF_ON_SUB_FILE  
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>0~100:进度 200:成功 <0:失败
</td></tr>
<tr><td style="text-align:center">str
</td><td>目标文件路径
</td></tr>
</table>

## 创建合并目标媒体文件

</style>
<table >
<tr><td style="background-color:#ccc;text-align:center;width:80px;">定义</td><td colspan="2"><b>int EMP4_CreateFormatFile(UI_HANDLE hUser, const char *szDesFile);
</b></td><tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">创建合并目标媒体文件（目前只支持MP4文件）
</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center;">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr style="text-align:center"><td>hUser</td><td>接收合并文件的进度及结果回调 </td></tr>
<tr style="text-align:center"><td>szDesFile</td><td>合并文件的目标文件路径 </td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>返回文件操作句柄值创建合并文件的操作句柄，供后续接口StartFormate、CancelFormate、DestoryFormate、InsertSrcFile、RemoveSrcFile使用。
<tr><td>备注</td><td colspan="2">创建合并文件的操作句柄，供后续接口StartFormate、CancelFormate、DestoryFormate、InsertSrcFile、RemoveSrcFile使用。</td></tr>
</table>

## 设置合并文件的音频文件

</style>
<table >
<tr><td style="background-color:#ccc;text-align:center;width:80px;">定义</td><td colspan="2"><b>int EMP4_SetAudioFile(int hFileObj, const char *szAudioFile);
</b></td><tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">设置合并文件的音频文件
</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center;">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr style="text-align:center"><td>hFileObj</td><td>合并文件操作句柄（CreateFormatFile返回值）</td></tr>
<tr style="text-align:center"><td>szAudioFile</td><td>音频文件路径（支持MP3格式） </td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>>=0成功；<0失败</td></tr>
</table>

## 设置媒体文件所在位置

</style>
<table >
<tr><td style="background-color:#ccc;text-align:center;width:80px;">定义</td><td colspan="2"><b>int EMP4_SetSrcFileIndex(int hFileObj, const char *szSrcFile, int nIndex);
</b></td><tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">设置文件所在位置,已存在先删除原先位置的文件,再添加
</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center;">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr style="text-align:center"><td>hFileObj</td><td>合并文件操作句柄（CreateFormatFile返回值）</td></tr>
<tr style="text-align:center"><td>szSrcFile</td><td>插入文件的路径</td></tr>
<tr style="text-align:center"><td>nIndex</td><td>插入文件的位置，从0开始</td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>>=0成功；<0失败</td></tr>
</table>

## 插入一个待合并的媒体文件

</style>
<table >
<tr><td style="background-color:#ccc;text-align:center;width:80px;">定义</td><td colspan="2"><b>int EMP4_InsertSrcFile(int hFileObj, const char *szSrcFile, int nIndex);
</b></td><tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">插入一个待合并的媒体文件
</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center;">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr style="text-align:center"><td>hFileObj</td><td>合并文件操作句柄（CreateFormatFile返回值）</td></tr>
<tr style="text-align:center"><td>szSrcFile</td><td>插入文件的路径</td></tr>
<tr style="text-align:center"><td>nIndex</td><td>插入文件的位置，从0开始</td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>>=0成功；<0失败</td></tr>
</table>

## 移除一个待合并的媒体文件

</style>
<table >
<tr><td style="background-color:#ccc;text-align:center;width:80px;">定义</td><td colspan="2"><b>int EMP4_RemoveSrcFile(int hFileObj, const char *szSrcFile);
</b></td><tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">移除一个待合并的媒体文件
</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center;">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr style="text-align:center"><td>hFileObj</td><td>合并文件操作句柄（CreateFormatFile返回值）</td></tr>
<tr style="text-align:center"><td>szSrcFile</td><td>移除文件的路径</td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>>=0成功；<0失败</td></tr>
</table>

## 开始合并媒体文件

</style>
<table >
<tr><td style="background-color:#ccc;text-align:center;width:80px;">定义</td><td colspan="2"><b>int EMP4_StartFormate(int hFileObj);
</b></td><tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">开始合并媒体文件
</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center;">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr style="text-align:center"><td>hFileObj</td><td>合并文件操作句柄（CreateFormatFile返回值）</td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>>=0成功；<0失败</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>EUIMSG.EMSG_MF_ON_EDIT_FILE：返回合并的进度及结果
EUIMSG.EMSG_MF_ON_SUB_FILE  
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>0~100:进度 200:成功 <0:失败
</td></tr>
</table>

## 取消合并媒体文件

</style>
<table >
<tr><td style="background-color:#ccc;text-align:center;width:80px;">定义</td><td colspan="2"><b>int EMP4_CancelFormate(int hFileObj);
</b></td><tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">取消合并媒体文件
</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center;">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr style="text-align:center"><td>hFileObj</td><td>合并文件操作句柄（CreateFormatFile返回值）</td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>>=0成功；<0失败</td></tr>
</table>

## 清除合并媒体文件

</style>
<table >
<tr><td style="background-color:#ccc;text-align:center;width:80px;">定义</td><td colspan="2"><b>int EMP4_DestoryFormate(int hFileObj)
</b></td><tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">清除合并媒体文件
</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center;">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr style="text-align:center"><td>hFileObj</td><td>合并文件操作句柄（CreateFormatFile返回值）</td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>>=0成功；<0失败</td></tr>
</table>
