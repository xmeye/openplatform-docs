  
<div style="text-align:center;font-size:25px;"><b>Simple development process
</b>(The calingl interface function parameters, please refer to the use of the interface function)</div>

#### 1.Initialization  ####
<br/>

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
<tr><td style="background-color:#dedebe">Calling function</td><td style="background-color:#B9B973">Significance</td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_Init()
</td><td style="background-color:#B9B973">SDK initialization</td></tr>
</table>
<br/>

#### 2.SDK functional information acquisition ####
<br/>

<table>
<tr><td style="background-color:#dedebe">Calling function</td><td style="background-color:#B9B973">Significance</td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_SetDVRMessCallBack()
</td><td style="background-color:#B9B973">Set alarm message callback</td></tr>
</table>
<br/>


####  3.Login connection device  ####
<br/>

<table>
<tr><td style="background-color:#dedebe">Calling function</td><td style="background-color:#B9B973">Significance</td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_Login()
</td><td style="background-color:#B9B973">Login device</td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_LoginEx()
</td><td style="background-color:#B9B973">Login device</td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_SetupAlarmChan()
</td><td style="background-color:#B9B973">Alarm message subscription</td></tr>
</table>
<br/>

####   4.Device function operation and information acquisition ####
<br/>

<table>
<tr><td style="background-color:#dedebe">Significance</td><td style="background-color:#B9B973">Significance</td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_GetDevConfig()
</td><td style="background-color:#B9B973">Get configuration</td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_SetDevConfig()
</td><td style="background-color:#B9B973">Save configuration</td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_FindDVRLog()
</td><td style="background-color:#B9B973">Query log </td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_PTZControl()
</td><td style="background-color:#B9B973">PTZ Control  </td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_PTZControlEx()
</td><td style="background-color:#B9B973">PTZ Control  </td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_OpenTransComChannel()
</td><td style="background-color:#B9B973">Transparent serial port control open</td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_CloseTransComChannel()
</td><td style="background-color:#B9B973">Close</td></tr>
</table>
<br/>

####    5.Real-time monitoring channel ####
<br/>

<table>
<tr><td style="background-color:#dedebe">Significance</td><td style="background-color:#B9B973">Significance</td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_RealPlay()
</td><td style="background-color:#B9B973">Open monitoring channel</td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_StopRealPlay()
</td><td style="background-color:#B9B973">Close monitoring channel</td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_SetRealDataCallBack()
</td><td style="background-color:#B9B973">Monitoring data callback save </td></tr>
</table>
<br/>

####   6.Playback download  ####
<br/>

<table>
<tr><td style="background-color:#dedebe">Significance</td><td style="background-color:#B9B973">Significance</td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_FindFile()
</td><td style="background-color:#B9B973">ind video files by file</td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_FindFileByTime()
</td><td style="background-color:#B9B973">Find video files by time</td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_PlayBackByName()
</td><td style="background-color:#B9B973">Playback video by file name </td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_PlayBackByName_V2()
</td><td style="background-color:#B9B973"> </td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_PlayBackByTime()
</td><td style="background-color:#B9B973">Playback video by time </td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_PlauBackByTimeEx()
</td><td style="background-color:#B9B973"> </td></tr>
</table>
<br/>

####   7.Remote control  ####
<br/>

<table>
<tr><td style="background-color:#dedebe">Significance</td><td style="background-color:#B9B973">Significance</td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_Upgrade()
</td><td style="background-color:#B9B973">Remote upgrade</td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_GetUpgradeState()
</td><td style="background-color:#B9B973">Gets upgrade status</td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_CloseUpgradeHandle()
</td><td style="background-color:#B9B973">Close upgrade </td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_ControlDVR()
</td><td style="background-color:#B9B973">Reset / clear log</td></tr>
</table>
<br/>

####   8.Cancel disconnected device ####
<br/>

<table>
<tr><td style="background-color:#dedebe">Significance</td><td style="background-color:#B9B973">Significance</td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_CloseAlarmChan()
</td><td style="background-color:#B9B973">Stop alarm message subscription</td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_Logout()
</td><td style="background-color:#B9B973">Disconnect</td></tr>
</table>
<br/>

####    9.Release SDK resources ####
<br/>

<table>
<tr><td style="background-color:#dedebe">Significance</td><td style="background-color:#B9B973">Significance</td></tr>
<tr><td style="background-color:#dedebe">H264_DVR_Cleanup()
</td><td style="background-color:#B9B973">SDK exit  </td></tr>
</table>
<br/>