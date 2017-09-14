## Initialization

<table >
<tr><td style="background-color:#ccc;text-align:center;width:80px;">Definition</td><td colspan="2"><b>int FUN_Init(int nType = 0, SInitParam *pParam = NULL);
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
<tr><td style="background-color:#ccc;text-align:center;width:200px;">Definition</td><td colspan="2"><b>void FUN_UnInit();</b></td><tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Function library anti initialization
</td></tr>
</table>

## Initialization service (AP mode)

<table >
<tr><td style="background-color:#ccc;text-align:center;width:100px;">Definition</td><td colspan="2">int FUN_SysInitAsAPModle(const char *szDBFile);
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Initialization service, suitable for AP mode
</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">Paramets <br/>description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr style="text-align:center"><td>szDBFile</td><td>The data file path of device information storage in AP mode
</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Return</td><td colspan="2" style="text-align:center";>For details, see error code description</td><tr>
</table>
<br/>

## Initialization service (Cloud login)

<table >
<tr><td style="background-color:#ccc;text-align:center;width:100px;">Definition</td><td colspan="2">int FUN_SysInitNet(const char *szIP, int nPort);
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
<tr><td style="background-color:#ccc;text-align:center;width:100px;">Definition</td><td colspan="2">int FUN_InitNetSDK();</td><tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Initialization NetSDK</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">Paramets<br/>Parameters</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr style="height:30px"><td></td><td></td></tr>
<tr><td style="background-color:#ccc;text-align:center">Return</td><td colspan="2" style="text-align:center";>For details, see error code description</td><tr>
</table>
<br/>

## Anti-initialization (NetSDK)

<table>
<tr><td style="background-color:#ccc;text-align:center;width:100px;">Definition</td><td colspan="2">void FUN_UnInitNetSDK();</td><tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Anti-initialization NetSDK</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">Parameters <br/>description</td><td style="background-color:#ccc;text-align:center;width:20%;">Name</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr style="text-align:center"><td>szDBFile</td><td>The data file path of device information storage in AP mode</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Return</td><td colspan="2" style="text-align:center";>For details, see error code description</td><tr>
</table>
<br/>

## Initialization service (Local Login）

<table >
<tr><td style="background-color:#ccc;text-align:center;width:100px;">Definition</td><td colspan="2">int FUN_SysInitLocal(const char *szDBFile);</td><tr>
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
<br/>

## Initialize App certificates

<table >
<tr><td style="background-color:#ccc;text-align:center;width:100px;">Definition</td><td colspan="2">int FUN_XMCloundPlatformInit(const char *uuid, const char *appKey, const char *appSecret, int movedCard);</td><tr>
<tr><td style="background-color:#ccc;text-align:center">Description</td><td colspan="2">Initialize App certificates, after app runs, just need to call once
</td></tr>
<tr><td rowspan="2" style="background-color:#ccc;text-align:center">Parameters<br/>description</td><td style="background-color:#ccc;text-align:center;width:20%;">名称</td><td style="background-color:#ccc;text-align:center">Description
</td></tr>
<tr style="text-align:center"><td></td><td>Obtain the field after register application</td></tr>
<tr><td style="background-color:#ccc;text-align:center">Return</td><td colspan="2" style="text-align:center";>For details, see error code description</td><tr>
</table>
