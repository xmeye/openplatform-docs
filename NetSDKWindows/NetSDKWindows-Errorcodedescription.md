## 基本错误码

<style>
	table{
		text-align:center;
		border-collapse:collapse;
		width:100%;
	}
	table tr td{
		border:1px solid #fff;
	}
</style>
<table>
<tr><td style="width:10%;background-color:#fff8dc">序号</td><td style="width:35%;background-color:#cc9">错误码对应的宏定义</td><td style="width:10%;background-color:pink">错误值</td><td style="width:35%;background-color:#f08080">错误码意义</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">1</td><td style="width:35%;background-color:#cc9">H264_DVR_NOERROR</td><td style="width:10%;background-color:pink">0</td><td style="width:35%;background-color:#f08080">没有错误</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">2</td><td style="width:35%;background-color:#cc9">H264_DVR_SUCCESS 
</td><td style="width:10%;background-color:pink">1</td><td style="width:35%;background-color:#f08080">返回成功</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">3</td><td style="width:35%;background-color:#cc9">H264_DVR_SDK_NOTVALID
</td><td style="width:10%;background-color:pink">-10000
</td><td style="width:35%;background-color:#f08080">非法请求</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">4</td><td style="width:35%;background-color:#cc9">H264_DVR_NO_INIT 
</td><td style="width:10%;background-color:pink">-10001
</td><td style="width:35%;background-color:#f08080">SDK未经初始化</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">5</td><td style="width:35%;background-color:#cc9">H264_DVR_ILLEGAL_PARAM
</td><td style="width:10%;background-color:pink">-10002
</td><td style="width:35%;background-color:#f08080">用户参数不合法</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">6</td><td style="width:35%;background-color:#cc9">H264_DVR_INVALID_HANDLE
</td><td style="width:10%;background-color:pink">-10003
</td><td style="width:35%;background-color:#f08080">句柄无效</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">7</td><td style="width:35%;background-color:#cc9">H264_DVR_SDK_UNINIT_ERROR
</td><td style="width:10%;background-color:pink">-10004
</td><td style="width:35%;background-color:#f08080">SDK清理出错</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">8</td><td style="width:35%;background-color:#cc9">H264_DVR_SDK_TIMEOUT
</td><td style="width:10%;background-color:pink">-10005
</td><td style="width:35%;background-color:#f08080">等待超时</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">9</td><td style="width:35%;background-color:#cc9">H264_DVR_SDK_MEMORY_ERROR
</td><td style="width:10%;background-color:pink">-10006
</td><td style="width:35%;background-color:#f08080">内存错误，创建内存</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">10</td><td style="width:35%;background-color:#cc9">H264_DVR_SDK_NET_ERROR
</td><td style="width:10%;background-color:pink">-10007
</td><td style="width:35%;background-color:#f08080">网络错误
</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">11</td><td style="width:35%;background-color:#cc9">H264_DVR_SDK_OPEN_FILE_ERROR</td><td style="width:10%;background-color:pink">-10008</td><td style="width:35%;background-color:#f08080">打开文件失败</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">12</td><td style="width:35%;background-color:#cc9">H264_DVR_SDK_UNKNOWNERROR</td><td style="width:10%;background-color:pink">-10009</td><td style="width:35%;background-color:#f08080">未知错误</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">13</td><td style="width:35%;background-color:#cc9">H264_DVR_DEV_VER_NOMATCH</td><td style="width:10%;background-color:pink">-11000</td><td style="width:35%;background-color:#f08080">收到数据不正确，可能版本不匹配</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">14</td><td style="width:35%;background-color:#cc9">H264_DVR_SDK_NOTSUPPORT</td><td style="width:10%;background-color:pink">-11001</td><td style="width:35%;background-color:#f08080">版本不支持</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">15</td><td style="width:35%;background-color:#cc9">H264_DVR_ANAS_EXIST</td><td style="width:10%;background-color:pink">-11130</td><td style="width:35%;background-color:#f08080">NAS地址已存在</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">16</td><td style="width:35%;background-color:#cc9">H264_DVR_ANAS_ALIVE	</td><td style="width:10%;background-color:pink">-11131</td><td style="width:35%;background-color:#f08080">路径被使用，无法操作</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">17</td><td style="width:35%;background-color:#cc9">H264_DVR_ANAS_FULL</td><td style="width:10%;background-color:pink">-11132</td><td style="width:35%;background-color:#f08080">NAS已达到支持的最大值</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">18</td><td style="width:35%;background-color:#cc9">H264_DVR_OPEN_CHANNEL_ERROR</td><td style="width:10%;background-color:pink">-11200</td><td style="width:35%;background-color:#f08080">打开通道失败,可能检测到设备已经不在线</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">19</td><td style="width:35%;background-color:#cc9">H264_DVR_CLOSE_CHANNEL_ERROR
</td><td style="width:10%;background-color:pink">-11201</td><td style="width:35%;background-color:#f08080">关闭通道失败</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">20</td><td style="width:35%;background-color:#cc9">H264_DVR_SUB_CONNECT_ERROR
</td><td style="width:10%;background-color:pink">-11202</td><td style="width:35%;background-color:#f08080">建立媒体子连接失败,网络出错或者设备可能不在线
</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">21</td><td style="width:35%;background-color:#cc9">H264_DVR_SUB_CONNECT_SEND_ERROR
</td><td style="width:10%;background-color:pink">-11203</td><td style="width:35%;background-color:#f08080">媒体子连接通讯失败,可能检测到设备已经不在线
</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">22</td><td style="width:35%;background-color:#cc9">H264_DVR_NATCONNET_REACHED_MAX
</td><td style="width:10%;background-color:pink">-11204
</td><td style="width:35%;background-color:#f08080">Nat视频链接达到最大，不允许新的Nat视频链接</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">23</td><td style="width:35%;background-color:#cc9">H264_DVR_NOTSUPPORT
</td><td style="width:10%;background-color:pink">-11205
</td><td style="width:35%;background-color:#f08080">版本不支持</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">24</td><td style="width:35%;background-color:#cc9">H264_DVR_NOTVALID
</td><td style="width:10%;background-color:pink">-11206
</td><td style="width:35%;background-color:#f08080">请求非法,主连接可能已断开</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">25</td><td style="width:35%;background-color:#cc9">H264_DVR_TCPCONNET_REACHED_MAX
</td><td style="width:10%;background-color:pink">-11207
</td><td style="width:35%;background-color:#f08080">Tcp视频链接达到最大，不允许新的Tcp视频链接</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">26</td><td style="width:35%;background-color:#cc9">H264_DVR_OPENEDPREVIEW
</td><td style="width:10%;background-color:pink">-11208
</td><td style="width:35%;background-color:#f08080">该通道已经打开预览(通道的打开关闭需要一一对应,打开几次需要关闭几次不一致会打开提示该错误;预防客户端开发逻辑上的不合理设计增加该错误值)
</td><tr>
</table>

