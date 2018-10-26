## 关于FunSDK设备配置的说明

### 设备配置时与设备进行交互的方式
FunSDK 通过与设备约定的 一定格式的配置 进行数据交互
相应配置的修改是通过修改配置内的相对应元素来完成的

以 编码配置 为例

获取到的json字符串为：
{ "Name" : "Simplify.Encode", "Ret" : 100, "SessionID" : "0x00000031", "Simplify.Encode" : [ { "ExtraFormat" : { "AudioEnable" : true, "Video" : { "BitRate" : 786, "BitRateControl" : "VBR", "Compression" : "H.264", "FPS" : 10, "GOP" : 2, "Quality" : 3, "Resolution" : "D1" }, "VideoEnable" : true }, "MainFormat" : { "AudioEnable" : true, "Video" : { "BitRate" : 1024, "BitRateControl" : "VBR", "Compression" : "H.264", "FPS" : 20, "GOP" : 2, "Quality" : 4, "Resolution" : "720P" }, "VideoEnable" : true } } ] }

其中每个元素代表的含义如下表所示
如果希望修改主码流音频，则需要修改 MainFormat 里的 AudioEnable 为 false
然后set 配置时将修改后的完整json字符串作为参数传入 ，如下所示
{ "Name" : "Simplify.Encode", "Ret" : 100, "SessionID" : "0x00000031", "Simplify.Encode" : [ { "ExtraFormat" : { "AudioEnable" : true, "Video" : { "BitRate" : 786, "BitRateControl" : "VBR", "Compression" : "H.264", "FPS" : 10, "GOP" : 2, "Quality" : 3, "Resolution" : "D1" }, "VideoEnable" : true }, "MainFormat" : { "AudioEnable" : false, "Video" : { "BitRate" : 1024, "BitRateControl" : "VBR", "Compression" : "H.264", "FPS" : 20, "GOP" : 2, "Quality" : 4, "Resolution" : "720P" }, "VideoEnable" : true } } ] }

<style>
	table{
		border-collapse:collapse;
		width:100%;
	}
	
</style>
<table>
<tr><td style="width:33%;border:1px solid #000;">“Simplify.Encode”   : [ {</td><td style="width:33%">编码参数配置</td><td style="width:33%">是一个数组，每个通道一个配置</td></tr>
<tr><td>“MainFormat” : {</td><td>主码流格式 </td><td></td></tr>
<tr><td>“AudioEnable” : false,</td><td>音频使能</td><td>整形0，1</td></tr>
<tr><td>“VideoEnable” : true,</td><td>视频使能</td><td></td></tr>
<tr><td>“Video” : {</td><td>视频格式</td><td></td></tr>
<tr><td>"Compression" :   "H.264",</td><td>视频压缩格式</td><td>MPEG4",   "MPEG2", "MPEG1", "MJPG",   "H.263",  "H.264", “AVS”,   “H.264MF”, “H.264HF”, “JPEG”</td></tr>
<tr><td>"Resolution"："HD1"</td><td>分辨率</td><td>以下几种分辨率："D1", "HD1", "BCIF",   "CIF", "QCIF", "VGA", "QVGA",  "SVCD", "QQVGA", “SXVGA”,   “UXGA”
</td></tr>
<tr><td>"BitRateControl" :   "CBR",</td><td>码流控制模式</td><td>"CBR"固定码流，"VBR"可变码流，“MBR“混和码流</td></tr>
<tr><td>"BitRate" : 1200,</td><td>视频码流(kbps)</td><td></td></tr>
<tr><td>"FPS" : 25,</td><td>视频帧率</td><td>负数表示多秒一帧，比如-3表示3秒一帧，取值范围-5~30</td></tr>
<tr><td>"GOP" : 2,</td><td>I帧间隔</td><td>[2-12]，2S到12S一个I帧</td></tr>
<tr><td>"Quality" : 1,</td><td>图像质量,只有在可变码流下才起作用。</td><td>取值1-6，值越大，图像质量越好。</td></tr>
<tr><td>},// end of Video</td><td></td><td></td></tr>
<tr><td>},…, {}]// end of MainFormat</td><td></td><td></td></tr>
<tr><td>“ExtraFormat” : {</td><td>辅码流，参见MainFormat</td><td></td></tr>
<tr><td>}, // end of ExtraFormat</td><td></td><td></td></tr>
<tr><td>},…,   {}]</td><td>其他通道配置</td><td></td></tr>
</table>


