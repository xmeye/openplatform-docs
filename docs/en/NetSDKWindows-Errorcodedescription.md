## Error code description

1. Basic error code                            
2. User management error code                
3. configuration management error code         
4. DNS protocol parse error code               
5. Copyright related error code     
6. Upgrade error code                        

  

<hr> 

## Basic error code

<table>
<tr><td style="width:10%;background-color:#fff8dc"> Sequence number
</td><td style="width:35%;background-color:#cc9">Macro definition of error code
</td><td style="width:10%;background-color:pink">Error value
</td><td style="width:35%;background-color:#f08080">Error code meaning</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">1</td><td style="width:35%;background-color:#cc9">H264_DVR_NOERROR</td><td style="width:10%;background-color:pink">0</td><td style="width:35%;background-color:#f08080">No errors</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">2</td><td style="width:35%;background-color:#cc9">H264_DVR_SUCCESS 
</td><td style="width:10%;background-color:pink">1</td><td style="width:35%;background-color:#f08080">Return success</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">3</td><td style="width:35%;background-color:#cc9">H264_DVR_SDK_NOTVALID
</td><td style="width:10%;background-color:pink">-10000
</td><td style="width:35%;background-color:#f08080">Illegal request</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">4</td><td style="width:35%;background-color:#cc9">H264_DVR_NO_INIT 
</td><td style="width:10%;background-color:pink">-10001
</td><td style="width:35%;background-color:#f08080">SDK without initialization</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">5</td><td style="width:35%;background-color:#cc9">H264_DVR_ILLEGAL_PARAM
</td><td style="width:10%;background-color:pink">-10002
</td><td style="width:35%;background-color:#f08080">User parameter is invalid</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">6</td><td style="width:35%;background-color:#cc9">H264_DVR_INVALID_HANDLE
</td><td style="width:10%;background-color:pink">-10003
</td><td style="width:35%;background-color:#f08080">Invalid handle</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">7</td><td style="width:35%;background-color:#cc9">H264_DVR_SDK_UNINIT_ERROR
</td><td style="width:10%;background-color:pink">-10004
</td><td style="width:35%;background-color:#f08080">SDK cleanup error</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">8</td><td style="width:35%;background-color:#cc9">H264_DVR_SDK_TIMEOUT
</td><td style="width:10%;background-color:pink">-10005
</td><td style="width:35%;background-color:#f08080">Wait timeout</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">9</td><td style="width:35%;background-color:#cc9">H264_DVR_SDK_MEMORY_ERROR
</td><td style="width:10%;background-color:pink">-10006
</td><td style="width:35%;background-color:#f08080">Memory error, create memory failed</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">10</td><td style="width:35%;background-color:#cc9">H264_DVR_SDK_NET_ERROR
</td><td style="width:10%;background-color:pink">-10007
</td><td style="width:35%;background-color:#f08080">Network error</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">11</td><td style="width:35%;background-color:#cc9">H264_DVR_SDK_OPEN_FILE_ERROR</td><td style="width:10%;background-color:pink">-10008</td><td style="width:35%;background-color:#f08080">Open file failed</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">12</td><td style="width:35%;background-color:#cc9">H264_DVR_SDK_UNKNOWNERROR</td><td style="width:10%;background-color:pink">-10009</td><td style="width:35%;background-color:#f08080">Unknown error</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">13</td><td style="width:35%;background-color:#cc9">H264_DVR_DEV_VER_NOMATCH</td><td style="width:10%;background-color:pink">-11000</td><td style="width:35%;background-color:#f08080"> The received data is incorrect, the   version may not match</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">14</td><td style="width:35%;background-color:#cc9">H264_DVR_SDK_NOTSUPPORT</td><td style="width:10%;background-color:pink">-11001</td><td style="width:35%;background-color:#f08080">Version not supported
</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">15</td><td style="width:35%;background-color:#cc9">H264_DVR_ANAS_EXIST</td><td style="width:10%;background-color:pink">-11130</td><td style="width:35%;background-color:#f08080">NAS address already exists</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">16</td><td style="width:35%;background-color:#cc9">H264_DVR_ANAS_ALIVE	</td><td style="width:10%;background-color:pink">-11131</td><td style="width:35%;background-color:#f08080">   The path is used and cannot be    operated.</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">17</td><td style="width:35%;background-color:#cc9">H264_DVR_ANAS_FULL</td><td style="width:10%;background-color:pink">-11132</td><td style="width:35%;background-color:#f08080">  NAS has reached the maximum      supported value</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">18</td><td style="width:35%;background-color:#cc9">H264_DVR_OPEN_CHANNEL_ERROR</td><td style="width:10%;background-color:pink">-11200</td><td style="width:35%;background-color:#f08080">Open channel failed, may detect the  device is not online</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">19</td><td style="width:35%;background-color:#cc9">H264_DVR_CLOSE_CHANNEL_ERROR
</td><td style="width:10%;background-color:pink">-11201</td><td style="width:35%;background-color:#f08080">Close channel failed
</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">20</td><td style="width:35%;background-color:#cc9">H264_DVR_SUB_CONNECT_ERROR
</td><td style="width:10%;background-color:pink">-11202</td><td style="width:35%;background-color:#f08080">Eestablish the media sub connection  failed, network errors or devices may not   be online</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">21</td><td style="width:35%;background-color:#cc9">H264_DVR_SUB_CONNECT_SEND_ERROR
</td><td style="width:10%;background-color:pink">-11203</td><td style="width:35%;background-color:#f08080">Media sub connection communication failure, may detect the device is not  online</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">22</td><td style="width:35%;background-color:#cc9">H264_DVR_NATCONNET_REACHED_MAX
</td><td style="width:10%;background-color:pink">-11204
</td><td style="width:35%;background-color:#f08080">Nat video link reaches the maximum, do   not allow the new Nat video link
</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">23</td><td style="width:35%;background-color:#cc9">H264_DVR_NOTSUPPORT
</td><td style="width:10%;background-color:pink">-11205
</td><td style="width:35%;background-color:#f08080">Version not supported</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">24</td><td style="width:35%;background-color:#cc9">H264_DVR_NOTVALID
</td><td style="width:10%;background-color:pink">-11206
</td><td style="width:35%;background-color:#f08080">Illegal request, the main connection  may have been disconnected
</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">25</td><td style="width:35%;background-color:#cc9">H264_DVR_TCPCONNET_REACHED_MAX
</td><td style="width:10%;background-color:pink">-11207
</td><td style="width:35%;background-color:#f08080">Tcp video link   reaches the maximum, do not allow the new Tcp video link
</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">26</td><td style="width:35%;background-color:#cc9">H264_DVR_OPENEDPREVIEW
</td><td style="width:10%;background-color:pink">-11208
</td><td style="width:35%;background-color:#f08080">  The channel has already opened the preview (the opening and   closing of the channel need to correspond one-to-one, if you open several   times and you need to close several times.      Inconsistency will prompt the error;   to prevent the unreasonable design of   the client development logic to increase this error value).
</td><tr>
</table>
<br/>

