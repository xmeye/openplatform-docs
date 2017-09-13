<br/>
<label style="color:#000044;"><b>1.Can the message be pushed to the phone if the device is off-line?
</b></label><br/>
In the case of network outage, IOS will save the last few warning messages and will save the history alarm messages.<br/>

<label style="color:#000044;"><b>2.When developing App, how to set the development certificate information?</b></label><br/>
Calling FUN_XMCloundPlatformInit, this interface will set the parameters UUID, appKey, appSecret and movedCard into SDK.<br/>

<label style="color:#000044;"><b>3.Reset the device command?</b></label><br/>
（1）Interface use <br/>
int FUN_DevCmdGeneral(UI_HANDLE hUser, const char *szDevId, int nCmdReq, const char *szCmd, int nIsBinary, int nTimeout, char *pInParam = NULL, int nInParamLen = 0, int nCmdRes = -1, int nSeq = 0);<br/>
(2)Parameters setting nCmdReq：1450 nIsBinary：4096,2048,1042等 szCmd：OPMachine pInParam: json request that waited to send
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
(3)Callback  misId:5131 IOS: EMSG_DEV_CMD_EN

<label style="color:#000044;"><b>4.When the screen of IOS turns black, the schedule of upgrade camera cannot receive the data. If calling FUN_DevStartUpgrade again, will it start again or continue to get the current progress?</b></label><br/>
After the screen turns black, IOS program may be suspended and there may be no data. But when cloud upgrade, the device still upgrades normally.<br/>

<label style="color:#000044;"><b>5.In order to reduce the latency, mobile phone needs to configure the interface that cache one second?</b></label><br/>
int FUN_MediaSetFluency(FUN_HANDLE hPlayer, int nLevel, int nSeq);<br/>
Parameters：<br/>
nLevel：set according to the following<br/>
typedef enum EDECODE_TYPE
<pre>
{
    EDECODE_REAL_TIME_STREAM0,      // The most real-time - apply to the IP \ AP mode and and other situation that the network state is very good
    EDECODE_REAL_TIME_STREAM1,      //
    EDECODE_REAL_TIME_STREAM2,      //
    EDECODE_REAL_TIME_STREAM3,      // medium
    EDECODE_REAL_TIME_STREAM4,      //
    EDECODE_REAL_TIME_STREAM5,      //
    EDECODE_REAL_TIME_STREAM6,      //The most fluent - apply to the situation that the network is not good, or the network fluctuation is big
    EDECODE_FILE_STREAM = 100,                // File stream

} EDECODE_TYPE;
</pre>
<br/>
<label style="color:#000044;"><b>6.If you want to change the phone cache, which parameters should be selected?
</b></label><br/>
EDECODE_TYPE，EDECODE_REAL_TIME_STREAM1 in this<br/>

<label style="color:#000044;"><b>7.What is the interface to download the alarm picture?
</b></label><br/>
MC_SearchAlarmPic(UI_HANDLE hUser, const char *fileName, XPMS_SEARCH_ALARMPIC_REQ *pXPMS_SEARCH_ALARMPIC_REQ, int nSeq = 0);<br/>

<label style="color:#000044;"><b>8.Does our IOS support H.265?
</b></label><br/>
Support<br/>

<label style="color:#000044;"><b>9.The following error occurred while using mobile phone to compile
</b></label><br/>
![All text](http://open.xmeye.net/upload/image/20161110/1478742789362023697.png)
<div style="margin-left:20px;">
<b>Solution</b><br/>
Set  Enable Testability to NO<br/>
</div>

![All text](http://open.xmeye.net/upload/image/20161110/1478742815379085531.png)