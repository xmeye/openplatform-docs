## 抓图问题

<div style="color:red;margin-left:20px;">
  1.抓图功能得到的图片是什么格式？
</div>
<div style="margin-left:20px;">
    答：默认为bmp格式，可设置为jpg格式，但前提需要有Tojpg.dll库（由技术支持提供）。
</div>
<div style="color:red;margin-left:20px;">
  2.抓图的路径可以修改吗？
</div>
<div style="margin-left:20px;">
    答：可以，windows下路径需设置为"C:\\"格式。<br/>
  有什么问题可向技术支持询问。。。。

</div>

## 预览时码流问题

<div style="color:red;margin-left:20px;">
  1.可以提供linux下的解码库吗？
</div>
<div style="margin-left:20px;">
    答：只有windows下有，linux下不提供解码库。
</div>
<div style="color:red;margin-left:20px;">
  2.正确的预览接口函数调用流程：
</div>
<div style="margin-left:20px;">
    答：H264_PLAY_GetPort(&nIndex) -> H264_PLAY_OpenStream(nIndex,NULL,0,buffersize) <br/>
	  -> H264_PLAY_Play(nIndex, hWnd) -> H264_DVR_RealPlay(m_lLoginId, &playstru) <br/>
      -> H264_DVR_SetRealDataCallBack()
</div>
<div style="color:red;margin-left:20px;">
  3.正确的停止预览接口函数调用流程：
</div>
<div style="margin-left:20px;">
    答：H264_PLAY_Stop(nIndex) -> H264_PLAY_CloseStream(nIndex) -> H264_PLAY_FreePort(nIndex)
</div>
<div style="color:red;margin-left:20px;">
  4.码流格式？
</div>
<div style="margin-left:20px;">
    答：YUV格式的获取：使用play播放库H264_PLAY_SetDisplayCallBack接口函数回调获得。 <br/>
    I帧和P帧的获取：使用NETSDK库H264_DVR_SetRealDataCallBack接口函数回调获得。 <br/>
</div>
<div style="color:red;margin-left:20px;">
   5.音频数据获取
</div>
<div style="margin-left:20px;">
    答：可使用H264_DVR_DelRealDataCallBack_V2接口函数的第二个回调函数回调获取，该回调函数中第二个参数的结构体中的第一个字段即为码流包的类型MEDIA_PACK_TYPE，可通过判断该类型，来获取相应的码流包。
</div>
<div style="color:red;margin-left:20px;">
  6.标准H264码流格式获取
</div>
<div style="margin-left:20px;">
    答：使用对应码流回调函数带有H264_DVR_SetRealDataCallBackV2的接口，用以获取每个带有私有头的帧，帧类型由该回调函数中的第二个形参结构体中的第一个字段解析。获取到每一帧的数据后，将码流数据的私有头去掉便是标准的H264码流数据了，I帧码流数据的私有头为16位，P帧码流数据的私有头为8位。回放时获取标准H264码流操作同上(请参考Clientdemo2)
</div>

## 录像回放问题

<label style="color:red;margin-left:20px;">
  1.远程回放查询录像有两种方法：</label>按文件查询录像和按时间查询录像。

<label style="color:red;margin-left:20px;">
  2.播放远程回放的录像文件有两种方法：</label>按文件播放和按时间播放。（查询和播放必须一一对应，可参考Clientdemo2）

<div style="color:red;margin-left:20px;">
  3.多路回放问题：
</div>
<div style="margin-left:20px;">
    (1)只有按时间查询->按时间回放才有多路回放功能，在回放的同时不可下载当前文件。 <br/>
    (2)按文件查询->按文件回放可同时下载当前文件。
</div>

## 云台控制问题

<div style="color:red;margin-left:20px;">
  1.云台控制接口函数的形参怎么添加？
</div>
<div style="margin-left:20px;">
    答：方向控制调用H264_DVR_PTZControl接口函数， <br/>
      参数填写：lLoginID：登陆句柄，nChannelNo:通道号，lPTZCommand:控制命令，bStop:是否停止(0:开始，1:停止)，lSpeed:移动速度。 <br/>
	  其他功能设置调用H264_DVR_PTZControlEx函数， <br/>
      参数填写：(1)设置、删除、转到预置点时：lPTZCommand:控制命令,lParam1:预置点值即可。 <br/>
      (2)加入预置点到巡航、删除巡航中预置点时：lPTZCommand:控制命令,lParam1:巡航路线值，lParam2:预置点值，lParam3:时间间隔 <br/>
	  (3)开始巡航、停止巡航、删除巡航线路：lPTZCommand:控制命令,lParam1:巡航路线值 <br/>
      (4)自动扫线功能：lPTZCommand:控制命令即可。运行步骤:选择当前方向为左边界->使用云台方向移动为右边界->开始自动扫线即可。 <br/>
</div>
<div style="color:red;margin-left:20px;">
  2.预置点和巡航线路如何获取？
</div>
<div style="margin-left:20px;">
    答：可通过该命令E_SDK_CFG_PTZPRESET获取球机的设备的所有预置点，通过命令E_SDK_CFG_PTZTOUR获取球机所有的巡航路线和对应的所有预置点信息。
</div>

## 配置设置和保存问题

<div style="color:red;margin-left:20px;">
  1.录像配置问题
</div>
<div style="margin-left:20px;">
    答：是作为IPC或NVR的设备参数来作用的，抓包发现:命令是发送给了设备，所以这个功能应该是配置NVR录像时使用的，并且经过测试对客户端录像不起作用。
</div>
<div style="color:red;margin-left:20px;">
  2.所需要的功能是否可以用？
</div>
<div style="margin-left:20px;">
    答：若想知道该功能是否存在，首先得获取该功能的能力级，使用命令E_SDK_CONFIG_ABILITY_SYSFUNC获取对应的SDK_SystemFunction结构体信息即可，可通过注释去了解该字段是哪个功能的能力级。
</div>

## 云序列号登陆问题

<div style="margin-left:20px;">
    答：使用该H264_DVR_Login接口时，第一个参数为设备序列号，例如:
	"12184db7e85c4e25";第二个参数为端口号，第三个参数为用户名，第四个参数为密码，第五个参数为设备信息，第六个参数为错误码，第七个参数为2
 </div>
​