## User management section error code

 </b></div>
<br/>

<table>
<tr><td style="width:10%;background-color:#fff8dc">Sequence number</td>
<td style="width:35%;background-color:#cc9">Macro definition of error code</td>
<td style="width:10%;background-color:pink">Error value</td><td style="width:35%;background-color:#f08080">Error code   meaning</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">1</td><td style="width:35%;background-color:#cc9">H264_DVR_NOPOWER</td><td style="width:10%;background-color:pink">-11300
</td><td style="width:35%;background-color:#f08080">No permission
</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">2</td><td style="width:35%;background-color:#cc9">H264_DVR_PASSWORD_NOT_VALID</td>
<td style="width:10%;background-color:pink">-11301
</td><td style="width:35%;background-color:#f08080">Incorrect account   and password</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">3</td><td style="width:35%;background-color:#cc9">H264_DVR_LOGIN_USER_NOEXIST
</td><td style="width:10%;background-color:pink">-11302
</td><td style="width:35%;background-color:#f08080">User does not   exist</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">4</td><td style="width:35%;background-color:#cc9">H264_DVR_USER_LOCKED
</td><td style="width:10%;background-color:pink">-11303
</td><td style="width:35%;background-color:#f08080">User is locked</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">5</td><td style="width:35%;background-color:#cc9">H264_DVR_USER_IN_BLACKLIST
</td><td style="width:10%;background-color:pink">-11304
</td><td style="width:35%;background-color:#f08080">  User is not allowed to visit(in the black list)</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">6</td><td style="width:35%;background-color:#cc9">H264_DVR_USER_HAS_USED
</td><td style="width:10%;background-color:pink">-11305
</td><td style="width:35%;background-color:#f08080">User is logged in</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">7</td><td style="width:35%;background-color:#cc9">H264_DVR_USER_NOT_LOGIN
</td><td style="width:10%;background-color:pink">-11306
</td><td style="width:35%;background-color:#f08080"> User is not   logged in</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">8</td><td style="width:35%;background-color:#cc9">H264_DVR_CONNECT_DEVICE_ERROR
</td><td style="width:10%;background-color:pink">-11307
</td><td style="width:35%;background-color:#f08080">Device may not   exist</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">9</td><td style="width:35%;background-color:#cc9">H264_DVR_ACCOUNT_INPUT_NOT_VALID
</td><td style="width:10%;background-color:pink">-11308
</td><td style="width:35%;background-color:#f08080">User management   input is invalid</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">10</td><td style="width:35%;background-color:#cc9">H264_DVR_ACCOUNT_OVERLAP
</td><td style="width:10%;background-color:pink">-11309
</td><td style="width:35%;background-color:#f08080">Index overlap</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">11</td><td style="width:35%;background-color:#cc9">H264_DVR_ACCOUNT_OBJECT_NONE
</td><td style="width:10%;background-color:pink">-11310
</td><td style="width:35%;background-color:#f08080">There is no   object, used for query</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">12</td><td style="width:35%;background-color:#cc9">H264_DVR_ACCOUNT_OBJECT_NOT_VALID
</td><td style="width:10%;background-color:pink">-11311
</td><td style="width:35%;background-color:#f08080">There is no   object</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">13</td><td style="width:35%;background-color:#cc9">H264_DVR_ACCOUNT_OBJECT_IN_USE
</td><td style="width:10%;background-color:pink">-11312
</td><td style="width:35%;background-color:#f08080">Object is being   used</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">14</td><td style="width:35%;background-color:#cc9">H264_DVR_ACCOUNT_SUBSET_OVERLAP
</td><td style="width:10%;background-color:pink">--11313
</td><td style="width:35%;background-color:#f08080"> Subset exceeds range     (for example, the permissions of  group exceed permissions table,    user rights exceed the scope of   the permissions range of group and so on)</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">15</td><td style="width:35%;background-color:#cc9">H264_DVR_ACCOUNT_PWD_NOT_VALID
</td><td style="width:10%;background-color:pink">-11314
</td><td style="width:35%;background-color:#f08080">Incorrect   password</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">16</td><td style="width:35%;background-color:#cc9">H264_DVR_ACCOUNT_PWD_NOT_MATCH
</td><td style="width:10%;background-color:pink">-11315
</td><td style="width:35%;background-color:#f08080">Passwords do not   match</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">17</td><td style="width:35%;background-color:#cc9">H264_DVR_ACCOUNT_RESERVED
</td><td style="width:10%;background-color:pink">-11316
</td><td style="width:35%;background-color:#f08080">Keep account</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">18</td><td style="width:35%;background-color:#cc9">H264_DVR_ACCOUNT_SYS_MAINTAIN
</td><td style="width:10%;background-color:pink">-11317
</td><td style="width:35%;background-color:#f08080">  System maintenance, cannot be logged in</td><tr>
</td><tr>
</table>
<br/>