## 用户管理部分错误码 

<table>
<tr><td style="width:10%;background-color:#fff8dc">序号</td><td style="width:35%;background-color:#cc9">错误码对应的宏定义</td><td style="width:10%;background-color:pink">错误值</td><td style="width:35%;background-color:#f08080">错误码意义</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">1</td><td style="width:35%;background-color:#cc9">H264_DVR_NOPOWER</td><td style="width:10%;background-color:pink">-11300
</td><td style="width:35%;background-color:#f08080">无权限</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">2</td><td style="width:35%;background-color:#cc9">H264_DVR_PASSWORD_NOT_VALID</td>
<td style="width:10%;background-color:pink">-11301
</td><td style="width:35%;background-color:#f08080">账号密码不对</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">3</td><td style="width:35%;background-color:#cc9">H264_DVR_LOGIN_USER_NOEXIST
</td><td style="width:10%;background-color:pink">-11302
</td><td style="width:35%;background-color:#f08080">用户不存在</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">4</td><td style="width:35%;background-color:#cc9">H264_DVR_USER_LOCKED
</td><td style="width:10%;background-color:pink">-11303
</td><td style="width:35%;background-color:#f08080">该用户被锁定</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">5</td><td style="width:35%;background-color:#cc9">H264_DVR_USER_IN_BLACKLIST
</td><td style="width:10%;background-color:pink">-11304
</td><td style="width:35%;background-color:#f08080">该用户不允许访问(在黑名单中)</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">6</td><td style="width:35%;background-color:#cc9">H264_DVR_USER_HAS_USED
</td><td style="width:10%;background-color:pink">-11305
</td><td style="width:35%;background-color:#f08080">该用户已登陆</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">7</td><td style="width:35%;background-color:#cc9">H264_DVR_USER_NOT_LOGIN
</td><td style="width:10%;background-color:pink">-11306
</td><td style="width:35%;background-color:#f08080"> 该用户没有登陆</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">8</td><td style="width:35%;background-color:#cc9">H264_DVR_CONNECT_DEVICE_ERROR
</td><td style="width:10%;background-color:pink">-11307
</td><td style="width:35%;background-color:#f08080">可能设备不存在</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">9</td><td style="width:35%;background-color:#cc9">H264_DVR_ACCOUNT_INPUT_NOT_VALID
</td><td style="width:10%;background-color:pink">-11308
</td><td style="width:35%;background-color:#f08080">用户管理输入不合法</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">10</td><td style="width:35%;background-color:#cc9">H264_DVR_ACCOUNT_OVERLAP
</td><td style="width:10%;background-color:pink">-11309
</td><td style="width:35%;background-color:#f08080">索引重复</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">11</td><td style="width:35%;background-color:#cc9">H264_DVR_ACCOUNT_OBJECT_NONE
</td><td style="width:10%;background-color:pink">-11310
</td><td style="width:35%;background-color:#f08080">不存在对象, 用于查询时</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">12</td><td style="width:35%;background-color:#cc9">H264_DVR_ACCOUNT_OBJECT_NOT_VALID
</td><td style="width:10%;background-color:pink">-11311
</td><td style="width:35%;background-color:#f08080">不存在对象</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">13</td><td style="width:35%;background-color:#cc9">H264_DVR_ACCOUNT_OBJECT_IN_USE
</td><td style="width:10%;background-color:pink">-11312
</td><td style="width:35%;background-color:#f08080">对象正在使用</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">14</td><td style="width:35%;background-color:#cc9">H264_DVR_ACCOUNT_SUBSET_OVERLAP
</td><td style="width:10%;background-color:pink">--11313
</td><td style="width:35%;background-color:#f08080">子集超范围 (如组的权限超过权限表，用户权限超出组的权限范围等等)</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">15</td><td style="width:35%;background-color:#cc9">H264_DVR_ACCOUNT_PWD_NOT_VALID
</td><td style="width:10%;background-color:pink">-11314
</td><td style="width:35%;background-color:#f08080">密码不正确</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">16</td><td style="width:35%;background-color:#cc9">H264_DVR_ACCOUNT_PWD_NOT_MATCH
</td><td style="width:10%;background-color:pink">-11315
</td><td style="width:35%;background-color:#f08080">密码不匹配</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">17</td><td style="width:35%;background-color:#cc9">H264_DVR_ACCOUNT_RESERVED
</td><td style="width:10%;background-color:pink">-11316
</td><td style="width:35%;background-color:#f08080">保留帐号</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">18</td><td style="width:35%;background-color:#cc9">H264_DVR_ACCOUNT_SYS_MAINTAIN
</td><td style="width:10%;background-color:pink">-11317
</td><td style="width:35%;background-color:#f08080">系统维护中，不可登陆</td><tr>
</td><tr>
</table>

