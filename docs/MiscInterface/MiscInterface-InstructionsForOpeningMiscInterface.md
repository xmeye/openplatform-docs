## 文档概述

### 目的

本文旨在阐述部分对外开放接口的使用说明。

### 范围

本文仅供公司内部及授权的合作客户之间传阅，未经杭州雄迈信息技术有限公司授权，不得转发任何第三方使用。

## 接口使用说明

### 获取 HSL 播放地址

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
"deviceSn": "c5bf7751f17a23bd",
"playUrl":"http://pub-dss-hls.secu100.net:8080/hls/0199957bf94b099029/c5bf7751f17a23bd/1.m3u8"
}
```

示例：

```
https://misc.xmeye.net/api/getPlayUrl?
                uuid=9605b67eadbe47c98448f4a72e724bb6
                &appkey=4e5cc7a4424348daa50698771c5fe72a
                &tm=00000011539754039447
                &sign=fa254a979feed5ee840a7c4923497c2b
                &sn=c5bf7751f17a23bd
                &ver=1
```

