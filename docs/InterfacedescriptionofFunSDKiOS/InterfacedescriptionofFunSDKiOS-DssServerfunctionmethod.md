## 连接设备某路码流

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
<tr><td style="background-color:#ccc;text-align:center;width:80px;">定义</td><td colspan="2"><b>int XD_LinkMedia(UI_HANDLE hUser, const char * uuid, int mediaId ,int nSeq = 0);
</b></td><tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">连接设备某路码流
</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center;">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr style="text-align:center"><td>uuid</td><td>序列号</td>
<tr style="text-align:center"><td>mediaId</td><td>媒体ID*</td>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";></td><tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>EUIMSG.EMSG_XD_LinkMedia=7001 (7001)
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>返回结果 < 0失败 >=0成功 详见详见错误码说明
</td></tr>
<tr><td style="text-align:center">str
</td><td>dssIp
</td></tr>
</table>

## 断开连接

</style>
<table >
<tr><td style="background-color:#ccc;text-align:center;width:80px;">定义</td><td colspan="2"><b>int XD_UnlinkMedia(UI_HANDLE hUser, const char * uuid, int mediaId ,int nSeq = 0);
</b></td><tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">断开连接
</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center;">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr style="text-align:center"><td>uuid</td><td>序列号</td>
<tr style="text-align:center"><td>mediaId</td><td>媒体ID*</td>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";></td><tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>EUIMSG.EMSG_XD_UnlinkMedia (7002)
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>返回结果 < 0失败 >=0成功 详见详见错误码说明
</td></tr>
</table>

## 查询历史点击数前num的设备

</style>
<table >
<tr><td style="background-color:#ccc;text-align:center;width:80px;">定义</td><td colspan="2"><b>int XD_PublicHistoryList(UI_HANDLE hUser, const int num, int nSeq = 0);
</b></td><tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">查询历史点击数前num的设备
</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center;">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr style="text-align:center"><td>num</td><td>个数</td>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";></td><tr>
<tr><td rowspan="6" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>EUIMSG.EMSG_XD_PublicHistoryList (7003)
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>0：失败，详见错误码说明 >=0查询到的设备信息大小
</td></tr>
<tr><td style="text-align:center">arg2
</td><td>查询到的设备个数
</td></tr>
<tr><td style="text-align:center">str
</td><td>失败返回错误信息，成功返回””
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>查询到的设备信息
</td></tr>
</table>

## 查询当前在线数前num的设备

</style>
<table >
<tr><td style="background-color:#ccc;text-align:center;width:80px;">定义</td><td colspan="2"><b>int XD_PublicCurrentList(UI_HANDLE hUser, const int num, int nSeq = 0);
</b></td><tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">查询当前在线数前num的设备
</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center;">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr style="text-align:center"><td>num</td><td>个数</td>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";></td><tr>
<tr><td rowspan="6" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>EUIMSG.EMSG_XD_PublicCurrentList (7004)
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>0：失败，详见错误码说明 >=0查询到的设备信息大小
</td></tr>
<tr><td style="text-align:center">arg2
</td><td>查询到的设备个数
</td></tr>
<tr><td style="text-align:center">str
</td><td>失败返回错误信息，成功返回””
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>查询到的设备信息
</td></tr>
</table>

##查询设备的点击量和在线数

</style>
<table >
<tr><td style="background-color:#ccc;text-align:center;width:80px;">定义</td><td colspan="2"><b>int XD_PublicDevInfo(UI_HANDLE hUser, const char * uuid, int nSeq = 0);
</b></td><tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">查询设备的点击量和在线数
</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center;">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr style="text-align:center"><td>uuid</td><td>设备序列号</td>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";></td><tr>
<tr><td rowspan="6" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>EUIMSG  . EMSG_XD_PublicDevInfo (7005)
</td></tr>
<tr><td style="text-align:center">arg1
</td><td><0：失败，详见错误码说明 >=0历史点击量
</td></tr>
<tr><td style="text-align:center">arg2
</td><td>当前点击量
</td></tr>
<tr><td style="text-align:center">str
</td><td>查询到的设备个数/在线数
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>失败返回错误信息，成功返回””
</td></tr>
</table>

##获取设备的缩略图

</style>
<table >
<tr><td style="background-color:#ccc;text-align:center;width:80px;">定义</td><td colspan="2"><b>int XD_FetchPicture(UI_HANDLE hUser, const char *ip, const char *uuid,const char *szFileName,int nSeq = 0);
</b></td><tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">获取设备的缩略图，注意:buf的内存需要在外面delete
</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center;">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr style="text-align:center"><td>ip</td><td>ip地址</td>
<tr style="text-align:center"><td>uuid</td><td>设备序列号</td>
<tr style="text-align:center"><td>szFileName</td><td>文件名</td>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";></td><tr>
<tr><td rowspan="6" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>EUIMSG.EMSG_XD_FetchPicture (7006)
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==EE_OK：成功；<0：失败，详见错误码说明
</td></tr>
<tr><td style="text-align:center">str
</td><td>文件名（绝对路径）
</td></tr>
</table>