## 配置管理相关错误码

<table>
<tr><td style="width:10%;background-color:#fff8dc">序号</td><td style="width:35%;background-color:#cc9">错误码对应的宏定义</td><td style="width:10%;background-color:pink">错误值</td><td style="width:35%;background-color:#f08080">错误码意义</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">1</td><td style="width:35%;background-color:#cc9">H264_DVR_OPT_RESTART
</td><td style="width:10%;background-color:pink">-11400
</td><td style="width:35%;background-color:#f08080">保存配置后需要重启应用程序</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">2</td><td style="width:35%;background-color:#cc9">H264_DVR_OPT_REBOOT
</td><td style="width:10%;background-color:pink">-11401
</td><td style="width:35%;background-color:#f08080">需要重启系统</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">3</td><td style="width:35%;background-color:#cc9">H264_DVR_OPT_FILE_ERROR
</td><td style="width:10%;background-color:pink">-11402
</td><td style="width:35%;background-color:#f08080">写文件出错</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">4</td><td style="width:35%;background-color:#cc9">H264_DVR_OPT_CAPS_ERROR
</td><td style="width:10%;background-color:pink">-11403
</td><td style="width:35%;background-color:#f08080">配置特性不支持</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">5</td><td style="width:35%;background-color:#cc9">H264_DVR_OPT_VALIDATE_ERROR
</td><td style="width:10%;background-color:pink">-11404
</td><td style="width:35%;background-color:#f08080">配置校验失败</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">6</td><td style="width:35%;background-color:#cc9">H264_DVR_OPT_CONFIG_NOT_EXIST
</td><td style="width:10%;background-color:pink">-11405
</td><td style="width:35%;background-color:#f08080">请求或者设置的配置不存在</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">7</td><td style="width:35%;background-color:#cc9">H264_DVR_CTRL_PAUSE_ERROR
</td><td style="width:10%;background-color:pink">-11500
</td><td style="width:35%;background-color:#f08080"> 暂停失败</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">8</td><td style="width:35%;background-color:#cc9">H264_DVR_SDK_NOTFOUND
</td><td style="width:10%;background-color:pink">-11501
</td><td style="width:35%;background-color:#f08080">查找失败，没有找到对应文件</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">9</td><td style="width:35%;background-color:#cc9">H264_DVR_CFG_NOT_ENABLE
</td><td style="width:10%;background-color:pink">-11502
</td><td style="width:35%;background-color:#f08080">配置未启用</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">10</td><td style="width:35%;background-color:#cc9">H264_DVR_DECORD_FAIL
</td><td style="width:10%;background-color:pink">-11503
</td><td style="width:35%;background-color:#f08080">解码失败</td><tr>
</table>

