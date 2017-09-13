(调用的接口函数参数请参考接口函数的使用)

## 初始化

<style>
	table{
		border-collapse:collapse;
		width:100%;
		text-align:center;
	}
	table tr td{
		border:1px solid #fff;
	}
</style>
<table>
<tr><td style="background-color:#dedebe">调用函数</td><td style="background-color:#B9B973">意义</td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_Init()
</td><td style="background-color:#B9B973">SDK初始化</td></tr>
</table>


## SDK功能信息获取

<table>
<tr><td style="background-color:#dedebe">调用函数</td><td style="background-color:#B9B973">意义</td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_SetDVRMessCallBack()
</td><td style="background-color:#B9B973">设置报警消息回调</td></tr>
</table>



## 登录连接设备

<table>
<tr><td style="background-color:#dedebe">调用函数</td><td style="background-color:#B9B973">意义</td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_Login()
</td><td style="background-color:#B9B973">登录设备</td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_LoginEx()
</td><td style="background-color:#B9B973">登录设备</td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_SetupAlarmChan()
</td><td style="background-color:#B9B973">报警消息订阅</td></tr>
</table>


## 设备功能操作与信息获取

<table>
<tr><td style="background-color:#dedebe">调用函数</td><td style="background-color:#B9B973">意义</td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_GetDevConfig()
</td><td style="background-color:#B9B973">获取配置</td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_SetDevConfig()
</td><td style="background-color:#B9B973">保存配置</td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_FindDVRLog()
</td><td style="background-color:#B9B973">查询日志 </td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_PTZControl()
</td><td style="background-color:#B9B973">云台控制 </td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_PTZControlEx()
</td><td style="background-color:#B9B973">云台控制 </td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_OpenTransComChannel()
</td><td style="background-color:#B9B973">透明串口控制打开</td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_CloseTransComChannel()
</td><td style="background-color:#B9B973">关闭</td></tr>
</table>


## 实时监视通道

<table>
<tr><td style="background-color:#dedebe">调用函数</td><td style="background-color:#B9B973">意义</td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_RealPlay()
</td><td style="background-color:#B9B973">打开监视通道</td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_StopRealPlay()
</td><td style="background-color:#B9B973">关闭监视通道</td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_SetRealDataCallBack()
</td><td style="background-color:#B9B973">监视数据回调保存 </td></tr>
</table>


## 回放下载

<table>
<tr><td style="background-color:#dedebe">调用函数</td><td style="background-color:#B9B973">意义</td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_FindFile()
</td><td style="background-color:#B9B973">按文件查找录像文件</td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_FindFileByTime()
</td><td style="background-color:#B9B973">按时间查找录像文件</td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_PlayBackByName()
</td><td style="background-color:#B9B973">按文件名回放录像 </td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_PlayBackByName_V2()
</td><td style="background-color:#B9B973"> </td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_PlayBackByTime()
</td><td style="background-color:#B9B973">按时间回放录像 </td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_PlauBackByTimeEx()
</td><td style="background-color:#B9B973"> </td></tr>
</table>


## 远程控制

<table>
<tr><td style="background-color:#dedebe">调用函数</td><td style="background-color:#B9B973">意义</td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_Upgrade()
</td><td style="background-color:#B9B973">远程升级</td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_GetUpgradeState()
</td><td style="background-color:#B9B973">获取升级的状态</td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_CloseUpgradeHandle()
</td><td style="background-color:#B9B973">关闭升级 </td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_ControlDVR()
</td><td style="background-color:#B9B973">重启/清除日志</td></tr>
</table>


## 注销断开设备

<table>
<tr><td style="background-color:#dedebe">调用函数</td><td style="background-color:#B9B973">意义</td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_CloseAlarmChan()
</td><td style="background-color:#B9B973">停止报警消息订阅</td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_Logout()
</td><td style="background-color:#B9B973">断开连接</td></tr>
</table>


## 释放SDK资源

<table>
<tr><td style="background-color:#dedebe">调用函数</td><td style="background-color:#B9B973">意义</td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_Cleanup()
</td><td style="background-color:#B9B973">SDK退出 </td></tr>
</table>
