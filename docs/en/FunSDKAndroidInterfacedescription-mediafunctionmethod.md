
<div name="shishi" id="shishi" style="font-size:20px;"><b>5.1 Play device real-time video</b></div> 
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
<tr><td style="background-color:#ccc;text-align:center;width:5px;">Definition</td><td colspan="2">int MediaRealPlay(int hUser, String devId, int  nChnIndex, int  nStreamType, Object hWnd, int  nSeq)</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Play device  channel real-time video</td></tr>
<tr><td rowspan="6" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>Device serial number</td></tr>
<tr><td style="text-align:center">nChnIndex</td>
<td>Channel number (start from 0)</td></tr>
<tr><td style="text-align:center">nStreamType</td>
<td>Stream type; 0: main stream; 1: sub stream1</td></tr>
<tr><td style="text-align:center">hWnd</td>
<td>Display window GLSurfaceView20 object</td></tr>
<tr><td style="text-align:center">nSeq</td>
<td>Operating serial number (user defined)</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Return</td>
<td colspan="2">Video play object handle, it can be used to achieve the beginning of the video, video capture, video record and other operations.</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id</td>
<td>Message value：EUIMSG   .EMSG_START_PLAY</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==EE_OK：success; <0: fail, for details, see error code description</td></tr>
</table>
<br/>

<div name="yuancheng1" id="yuancheng1" style="font-size:20px;"><b>5.2 Play remote video</b></div>
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">Definition</td><td colspan="2">int MediaNetRecordPlay(int hUser, String devId, byte []sPlayBackFile, Object hWnd,   int  nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Play remote video</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">Parameters<br>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>Device serial number</td></tr>
<tr><td style="text-align:center">sPlayBackFile</td>
<td>Video information structure object H264_DVR_FILE_DATA byte stream</td></tr>
<tr><td  style="text-align:center">hWnd
</td><td>	
Display window GLSurfaceView20 object</td></tr>
<tr><td  style="background-color:#ccc;text-align:center">Return</td>
<td colspan="2">Video play object handle, it can be used to achieve the beginning of the video, video capture, video record and other operations.</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td  style="text-align:center">id
</td><td>Message value：EUIMSG   .EMSG_START_PLAY<br/>
Message in playback process will timing notify via“EUIMSG   .EMSG_ON_PLAY_INFO”<br/>
Message at the end of the playback will notify via“EUIMSG   .EMSG_ON_PLAY_END”<br/>
</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>==EE_OK：success; <0: fail, for details, see error code   description</td></tr>
</table>
<br/>

<div name="yuancheng2" id="yuancheng2" style="font-size:20px;"><b>5.3 Play remote video – by time</b></div>
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">Definition</td><td colspan="2">int   MediaNetRecordPlayByTime(int hUser,String szDevId, byte[] pH264_DVR_FINDINFO,   Object hWnd, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Play remote video – by time</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>Device serial number</td></tr>
<tr><td style="text-align:center">pH264_DVR_FINDINFO
</td><td>	
Video information structure object H264_DVR_FILE_DATA byte stream</td></tr>
<tr><td  style="text-align:center">hWnd</td>
<td>Display window GLSurfaceView20 object</td></tr>
<tr><td  style="background-color:#ccc;text-align:center">Return</td>
<td colspan="2">Video play object handle, it can be used to achieve the beginning of the video, video capture, video record and other operations.</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result <br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td  style="text-align:center">id
</td><td>Message value：EUIMSG   .EMSG_START_PLAY<br/>
Message in playback process will timing notify via“EUIMSG   .EMSG_ON_PLAY_INFO”<br/>
Message at the end of the playback will notify via“EUIMSG   .EMSG_ON_PLAY_END”<br/>
</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>==EE_OK：success; <0: fail, for details, see error code  description</td></tr>
</table>
<br/>

<div name="bendi" id="bendi" style="font-size:20px;"><b>5.4 Play local video</b></div> 
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">Definition</td><td colspan="2">INT  MediaLocRecordPlay(int   hUser, String szFileName, Object hWnd, int    nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Play local video</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr><td style="text-align:center">szFileName</td>
<td>Local file path and name</td></tr>
<tr><td  style="text-align:center">hWnd</td>
<td>Display window GLSurfaceView20 object</td></tr>
<tr><td  style="background-color:#ccc;text-align:center">Return</td>
<td colspan="2">Video play object handle, it can be used to achieve the beginning of the video, video capture and other operations.</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result <br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td  style="text-align:center">id
</td><td>Message value：EUIMSG   .EMSG_START_PLAY<br/>
Message in playback process will timing notify via“EUIMSG   .EMSG_ON_PLAY_INFO”<br/>
Message at the end of the playback will notify via“EUIMSG   .EMSG_ON_PLAY_END”<br/>
</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>==EE_OK：success; <0: fail, for details, see error code  description</td></tr>
</table>
<br/>