配置名称：SystemInfo
所有的配置都是使用Json字符串的方式传递
获取配置的接口：
int DevGetConfigByJson(int   hUser, String szDevId,String szCommand,intnOutBufLen,int nChannelNO,int   nTimeout,int nSeq);
参数：hUser  句柄（回调句柄）
<div style="margin-left:30px;">
      szDevId 序列号
     szCommand 配置名称
     nOutBufLen 字符串长度
     nChannelNo 通道号
     nTimeout   超时时间
     nSeq       标志位
</div>


设置配置的接口：
Int DevGetConfigByJson(int   hUser, String szDevId,String szCommand,String pConfig,int nChannelNO,int   nTimeout,int   nSeq);
参数：hUser     句柄
<div style="margin-left:30px;">
     szDevId    序列号
     szCommand  配置名称
     pConfig    配置内容（Json字符串，格式需要跟获取到的Json字符串保持一致）
     nChannelNo 通道号
     nTimeout   超时时间
     nSeq       标志位
</div>

 

Demo 中配置页面先获取配置，解析到相应的配置类里，并从相应配置类里取值显示
<div style="margin-left:40px;">
     设置时将相应配置组成规定格式json字符串，调用设置配置接口，完成相应的配置设置
</div>

## 主动录像配置问题

录像模式有三种

（1）停止录像

（2）配置录像

（3）手动录像

配置（3）手动录像不再使用
配置为停止录像时，设备停止录像
配置为配置录像时，由掩码Mask决定是始终录像还是联动录像
"Mask" : [ [ "0x00000007", "0x00000000", "0x00000000", "0x00000000", "0x00000000", "0x00000000" ]....]
当配置为7的时候，是始终录像
配置为6的时候，是联动录像
TimeSection 设置在某段时间内录像

主动开始和停止录像的功能，可通过配置相关录像模式实现

<style>
	table{
		border-collapse:collapse;
		width:100%;
	}
	
</style>
<table>
<tr><td style="width:33%;border:1px solid #000;"><b>Sample</b></td>
<td style="width:33%"><b>Description</b></td><td  style="width:33%"><b>Value</b></td></tr>
<tr><td>“Record” : [   {</td><td>录像配置</td><td>是一个数组，每个录像通道对应一个配置</td></tr>
</table>

<table>
<tr><td style="width:33%;border:1px solid #000;">"PreRecord" : 4,</td>
<td style="width:33%">预录时间，0为关闭</td><td  style="width:33%">[0, 30]</td></tr>
<tr><td>"PacketLength" : 60,</td><td>录像打包时间</td><td>[1,   120]</td></tr>
<tr><td>"TimeSection " : {[   "1 00:00:00-24:00:00", "0 00:00:00-24:00:00", "0   00:00:00-24:00:00", "0 00:00:00-24:00:00", "0   00:00:00-24:00:00", "0 00:00:00-24:00:00" ],}
</td><td>录像工作表</td><td> </td></tr>
<tr><td>“RecordMode” : “ManualRecord”</td><td>录像模式,配置录像，手动录像，关闭录像
</td><td>“ConfigRecord”,   “ManualRecord”, “ClosedRecord”</td></tr>
<tr><td>"Redundancy" : false，</td><td>冗余开关</td><td> </td></tr>
<tr><td> "Mask" : [ [   "0x00000007", "0x00000000", "0x00000000",   "0x00000000", "0x00000000", "0x00000000" ]....]</td><td> </td><td> </td></tr>
<tr><td>},…{}],</td><td>其他通道配置</td><td> </td></tr>
</table>

## 报警配置以及时段设置问题

<div style="margin-left:20px;">
1.报警开关及抓拍常规设置参考FunSDKDemo
2.关于时间段的设置
（1）TimeSection 参数就是设置时间段的参数
</div>

