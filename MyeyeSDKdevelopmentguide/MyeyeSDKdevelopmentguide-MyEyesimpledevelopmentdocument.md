## 简介

### 概述

本文档为配套ClientSDK演示程序的说明，介绍了该Demo的界面以及操作流程。<br/>
由于本Demo仅是作为演示程序使用，仅代表了控件的接口的使用方法，Demo程序的设计上可能不完善之处，特此说明。

### 前期准备

在启动Demo前，请先确认执行程序下的文件是否完整：<br/>

<img src="http://open.xmeye.net/upload/image/20161110/1478763898739097377.png">

启动Demo程序，启动后界面如下<br/>

<img src="http://open.xmeye.net/upload/image/20161110/1478763898736052953.png">


## 功能模块使用说明

### 登录

调用接口：<br/>
Int P_Client_LoginServer (<br/>
)

参数来源：<br/>
<div style="margin-left:30px;">
   编辑框“IP地址”、“端口号”、“用户名”、“密码”。
</div>
操作说明：
<div style="margin-left:30px;">
本操作应该是作为程序启动后的第一步功能区界面如下：
</div>

<img src="http://open.xmeye.net/upload/image/20161110/1478763898733004835.png">

<div style="margin-left:30px;">
在编辑框中按提示输入ip地址、端口号、用户名、密码，再点击登录即可。
</div>

### 获取设备信息

控件基础设置以及设备获取等，界面如下<br/>

<img src="http://open.xmeye.net/upload/image/20161110/1478763898800031683.png">

### 获取设备信息

调用接口：
<div style="margin-left:30px;">
    <lable><b>Int</b></lable>  P_Client_GetDevicesLen;
</div>
操作说明：
<div style="margin-left:30px;">
    获取设备信息缓冲长度
</div>
<label>int</label>  P_Client_GetDevices(<label>char</label>  *pBuf, <lable>int</label>  nLen)
<div style="margin-left:30px;">
获取具体设备信息，获取到的信息使用CFLOrganization解析成一个个节点，显示在下方的树控件中
</div>

<img src="http://open.xmeye.net/upload/image/20161110/1478763898810097184.png">如：
<br/>

### 实时监控

设备树上选择一个通道的节点(选择设备节点无效)<br>
点击OPenVideo，成功后，会在下方显示图像，并且Handle中显示播放句柄

<img src="http://open.xmeye.net/upload/image/20161110/1478763898839095226.png">如：

### 打开视频

调用接口：
<div style="margin-left:30px;">
P_Client_ConnectRealPlay
</div>
 
### 关闭视频

调用接口：
<div style="margin-left:30px;">
   P_Client_StopRealPlay
</div>
参数来源：
<div style="margin-left:30px;">
    编辑框“视频ID”
</div>
操作说明：
<div style="margin-left:30px;">
    点击关闭指定ID的视频，并无效化该ID。
</div>
 
### 打开对讲

调用接口：
<div style="margin-left:30px;">
P_Client_StartTalk
</div>
参数来源：
<div style="margin-left:30px;">
    同打开视频，设备树中选择一个设备节点(通道节点无效)
</div>
操作说明：
<div style="margin-left:30px;">
    点击Talk
</div>
 
### 关闭对讲

调用接口：
<div style="margin-left:30px;">
P_Client_StopTalk
</div>
参数来源：
<div style="margin-left:30px;">
    编辑框“对讲ID”
</div>
操作说明：
<div style="margin-left:30px;">
    关闭指定对讲，成功后，该对讲ID将无效化。
</div>

### 录像回放

设备树中，选择一个通道节点，右键，如
<img src="http://open.xmeye.net/upload/image/20161110/1478763898822025791.png">
点击“Playback“后进入回放界面，如：

<img src="http://open.xmeye.net/upload/image/20161110/1478763898852035309.png">

### 查询

调用接口：
<div style="margin-left:30px;">
P_Client_QueryRecord
</div>
参数来源：
<div style="margin-left:30px;">
“开始时间”、“结束时间”、“录像来源”、“录像类型”→(组成)<br/>
→查询字符串<br/>
编辑框“设备ID”、“通道号”<br/>
超时时间 = 0，即默认10000ms<br/>
</div>
操作说明：
<div style="margin-left:30px;">
在“开始时间”、“结束时间”中输入时间，如：<br/>
2011-1-1-00-00-00、2011-1-01--23-59-59<br/>
点击查询后，会在列表中显示查询到的录像信息，如：<br/>
</div>

<img src="http://open.xmeye.net/upload/image/20161110/1478763898864063696.png">
<br/>

### 注意

查询中心录像时，需要注意直连模式为“非直连”，否则将返回错误。

### 回放

选择一条录像信息，点击Play，则播放录像

#### 开始回放

调用接口：
<div style="margin-left:30px;">
P_Client_PlaybackByFile
</div>

#### 停止回放

调用接口：
<div style="margin-left:30px;">
P_Client_StopPlaybackByFile
</div><br/>
也可以输入开始时间和结束时间后，直接点击TimePlay进行按时间回放
调用接口 P_Client_PlaybackByTime

#### 回放控制

调用接口：
<div style="margin-left:30px;">
P_Client_PlaybackControl
</div><br/>

#### 回放进度

调用接口：
<div style="margin-left:30px;">
P_Client_PlaybackByTime
</div>
操作说明：
<div style="margin-left:30px;">
通过这个接口获取到当前播放的时间，同时根据开始时间和结束时间，外部自己计算进度
</div><br/>
