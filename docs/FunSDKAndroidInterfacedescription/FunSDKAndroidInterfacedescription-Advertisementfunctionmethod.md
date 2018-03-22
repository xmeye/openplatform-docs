## 初始化

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
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int Init(byte []pSClientMessageInfo);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">广告模块类的一些参数初始化</td></tr>
tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td  style="text-align:center">pSClientMessageInfo</td>
<td>广告请求的参数 详见SClientMessageInfo </td></tr>
</table>

## 更新广告
</style>
<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">void UpdateMessage();</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">检测服务器广告版本是否进行了变更，然后进行更新</td></tr>
<tr><td style="background-color:#ccc;text-align:center">备注</td><td colspan="2" style="text-align:center";>向服务器发送的请求信息:<br/>/advert?app=%s&advertUse=%s&imgWidth=%d&imgHeight=%d<br/>
参数说明：App：应用唯一的短名称
advertUse 广告用途 
imgWidth 广告宽
imgHeight广告高 //视频默认传0或者不传
</td><tr>
</table>

## 获取广告图片路径
</style>
<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">String GetPicPath();</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">获取广告图片路径</td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>返回广告图片路径 格式:URL1; URL2 //广告路径结尾没有分号
</td><tr>
</table>

## 获取广告视频路径
</style>
<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">String GetVideoPath();</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">获取广告视频路径</td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>返回广告视频路径 格式:URL1; URL2 //广告路径结尾没有分号
</td><tr>
</table>

## 获取广告界面跳转链接路径
</style>
<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">String GetADUrl();</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">获取广告界面跳转链接路径</td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>返回广告界面跳转链接路径(String)
</td><tr>
</table>

## 获取广告显示时间
</style>
<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int GetTimeLong();</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">获取广告显示时间</td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>返回广告显示时间(int)
</td><tr>
</table>


## 获取广告配置信息(String)
</style>
<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">String GetValue(String key, String defValue);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">获取广告配置信息(String)</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td  style="text-align:center">key</td>
<td>请求的参数 详见保存在手机内存的AdvertInfo.txt<br/>
例 #define KEY_LOC_Version "CM_AdvertVersion"  当前版本号
</td></tr>
<tr><td  style="text-align:center">defValue</td>
<td>默认值</td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>返回网络配置信息(String)
</td><tr>
</table>

## 获取广告配置信息(int)
</style>
<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">定义</td><td colspan="2">int GetIntValue(String key, int nDefValue);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">获取广告配置信息(int)</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td  style="text-align:center">key</td>
<td>请求的参数 详见保存在手机内存的AdvertInfo.txt<br/>
例 #define KEY_LOC_Version "CM_AdvertVersion"  当前版本号
</td></tr>
<tr><td  style="text-align:center">defValue</td>
<td>默认值</td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>返回网络配置信息(String)
</td><tr>
</table>

## 更新当前最新的系统消息

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
<tr><td style="background-color:#ccc;text-align:center;width:80px;">定义</td><td colspan="2"><b>int UpdateSysMsg(int hUser);
</b></td><tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">获取当前最新系统消息
</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center;">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr style="text-align:center"><td>hUser</td><td>接收分割进度及结果回调</td>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>返回结果 < 0失败 >=0成功
</td><tr>

<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG . CM_ON_GET_SYS_MSG
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>系统消息个数
</td></tr>
<tr><td style="text-align:center">pData
</td><td>系统消息信息 json格式 
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">备注</td><td colspan="2">/announcement?bid=%s&lan=%s&type=%s<br/>
参数说明：<br/>
bid: Android的包名或IOS的Boundle Idtentifier<br/>
lan: 语言 //默认为简体中文，；目前支持简体中文、英两种语言；<br/>
type:系统类型<br/> //#define SYS_MSG_CLIENT    "ios"<br/>
//#define SYS_MSG_CLIENT    "android"
</td></tr>
</table>

## 不再显示当前最新系统消息

</style>
<table >
<tr><td style="background-color:#ccc;text-align:center;width:80px;">定义</td><td colspan="2"><b>int NoShowMsg(long nMsgId);
</b></td><tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">不再显示当前最新系统消息
</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center;">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr style="text-align:center"><td>nMsgId</td><td>消息ID </td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>返回结果 < 0失败 >=0成功</td></tr>
</table>

## 获取系统

</style>
<table >
<tr><td style="background-color:#ccc;text-align:center;width:80px;">定义</td><td colspan="2"><b>int GetSysMsgList(int hUser);
</b></td><tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">获取当前最新系统消息
</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center;">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr style="text-align:center"><td>hUser</td><td>接收分割进度及结果回调</td>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>返回结果 < 0失败 >=0成功
</td><tr>

<tr><td rowspan="4" style="background-color:#ccc;text-align:center">结果消息
</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center;">说明
</td></tr>
<tr><td style="text-align:center">id
</td><td>消息值：EUIMSG . CM_ON_GET_SYS_MSG_LIST
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>系统消息个数
</td></tr>
<tr><td style="text-align:center">pData
</td><td>系统消息信息 json格式 
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">备注</td><td colspan="2">
/announcement/list?bid=com.xm.xmcsee&lan=en&type=android<br/>
参数说明：<br/>
bid: Android的包名或IOS的Boundle Idtentifier<br/>
lan: 语言 //默认为简体中文，；目前支持简体中文、英两种语言；<br/>
type:系统类型<br/> //#define SYS_MSG_CLIENT    "ios"<br/>
//#define SYS_MSG_CLIENT    "android"
</td></tr>
</table>