## Configuration management related error code

<br/>

<table>
<tr><td style="width:10%;background-color:#fff8dc">Sequence number
</td><td style="width:35%;background-color:#cc9">Macro definition of error code
</td><td style="width:10%;background-color:pink">Error value</td><td style="width:35%;background-color:#f08080">Error code meaning</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">1</td><td style="width:35%;background-color:#cc9">H264_DVR_OPT_RESTART
</td><td style="width:10%;background-color:pink">-11400
</td><td style="width:35%;background-color:#f08080">   After saving the configuration, need to restart the application</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">2</td><td style="width:35%;background-color:#cc9">H264_DVR_OPT_REBOOT
</td><td style="width:10%;background-color:pink">-11401
</td><td style="width:35%;background-color:#f08080">Need to reboot the system</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">3</td><td style="width:35%;background-color:#cc9">H264_DVR_OPT_FILE_ERROR
</td><td style="width:10%;background-color:pink">-11402
</td><td style="width:35%;background-color:#f08080">Writing file error</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">4</td><td style="width:35%;background-color:#cc9">H264_DVR_OPT_CAPS_ERROR
</td><td style="width:10%;background-color:pink">-11403
</td><td style="width:35%;background-color:#f08080">Configuration properties are not   supported</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">5</td><td style="width:35%;background-color:#cc9">H264_DVR_OPT_VALIDATE_ERROR
</td><td style="width:10%;background-color:pink">-11404
</td><td style="width:35%;background-color:#f08080">Configuration check failed</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">6</td><td style="width:35%;background-color:#cc9">H264_DVR_OPT_CONFIG_NOT_EXIST
</td><td style="width:10%;background-color:pink">-11405
</td><td style="width:35%;background-color:#f08080">  Requested or setting configuration   does not exist</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">7</td><td style="width:35%;background-color:#cc9">H264_DVR_CTRL_PAUSE_ERROR
</td><td style="width:10%;background-color:pink">-11500
</td><td style="width:35%;background-color:#f08080"> Pause failed</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">8</td><td style="width:35%;background-color:#cc9">H264_DVR_SDK_NOTFOUND
</td><td style="width:10%;background-color:pink">-11501
</td><td style="width:35%;background-color:#f08080">Find failed, not find the   corresponding file</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">9</td><td style="width:35%;background-color:#cc9">H264_DVR_CFG_NOT_ENABLE
</td><td style="width:10%;background-color:pink">-11502
</td><td style="width:35%;background-color:#f08080">Configuration not enabled</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">10</td><td style="width:35%;background-color:#cc9">H264_DVR_DECORD_FAIL
</td><td style="width:10%;background-color:pink">-11503
</td><td style="width:35%;background-color:#f08080">Decode failed</td><tr>
</table>
<br/>