<table>
<tr><td style="width:33%;border:1px solid #000;"><b>Sample</b></td>
<td style="width:33%"><b>Description</b></td><td  style="width:33%"><b>Value</b></td></tr>
<tr><td>“Detect.MotionDetect”   : [{</td><td>动态检测配置 </td><td>每个通道对应一个配置</td></tr>
<tr><td>“Enable” : true,</td><td>动态检测开启</td><td> </td></tr>
<tr><td>“Level” : 3,</td><td>灵敏度</td><td>[1, 6]</td></tr>
<tr><td><pre>“Region”   :
[
  “0xFFFFFF”,
  “0xFFFFFF”,
   …
],
</pre></td><td>区域块</td><td>是一个数组，区域的每一行使用一个32位整型表示，整型的每一位对应一个小块</td></tr>
<tr><td>“EventHandler”   : {</td><td>动态检测联动</td><td> </td></tr>
<tr><td>"EventLatch"   : 1,</td><td> </td><td> </td></tr>
<tr><td><pre>“TimeSection” :
[[
    [“1 00:00:00-24:00:00”,
    “0 00:00:00-24:00:00”,
	“0 00:00:00-24:00:00”
	“0 00:00:00-24:00:00”
	“0 00:00:00-24:00:00”
	“0 00:00:00-24:00:00”
    ], …,[ ]],
</pre></td><td>事件时间段</td><td>是一个二维数组，每周7天，每天6个时间段。时间段用字符串表示，字符串首的数字1表示该时间段有效，0表示该时间段无效。如果某些事件处理参数中没有这个成员，表示不区分时间段，全天候响应事件。</td></tr>
<tr><td>“RecordMask” : “0x0F”</td><td>录像通道掩码</td><td></td></tr>
<tr><td>“RecordEnable” = true，</td><td>录像使能</td><td> </td></tr>
<tr><td>“RecordLatch” = 10，</td><td>录像延时时间（秒）</td><td>10~300
</td></tr>
<tr><td>“AlarmOutMask”   = “0x0F”，</td><td>报警输出通道掩码
</td><td> </td></tr>
<tr><td>“AlarmOutEnable” : true，</td><td>报警输出使能</td><td> </td></tr>
<tr><td>}“RecordLatch” = 10，</td><td>报警输出延时时间（秒）
</td><td> 10~300</td></tr>
<tr><td>“PtzEnable” : true，</td><td>云台联动使能</td><td> </td></tr>
<tr><td><pre>“PtzLink” :
[
    [“None”, 0],
    [“Preset”, 3],
    [“Tour”, 4],
    [“Pattern”, 1],
    …
],
</pre></td><td>云台联动项</td><td>是一个二维数组，每个云台通道对应一个项，每一项包含联动的类型和取值，联动类型有:
“None”,   “Preset”, “Tour”, “Pattern”
</td></tr>
<tr><td>“TourEnable” : true,</td><td>轮询使能</td><td></td></tr>
<tr><td>“TourMask” : “0x0001”,</td><td>轮询掩码</td><td></td></tr>
<tr><td>“SnapShotMask” : “0x001”,</td><td>快照通道号掩码</td><td></td></tr>
<tr><td>“SnapEnable” : true,</td><td>快照使能</td><td></td></tr>
<tr><td>“TipEnable” : true,</td><td>本地消息框提示</td><td></td></tr>
<tr><td>“MailEnable” : true,</td><td>发送邮件，如果有图片，作为附件</td><td></td></tr>
<tr><td>“MessageEnable” : true,</td><td>上传到报警服务器</td><td></td></tr>
<tr><td>“MsgtoNetEnable” : true,</td><td>消息上传到网络使能</td><td></td></tr>
<tr><td>“BeepEnable” : true,</td><td>蜂鸣</td><td></td></tr>
<tr><td>“VoiceEnable” : true,</td><td>语音提示</td><td></td></tr>
<tr><td>“MatrixEnable” : true,</td><td>联动视频矩阵通道掩码</td><td></td></tr>
<tr><td>“MatrixMask” : “0x000F”,</td><td>联动视频矩阵</td><td></td></tr>
<tr><td>“LogEnable” : true</td><td>日志使能</td><td></td></tr>
<tr><td>“FtpEnable” : true</td><td>Ftp上传使能</td><td></td></tr>
<tr><td>} // end of EventHandler</td><td> </td><td></td></tr>
<tr><td>},…,   {}]</td><td>其他通道配置</td><td></td></tr>
<tr><td>&#160</td><td> </td><td></td></tr>
</table>

