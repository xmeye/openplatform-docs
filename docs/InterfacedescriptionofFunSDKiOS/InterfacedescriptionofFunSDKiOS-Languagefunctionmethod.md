## 用文件初始化语言部分

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
<tr><td style="background-color:#ccc;text-align:center;width:80px;">定义</td><td colspan="2"><b>int Fun_InitLanguage(const char *szLanguaeFileName);
</b></td><tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">通过语言文本文件进行初始化语言
</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center;">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr style="text-align:center"><td>szLanguaeFileName</td><td>要初始化的语言文件名</td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>返回1：成功 返回0/-1：失败
</td><tr>
<tr><td rowspan="5" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>
</table>

## 翻译语言部分

</style>
<table >
<tr><td style="background-color:#ccc;text-align:center;width:80px;">定义</td><td colspan="2"><b>const char *Fun_TS(const char *szKey, const char *szDefault = NULL);
</b></td><tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">多语言翻译
</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center;">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr style="text-align:center"><td>szKey</td><td>要翻译的字符串</td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>翻译出来的String字符串
</td><tr>
<tr><td rowspan="5" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>
</table>
