# 1.Brief introduction

## Summary

This document introduces the Demo interface and operating procedures in order to support the instructions of ClientSDK demonstration program.<br/>
Since this Demo is only used as a demonstration program and only represents the usage method of control interface. The design of Demo program may not be perfect, hereby note.

## Preliminary preparation

Before starting Demo, please make sure that the file in the executing program is complete:<br/>

<img src="http://open.xmeye.net/upload/image/20161110/1478763898739097377.png">

Start Demo program, the interface is as follows<br/>
<img src="http://open.xmeye.net/upload/image/20161110/1478763898736052953.png">
<br/><br/>

## Function module instructions


## Login

Calling interface：<br/>
Int P_Client_LoginServer (<br/>
)

Parameters source: <br/>
<div style="margin-left:30px;">
   Edit box “IP address”, “port number”, “username”, “password”.
</div>
Operation instructions:
<div style="margin-left:30px;">
This operation should be used as the first step after the program startup.
</div>
Function area interface is as follows:
<img src="http://open.xmeye.net/upload/image/20161110/1478763898733004835.png">

<div style="margin-left:30px;">
In the edit box, follow the prompts to input the IP address, port number, username, password, and then click to login.
</div>

## Get device information

Control basic settings and device acquisition, the interface is as follows<br/>
<img src="http://open.xmeye.net/upload/image/20161110/1478763898800031683.png">

## Get device information

Calling interface:
<div style="margin-left:30px;">
    <lable style="color:blue;"><b>Int</b></lable>  P_Client_GetDevicesLen;
</div>
Operation instructions:
<div style="margin-left:30px;">
   Get the device information buffering length
</div>
<label style="color:blue;">int</label>  P_Client_GetDevices(<label style="color:blue;">char</label>  *pBuf, <lable style="color:blue;">int</label>  nLen)
<div style="margin-left:30px;">
Get the specific device information, acquired information uses CFLOrganization to parse into nodes, showing in the tree control below.
</div>
For example:
<img src="http://open.xmeye.net/upload/image/20161110/1478763898810097184.png">
<br/>

## Real-time monitoring

Select a channel node on the device tree (select device node is invalid).<br>
Click OPenVideo, after the success, it will display the image below, and display play handle in Handle

<img src="http://open.xmeye.net/upload/image/20161110/1478763898839095226.png">

## Open video

Calling interface:
<div style="margin-left:30px;">
P_Client_ConnectRealPlay
</div>
 
## Close video

Calling interface:
<div style="margin-left:30px;">
   P_Client_StopRealPlay
</div>
Parameters source: 
<div style="margin-left:30px;">
     Edit box “video ID”
</div>
Operation instructions:
<div style="margin-left:30px;">
     Click to close the video which is specified ID and this ID will invalidate.
</div>
 

 

## Open the intercom

Calling interface:
<div style="margin-left:30px;">
P_Client_StartTalk
</div>
Parameters source:
<div style="margin-left:30px;">
   Open the video, select a device node in the device tree (channel node is invalid).
</div>
Operation instructions:
<div style="margin-left:30px;">
     Click Talk
</div>
 

## Close the intercom

Calling interface:
<div style="margin-left:30px;">
P_Client_StopTalk
</div>
Parameters source:
<div style="margin-left:30px;">
     Edit box “intercome ID”
</div>
Operation instructions:
<div style="margin-left:30px;">
    Close the specified intercom, after the success, the intercom ID will invalidate.
</div>
 
## Video playback

Select a channel node in the device tree, right-click, for example
<img src="http://open.xmeye.net/upload/image/20161110/1478763898822025791.png">
Click “Playback” into the playback interface, for example:
<img src="http://open.xmeye.net/upload/image/20161110/1478763898852035309.png">
<br/>

## Query

Calling interface:
<div style="margin-left:30px;">
P_Client_QueryRecord
</div>
Parameters source:
<div style="margin-left:30px;">
“start time”, “end time”, “video source”, “video type” à(compose)<br/>
àQuery string<br/>
Edit box “device ID”, “channel number”<br/>
Timeout = 0, that is, default 10000ms<br/>
</div>
Operation instructions:
<div style="margin-left:30px;">
Input time in “start time” and “end time”, for example:<br/>
2011-1-1-00-00-00、2011-1-01--23-59-59<br/>
 After click the query, it will display the information in the list, for example:<br/>
</div>
<img src="http://open.xmeye.net/upload/image/20161110/1478763898864063696.png">
<br/>

## Note

When query the center video, need to pay attention that direct mode is “non direct”, otherwise it will return an error.

## Playback

Select video information, click to Play and play video

## Start playback
Calling interface:
<div style="margin-left:30px;">
P_Client_PlaybackByFile
</div>

## Stop playback

Calling interface:
<div style="margin-left:30px;">
P_Client_StopPlaybackByFile
</div><br/>
After input the start time and the end time, directly click the TimePlay to playback by time<br/>
Calling interface P_Client_PlaybackByTime

## Playback control

Calling interface:
<div style="margin-left:30px;">
P_Client_PlaybackControl
</div><br/>

## Playback progress

Calling interface:
<div style="margin-left:30px;">
P_Client_PlaybackByTime
</div>
Operation instructions:
<div style="margin-left:30px;">
Get the current play time via this interface, and meanwhile according to the start time and end time, the external calculate the progress on their own.
</div><br/>
