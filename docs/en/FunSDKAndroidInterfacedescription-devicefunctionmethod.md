## Get channel name

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">Definition</td><td colspan="2">int   DevGetChnName(int hUser, String devId, String szUser, String password,   int  nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Get channel name</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr><td style="text-align:center">devId</td><td>Device serial number</td></tr>
<tr><td style="text-align:center">szUser
</td><td>Device login username; when it is empty, use the default user   name (default user name when adding device)</td></tr>
<tr><td style="text-align:center">password</td><td>	
Device login password;</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id</td>
<td>Message value：EUIMSG   .EMSG_DEV_GET_CHN_NAME</td></tr>
<tr><td style="text-align:center">arg1
</td><td>>0：number of channels；<0: fail, for details, see error code      description</td></tr>
<tr><td style="text-align:center">pData
</td><td>Point to SDK_ChannelNameConfigAll object byte stream</td></tr>
</table>

## Query video

<table >
<tr><td style="background-color:#ccc;text-align:center;width:100px;">Definition</td><td colspan="2">int  DevFindFile(int hUser, String devId, byte   []pH264_DVR_FINDINFO, int  nMaxCount,   int  waittime, int  nSeq);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Query video</td></tr>
<tr><td rowspan="5" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr><td style="text-align:center">devId</td>
<td>Device serial number</td></tr>
<tr><td style="text-align:center">pH264_DVR_FINDINFO</td>
<td>Query condition. H264_DVR_FINDINFO object byte stream</td></tr>
<tr><td  style="text-align:center">nMaxCount
</td><td>Return the maximum counts</td></tr>
<tr><td  style="text-align:center">waittime</td><td>Timeout</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">Result<br/>
message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td  style="text-align:center">id
</td><td>Message value：EUIMSG   . EMSG_DEV_FIND_FILE</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>>0：number of results；<0: fail, for details, see error code      description</td></tr>
<tr><td  style="text-align:center">pData</td>
<td>Point to H264_DVR_FILE_DATA object array byte stream</td></tr>
</table>

## Query video (by time)

