<label style="color:#000044;"><b>1.Can the message be pushed to the phone if the device is off-line?</b></label><br/>
In the case of the client network outage, Android will not push message to mobile phone, but will save the history alarm messages<br/>

<label style="color:#000044;"><b>2.When developing App, how to set the development certificate information?</b></label><br/>
Calling XMCloundPlatformInit, this interface will set the parameters UUID, appKey, appSecret and movedCard into SDK.<br/>

<label style="color:#000044;"><b>3.Reset the device command?</b></label><br/>
（1）Interface use  
public static native int DevCmdGeneral(int hUser, String szDevId, int nCmdReq, String szCmd, int nRetSize, int nTimeout, byte[] pInParam, int nCmdRes, int nSeq);  
(2)Parameters setting  nCmdReq：1450 nIsBinary：4096,2048,1042等 szCmd：OPMachine pInParam: json request that waited to send 
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
(3)Callback misId:5131 DEV_CMD_EN<br/>

<label style="color:#000044;"><b>4.In order to reduce the latency, mobile phone needs to configure the interface that cache one second?</b></label><br/>
Android: int MediaSetFluency(int hPlayer, int nLevel, int nSeq);<br/>
Parameters：<br/>
nLevel：set according to the following<br/>
<pre>
typedef enum EDECODE_TYPE
{
   EDECODE_REAL_TIME_STREAM0,      // The most real-time - apply to the IP \ AP mode and and other situation that the network state is very good
   EDECODE_REAL_TIME_STREAM1,      //
   EDECODE_REAL_TIME_STREAM2,      //
   EDECODE_REAL_TIME_STREAM3,      // medium
   EDECODE_REAL_TIME_STREAM4,      //
   EDECODE_REAL_TIME_STREAM5,      //
   EDECODE_REAL_TIME_STREAM6,      // The most fluent - apply to the situation that the network is not good, or the network fluctuation is big
   EDECODE_FILE_STREAM = 100,                // File stream
} EDECODE_TYPE;
</pre>

<label style="color:#000044;"><b>5.If you want to change the phone cache, which parameters should be selected?
</b></label><br/>
EDECODE_TYPE，这个中的EDECODE_REAL_TIME_STREAM1

<label style="color:#000044;"><b>6.What is the interface to download the alarm picture?</b></label><br/>
int SearchAlarmPic(int hUser, String fileName, byte []pXPMS_SEARCH_ALARMPIC_REQ, int nSeq);






 