## DNS protocol parse return error code

<br/>

<table>
<tr><td style="width:10%;background-color:#fff8dc">Sequence number
</td><td style="width:35%;background-color:#cc9">Macro definition of   error code
</td><td style="width:10%;background-color:pink">Error value</td><td style="width:35%;background-color:#f08080">Error code meaning</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">1</td><td style="width:35%;background-color:#cc9">H264_DVR_SOCKET_ERROR
</td><td style="width:10%;background-color:pink">-11600
</td><td style="width:35%;background-color:#f08080">Create socket failed </td><tr>
<tr><td style="width:10%;background-color:#fff8dc">2</td><td style="width:35%;background-color:#cc9">H264_DVR_SOCKET_CONNECT
</td><td style="width:10%;background-color:pink">-11601
</td><td style="width:35%;background-color:#f08080">Connect socket failed</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">3</td><td style="width:35%;background-color:#cc9">H264_DVR_SOCKET_DOMAIN
</td><td style="width:10%;background-color:pink">-11602
</td><td style="width:35%;background-color:#f08080">Domain name resolution failed</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">4</td><td style="width:35%;background-color:#cc9">H264_DVR_SOCKET_SEND
</td><td style="width:10%;background-color:pink">-11603
</td><td style="width:35%;background-color:#f08080">Send data failed  </td><tr>
<tr><td style="width:10%;background-color:#fff8dc">5</td><td style="width:35%;background-color:#cc9">H264_DVR_ARSP_NO_DEVICE
</td><td style="width:10%;background-color:pink">-11604
</td><td style="width:35%;background-color:#f08080"> Not get to device information, device should   not be online
</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">6</td><td style="width:35%;background-color:#cc9">H264_DVR_ARSP_BUSING
</td><td style="width:10%;background-color:pink">-11605
</td><td style="width:35%;background-color:#f08080">ARSP server is busy</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">7</td><td style="width:35%;background-color:#cc9">H264_DVR_ARSP_BUSING_SELECT
</td><td style="width:10%;background-color:pink">-11606
</td><td style="width:35%;background-color:#f08080">ARSP server is busy, select failed</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">8</td><td style="width:35%;background-color:#cc9">H264_DVR_ARSP_BUSING_RECVICE
</td><td style="width:10%;background-color:pink">-11607
</td><td style="width:35%;background-color:#f08080">ARSP server is busy, recvice failed</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">9</td><td style="width:35%;background-color:#cc9">H264_DVR_CONNECTSERVER_ERROR
</td><td style="width:10%;background-color:pink">-11608
</td><td style="width:35%;background-color:#f08080">Connect to server failed  </td><tr>
<tr><td style="width:10%;background-color:#fff8dc">10</td><td style="width:35%;background-color:#cc9">H264_DVR_CONNECT_AGNET
</td><td style="width:10%;background-color:pink">-11609
</td><td style="width:35%;background-color:#f08080">Agent</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">11</td><td style="width:35%;background-color:#cc9">H264_DVR_CONNECT_NAT
</td><td style="width:10%;background-color:pink">-11610
</td><td style="width:35%;background-color:#f08080">Nat</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">12</td><td style="width:35%;background-color:#cc9">H264_DVR_CONNECT_FAILED
</td><td style="width:10%;background-color:pink">-11611
</td><td style="width:35%;background-color:#f08080">Connect failed</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">13</td><td style="width:35%;background-color:#cc9">H264_DVR_CONNECT_FULL
</td><td style="width:10%;background-color:pink">-11612
</td><td style="width:35%;background-color:#f08080">Numbers of server connection are full</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">14</td><td style="width:35%;background-color:#cc9">H264_DVR_CLOUD_LOGIN_ERR
</td><td style="width:10%;background-color:pink">-11613
</td><td style="width:35%;background-color:#f08080">  Cloud login specific error code, description: when the login interface   error=-11613, get the error code via H264_DVR_DEVICEINFO member sCloudErrCode.     When the bottom layer   increases the error code, the upper layer   does not add the code.</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">15</td><td style="width:35%;background-color:#cc9">H264_DVR_NO_CONNECT_FRONT
</td><td style="width:10%;background-color:pink">-11614
</td><td style="width:35%;background-color:#f08080">The front-end device is not connected   or the resolution of connected front-end device is unknown</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">16</td><td style="width:35%;background-color:#cc9">H264_DVR_LOGIN_FULL
</td><td style="width:10%;background-color:pink">-11615
</td><td style="width:35%;background-color:#f08080">The login handle reaches its maximum value and cannot   be logged in.
</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">17</td><td style="width:35%;background-color:#cc9">H264_DVR_ARSP_USER_NOEXIST
</td><td style="width:10%;background-color:pink">-11619
</td><td style="width:35%;background-color:#f08080">User does not exist</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">18</td><td style="width:35%;background-color:#cc9">H264_DVR_ARSP_PASSWORD_ERROR
</td><td style="width:10%;background-color:pink">-11620
</td><td style="width:35%;background-color:#f08080">Incorrect account and password</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">19</td><td style="width:35%;background-color:#cc9">H264_DVR_ARSP_QUERY_ERROR
</td><td style="width:10%;background-color:pink">-11621
</td><td style="width:35%;background-color:#f08080">Search failed</td><tr>
</table>
<br/>