## DNS协议解析返回错误码

<table>
<tr><td style="width:10%;background-color:#fff8dc">序号</td><td style="width:35%;background-color:#cc9">错误码对应的宏定义</td><td style="width:10%;background-color:pink">错误值</td><td style="width:35%;background-color:#f08080">错误码意义</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">1</td><td style="width:35%;background-color:#cc9">H264_DVR_SOCKET_ERROR
</td><td style="width:10%;background-color:pink">-11600
</td><td style="width:35%;background-color:#f08080">创建套节字失败</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">2</td><td style="width:35%;background-color:#cc9">H264_DVR_SOCKET_CONNECT
</td><td style="width:10%;background-color:pink">-11601
</td><td style="width:35%;background-color:#f08080">连接套节字失败</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">3</td><td style="width:35%;background-color:#cc9">H264_DVR_SOCKET_DOMAIN
</td><td style="width:10%;background-color:pink">-11602
</td><td style="width:35%;background-color:#f08080">域名解析失败</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">4</td><td style="width:35%;background-color:#cc9">H264_DVR_SOCKET_SEND
</td><td style="width:10%;background-color:pink">-11603
</td><td style="width:35%;background-color:#f08080">发送数据失败</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">5</td><td style="width:35%;background-color:#cc9">H264_DVR_ARSP_NO_DEVICE
</td><td style="width:10%;background-color:pink">-11604
</td><td style="width:35%;background-color:#f08080">没有获取到设备信息，设备应该不在线
</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">6</td><td style="width:35%;background-color:#cc9">H264_DVR_ARSP_BUSING
</td><td style="width:10%;background-color:pink">-11605
</td><td style="width:35%;background-color:#f08080">ARSP服务繁忙</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">7</td><td style="width:35%;background-color:#cc9">H264_DVR_ARSP_BUSING_SELECT
</td><td style="width:10%;background-color:pink">-11606
</td><td style="width:35%;background-color:#f08080">ARSP服务繁忙,select失败</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">8</td><td style="width:35%;background-color:#cc9">H264_DVR_ARSP_BUSING_RECVICE
</td><td style="width:10%;background-color:pink">-11607
</td><td style="width:35%;background-color:#f08080">ARSP服务繁忙,recvice失败</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">9</td><td style="width:35%;background-color:#cc9">H264_DVR_CONNECTSERVER_ERROR
</td><td style="width:10%;background-color:pink">-11608
</td><td style="width:35%;background-color:#f08080">连接服务器失败</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">10</td><td style="width:35%;background-color:#cc9">H264_DVR_CONNECT_AGNET
</td><td style="width:10%;background-color:pink">-11609
</td><td style="width:35%;background-color:#f08080">代理</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">11</td><td style="width:35%;background-color:#cc9">H264_DVR_CONNECT_NAT
</td><td style="width:10%;background-color:pink">-11610
</td><td style="width:35%;background-color:#f08080">穿透</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">12</td><td style="width:35%;background-color:#cc9">H264_DVR_CONNECT_FAILED
</td><td style="width:10%;background-color:pink">-11611
</td><td style="width:35%;background-color:#f08080">连接失败</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">13</td><td style="width:35%;background-color:#cc9">H264_DVR_CONNECT_FULL
</td><td style="width:10%;background-color:pink">-11612
</td><td style="width:35%;background-color:#f08080">服务器连接数已满</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">14</td><td style="width:35%;background-color:#cc9">H264_DVR_CLOUD_LOGIN_ERR
</td><td style="width:10%;background-color:pink">-11613
</td><td style="width:35%;background-color:#f08080">云登陆具体的错误码,说明:当登陆接口的error=-11613时，通过H264_DVR_DEVICEINFO成员sCloudErrCode获取错误码,底层增加错误码时上层不用增加代码</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">15</td><td style="width:35%;background-color:#cc9">H264_DVR_NO_CONNECT_FRONT
</td><td style="width:10%;background-color:pink">-11614
</td><td style="width:35%;background-color:#f08080">前端设备未连接或者连接的前端设备分辨率未知
</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">16</td><td style="width:35%;background-color:#cc9">H264_DVR_LOGIN_FULL
</td><td style="width:10%;background-color:pink">-11615
</td><td style="width:35%;background-color:#f08080">登录句柄已达到最大值，无法再登录
</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">17</td><td style="width:35%;background-color:#cc9">H264_DVR_ARSP_USER_NOEXIST
</td><td style="width:10%;background-color:pink">-11619
</td><td style="width:35%;background-color:#f08080">用户不存在</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">18</td><td style="width:35%;background-color:#cc9">H264_DVR_ARSP_PASSWORD_ERROR
</td><td style="width:10%;background-color:pink">-11620
</td><td style="width:35%;background-color:#f08080">账号密码不对</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">19</td><td style="width:35%;background-color:#cc9">H264_DVR_ARSP_QUERY_ERROR
</td><td style="width:10%;background-color:pink">-11621
</td><td style="width:35%;background-color:#f08080">查询失败</td><tr>
</table>

