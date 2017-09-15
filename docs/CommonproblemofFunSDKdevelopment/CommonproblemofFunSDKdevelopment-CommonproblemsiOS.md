## 设备离线可以做消息推送到手机吗?

IOS在断网情况下 会保存最近几条报警消息<br/>
但是会保存历史报警消息<br/>

## 开发app时，开发证书信息的设置？

调用FUN_XMCloundPlatformInit这个接口将uuid、appKey、appSecret、movedCard等参数设入SDK中。<br/>

## 重启设备命令？

（1）接口使用 <br/>
int FUN_DevCmdGeneral(UI_HANDLE hUser, const char *szDevId, int nCmdReq, const char *szCmd, int nIsBinary, int nTimeout, char *pInParam = NULL, int nInParamLen = 0, int nCmdRes = -1, int nSeq = 0);<br/>

(2)参数设定 nCmdReq：1450 nIsBinary：4096,2048,1042等 szCmd：OPMachine pInParam: 待发的请求json

<pre>
{
    "Name": "OPMachine",
    "OPMachine": {
        "Action": "Reboot",
        "SessionID": "0x3"
    }
}
</pre>

nCmdRes:-1 nSeq:0,1,2,...<br/>

(3)回调 misId:5131 IOS: EMSG_DEV_CMD_EN

## IOS黑屏后升级摄像头进度就接不到数据，如果再次调用FUN_DevStartUpgrade会重新来过还是接着获取当前进度？

黑屏之后，IOS的程序应该就会被挂起，可能不会有数据，但是云升级时，设备还是正常在升级。<br/>

## 为了降低延迟，手机端需要配置缓存1秒的接口？

int FUN_MediaSetFluency(FUN_HANDLE hPlayer, int nLevel, int nSeq);<br/>
参数：<br/>

nLevel：按如下设置<br/>

typedef enum EDECODE_TYPE

<pre>
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

EDECODE_TYPE，这个中的EDECODE_REAL_TIME_STREAM1<br/>

## 报警图片下载是什么接口？

MC_SearchAlarmPic(UI_HANDLE hUser, const char *fileName, XPMS_SEARCH_ALARMPIC_REQ *pXPMS_SEARCH_ALARMPIC_REQ, int nSeq = 0);<br/>

## 我们IOS端支持H.265吗？

支持<br/>

## 使用真机编译时出现如下错误

<div>![All text](http://open.xmeye.net/upload/image/20161110/1478742789362023697.png)</div>

<div style="margin-left:20px;">
<b>解决方法</b><br/>
设置 Enable Testability为NO<br/>
</div>

<div>![All text](http://open.xmeye.net/upload/image/20161110/1478742815379085531.png)</div>
