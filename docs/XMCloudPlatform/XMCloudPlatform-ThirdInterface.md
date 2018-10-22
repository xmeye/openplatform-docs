## 报警消息推送对接

以http的POST方式发送给第三方服务器:

body格式: "param=" + json

如下例:

```
POST / HTTP/1.1
Host: xxxx
Content-Type: application/x-www-form-urlencoded
Content-Length: xxx
```

```
param={
	"AlarmEvent": "VideoMotion:1",			//报警类型
	"AlarmID": "18101893921",				//消息Id
	"AlarmMsg": "",							//额外信息
	"AlarmTime": "2018-10-18 09:39:21",		//报警时间
	"AuthCode": "3ead6a672e1c3724",			//忽略
	"Channel": 0,							//报警通道号
	"SerialNumber": "3ead6a672e1c3724",		//设备序列号
	"Status": "appEventStart"				//报警状态(开始 或结束)
}
```