## 获取录像信息回调处理

1.按文件获取
按文件获取时返回byte型数据，使用提供的工具类G里的方法解析成H264_DVR_FILE_DATA 即可获得相关信息

2.按时间获取
按时间获取录像信息时，返回一个720个元素的byte数组，该数组的每一个元素的高四位和低四位分别代表一天的某一分钟，720个元素包含一天24小时的每一分钟

当代表某分钟的四位（比如 0001 0000）中的低四位为0000 的时候，说明这一分钟没有录像，而类似高四位0001 的时候，说明有录像

当代表某一分钟的四位不为零的时候，其具体的数值代表录像的类型
0001普通录像
0010 和0011和0100 代表报警录像

## 时间夏令时同步

### 同步设备时间

```
  JsonConfig.OPTIME_SET  =  "OPTimeSetting"
    protected void syncDevTime(int userID,String devSN) {
        Calendar c = Calendar.getInstance(Locale.getDefault());
        String time = new SimpleDateFormat("yyyy-MM-dd HH:mm:ss", Locale.getDefault()).format(c.getTime());
        FunSDK.DevSetConfigByJson(userID,devSN, JsonConfig.OPTIME_SET,
                HandleConfigData.getSendData(JsonConfig.OPTIME_SET, "0x00000001", time), -1, 5000, 0);
    }
```

### 设备时区同步

```
    /**
     * JsonConfig.SYSTEM_TIMEZONE = "System.TimeZone"
     * @param userID
     * @param devSN  设备序列号
     */
    protected void syncDevTimeZone(int userID,String devSN){
        TimeZoneBean timeZoneBean = new TimeZoneBean();
        timeZoneBean.timeMin = setTimeZone();
        timeZoneBean.FirstUserTimeZone = 0;
        FunSDK.DevSetConfigByJson(userID, devSN, JsonConfig.SYSTEM_TIMEZONE,
                HandleConfigData.getSendData(JsonConfig.SYSTEM_TIMEZONE, "0x1", timeZoneBean), -1, 5000, 0);

    }
```

### 同步夏令时
```
/**
     * @ param userID
     * @param userID
     * @param locationBean  设置夏令时之前要先获取” General.Location”配置,然后设置该配置
     */

    protected void syncDevTimeZone(int userID, String devSN, LocationBean locationBean){
        TimeZoneBean timeZoneBean = new TimeZoneBean();
        timeZoneBean.timeMin = setTimeZone();
        timeZoneBean.FirstUserTimeZone = 0;
        FunSDK.DevSetConfigByJson(userID, devSN, JsonConfig.SYSTEM_TIMEZONE,
                HandleConfigData.getSendData(JsonConfig.SYSTEM_TIMEZONE, "0x1", timeZoneBean), -1, 5000, 0);
        if (locationBean != null) {
            DayLightTimeBean dayLightTimeBean = getDayLightTimeInfo(TimeZone.getDefault());
            if (dayLightTimeBean != null) {
                if (dayLightTimeBean.useDLT) {
                    locationBean.setdSTRule("On");
                    DSTimeBean dstStart = new DSTimeBean();
                    dstStart.setYear(dayLightTimeBean.year);
                    dstStart.setMonth(dayLightTimeBean.beginMonth);
                    dstStart.setDay(dayLightTimeBean.beginDay);
                    DSTimeBean dstEnd = new DSTimeBean();
                    dstEnd.setYear(dayLightTimeBean.year);
                    dstEnd.setMonth(dayLightTimeBean.endMonth);
                    dstEnd.setDay(dayLightTimeBean.endDay);
                    locationBean.setdSTStart(dstStart);
                    locationBean.setdSTEnd(dstEnd);
                }else {
                    locationBean.setdSTRule("Off");
                }
            }
            FunSDK.DevSetConfigByJson(userID, devSN, ” General.Location”,
                    HandleConfigData.getSendData(” General.Location”, "0x02", locationBean), -1, 5000, 0);
        }
    }
```

