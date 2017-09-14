## Initialization

<table >
<tr><td style="background-color:#ccc;text-align:center;width:80px;">Definition</td><td colspan="2"><b>int Init(int nType = 0, byte []pParam = NULL);
</b></td><tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Function library initialization
</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center;">Parameters<br/>description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr style="text-align:center"><td>nType</td><td>Retain</td></tr>
<tr style="text-align:center"><td>pParam</td><td>public int st_0_nAppType;//APPtype<br/>public int st_1_nSource;//source</td><tr>
<tr><td style="background-color:#ccc;text-align:center">Return</td><td colspan="2" style="text-align:center";>For details, see error code description
</td><tr>
</table>

## Anti-initialization

<table>
<tr><td style="background-color:#ccc;text-align:center;width:200px;">Definition</td><td colspan="2"><b>void UnInit();</b></td><tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Function library anti initialization
</td></tr>
</table>

## Initialization service (AP mode)

<table >
<tr><td style="background-color:#ccc;text-align:center;width:100px;">Definition</td><td colspan="2">int SysInitAsAPModle(String szDBFile);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Initialization service, suitable for AP mode
</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">Paramets <br/>description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr style="text-align:center"><td>szDBFile</td><td>The data file path of device information storage in AP mode
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Return</td><td colspan="2" style="text-align:center";>For details, see error code description</td><tr>
</table>

## Initialization service (Cloud login) 

<table >
<tr><td style="background-color:#ccc;text-align:center;width:100px;">Definition</td><td colspan="2">int SysInitNet(String szIP, int nPort);
</td><tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Initialization service, suitable for Cloud login
</td></tr>
<tr><td rowspan="3" style="background-color:#ccc;text-align:center">Paramets <br/>description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr><td style="text-align:center">szIP</td><td style="text-align:center">Server ip</td></tr>
<tr><td style="text-align:center">nPort</td><td style="text-align:center">Port number</td><tr>
<tr><td style="background-color:#ccc;text-align:center">Return</td><td colspan="2" style="text-align:center";>For details, see error code description

</td><tr>
</table>

## Initialization (NetSDK) 

<table >
<tr><td style="background-color:#ccc;text-align:center;width:100px;">Definition</td><td colspan="2">int InitNetSDK();</td><tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Initialization NetSDK</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">Paramets<br/>Parameters</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr style="height:30px"><td></td><td></td></tr>
<tr><td style="background-color:#ccc;text-align:center">Return</td><td colspan="2" style="text-align:center";>For details, see error code description</td><tr>
</table>

## Anti-initialization (NetSDK) 

<table>
<tr><td style="background-color:#ccc;text-align:center;width:100px;">Definition</td><td colspan="2">void UnInitNetSDK();</td><tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Anti-initialization NetSDK</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">Parameters <br/>description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr style="text-align:center"><td>szDBFile</td><td>The data file path of device information storage in AP mode</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Return</td><td colspan="2" style="text-align:center";>For details, see error code description</td><tr>
</table>

## Initialization service (Local Login）

<table >
<tr><td style="background-color:#ccc;text-align:center;width:100px;">Definition</td><td colspan="2">int SysInitLocal(String szDBFile);</td><tr>
<tr><td style="background-color:#ccc;text-align:center">Description
</td><td colspan="2">Initialization service, suitable for local login</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">Parameters<br/>description
</td><td style="background-color:#ccc;text-align:center;width:20%;">Name
</td><td style="background-color:#ccc;text-align:center">Description

</td></tr>
<tr style="text-align:center"><td>szDBFile</td><td>The path of data storage file of local device information
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Return</td><td colspan="2" style="text-align:center";>For details, see error code description</td><tr>
</table>

## nitialize App certificates

<table >
<tr><td style="background-color:#ccc;text-align:center;width:100px;">Definition</td><td colspan="2">int XMCloundPlatformInit(String uuid, String appKey, String appSecret, int movedCard);</td><tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Initialize App certificates, after app runs, just need to call once
</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">Parameters<br/>description</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr style="text-align:center"><td></td><td>Obtain the field after register application</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Return</td><td colspan="2" style="text-align:center";>For details, see error code description</td><tr>
</table>