<div name="yunbofang" id="yunbofang" style="font-size:20px;"><b>5.5 Cloud play video</b></div> 
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">Definition</td><td colspan="2">int   MediaCloudRecordPlay(int hUser, String szFileName,int nType, int nStartTime,   Object hWnd, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Cloud play video</td></tr>
<tr><td rowspan="5" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr><td style="text-align:center">szFileName</td>
<td>Cloud video file path and name</td></tr>
<tr><td style="text-align:center">nType</td>
<td>Type</td></tr>
<tr><td style="text-align:center">nStartTime</td>
<td>Start time</td></tr>
<tr><td style="text-align:center">hWnd</td>
<td>Display window GLSurfaceView20 object</td></tr>
<tr><td  style="background-color:#ccc;text-align:center">Return</td>
<td colspan="2">Video play object handle, it can be used to achieve the beginning of the video, video capture and other operations.</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td  style="text-align:center">id
</td><td>Message value：EUIMSG   .EMSG_START_PLAY<br/>
Message in playback process will timing notify via “EUIMSG   .EMSG_ON_PLAY_INFO”<br/>
Message at the end of the playback will notify via “EUIMSG   .EMSG_ON_PLAY_END”<br/>
</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>==EE_OK：success; <0: fail, for details, see error code  description</td></tr>
</table>
<br/>