### 时区设置

```
    private int setTimeZone() {
        Calendar cal = Calendar.getInstance(Locale.getDefault());
        float zoneOffset = (float) cal.get(java.util.Calendar.ZONE_OFFSET);
        float zone = (float) (zoneOffset / 60.0 / 60.0 / 1000.0);// 时区，东时区数字为正，西时区为负
        return (int) (-zone * 60);
    }
```

### 通过时区信息返回当年的夏令时的起止日期

```
    /**
     * @param tz
     * @return
     */
    protected DayLightTimeBean getDayLightTimeInfo(TimeZone tz) {
        DayLightTimeBean dltInfo = new DayLightTimeBean();
        dltInfo.useDLT = tz.useDaylightTime();
        if (dltInfo.useDLT) {
            try {
                Date date = new Date();
                SimpleDateFormat sdfYear = new SimpleDateFormat("yyyy");
                sdfYear.setTimeZone(tz);

                SimpleDateFormat sdfDay = new SimpleDateFormat("yyyy-MM-dd");
                sdfDay.setTimeZone(tz);

                SimpleDateFormat sdf = new SimpleDateFormat("yyyy-MM-dd HH:mm");
                sdf.setTimeZone(tz);

                // 年份就取当年
                dltInfo.year = Integer.parseInt(sdfYear.format(date));

                // 先找到起始月份
                for ( int month = 1; month <= 12; month ++ ) {
                    String tmpStr = String.format("%04d-%02d-%02d", dltInfo.year, month, 1);

                    if ( dltInfo.beginMonth == 0 && tz.inDaylightTime(sdfDay.parse(tmpStr)) ) {
                        dltInfo.beginMonth = month;
                    }

                    if ( dltInfo.beginMonth > 0 && dltInfo.endMonth == 0 && !tz.inDaylightTime(sdfDay.parse(tmpStr)) ) {
                        // 这个只是可能的结束月份,实际的结束月份很可能是上个月
                        dltInfo.endMonth = month;
                        break;
                    }
                }

                // 起始天肯定在起始月份当中的某一天,简单查找,就认为每个月都有31天吧
                for ( int day = 1; day <= 31; day ++ ) {
                    String tmpStr = String.format("%04d-%02d-%02d", dltInfo.year, dltInfo.beginMonth, day);
                    if ( tz.inDaylightTime(sdfDay.parse(tmpStr)) ) {
                        dltInfo.beginDay = day;
                        break;
                    }
                }

                // 结束的天,应该是上述结束月份中的1号,或者是之前一个月的某一天
                if ( dltInfo.endMonth > 1 ) {
                    dltInfo.endDay = 1;
                    // 上个月中查找是否存在结束日期,如果不存在就是之前找到的月份的1号,简单查找,就认为每个月都有31天吧
                    for ( int day = 1; day <= 31; day ++ ) {
                        String tmpStr = String.format("%04d-%02d-%02d", dltInfo.year, dltInfo.endMonth-1, day);
                        if ( !tz.inDaylightTime(sdfDay.parse(tmpStr)) ) {
                            dltInfo.endMonth = dltInfo.endMonth-1;
                            dltInfo.endDay = day;
                            break;
                        }
                    }
                }
                // 时/分暂不处理,暂定00:00
            } catch (Exception e) {
            }
        }
        return dltInfo;
    }
```

## 用URL初始化报警消息订阅

```
public class SMCInitInfo {
    public byte[] st_0_user = new byte[512];
    public byte[] st_1_password = new byte[512];
    public byte[] st_2_token = new byte[256];
    public int st_3_language;
    public int st_4_appType;
    public byte[] st_5_appType = new byte[64];

    public SMCInitInfo() {
        this.st_5_appType[0] = 0;
    }
}

//使用Url初始化报警推送,只需要将url设置到token参数里就行
SMCInitInfo info = new SMCInitInfo();
        G.SetValue(info.st_0_user, mUserName);
        G.SetValue(info.st_1_password, mPassWord);
        G.SetValue(info.st_2_token, url);
MpsClient.Init(userId, G.ObjToBytes(info), 0);
```