## 版权相关

<table>
<tr><td style="width:10%;background-color:#fff8dc">序号</td><td style="width:35%;background-color:#cc9">错误码对应的宏定义</td><td style="width:10%;background-color:pink">错误值</td><td style="width:35%;background-color:#f08080">错误码意义</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">1</td><td style="width:35%;background-color:#cc9">H264_DVR_PIRATESOFTWARE
</td><td style="width:10%;background-color:pink">-11700
</td><td style="width:35%;background-color:#f08080">设备盗版</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">2</td><td style="width:35%;background-color:#cc9">H264_DVR_AUTH_TIMEOUT
</td><td style="width:10%;background-color:pink">-11800
</td><td style="width:35%;background-color:#f08080">鉴权超时</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">3</td><td style="width:35%;background-color:#cc9">H264_DVR_AUTH_FILE_FAILED
</td><td style="width:10%;background-color:pink">-11801
</td><td style="width:35%;background-color:#f08080">鉴权文件失败</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">4</td><td style="width:35%;background-color:#cc9">H264_DVR_GAIN_LIST_TIMEOUT
</td><td style="width:10%;background-color:pink">-11802
</td><td style="width:35%;background-color:#f08080">获取服务器列表超时</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">5</td><td style="width:35%;background-color:#cc9">H264_DVR_AUTH_CODE_ERR
</td><td style="width:10%;background-color:pink">-11803
</td><td style="width:35%;background-color:#f08080">鉴权码错误</td><tr>
</table>

