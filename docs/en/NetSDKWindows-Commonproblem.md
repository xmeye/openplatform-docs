### Customer FAQ： ###

#### 一、Capture problem ####
<div style="color:red;margin-left:20px;">
  1.The capture function get a picture of what format?
</div>
<div style="margin-left:20px;">
    Answer：The defaults are in BMP format and can be set to JPG, but the premise requires a Tojpg.dll Library (provided by technical support).
</div>
<div style="color:red;margin-left:20px;">
  2.Capture path can be modified?
</div>
<div style="margin-left:20px;">
    Answer：Yes, the path under Windows needs to be set as "C:\\" format.<br/>
  If you have any questions, ask for technical support....

</div>
#### 二、Bitstream issues in Preview ####
<div style="color:red;margin-left:20px;">
  1.Can you provide the decoding library under Linux?
</div>
<div style="margin-left:20px;">
    Answer：Only under windows, Linux does not provide decoding libraries.
</div>
<div style="color:red;margin-left:20px;">
  2.The correct preview interface function calls the process:
</div>
<div style="margin-left:20px;">
    Answer：H264_PLAY_GetPort(&nIndex) -> H264_PLAY_OpenStream(nIndex,NULL,0,buffersize) <br/>
	  -> H264_PLAY_Play(nIndex, hWnd) -> H264_DVR_RealPlay(m_lLoginId, &playstru) <br/>
      -> H264_DVR_SetRealDataCallBack()
</div>
<div style="color:red;margin-left:20px;">
  3.The correct stop preview interface function calls the process:
</div>
<div style="margin-left:20px;">
    Answer：H264_PLAY_Stop(nIndex) -> H264_PLAY_CloseStream(nIndex) -> H264_PLAY_FreePort(nIndex)
</div>
<div style="color:red;margin-left:20px;">
  4.码流格式？
</div>
<div style="margin-left:20px;">
    Answer：YUV format access: use the play play library H264_PLAY_SetDisplayCallBack interface function callback to obtain. <br/>
    For I frame and P frame: using NETSDK library H264_DVR_SetRealDataCallBack function callback interface. <br/>
</div>
<div style="color:red;margin-left:20px;">
   5.Audio data capture
</div>
<div style="margin-left:20px;">
    Answer：Second callback callback can use the H264_DVR_DelRealDataCallBack_V2 interface function of the acquisition, the first field structure of the callback function in the second parameters in that stream packet type MEDIA_PACK_TYPE, can determine the type, to obtain the corresponding stream packet.
</div>
<div style="color:red;margin-left:20px;">
  6.Standard H264 bitstream format acquisition
</div>
<div style="margin-left:20px;">
    Answer：Using the corresponding stream callback function with H264_DVR_SetRealDataCallBackV2 interface, to obtain each with a private head frame, the frame type from the first field analysis of second parameter structure of the callback function in the body. Access to each frame of data, the private data stream is removed from the head of H264 stream data standard, private head for a 16 bit data stream I frame, P frame head of private data stream for 8. The standard H264 code stream is used for playback. The operation is the same as above (refer to Clientdemo2)
</div>

三、Video playback problem <br/>
<label style="color:red;margin-left:20px;">
  1.There are two ways to remotely replay query Videos: </label>, document querying, video recording, and video recording by time.

<label style="color:red;margin-left:20px;">
  2.There are two ways to play video files for remote playback:</label>Play by file and play by time. (query and play must be one-to-one correspondence, refer to Clientdemo2)

<div style="color:red;margin-left:20px;">
  3.Multiple playback problems:
</div>
<div style="margin-left:20px;">
    (1)Only by the time the query according to the time to multi-channel playback, playback, can not download the current file playback at the same time. <br/>
    (2)According to the file by file playback can also query, download the file.
</div>

#### 四、Yuntai control problem ####
<div style="color:red;margin-left:20px;">
  1.How to add the parameters of the pan tilt control interface function?
</div>
<div style="margin-left:20px;">
    Answer：The direction control calls the H264_DVR_PTZControl interface function, <br/>
     Parameter fill: lLoginID: login handle, nChannelNo: channel number, lPTZCommand: control command, bStop: whether to stop (0: start, 1: stop), lSpeed: move speed. <br/>
	 Other function settings call the H264_DVR_PTZControlEx function, <br/>
     Fill in the parameters: (1) setting, delete, go to the preset point: lPTZCommand: control commands, lParam1: values can be preset.<br/>
      (2)Join the preset cruise, cruise to delete preset point: lPTZCommand: control command, lParam1: cruise route, lParam2: lParam3: time interval preset value. <br/>
	  (3)Start cruise, stop cruise, remove cruise line: lPTZCommand: control command, lParam1: cruise route value <br/>
      (4)Auto sweep function: lPTZCommand: control command can be. Operation steps: left boundary direction select - > use tilt direction for the right boundary - > start automatic sweep line can be. <br/>
</div>
<div style="color:red;margin-left:20px;">
  2.How do you get preset points and cruise lines?
</div>
<div style="margin-left:20px;">
    Answer：You can obtain all preset points of the device of the ball player through the command E_SDK_CFG_PTZPRESET, and obtain all the cruise routes and all preset point information of the ball machine by command E_SDK_CFG_PTZTOUR.
</div>
#### 五、Configuration settings and save questions ####
<div style="color:red;margin-left:20px;">
  1.Video configuration problem
</div>
<div style="margin-left:20px;">
    Answer：Is to function as equipment parameters of IPC or NVR, found that capture command is sent to the equipment, so it should be used to configure the NVR video, and after the test had no effect on the video client.
</div>
<div style="color:red;margin-left:20px;">
  2.Is the required function available?
</div>
<div style="margin-left:20px;">
    Answer: if you want to know whether the function exists, must first obtain the level of function, use the command E_SDK_CONFIG_ABILITY_SYSFUNC to obtain the SDK_SystemFunction structure information can correspond, through the notes to understand the field is the ability which function.
</div>
#### 六、Cloud sequence number landing problem ####
<div style="margin-left:20px;">
    Answer: when using the H264_DVR_Login interface, the first parameter is the device serial number, for example:
"12184db7e85c4e25"; the second parameter is the port number; the third parameter is the user name; the fourth parameter is the password; the fifth parameter is the device information; the sixth parameter is the error code; and the seventh parameter is 2
 </div>
​