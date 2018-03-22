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
<tr><td style="background-color:#ccc;text-align:center;width:80px;">定义</td><td colspan="2"><b>int FUN_Init(int nParam = 0, SInitParam *pParam = NULL);
</b></td><tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">函数库初始化(整个程序只需要调用一次)
</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center;">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr style="text-align:center"><td>nType</td><td>保留</td></tr>
<tr style="text-align:center"><td>pParam</td><td><pre>typedef struct SInitParam
{
    int nAppType;
char nSource[64]; // “xmshop”：商城（默认） “kingsun”：勤上
char sLanguage[32]; //中文 zh 英文 en 
}SInitParam;</pre>
</td><tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>详见错误码说明
</td><tr>
</table>

## 反初始化

<table>
<tr><td style="background-color:#ccc;text-align:center;width:200px;">定义</td><td colspan="2"><b>void FUN_UnInit(int nType = 0);</b></td><tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">函数库反初始化
</td></tr>
</table>

## 初始化服务（本地登入）

<table >
<tr><td style="background-color:#ccc;text-align:center;width:100px;">定义</td><td colspan="2">int FUN_SysInit(const char *szDBFile);</td><tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">初始化服务，适用于本地登入</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr style="text-align:center"><td>szDBFile</td><td>本地设备信息数据存储文件的路径
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>详见错误码说明</td><tr>
</table>

## 初始化服务（AP模式）

<table >
<tr><td style="background-color:#ccc;text-align:center;width:100px;">定义</td><td colspan="2">int FUN_SysInitAsAPModel(const char *szDBFile);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">初始化服务，适用于AP模式
</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr style="text-align:center"><td>szDBFile</td><td>AP模式设备信息存储的数据文件路径
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>详见错误码说明</td><tr>
</table>

## 初始化服务（云登录） 

<table >
<tr><td style="background-color:#ccc;text-align:center;width:100px;">定义</td><td colspan="2">int FUN_SysInit(const char *szIP, int nPort);
</td><tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">初始化服务，适用于云登入
</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">szIP</td><td style="text-align:center">服务器ip</td></tr>
<tr><td style="text-align:center">nPort</td><td style="text-align:center">端口号</td><tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>详见错误码说明
</td><tr>
</table>

## 初始化（NetSDK）

<table >
<tr><td style="background-color:#ccc;text-align:center;width:100px;">定义</td><td colspan="2">int FUN_InitNetSDK()</td><tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">初始化NetSDK</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr style="height:30px"><td></td><td></td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>详见错误码说明</td><tr>
</table>

## 反初始化（NetSDK）

<table>
<tr><td style="background-color:#ccc;text-align:center;width:100px;">定义</td><td colspan="2">void FUN_UnInitNetSDK();</td><tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">反初始化NetSDK</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr style="height:30px"><td></td><td></td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>详见错误码说明</td><tr>
</table>

## 初始化app证书

<table >
<tr><td style="background-color:#ccc;text-align:center;width:100px;">定义</td><td colspan="2">iint FUN_XMCloundPlatformInit(const char *uuid, const char *appKey, const char *appSecret, int movedCard);</td><tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">初始化app证书，app运行调用一次即可
</td></tr>
<tr><td rowspan="5" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr style="text-align:center"><td>uuid</td><td>客户唯一标识</td></tr>
<tr style="text-align:center"><td>appKey</td><td>应用唯一标识符</td></tr>
<tr style="text-align:center"><td>appSecret</td><td>应用密钥</td></tr>
<tr style="text-align:center"><td>movedCard</td><td>移动取模基数</td></tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>0</td><tr>
</table>

## 初始化服务器ip和port

<table >
<tr><td style="background-color:#ccc;text-align:center;width:100px;">定义</td><td colspan="2">int FUN_SysSetServerIPPort(const char *szKey, const char *szServerIP, int nServerPort);
</td><tr>
<tr><td style="background-color:#ccc;text-align:center">描述</td><td colspan="2">如果帐户服务器IP不是默认，使用此接口进行配置
</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">参数说明</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">说明
</td></tr>
<tr><td style="text-align:center">szKey</td><td style="text-align:center">帐户服务id，通用账号服务szKey:"MI_SERVER"</td></tr>
<tr><td style="text-align:center">szServerIP</td><td style="text-align:center">服务器ip</td></tr>
<tr><td style="text-align:center">nServerPort</td><td style="text-align:center">端口号</td><tr>
<tr><td style="background-color:#ccc;text-align:center">返回</td><td colspan="2" style="text-align:center";>0
</td><tr>
</table>