<div name="shishiliu" id="shishiliu" style="font-size:20px;"><b>5.6 Play real-time streaming video</b></div>
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">Definition
</td><td colspan="2">int   MediaRtspPlay(int hUser, String uuid, int mediaId,String sUrl, Object hWnd,   int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Cloud play video</td></tr>
<tr><td rowspan="5" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr><td style="text-align:center">uuid</td>
<td>Unique identifier</td></tr>
<tr><td style="text-align:center">mediaId</td>
<td>Stream ID</td></tr>
<tr><td style="text-align:center">sUrl</td>
<td>URL</td></tr>
<tr><td style="text-align:center">hWnd</td>
<td>Display window GLSurfaceView20 object</td></tr>
<tr><td  style="background-color:#ccc;text-align:center">Return</td>
<td colspan="2">Video play object handle, it can be used to achieve the beginning of the video, video capture and other operations.</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td  style="text-align:center">id
</td><td>Message value：EUIMSG   .EMSG_START_PLAY<br/>
Message in playback process will timing notify via“EUIMSG   .EMSG_ON_PLAY_INO”<br/>
Message at the end of the playback will notify via“EUIMSG   .EMSG_ON_PLAY_END”<br/>
</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>==EE_OK：success; <0: fail, for details, see error code description</td></tr>
</table>
<br/>

<div name="shiping" id="shiping" style="font-size:20px;"><b>5.7 Play Video - video ID </b></div> 
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">Definition</td><td colspan="2">int   MediaByVideoId(int hUser, String szVideoId, Object hWnd,int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Play video</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr><td style="text-align:center">szVideoId</td>
<td>Video ID</td></tr>
<tr><td style="text-align:center">hWnd</td>
<td>Display window GLSurfaceView20 object</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td  style="text-align:center">id
</td><td>Message value：EUIMSG   .EMSG_START_PLAY<br/>
Message in playback process will timing notify via“EUIMSG   .EMSG_ON_PLAY_INFO”<br/>
Message at the end of the playback will notify via“EUIMSG   .EMSG_ON_PLAY_END”<br/>
</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>==EE_OK：success; <0: fail, for details, see error code description</td></tr>
</table>
<br/>

<div name="bozan" id="bozan" style="font-size:20px;"><b>5.8 Video control - play / pause</b></div> 
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">Definition</td><td colspan="2">int  MediaPause(INT  hPlayer, int  bPause, int    nSeq = 0);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Video control - play / pause</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr><td style="text-align:center">hPlayer</td>
<td>Video control handle - the return value of video play</td></tr>
<tr><td style="text-align:center">bPause</td>
<td>0: play; 1: pause; -1: switch between the two</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td  style="text-align:center">id
</td><td>Message value：EUIMSG   .EMSG_PAUSE_PLAY</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>Current status; 1: playing; 0: pause status</td></tr>
</table>
<br/>

<div name="tingzhi" id="tingzhi" style="font-size:20px;"><b>5.9 Video control – pause</b></div>
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">Definition</td><td colspan="2">int  MediaStop(INT  hPlayer, int  nSeq = 0);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Video control – pause</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr><td style="text-align:center">hPlayer</td>
<td>	
Video control handle - the return value of video play</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td  style="text-align:center">id
</td><td>Message value：EUIMSG   .EMSG_STOP_PLAY</td></tr>
</table>
<br/>

<div name="weizhi" id="weizhi" style="font-size:20px;"><b>5.10 Video control - locate play position</b></div> 
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">Definition</td><td colspan="2">int   MediaSeekToPos(int hPlayer, int nPos, int nSeq);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Video control - locate play position</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Parameters <br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr><td style="text-align:center">hPlayer</td>
<td>Video control handle - the return value of video play</td></tr>
<tr><td style="text-align:center">nPos</td>
<td>Position</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td  style="text-align:center">id
</td><td>Message value：EUIMSG   .EMSG_ SEEK_TO_POS</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>0</td></tr>
</table>
<br/>

<div name="shijian" id="shijian" style="font-size:20px;"><b>5.11 Video control – locate play time</b></div> 
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">Definition</td><td colspan="2">int   MediaSeekToTime(int hPlayer, int nAddTime,   int   nAbsTime, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Video control – locate play time</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">Parameters <br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr><td style="text-align:center">hPlayer</td>
<td>Video control handle - the return value of video play</td></tr>
<tr><td style="text-align:center">nAddTime</td>
<td>Add time</td></tr>
<tr><td style="text-align:center">nAbsTime</td>
<td>Absolute time</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td  style="text-align:center">id
</td><td>Message value:EUIMSG .EMSG_ SEEK_TO_TIME</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>0</td></tr>
</table>
<br/>

<div name="shengyin" id="shengyin" style="font-size:20px;"><b>5.12 Video control – set time</b></div> 
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">Definition</td><td colspan="2">int   MediaSetSound(int hPlayer, int nSound, int nSeq);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Video control – set time</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Parameters <br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr><td style="text-align:center">hPlayer</td>
<td>Video control handle - the return value of video play</td></tr>
<tr><td style="text-align:center">nSound</td>
<td>Sound value</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result   <br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td  style="text-align:center">id
</td><td>Message value：EUIMSG   .EMSG_ SET_SOUND</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>None</td></tr>
</table>
<br/>

<div name="sudu" id="sudu" style="font-size:20px;"><b>5.13 Play speed control</b></div>  
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">Definition</td><td colspan="2">int  MediaSetPlaySpeed(INT  hPlayer, int  nSpeed, int    nSeq = 0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Play speed control</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Parameters 
<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr><td style="text-align:center">hPlayer</td>
<td>Video control handle - the return value of video play</td></tr>
<tr><td style="text-align:center">nSpeed</td>
<td>Play speed. The value of -3~3 respectively represent -8,  -4, -2, 1, 2, 4, 8 times speed</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result   <br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td  style="text-align:center">id
</td><td>Message value：EUIMSG   .EMSG_SET_PLAY_SPEED</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>Current speed value</td></tr>
</table>
<br/>

<div name="kaishi" id="kaishi" style="font-size:20px;"><b>5.14 Start to record</b></div>
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">Definition</td><td colspan="2">int  MediaStartRecord(INT  hPlayer, const char *szFileName, int  nSeq = 0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Start to record</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Parameters <br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr><td style="text-align:center">hPlayer</td>
<td>Video control handle - the return value of video play</td></tr>
<tr><td style="text-align:center">szFileName</td>
<td>Save video file name; file format is using suffix name;  “H.264”; private format; others, such as AVI, etc.
</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">Result   <br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td  style="text-align:center">id
</td><td>Message value：EUIMSG   .EMSG_START_SAVE_MEDIA_FILE</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>==EE_OK：success; <0: fail, for details, see error code   description</td></tr>
<tr><td  style="text-align:center">szStr</td>
<td>Save file name</td></tr>
</table>
<br/>

<div name="tingzhiluxiang" id="tingzhiluxiang" style="font-size:20px;"><b>5.15 Stop recording</b></div>
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">Definition</td><td colspan="2">int  MediaStopRecord (int  hPlayer, int  nSeq = 0);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Stop recording</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">Parameters <br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr><td style="text-align:center">hPlayer</td>
<td>Video control handle - the return value of video play</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">Result   <br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td  style="text-align:center">id
</td><td>Message value：EUIMSG   .EMSG_STOP_SAVE_MEDIA_FILE</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>==EE_OK： success; <0: fail, for details, see error code   description</td></tr>
<tr><td  style="text-align:center">szStr</td>
<td>Save file name</td></tr>
</table>
<br/>

<div name="zhuatu" id="zhuatu" style="font-size:20px;"><b>5.16 Video capture</b></div> 
<br/>

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">Definition</td><td colspan="2">int  MediaSnapImage(HANDLE hPlayer, const char   *szFileName, int  nSeq = 0);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description
</td><td colspan="2">Video capture</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Parameters <br/>Description
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description

</td></tr>
<tr><td style="text-align:center">hPlayer</td>
<td>Video control handle - the return value of video play</td></tr>
<tr><td style="text-align:center">szFileName</td>
<td>Save video file name; file format is using suffix name;  “H.264”; private format; others, such as AVI, etc.
</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">Result   <br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description

</td></tr>
<tr><td  style="text-align:center">id
</td><td>Message value：EUIMSG   .EMSG_SAVE_IMAGE_FILE</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>==EE_OK：success; <0: fail, for details, see error code   description</td></tr>
<tr><td  style="text-align:center">szStr</td>
<td>Save file name</td></tr>
</table>
<br/>