## Copyright related

<br/>

<table>
<tr><td style="width:10%;background-color:#fff8dc">Sequence number
</td><td style="width:35%;background-color:#cc9">Macro definition of   error code Error
</td><td style="width:10%;background-color:pink">Error value</td><td style="width:35%;background-color:#f08080">Error code meaning</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">1</td><td style="width:35%;background-color:#cc9">H264_DVR_PIRATESOFTWARE
</td><td style="width:10%;background-color:pink">-11700
</td><td style="width:35%;background-color:#f08080">Device piracy</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">2</td><td style="width:35%;background-color:#cc9">H264_DVR_AUTH_TIMEOUT
</td><td style="width:10%;background-color:pink">-11800
</td><td style="width:35%;background-color:#f08080">Authentication timeout</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">3</td><td style="width:35%;background-color:#cc9">H264_DVR_AUTH_FILE_FAILED
</td><td style="width:10%;background-color:pink">-11801
</td><td style="width:35%;background-color:#f08080">Authentication file failed</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">4</td><td style="width:35%;background-color:#cc9">H264_DVR_GAIN_LIST_TIMEOUT
</td><td style="width:10%;background-color:pink">-11802
</td><td style="width:35%;background-color:#f08080">Get server list timeout</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">5</td><td style="width:35%;background-color:#cc9">H264_DVR_AUTH_CODE_ERR
</td><td style="width:10%;background-color:pink">-11803
</td><td style="width:35%;background-color:#f08080">Authentication code error</td><tr>
</table>