## 升级错误码

<table>
<tr><td style="width:10%;background-color:#fff8dc">序号</td><td style="width:35%;background-color:#cc9">错误码对应的宏定义</td><td style="width:10%;background-color:pink">错误值</td><td style="width:35%;background-color:#f08080">错误码意义</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">1</td><td style="width:35%;background-color:#cc9">H264_DVR_NOENOUGH_MEMORY
</td><td style="width:10%;background-color:pink">-11804
</td><td style="width:35%;background-color:#f08080">内存不足</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">2</td><td style="width:35%;background-color:#cc9">H264_DVR_INVALID_FORMAT
</td><td style="width:10%;background-color:pink">-11805
</td><td style="width:35%;background-color:#f08080">升级文件格式不对</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">3</td><td style="width:35%;background-color:#cc9">H264_DVR_UPDATE_PART_FAIL
</td><td style="width:10%;background-color:pink">-11806
</td><td style="width:35%;background-color:#f08080">某个分区升级失败</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">4</td><td style="width:35%;background-color:#cc9">H264_DVR_INVALID_HARDWARE
</td><td style="width:10%;background-color:pink">-11807
</td><td style="width:35%;background-color:#f08080">硬件型号不匹配</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">5</td><td style="width:35%;background-color:#cc9">H264_DVR_INVALID_VENDOR
</td><td style="width:10%;background-color:pink">-11808
</td><td style="width:35%;background-color:#f08080">客户信息不匹配</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">6</td><td style="width:35%;background-color:#cc9">H264_DVR_INVALID_COMPALIBLE
</td><td style="width:10%;background-color:pink">-11809
</td><td style="width:35%;background-color:#f08080">升级程序的兼容版本号比设备现有的小，不允许设备升级回老程序</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">7</td><td style="width:35%;background-color:#cc9">H264_DVR_INVALID_VERSION
</td><td style="width:10%;background-color:pink">-11810
</td><td style="width:35%;background-color:#f08080"> 非法的版本</td><tr>
<tr><td style="width:10%;background-color:#fff8dc">8</td><td style="width:35%;background-color:#cc9">H264_DVR_INVALID_WIFI_DRIVE	
</td><td style="width:10%;background-color:pink">-11811
</td><td style="width:35%;background-color:#f08080">升级程序里wifi驱动和设备当前在使用的wifi网卡不匹配</td><tr>
</table>
