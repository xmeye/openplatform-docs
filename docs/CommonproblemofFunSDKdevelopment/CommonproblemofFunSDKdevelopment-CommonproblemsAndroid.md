## 设备离线可以做消息推送到手机吗

安卓的在客户端断网的情况下不会推送<br/>
但是会保存历史报警消息<br/>

## 开发app时，开发证书信息的设置？

调用XMCloundPlatformInit这个接口将uuid、appKey、appSecret、movedCard等参数设入SDK中。<br/>

## 重启设备命令？

（1）接口使用   
public static native int DevCmdGeneral(int hUser, String szDevId, int nCmdReq, String szCmd, int nRetSize, int nTimeout, byte[] pInParam, int nCmdRes, int nSeq);  

(2)参数设定 nCmdReq：1450 nIsBinary：4096,2048,1042等 szCmd：OPMachine pInParam: 待发的请求json 
<pre> 
{
   "Name": "OPMachine",
   "OPMachine": 

        "Action": "Reboot",

        "SessionID": "0x3"
    }
}
</pre>

nCmdRes:-1 nSeq:0,1,2,...<br/>

(3)回调 misId:5131 DEV_CMD_EN<br/>

## 为了降低延迟，手机端需要配置缓存1秒的接口？

Android: int MediaSetFluency(int hPlayer, int nLevel, int nSeq);<br/>
参数：<br/>
nLevel：按如下设置<br/>
<pre>
typedef enum EDECODE_TYPE
{
   EDECODE_REAL_TIME_STREAM0,      // 最实时--适用于IP\AP模式等网络状态很好的情况
   EDECODE_REAL_TIME_STREAM1,      //
   EDECODE_REAL_TIME_STREAM2,      //
   EDECODE_REAL_TIME_STREAM3,      // 中等
   EDECODE_REAL_TIME_STREAM4,      //
   EDECODE_REAL_TIME_STREAM5,      //
   EDECODE_REAL_TIME_STREAM6,      // 最流畅--适用于网络不好,网络波动大的情况
   EDECODE_FILE_STREAM = 100,                // 文件流
} EDECODE_TYPE;
</pre>

## 如果想要改手机缓存，应该选用哪个参数？

EDECODE_TYPE，这个中的EDECODE_REAL_TIME_STREAM1

## 报警图片下载是什么接口？

int SearchAlarmPic(int hUser, String fileName, byte []pXPMS_SEARCH_ALARMPIC_REQ, int nSeq);






 
