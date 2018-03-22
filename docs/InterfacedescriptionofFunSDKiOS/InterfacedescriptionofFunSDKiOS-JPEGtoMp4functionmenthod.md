## 创建

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
<tr><td style="background-color:#ccc;text-align:center;width:80px;">定义</td><td colspan="2"><b>int FUN_Jpeg2Mp4_Create(UI_HANDLE hUser, const char *szDesFileName, int nFrameRate, int nBits, int nWidth, int nHeight);
</b></td><tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">创建。使用流程参考“jpeg转MP4.dcox”文档
</td></tr>
<tr><td rowspan="6" style="background-color:#ccc;text-align:center;">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr style="text-align:center"><td>szDesFileName</td><td>目的文件名（绝对路径）</td></tr>
<tr style="text-align:center"><td>nFrameRate</td><td>帧率</td></tr>
<tr style="text-align:center"><td>nBits</td><td>码率， 一般填0，表示中码率。码率与分辨率对应关系见“jpeg转MP4.dcox”文档</td></tr>
<tr style="text-align:center"><td>nWidth</td><td>目的文件宽</td></tr>
<tr style="text-align:center"><td>nHeight</td><td>目的文件高</td><tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>函数返回句柄，之后添加、取消、关闭时使用
</td><tr>
<tr><td rowspan="5" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG . EMSG_JPEG_TO_MP4_ON_PROGRESS 每1s会发送一条转换进度消息
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==EE_OK：成功；<0：失败，详见错误码说明 >0转换进度，在源文件添加完成后有效
</td></tr>
<tr><td style="text-align:center">arg2
</td><td>已编码帧数
</td></tr>
<tr><td style="text-align:center">str
</td><td>目的文件名
</td></tr>
</table>

## 添加文件

<table >
<tr><td style="background-color:#ccc;text-align:center;width:80px;">定义</td><td colspan="2"><b>int FUN_Jpeg2Mp4_Add(FUN_HANDLE hDecoder, const char *szFileName);
</b></td><tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">添加要转换的文件
</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center;">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr style="text-align:center"><td>hDecoder</td><td>Jpeg2Mp4Create返回的值）</td></tr>
<tr style="text-align:center"><td>szFileName</td><td>要转换的文件名（绝对路径）</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG . EMSG_JPEG_TO_MP4_ADD_FILE
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>已编码帧数
</td></tr>
<tr><td style="text-align:center">arg2
</td><td>总添加帧数
</td></tr>
</table>

## 关闭

<table >
<tr><td style="background-color:#ccc;text-align:center;width:80px;">定义</td><td colspan="2"><b>int FUN_Jpeg2Mp4_Close(FUN_HANDLE hDecoder);
</b></td><tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">全部文件已经添加进去了,关闭.-调用真正结束看返回的JPEG_TO_MP4_ON_PROGRESS
</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center;">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr style="text-align:center"><td>hDecoder</td><td>Jpeg2Mp4Create返回的值）</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG . EMSG_JPEG_TO_MP4_CLOSE
</td></tr>
</table>

## 取消转换

<table >
<tr><td style="background-color:#ccc;text-align:center;width:80px;">定义</td><td colspan="2"><b>int FUN_Jpeg2Mp4_Cancel(FUN_HANDLE hDecoder);
</b></td><tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">取消转换--->真正取消看返回的JPEG_TO_MP4_ON_PROGRESS
</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center;">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr style="text-align:center"><td>hDecoder</td><td>Jpeg2Mp4Create返回的值）</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG . EMSG_JPEG_TO_MP4_CANCEL
</td></tr>
</table>