<table >
<tr><td style="background-color:#ccc;text-align:center;width:50px;">Definition</td><td colspan="2">int  DevFindFileByTime (int hUser, String devId,   byte []pSDK_SearchByTime, int    waittime, int  nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Query video
</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr><td style="text-align:center">devId</td>
<td>Device serial number</td></tr>
<tr><td style="text-align:center">pSDK_SearchByTime
</td><td>Query condition. SDK_SearchByTime object byte stream</td></tr>
<tr><td  style="text-align:center">waittime</td><td>Timeout</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td  style="text-align:center">id
</td><td>Message value：EUIMSG   . DEV_FIND_FILE_BY_TIME
</td></tr>
<tr><td  style="text-align:center">arg1
</td><td>>0：number of results；<0: fail, for details, see error code description</td></tr>
<tr><td  style="text-align:center">pData
</td><td>Point to SDK_SearchByTimeResult object byte stream</td></tr>
</table>

## Download by file video

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">Definition</td><td colspan="2">int   DevDowonLoadByFile(int hUser, String szDevId, byte []pH264_DVR_FILE_DATA,   String szFileName, int nSeq)</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Download by file video</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr><td style="text-align:center">devId</td>
<td>Device serial number</td></tr>
<tr><td style="text-align:center">pH264_DVR_FILE_DATA
</td><td>Query condition. H264_DVR_FILE_DATA object byte stream</td></tr>
<tr><td  style="text-align:center">szFileName</td><td>Saved file path + file name</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value：EUIMSG   . EMSG_ON_FILE_DOWNLOAD:download function calling result<br/>EUIMSG   . EMSG_ON_FILE_DLD_COMPLETE:download      
completed message callback<br/>
EUIMSG   . EMSG_ON_FILE_DLD_POS:ownload progress   message callback<br/>
</td></tr>
<tr><td style="text-align:center">arg1
</td><td><0：fail, for details, see error code description</td></tr>
</table>

## Download by time video

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">Definition</td><td colspan="2">int   DevDowonLoadByTime(int hUser, String szDevId, byte []pH264_DVR_FINDINFO,   String szFileName, int nSeq)</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Download by time video</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr><td style="text-align:center">devIds</td>
<td>	
Device serial number</td></tr>
<tr><td style="text-align:center">pH264_DVR_FINDINFO
</td><td>Query condition. H264_DVR_FINDINFO object byte stream</td></tr>
<tr><td  style="text-align:center">szFileName</td><td>Saved file path + file name</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td  style="text-align:center">id
</td><td>Message value：EUIMSG   .EMSG_ON_FILE_DOWNLOAD:download function calling result<br/>
EUIMSG   . EMSG_ON_FILE_DLD_COMPLETE:download  completed message callback<br/>
EUIMSG   . EMSG_ON_FILE_DLD_POS:download progress   message callback<br/>
</td></tr>
<tr><td style="text-align:center">arg1
</td><td><0：fail, for details, see error code description</td></tr>
</table>

## Device stop downloading

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">Definition</td><td colspan="2">int   DevStopDownLoad(int hDownload);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Device stop downloading
</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr><td  style="text-align:center">hDownload</td>
<td>	
Download operating object handle</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value: none</td></tr>
<tr><td style="text-align:center">arg1
</td><td><0： fail, for details, see error code description</td></tr>
</table>

## PTZ control

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">Definition</td><td colspan="2">int   DevPTZControl(int hUser, String devId, int nChnIndex, int nPTZCommand, int   bStop, int nSpeed, int nSeq)</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">PTZ control
</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr><td style="text-align:center">devId</td><td>Device serial number</td></tr>
<tr><td style="text-align:center">nChnIndex</td>
<td>Channel number (starting from 0)</td></tr>
<tr><td style="text-align:center">nPTZCommand</td>
<td>PTZ command (see EPTZCMD)</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id</td>
<td>Message value: EUIMSG   . EMSG_DEV_PTZ_CONTROL</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：success；<0:  fail, for details, see error code description</td></tr>
</table>

## Voice talk-back – start

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">Definition</td><td colspan="2">int   DevStarTalk(int hUser, String devId, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Voice talk-back – start 
</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr><td style="text-align:center">devId</td>
<td>Device serial number</td></tr>
<tr><td style="background-color:#ccc;text-align:center">return</td>
<td colspan="2">Voice talk-back object handle, can be used to stop the intercom function</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value：EUIMSG   . EMSG_DEV_START_TALK
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：success；<0:  fail, for details, see error code description</td></tr>
</table>

## Voice talk-back – stop

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">Definition</td><td colspan="2">void   DevStopTalk(int hTalker);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Stop voice talk-back</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr><td style="text-align:center">hTalker</td>
<td>Voice talk-back object operating handle</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value：EUIMSG   . EMSG_DEV_STOP_TALK</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：success；<0:  fail, for details, see error code description</td></tr>
</table>

## Voice talk-back – send data

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">Definition</td><td colspan="2">int   DevSendTalkData(String devId, byte [] pPCMData);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Send client data of voice talk-back</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr><td style="text-align:center">devId</td>
<td>Device serial number</td></tr>
<tr><td style="text-align:center">pPCMData</td>
<td>PCM format data</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value：EUIMSG   . EMSG_DEV_SEND_MEDIA_DATA</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：success；<0:  fail, for details, see error code description</td></tr>
</table>

## Device search

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">Definition</td><td colspan="2">int   DevSearchDevice(int hUser, int nTimeout, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Device search
</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr><td style="text-align:center">nTimeout</td>
<td>Timeout</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value：EUIMSG   . EMSG_DEV_SEARCH_DEVICES
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：success；<0:  fail, for details, see error code description</td></tr>
</table>
.
## Parameter configuration - get configuration

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">Definition</td><td colspan="2">int   DevGetConfig(int hUser, String devId, int nCommand, int nOutBufLen, int   nChannelNO, int nTimeout, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Get device configuration</td></tr>
<tr><td rowspan="6" style="background-color:#ccc;text-align:center"> Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr><td style="text-align:center">devId
</td><td>Device serial number</td></tr>
<tr><td style="text-align:center">nCommand</td>
<td>Configure command word (see EConfigCmd)</td></tr>
<tr><td style="text-align:center">nOutBufLen
</td><td>Result length</td></tr>
<tr><td style="text-align:center">nChannelNO</td>
<td>Channel number (starting from 0)</td></tr>
<tr><td style="text-align:center">nTimeout
</td><td>Timeout</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value：EUIMSG   . EMSG_DEV_GET_CONFIG
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：success；<0:  fail, for details, see error code description</td></tr>
<tr><td style="text-align:center">pData
</td><td>Point to the result object byte stream</td></tr>
</table>

## Parameter configuration – get configuration (Json)

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">Definition</td><td colspan="2">int DevGetConfigByJson(int   hUser, String szDevId,String szCommand,int nOutBufLen,int nChannelNO,int   nTimeout,int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Get device configuration (Json)</td></tr>
<tr><td rowspan="6" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr style="text-align:center"><td>szDevId
</td><td>Device serial number</td></tr>
<tr style="text-align:center"><td>szCommand
</td><td>Configure command word (see EConfigCmd)</td></tr>
<tr style="text-align:center"><td>nOutBufLen
</td><td>	
Result length</td></tr>
<tr style="text-align:center"><td>nChannelNO
</td><td>Channel number (starting from 0)</td></tr>
<tr style="text-align:center"><td>nTimeout
</td><td>Timeout</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value：EUIMSG   . EMSG_DEV_GET_CONFIG_JSON
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：success；<0:  fail, for details, see error code description</td></tr>
<tr><td style="text-align:center">pData
</td><td>Point to the result object byte stream</td></tr>
</table>

## Parameter configuration - save configuration

<table >
<tr><td style="background-color:#ccc;text-align:center;width:20px;">Definition</td><td colspan="2">int   DevSetConfig(int hUser, String devId, int nCommand, byte []pConfig, int   nChannelNO, int nTimeout, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Save device configuration</td></tr>
<tr><td rowspan="6" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr><td style="text-align:center">devId</td>
<td>Device serial number</td></tr>
<tr><td style="text-align:center">nCommand</td>
<td>Configure command word (see EConfigCmd)</td></tr>
<tr><td style="text-align:center">pConfig
</td><td>Configure object byte stream</td></tr>
<tr><td style="text-align:center">nChannelNO
</td><td>Channel number (starting from 0)</td></tr>
<tr><td style="text-align:center">nTimeout
</td><td>Timeout</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value：EUIMSG   . EMSG_DEV_SET_CONFIG
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：success；<0:  fail, for details, see error code description
</td></tr>
</table>

## Parameter configuration - save configuration (Json)

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">Definition</td><td colspan="2">int DevSetConfigByJson(int   hUser, String szDevId,String szCommand,String pConfig,int nChannelNO,int   nTimeout,int   nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Save device configuration (Json)</td></tr>
<tr><td rowspan="6" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>Device serial number</td></tr>
<tr><td style="text-align:center">szCommand</td>
<td>Configure command word (see EConfigCmd)</td></tr>
<tr><td style="text-align:center">pConfig
</td><td>Configure object byte stream</td></tr>
<tr><td style="text-align:center">nChannelNO</td>
<td>Channel number (starting from 0)</td></tr>
<tr><td style="text-align:center">nTimeout
</td><td>Timeout</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value：EUIMSG   . EMSG_DEV_SET_CONFIG_JSON
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：success；<0:  fail, for details, see error code description
</td></tr>
</table>

## Parameter configuration – get device attributes

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">Definition</td><td colspan="2">int   DevGetAttr(int hUser, String devId, int nCommand, int nOutBufLen, int   nChannelNO, int nTimeout, int nSeq);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Get device attributes</td></tr>
<tr><td rowspan="6" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr><td style="text-align:center">devId</td>
<td>Device serial number</td></tr>
<tr><td style="text-align:center">nCommand</td>
<td>Configure command word (see EConfigCmd)</td></tr>
<tr><td style="text-align:center">nOutBufLen
</td><td>Result length</td></tr>
<tr><td style="text-align:center">nChannelNO</td>
<td>Channel number (starting from 0)</td></tr>
<tr><td style="text-align:center">nTimeout
</td><td>Timeout</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value：EUIMSG   . EMSG_DEV_GET_ATTR
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：success；<0:  fail, for details, see error code description</td>
<tr><td style="text-align:center">pData
</td><td>Result return to byte stream</td>
</tr>
</table>

## Parameter configuration – set device attributes

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">Definition</td><td colspan="2">int   DevSetAttr(int hUser, String devId, int nCommand, byte []pConfig, int   nChannelNO, int nTimeout, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Set device attributes</td></tr>
<tr><td rowspan="6" style="background-color:#ccc;text-align:center">Parameters <br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr><td style="text-align:center">devId</td>
<td>Device serial number</td></tr>
<tr><td style="text-align:center">nCommand</td>
<td>Configure command word (see EConfigCmd)</td></tr>
<tr><td style="text-align:center">pConfig
</td><td>Configure object byte stream</td></tr>
<tr><td style="text-align:center">nChannelNO</td>
<td>Channel number (starting from 0)</td></tr>
<tr><td style="text-align:center">nTimeout
</td><td>Timeout</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value：EUIMSG   . EMSG_DEV_SET_ATTR</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：success；<0:  fail, for details, see error code description</td>
</tr>
</table>

## Open quick configuration

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">Definition</td><td colspan="2">int   DevStartAPConfig(int hUser, int nGetRetType,String ssid, String data, String   info, String ipaddr, int type,int   isbroad, int nTimeout);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Open quick configuration</td></tr>
<tr><td rowspan="9" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr><td style="text-align:center">nGetRetType</td>
<td>Get network type</td></tr>
<tr><td style="text-align:center">ssid</td>
<td>id</td></tr>
<tr><td style="text-align:center">data</td>
<td>Data</td></tr>
<tr><td style="text-align:center">info</td>
<td>Information</td></tr>
<tr><td style="text-align:center">ipaddr</td>
<td>IP address</td></tr>
<tr><td style="text-align:center">type</td>
<td>Type</td></tr>
<tr><td style="text-align:center">isbroad</td>
<td>Range</td></tr>
<tr><td style="text-align:center">nTimeout</td>
<td>Timeout</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value：EUIMSG   . EMSG_DEV_AP_CONFIG
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：success；<0:  fail, for details, see error code description</td>
</tr>
</table>

## Close quick configuration

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">Definition</td><td colspan="2">void   DevStopAPConfig();</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Close quick configuration</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr><td style="text-align:center">None  </td>
<td>None  </td></tr>

<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value:</td></tr>
<tr><td style="text-align:center">arg1</td>
<td>None </td></tr>
</table>

## Set WiFi configuration

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">Definition</td><td colspan="2">int DevSetWIFIConfig(int   hUser,byte[] pSDK_NetWifiConfig, int nTimeout, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Set WiFi configuration</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr><td style="text-align:center">pSDK_NetWifiConfig</td>
<td>Network configuration</td></tr>
<tr><td style="text-align:center">nTimeout</td>
<td>Timeout</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value：EUIMSG   . EMSG_DEV_SET_WIFI_CFG</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：success；<0:  fail, for details, see error code description</td>
</tr>
</table>

## Device exit login

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">Definition</td><td colspan="2">int   DevLogout(int hUser, String szDevId, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Device exit login</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>Device serial number</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value: none</td></tr>
<tr><td style="text-align:center">arg1
</td><td> none</td>
</tr>
</table>

## Device options

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">Definition</td><td colspan="2">int   DevOption(int hUser, String szDevId, int nOptId,byte[] pData, int nDataLen,   int param1, int param2, int param3,String szStr, int seq);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">
Device options</td></tr>
<tr><td rowspan="9" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>Device serial number</td></tr>
<tr><td style="text-align:center">nOptId</td>
<td>Option ID</td></tr>
<tr><td style="text-align:center">pData</td>
<td>Data</td></tr>
<tr><td style="text-align:center">nDataLen</td>
<td>Data length</td></tr>
<tr><td style="text-align:center">param1</td>
<td>Parameter1</td></tr>
<tr><td style="text-align:center">param2</td>
<td>Parameter2</td></tr>
<tr><td style="text-align:center">param3</td>
<td>Parameter3</td></tr>
<tr><td style="text-align:center">szStr</td>
<td>Character string</td></tr>
<tr><td rowspan="5" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value：EUIMSG.EMSG_DEV_OPTION</td></tr>
<tr><td style="text-align:center">arg1
</td><td>>=0：success；<0:  fail, for details, see error code description</td>
</tr>
<tr><td style="text-align:center">arg3
</td><td>Option ID in above parameters</td>
</tr>
<tr><td style="text-align:center">pData
</td><td>If there is returned data, then that is the data returned by   the device. Note: it may be empty.</td>
</tr>
</table>

### Transparent serial port

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">Definition</td><td colspan="2">int DevOption(int hUser, String szDevId, int nOptId,byte[] pData, int   nDataLen, int param1, int param2, int param3,String szStr, int seq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">
Transparent serial port  provides three operations: open the serial port, write the serial port and close the serial port</td></tr>
<tr><td rowspan="7" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>Device serial number</td></tr>
<tr><td style="text-align:center">nOptId</td>
<td>Option:<br/>
Open：EDOPT_DEV_OPEN_TANSPORT_COM (5)<br/>
Write：EDOPT_DEV_TANSPORT_COM_WRITE（8）<br/>
 Close：EDA_DEV_CLOSE_TANSPORT_COM(6)<br/>
</td></tr>
<tr><td style="text-align:center">pData</td>
<td>It is effective when writing serial port. There is data to  be written</td></tr>
<tr><td style="text-align:center">nDataLen</td>
<td>Data length</td></tr>
<tr><td style="text-align:center">param1</td>
<td>Serial port type: 0: RS232;  1: RS485</td></tr>
<tr><td style="text-align:center">param2</td>
<td>The recipient of valid data returned by device; if it has been set when opening, it will cover the previous one if you set again when writing. (receiver handle)
</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value：EUIMSG.EMSG_DEV_OPTION
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>>=0：<0:  fail, for details, see error code description</td>
</tr>
<tr><td style="text-align:center">arg3
</td><td>nOptId in parameters</td>
</tr>
<tr><td style="background-color:#ccc;text-align:center">Description
</td><td colspan="2">Device returned data: id: EMSG_DEV_ON_TRANSPORT_COM_DATA（5130）; arg1: data length; pData: data content
</td>
</tr>
</table>

## Device set user data

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">Definition</td><td colspan="2">int   DevSetUserData(int nType, byte[] pData);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">
Device set user data </td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center"> Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr><td style="text-align:center">nType</td>
<td>Type</td></tr>
<tr><td style="text-align:center">pData</td>
<td>User data</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value: none
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>None</td>
</tr>
</table>

## Device check upgrade

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">Definition</td><td colspan="2">int   DevCheckUpgrade(int hUser, String szDevId, int nSeq);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">
Device check upgrade</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center"> Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr style="text-align:center"><td>szDevId</td>
<td>Device serial number</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id</td>
<td>Message value：EUIMSG   . EMSG_DEV_CHECK_UPGRADE</td></tr>
<tr ><td style="text-align:center">arg1
</td><td>0: the latest program currently, 1: support for Cloud upgrade, 2: local or server upgrade; <0: fail, for details, see error code description
</td></tr>
</table>

## Device start to upgrade

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">Definition</td><td colspan="2">int   DevStartUpgrade(int hUser, String szDevId, int nType, int nSeq);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">
Device start to upgrade  </td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>Device serial number</td></tr>
<tr><td style="text-align:center">nType</td>
<td>Upgrade type</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value：EUIMSG   . EMSG_DEV_START_UPGRADE<br/>
During the upgrade, download situation of the upgrade file is     handled via message”   EUIMSG . EMSG_CHECK_FILE_COMPLETE”<br/>
Download progress of the upgrade file is handled via message ” EUIMSG .EMSG_DEV_ON_UPGRADE_PROGRESS”<br/>
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：success；<0:  fail, for details, see error code description</td>
</tr>
</table>

## Upgrade via file

<table >
<tr><td style="background-color:#ccc;text-align:center;width:100px;">Definition</td><td colspan="2">int   DevStartUpgradeByFile(int hUser, String szDevId, String sFileName, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Upgrade via file</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr><td  style="text-align:center">szDevId
</td><td>Device serial number</td></tr>
<tr><td  style="text-align:center">sFileName</td>
<td>Upgrade file name</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td  style="text-align:center">id
</td><td>Message value：EUIMSG   .</td></tr>
<tr><td  style="text-align:center">arg1</td>
<td>==0：success；<0:  fail, for details, see error code description</td></tr>
</table>

## Device stop upgrading

<table >
<tr><td style="background-color:#ccc;text-align:center;width:50px;">Definition</td><td colspan="2">int   DevStopUpgrade(int hUser, String szDevId, int nSeq);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Device stop upgrading</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>Device serial number</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td  style="text-align:center">id
</td><td>Message value：EUIMSG   . EMSG_DEV_STOP_UPGRADE
</td></tr>
<tr><td  style="text-align:center">arg1
</td><td>==0：success；<0:  fail, for details, see error code description</td></tr>
</table>

## Device check upgrade - cloud upgrade

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">Definition</td><td colspan="2">int SysCloudUpGradeCheck (int hUser, String szDevId, int nSeq);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">
Device check upgrade - cloud upgrade</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>Device serial number</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value：EUIMSG . SYS_CLOUDUPGRADE_CHECK
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>0: the latest program currently, 1: device connection upgrade, the  server upgrade, 2: local upgrade, but the upgrade file has not been downloaded; 3: local upgrade, upgrade file has been downloaded, <0: fail, for details, see error code description
</td></tr>
</table>

## Download the upgrade file - cloud upgrade

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">Definition</td><td colspan="2">int SysCloudUpGradeDownLoad (int hUser, String szDevId, int nSeq);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">
Download the upgrade file - cloud upgrade</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center"> Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>Device serial number</td></tr>

<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td  style="text-align:center">id
</td><td>Message value：EUIMSG . SYS_CLOUDUPGRADE_DOWNLOAD
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：success；<0:  fail, for details, see error code description
</td></tr>
</table>

## Stop downloading the upgrade file- cloud upgrade

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">Definition</td><td colspan="2">int SysStopCloudUpGradeDownLoad (int hUser, String szDevId, int nSeq);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">
Upgrade via file</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr><td  style="text-align:center">szDevId</td>
<td>Device serial number</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value：EUIMSG . STOP_CLOUDUPGRADE_DOWNLOAD</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：success；<0:  fail, for details, see error code description</td></tr>
</table>

## Other methods

<table >
<tr><td style="background-color:#ccc;text-align:center;width:16%;">Definition</td><td colspan="5">GetObjHandle(EOOBJECT_ID.EOOBJECT_USER_SERVER)   + SendMsg</td></tr>
<tr><td style="background-color:#ccc;text-align:center;width:16%;">Description</td><td colspan="5">Use GetObjHandle to obtain object ID, complete the sending message processing function via SendMsg</td></tr>
<tr style="background-color:#69c;"><td style="text-align:center;width:16%;">Name+Message ID\ Parameters</td><td>nParam1</td><td>nParam2</td><td>nParam3</td><td>szParam</td><td>pData</td></tr>
<tr style="background-color:#ccc;"><td style="text-align:center;width:16%;">Get public device list</td><td></td><td></td><td></td><td></td><td></td></tr>
<tr><td style="text-align:center;width:16%;">GetPublicDevList</td><td>For details,    see error code
</td><td></td><td></td><td>JSON format</td><td></td></tr>
<tr style="background-color:#ccc;"><td style="text-align:center;width:16%;">Public device
</td><td></td><td></td><td></td><td>Device serial number</td><td></td></tr>
<tr><td style="text-align:center;width:16%;">SetDevPublic</td><td>For details,    see error code</td><td></td><td></td><td></td><td></td></tr>
<tr style="background-color:#ccc;"><td style="text-align:center;width:16%;">Cancel public device
</td><td></td><td></td><td></td><td>Device serial number</td><td></td></tr>
<tr><td style="text-align:center;width:16%;">CancelDevPublic</td><td>For details,    see error code</td><td></td><td></td><td></td><td></td></tr>
<tr style="background-color:#ccc;"><td style="text-align:center;width:16%;">Share device</td><td></td><td></td><td></td><td>Device serial number</td><td></td></tr>
<tr><td style="text-align:center;width:16%;">ShareDevVideo</td><td>For details,    see error code</td><td></td><td></td><td>Media URL</td><td></td></tr>
<tr style="background-color:#ccc;"><td style="text-align:center;width:16%;">Cancel share</td><td></td><td></td><td></td><td>Device serial number</td><td></td></tr>
<tr><td style="text-align:center;width:16%;">CancelShareDevVideo</td><td>For details,    see error code</td><td></td><td></td><td></td><td></td></tr>
<tr style="background-color:#ccc;"><td style="text-align:center;width:16%;">Get share device list</td><td></td><td></td><td></td><td></td><td></td></tr>
<tr><td style="text-align:center;width:16%;">GetShareDevList</td><td>For details,    see error code</td><td></td><td></td><td>JSON format</td><td></td></tr>
<tr style="background-color:#ccc;"><td style="text-align:center;width:16%;">DevRegister</td><td></td><td></td><td></td><td></td><td></td></tr>
<tr><td style="text-align:center;width:16%;">DevRegister</td><td>For details,    see error code</td><td></td><td></td><td>JSON format</td><td></td></tr>
<tr style="background-color:#ccc;"><td style="text-align:center;width:16%;">SendComment</td><td></td><td></td><td></td><td></td><td></td></tr>
<tr><td style="text-align:center;width:16%;">SendComment</td><td>For details,    see error code</td><td></td><td></td><td>JSON format</td><td></td></tr>
<tr style="background-color:#ccc;"><td style="text-align:center;width:16%;">GetCommentList
</td><td></td><td></td><td></td><td></td><td></td></tr>
<tr><td style="text-align:center;width:16%;">GetCommentList</td><td>For details,    see error code</td><td></td><td></td><td>JSON format</td><td></td></tr>
<tr style="background-color:#ccc;"><td style="text-align:center;width:16%;">GetVideoInfo
</td><td></td><td></td><td></td><td></td><td></td></tr>
<tr><td style="text-align:center;width:16%;">GetVideoInfo</td><td>For details,    see error code</td><td></td><td></td><td>JSON format</td><td></td></tr>
<tr style="background-color:#ccc;"><td style="text-align:center;width:16%;">GetUserPhotosList</td><td></td><td></td><td></td><td></td><td></td></tr>
<tr><td style="text-align:center;width:16%;">GetUserPhotosList</td><td>For details,    see error code</td><td></td><td></td><td>JSON format</td><td></td></tr>
<tr style="background-color:#ccc;"><td style="text-align:center;width:16%;">CreateUserPhotos
</td><td></td><td></td><td></td><td></td><td></td></tr>
<tr><td style="text-align:center;width:16%;">UpLoadPhoto</td><td>For details,    see error code</td><td></td><td></td><td>JSON format</td><td></td></tr>
<tr style="background-color:#ccc;"><td style="text-align:center;width:16%;">UpLoadPhoto
</td><td></td><td></td><td></td><td></td><td></td></tr>
<tr><td style="text-align:center;width:16%;">UpLoadPhoto</td><td>For details,    see error code</td><td></td><td></td><td>JSON format</td><td></td></tr>
<tr style="background-color:#ccc;"><td style="text-align:center;width:16%;">EditPhotoInfo
</td><td></td><td></td><td></td><td></td><td></td></tr>
<tr><td style="text-align:center;width:16%;">EditPhotoInfo</td><td>For details,    see error code</td><td></td><td></td><td>JSON format</td><td></td></tr>
<tr style="background-color:#ccc;"><td style="text-align:center;width:16%;">GetPhotoList
</td><td></td><td></td><td></td><td></td><td></td></tr>
<tr><td style="text-align:center;width:16%;">GetPhotoList</td><td>For details,    see error code</td><td></td><td></td><td>JSON format</td><td></td></tr>
<tr style="background-color:#ccc;"><td style="text-align:center;width:16%;">EditShortVideoInfo</td><td></td><td></td><td></td><td></td><td></td></tr>
<tr><td style="text-align:center;width:16%;">EditShortVideoInfo</td><td>For details,    see error code
</td><td></td><td></td><td>JSON format</td><td></td></tr>
<tr style="background-color:#ccc;"><td style="text-align:center;width:16%;">GetShortVideoList</td><td></td><td></td><td></td><td></td><td></td></tr>
<tr><td style="text-align:center;width:16%;">GetShortVideoList</td><td>For details,    see error code
</td><td></td><td></td><td>JSON format</td><td></td></tr>
<tr style="background-color:#ccc;"><td style="text-align:center;width:16%;">KSSAPIUpLoadVideo</td><td></td><td></td><td></td><td></td><td></td></tr>
<tr><td style="text-align:center;width:16%;">KSSAPIUpLoadVideo</td><td>For details,    see error code</td><td></td><td></td><td>JSON format</td><td></td></tr>
</table>

## Get KSS authorization information

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">Definition</td><td colspan="2">int   CSSAPICommandCFS(int hUser, String szDevId, String cmd, String param, String   date, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Turn on / off local area network alarm</td></tr>
<tr><td rowspan="5" style="background-color:#ccc;text-align:center">Parameter <br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr><td style="text-align:center">szDevId
</td><td>Device serial number</td></tr>
<tr><td style="text-align:center">cmd
</td><td>Command character: cfs_info (get bucket、accesskey information),   cfs_sig (get signature)</td></tr>
<tr><td style="text-align:center">param
</td><td>Specific request content JSON format:<br/>
when cmd is cfs_info:  <br/>
{"sigstring":"GET\n\n\n<label style="color:red">Wed,30 Sep 2015 09:08:03 GMT</label>\n/xmcfs/"}<br/>
when cdm is cfs_sig: <br/>
<pre>
{"sigstring":
<b>
 "{     

    "expiration":   "2015-01-01T12:00:00.000Z",

    "conditions": 

      [

        {"acl": "public-read"   },

        {"bucket":   "mybucket" },

        ["starts-with",   "$key", "2015/01/"]

      ]

  }"
</b>
}
</pre>
*The bold part need to use the base64 to encode<br/>
</td></tr>
<tr><td style="text-align:center">date</td><td>Date</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center"> Result <br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value：EUIMSG. CSS_API_CMD_CFS</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：success；<0:  fail, for details, see error code description</td></tr>
</table>

## Set to turn on / off local area network alarm

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">Definition</td><td colspan="2">int DevSetAttrAlarmByInt(int hUser, String szDevId, int nCommand, int nValue, int nSeq)<br/>
int DevSetAttrAlarmByInt(int hUser, String szDevId, int nCommand, int nValue, int nChannelNO, int nTimeout, int nSeq)<br/>
int DevSetAttrAlarmByString(int hUser, String szDevId, int nCommand, String sValue, int nChannelNO, int nTimeout, int nSeq)<br/>
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Set to turn on / off local area network alarm</td></tr>
<tr><td rowspan="6" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>Device serial number</td></tr>
<tr><td style="text-align:center">nCommand</td>
<td>Attribute name: use EDEV_ATTR.EDA_OPT_ALARM（2）</td></tr>
<tr><td style="text-align:center">nValue</td>
<td>Configuration information: 0 for closure, non 0 for open     (recommend to assign 1)</td></tr>
<tr><td style="text-align:center">nChannelNO</td>
<td>Temporarily useless</td></tr>
<tr><td style="text-align:center">nTimeout</td>
<td>Timeout, default 5 seconds</td></tr>
<tr><td rowspan="5" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>	
Message value：EUIMSG.DEV_SET_AT(5110)
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：success；<0:  fail, for details, see error code description</td></tr>
<tr><td style="text-align:center">arg2
</td><td>Configuration information: 0 for closure, 1 for open</td></tr>
<tr><td style="text-align:center">arg3
</td><td>Attribute name: EDEV_ATTR.EDA_OPT_ALARM（2）</td></tr>
<tr><td style="text-align:center">Note
</td><td colspan="2">Android: suggest to use the first function<br/>
IOS: useFUN_DevSetAttr (UI_HANDLE hUser, const char *szDevId, int nCommand, const void *pConfig, int nConfigLen, int nChannelNO = -1, int nTimeout = 15000, int nSeq = 0);<br/>
Note: before calling this function, make sure that it has called DevSetAlarmListener(int hUser, int nSeq), otherwise, real-time alarm message cannot be received.<br/>
</td></tr>
</table>

## Local area network alarm function

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">Definition</td><td colspan="2">int DevSetAlarmListener(int hUser, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Local area network alarm function, set the receiver of the real-time alarm message.  All the device alarm messages are received by the receiver, just set once.</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr><td style="text-align:center">&#160 </td>
<td>&#160</td></tr>
<tr><td rowspan="5" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value：EUIMSG .DEV_GET_LAN_ALARM（5132）</td></tr>
<tr><td style="text-align:center">arg1
</td><td>>0： success (alarm message length)；<=0:  fail, for details, see   error code description</td></tr>
<tr><td style="text-align:center">pData
</td><td>Return alarm message byte stream (json format)</td></tr>
<tr><td style="text-align:center">str
</td><td>Device serial number or ip</td></tr>
</table>

## General command interface

<table >
<tr><td style="background-color:#ccc;text-align:center;width:20px;">Definition</td><td colspan="2">int   DevCmdGeneral(int hUser, String szDevId,int nCmdReq, String szCmd, int   nRetSize, int nTimeout,byte[] pInParam, int nCmdRes, int nSeq);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">This interface is a common interface, most of the commands can be achieved by calling this interface.</td></tr>
<tr><td rowspan="8" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>Serial number</td></tr>
<tr><td style="text-align:center">nCmdReq</td>
<td>Command ID</td></tr>
<tr><td style="text-align:center">szCmd</td>
<td>Command string, cannot be empty. If there is no  this field,  casually assign a string</td></tr>
<tr><td style="text-align:center">nRetSize</td>
<td>When pInParam is the content of json format, assign 0; for  the string, assign 1024</td></tr>
<tr><td style="text-align:center">nTimeout</td>
<td>Timeout (unit: ms), generally 5000~8000</td></tr>
<tr><td style="text-align:center">pInParam</td>
<td>Request information</td></tr>
<tr><td style="text-align:center">nCmdRes</td>
<td>Temporarily useless</td></tr>
<tr><td rowspan="7" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value：EUIMSG   . DEV_CMD_EN</td></tr>
<tr><td style="text-align:center">arg1
</td><td>>=0：success；<0:  fail, for details, see error code description</td></tr>
<tr><td style="text-align:center">arg2
</td><td>Returnd data length</td></tr>
<tr><td style="text-align:center">arg3
</td><td>	
Command ID, that is command ID in parameters</td></tr>
<tr><td style="text-align:center">str
</td><td>Command string, that is command string in parameters</td></tr>
<tr><td style="text-align:center">pData
</td><td>	
Returnd byte stream</td></tr>
</table>
### Video calendar query

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">Definition</td><td colspan="2">int   DevCmdGeneral(int hUser, String szDevId,int nCmdReq, String szCmd, int   nRetSize, int nTimeout,byte[] pInParam, int nCmdRes, int nSeq);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Video calendar query</td></tr>
<tr><td rowspan="8" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>Serial number</td></tr>
<tr><td style="text-align:center">nCmdReq</td>
<td>Command ID:<br/>
&#160&#160&#160&#160 request:FILESEARCH_CALENDAR_REQ   = 1446, <br/>
&#160&#160&#160&#160 feedback:FILESEARCH_CALENDAR_RSP = 1447,<br/>
</td></tr>
<tr><td style="text-align:center">szCmd</td>
<td>Operation command</td></tr>
<tr><td style="text-align:center">nRetSize</td>
<td>0</td></tr>
<tr><td style="text-align:center">nTimeout</td>
<td>Timeout (unit: ms)</td></tr>
<tr><td style="text-align:center">pInParam</td>
<td>Request information</td></tr>
<tr><td style="text-align:center">nCmdRes</td>
<td>Temporarily useless</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value：EUIMSG   .DEV_CMD_EN
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>>=0：success；<0:  fail, for details, see error code description</td></tr>
<tr><td style="text-align:center">Note
</td><td colspan="2">Other information can refer to 4.35</td></tr>
</table>

### Transparent transmission

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">Definition</td><td colspan="2">int   DevCmdGeneral(int hUser, String szDevId,int nCmdReq, String szCmd, int   nRetSize, int nTimeout,byte[] pInParam, int nCmdRes, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Data transparent transmission</td></tr>
<tr><td rowspan="8" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>Serial number</td></tr>
<tr><td style="text-align:center">nCmdReq</td>
<td>Command ID  </td></tr>
<tr><td style="text-align:center">szCmd</td>
<td>Example“hello”</td></tr>
<tr><td style="text-align:center">nRetSize</td>
<td>1024</td></tr>
<tr><td style="text-align:center">nTimeout</td>
<td>Timeout (unit: ms), recommend 5000ms</td></tr>
<tr><td style="text-align:center">pInParam</td>
<td>Data information</td></tr>
<tr><td style="text-align:center">nCmdRes</td>
<td>Temporarily useless</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value：EUIMSG.DEV_CMD_EN
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>>=0：success；<0:  fail, for details, see error code description</td></tr>
<tr><td style="text-align:center">Note
</td><td colspan="2">Other information can refer to 4.35</td></tr>
</table>

### Query monthly video or picture information

<table >
<tr><td style="background-color:#ccc;text-align:center;width:35px;">Definition</td><td colspan="2">int  DevCmdGeneral(int hUser, String szDevId,int   nCmdReq, String szCmd, int   nRetSize, int nTimeout,byte[] pInParam, int   nCmdRes, int nSeq)
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">
Query monthly video or picture information</td></tr>
<tr><td rowspan="8" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>Serial number</td></tr>
<tr><td style="text-align:center">nCmdReq</td>
<td>1446</td></tr>
<tr><td style="text-align:center">szCmd</td>
<td>“OPSCalendar”</td></tr>
<tr><td style="text-align:center">nRetSize</td>
<td>0</td></tr>
<tr><td style="text-align:center">nTimeout</td>
<td>Timeout (unit: ms), recommend 5000ms</td></tr>
<tr><td style="text-align:center">pInParam</td>
<td>
<pre>
{
    "Name":   "OPSCalendar",
      "OPSCalendar": {
        "Event":   "*",
          "FileType": "h264",     //video is “h264"，picture is “jpg”
        "Month":   8,
        "Rev":   "",
        "Year":   2016
    },
    "SessionID":   "0x00000001"

}
</pre></td></tr>
<tr><td style="text-align:center">nCmdRes</td>
<td>Temporarily useless</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value：EUIMSG.DEV_CMD_EN
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>>=0：success；<0:  fail, for details, see error code description</td></tr>
<tr><td style="text-align:center">pData
</td><td colspan="2">
<pre>
{
      "Name": "OPSCalendar",
      "OPSCalendar": {
        "Mask": 0
      },
      "Ret": 100,
      "SessionID": "0x1c"
}
</pre>
Description：Maskis a number of binary 32-bit. Judge from the  first bit, 0: no video, 1: have video, until complete the judgement of the whole month
</td></tr>
</table>

## Query device compressed pictures

<table >
<tr><td style="background-color:#ccc;text-align:center;width:20px;">Definition</td><td colspan="2">int   DevSearchPicture(int hUser, String szDevId,int nCmdReq, int nRetSize, int   nTimeout,byte[] pInParam, int   nCount, int nCmdRes, String szFileName, int nSeq);</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Query device thumbnail</td></tr>
<tr><td rowspan="9" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr><td style="text-align:center">szDevId</td>
<td>Serial number</td></tr>
<tr><td style="text-align:center">nCmdReq</td>
<td>CommandID:<br/>
&#160&#160&#160&#160Request：COMPRESS_PICTURE_REQ   = 1448, <br/>
&#160&#160&#160&#160Feedback：COMPRESS_PICTURE_RSP = 1449,<br/>
</td></tr>
<tr><td style="text-align:center">nRetSize</td>
<td>Return size</td></tr>
<tr><td style="text-align:center">nTimeout</td>
<td>Timeout</td></tr>
<tr><td style="text-align:center">pInParam</td>
<td>Request information</td></tr>
<tr><td style="text-align:center">nCount</td>
<td>Maximum download volume</td></tr>
<tr><td style="text-align:center">nCmdRes</td>
<td>Command matching: ：<br/>
-1：doed not match<br/>
others: matching<br/>
</td></tr>
<tr><td style="text-align:center">szFileName</td>
<td>Pictures file name</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td style="text-align:center">id
</td><td>Message value：EUIMSG   . DEV_SEARCH_PIC
</td></tr>
<tr><td style="text-align:center">arg1
</td><td>==0：success；<0:  fail, for details, see error code description</td></tr>
</table>

## Save device real-time streaming

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">Definition</td><td colspan="2">int DevSaveRealTimeStream (int hUser, String szDevId, int nChannel,   int nStreamType, String szFileName, int nSeq)</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Query device thumbnail</td></tr>
<tr><td rowspan="4" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr><td style="text-align:center">nChannel</td>
<td>Channel number</td></tr>
<tr><td style="text-align:center">nStreamType</td>
<td>Stream type</td></tr>
<tr><td style="text-align:center">szFileName
</td><td>Saved file name (absolute path), for example xx/xx/xx.mp4</td></tr>
<tr><td rowspan="5" style="background-color:#ccc;text-align:center">Result<br/>message
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center;">Description
</td></tr>
<tr><td rowspan="3" style="text-align:center">id
</td><td>START_PLAY(5501),open video</td></tr>
<tr><td>EMSG_ON_MediaData_Save（5528，new add）, start to save data</td></tr>
<tr><td>EMSG_MediaData_Save_Process（5529， new add）, size of saved data, send once per 2 seconds
</td></tr>
<tr><td style="text-align:center">arg1
</td><td><0: fail, for details, see error code description; >=0: success, when  id = EMSG_MediaData_Save_Process, it is the size of saved data</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td>
<td colspan="2">If return failed, do not need to call DevCloseRealTimeStream</td></tr>
</table>

## Stop saving real-time streaming

<table >
<tr><td style="background-color:#ccc;text-align:center;width:40px;">Definition</td><td colspan="2">int DevCloseRealTimeStream(<label
style="color:red">int</label> <label style="color:#f63">hSaveObj<label>)

</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">
Stop saving real-time streaming </td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">Parameters<br/>Description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description</td></tr>
<tr><td style="text-align:center">hSaveObj</td>
<td>Return value of DevSaveRealTimeStream</td></tr>
</table>
<br/>
