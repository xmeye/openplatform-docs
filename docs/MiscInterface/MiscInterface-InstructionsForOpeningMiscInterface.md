## 文档概述

### 目的

本文旨在阐述部分对外开放接口的使用说明。

### 范围

本文仅供公司内部及授权的合作客户之间传阅，未经杭州雄迈信息技术有限公司授权，不得转发任何第三方使用。

## 接口使用说明

### 1.获取 HSL 播放地址

URL : https://misc.xmeye.net/api/getPlayUrl

参数说明：

| 参数名 | 说明 | 必填 | 类型 | 示例 |
| ------ | ------ | ------ | ------ | ------ |
| uuid | 在开发平台注册的 UUID | 是 | [string] | 9605b67eadbe47c98448f4a72e724bb6 |
| appkey | 在开发平台注册的 AppKey(UUID和AppKey 需要提供单独后台授权配置） | 是 | [string] | 4e5cc7a4424348daa50698771c5fe72a |
| tm | 当前时间，参考开放平台->开发者必读->协议规范->2.加密字校验权限算法 | 是 | [string] | 00000011539754039447 |
| sign | 签名，参考开放平台->开发者必读->协议规范->2.加密字校验权限算法 | 是 | [string] | fa254a979feed5ee840a7c4923497c2b |
| sn | 设备序列号 | 是 | [string] | c5bf7751f17a23bd |
| user | 设备登录信息（用户名和密码组成JSON 之后再做 Base64） | 否 | [string] | ewoidSI6ImFkbWluIiwKInAiOiIiCn0= |
| ver | ver=1, AuthCode 验证方式， ver=2，Token 验证方式 | 是 | [string] | 1 |

返回：

```
{
"deviceSn":"b723e62f184f3da8",
"playUrl":"http://pub-dss-hls.secu100.net:8080/hls/YWNiZTQxOWI0NnxiNzIzZTYyZjE4NGYzZGE4fGV5SndJam9pZEd4S2QzQmliellpTENKMUlq4b2lZV1J0YVc0aWZRPT18MTU0MjE5MDYxMDc0NHxkc3N8MTgzLjEyOS4xOTguMjQyfG1kNQ%3D%3D.45203f5d6ba7e1a61f19c2e1aa46cf41/b723e62f184f3da8/1131973286/1.m3u8",
"stopUrl":"http://pub-dss-hls.secu100.net:8080/hls/stop/YWNiZTQxOWI0NnxiNzIzZTYyZjE4NGYzZGE4fGV5SndJam9pZEd4S2QzQmliellpTENKMUlq4b2lZV1J0YVc0aWZRPT18MTU0MjE5MDYxMDc0NHxkc3N8MTgzLjEyOS4xOTguMjQyfG1kNQ%3D%3D.45203f5d6ba7e1a61f19c2e1aa46cf41/b723e62f184f3da8/1131973286/1.m3u8"}
```

示例：

<a href="https://misc.xmeye.net/api/getPlayUrl?uuid=9605b67eadbe47c98448f4a72e724bb6&appkey=4e5cc7a4424348daa50698771c5fe72a&tm=00000011539754039447&sign=fa254a979feed5ee840a7c4923497c2b&sn=c5bf7751f17a23bd&ver=1" target="_blank">https://misc.xmeye.net/api/getPlayUrl?uuid=9605b67eadbe47c98448f4a72e724bb6&appkey=4e5cc7a4424348daa50698771c5fe72a&tm=00000011539754039447&sign=fa254a979feed5ee840a7c4923497c2b&sn=c5bf7751f17a23bd</a>

### 2.获取DSS设备状态

URL : https://misc.xmeye.net/api/queryDssStatus

参数说明：

| 参数名 | 说明 | 必填 | 类型 | 示例 |
| ------ | ------ | ------ | ------ | ------ |
| uuid | 在开发平台注册的 UUID | 是 | [string] | 9605b67eadbe47c98448f4a72e724bb6 |
| appkey | 在开发平台注册的 AppKey(UUID和AppKey 需要提供单独后台授权配置） | 是 | [string] | 4e5cc7a4424348daa50698771c5fe72a |
| tm | 当前时间，参考开放平台->开发者必读->协议规范->2.加密字校验权限算法 | 是 | [string] | 00000011539754039447 |
| sign | 签名，参考开放平台->开发者必读->协议规范->2.加密字校验权限算法 | 是 | [string] | fa254a979feed5ee840a7c4923497c2b |
| sn | 设备序列号 | 是 | [string] | c5bf7751f17a23bd |


返回：

```
{
	"Ret": 200,
	"Msg": "Success",
	"Status": "Online",
	"Channels": [{
		"extra": 1,
		"main": 0
	}]
}
```

示例：

<a href="https://misc.xmeye.net/api/queryDssStatus?uuid=9605b67eadbe47c98448f4a72e724bb6&appkey=4e5cc7a4424348daa50698771c5fe72a&tm=00000011545620799767&sign=ef6e623ba1a07d1289ce68e82bc86a85&sn=c5bf7751f17a23bd" target="_blank">https://misc.xmeye.net/api/queryDssStatus?uuid=9605b67eadbe47c98448f4a72e724bb6&appkey=4e5cc7a4424348daa50698771c5fe72a&tm=00000011545620799767&sign=ef6e623ba1a07d1289ce68e82bc86a85&sn=c5bf7751f17a23bd</a>


### 3.获取报警图片地址

URL : https://misc.xmeye.net/api/getPicUrl

参数说明：

| 参数名 | 说明 | 必填 | 类型 | 示例 |
| ------ | ------ | ------ | ------ | ------ |
| uuid | 在开发平台注册的 UUID | 是 | [string] | 9605b67eadbe47c98448f4a72e724bb6 |
| appkey | 在开发平台注册的 AppKey(UUID和AppKey 需要提供单独后台授权配置） | 是 | [string] | 4e5cc7a4424348daa50698771c5fe72a |
| tm | 当前时间，参考开放平台->开发者必读->协议规范->2.加密字校验权限算法 | 是 | [string] | 00000011539754039447 |
| sign | 签名，参考开放平台->开发者必读->协议规范->2.加密字校验权限算法 | 是 | [string] | fa254a979feed5ee840a7c4923497c2b |
| sn | 设备序列号 | 是 | [string] | c5bf7751f17a23bd |
| alarmid | 报警ID（从报警消息中获取） | 是 | [long] | 123|

返回：

```
{"deviceSn":"c5bf7751f17a23bd",
  "alarmId":"123",
  "picUrl":"http://118.31.244.240:8082/download/YWNiZTQxOWI0NnxjNWJmNzc1MWYxN2EyM2JkfEB8MTU0NT4c5MTgwNzcyNHxwaWN8MTgzLjEyOS4xOTguMjQyfG1kNQ%3D%3D.1b84a7f959f512287525297150dca42d/c5bf7751f17a23bd/123.jpeg"}
```

示例：

<a href="https://misc.xmeye.net/api/getPicUrl?uuid=9605b67eadbe47c98448f4a72e724bb6&appkey=4e5cc7a4424348daa50698771c5fe72a&tm=00000011545620799767&sign=ef6e623ba1a07d1289ce68e82bc86a85&sn=c5bf7751f17a23bd&alarmid=123" target="_blank">https://misc.xmeye.net/api/getPicUrl?uuid=9605b67eadbe47c98448f4a72e724bb6&appkey=4e5cc7a4424348daa50698771c5fe72a&tm=00000011545620799767&sign=ef6e623ba1a07d1289ce68e82bc86a85&sn=c5bf7751f17a23bd&alarmid=123</a>