<br/>

## Upgrade error code

<br/>

<table>
<tr><td style="width:10%;background-color:#fff8dc"> Sequence number
</td><td style="width:35%;background-color:#cc9">Macro definition of   error code Error
</td><td style="width:10%;background-color:pink"> Error value</td><td style="width:35%;background-color:#f08080">Error code meaning</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">1</td><td style="width:35%;background-color:#cc9">H264_DVR_NOENOUGH_MEMORY
</td><td style="width:10%;background-color:pink">-11804
</td><td style="width:35%;background-color:#f08080">Insufficient memory</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">2</td><td style="width:35%;background-color:#cc9">H264_DVR_INVALID_FORMAT
</td><td style="width:10%;background-color:pink">-11805
</td><td style="width:35%;background-color:#f08080">Incorrect upgrade file format</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">3</td><td style="width:35%;background-color:#cc9">H264_DVR_UPDATE_PART_FAIL
</td><td style="width:10%;background-color:pink">-11806
</td><td style="width:35%;background-color:#f08080">A partition upgrade failed</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">4</td><td style="width:35%;background-color:#cc9">H264_DVR_INVALID_HARDWARE
</td><td style="width:10%;background-color:pink">-11807
</td><td style="width:35%;background-color:#f08080">Hardware model does not match</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">5</td><td style="width:35%;background-color:#cc9">H264_DVR_INVALID_VENDOR
</td><td style="width:10%;background-color:pink">-11808
</td><td style="width:35%;background-color:#f08080">Customer information does not match</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">6</td><td style="width:35%;background-color:#cc9">H264_DVR_INVALID_COMPALIBLE
</td><td style="width:10%;background-color:pink">-11809
</td><td style="width:35%;background-color:#f08080">Compatible version number of the upgrade program is smaller than the   existing one of device.   Do not allow    the device to upgrade to the old program</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">7</td><td style="width:35%;background-color:#cc9">H264_DVR_INVALID_VERSION
</td><td style="width:10%;background-color:pink">-11810
</td><td style="width:35%;background-color:#f08080"> Illegal version</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">8</td><td style="width:35%;background-color:#cc9">H264_DVR_INVALID_WIFI_DRIVE	
</td><td style="width:10%;background-color:pink">-11811
</td><td style="width:35%;background-color:#f08080">    Under the current WiFi card, WiFi     driver and device of the upgrade program   do not match</td><tr>
</table>
<br/>