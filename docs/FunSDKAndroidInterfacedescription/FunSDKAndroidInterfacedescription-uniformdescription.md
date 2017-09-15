## 统一说明

1) 若无特别说明方法返回“EE_OK”为成功；其它为失败，失败详见“错误码说明”部分

2) 函数功能都是异步消息的方式，直接返回到方法的消息接收者

3) 异步结果消息说明

方法使用异步消息的方式返回结果到调用者界面线程，接口说明如下：

功能接口使用者调用SDK.RegUser(this)方法，完成消息接收者的注册，实现接口“OnFunSDKResult(Message msg, XMSG ex)”，完成消息接收函数的处理。移除注册使用“SDK.UnRegUser()”。注册后，消息接收者会被分配到一个唯一的接收者ID（一个int值），使用相应的功能接口时，此值做为结果接收者标识传到接口中。

4) 一般系统功能相关方法以“Sys”打头；

设备功能相关方法以“Dev”打头

媒体功能相关方法以“Media”打头

5) C++类结构体与Java类可以用统一的转换函数进行与字节流进行相互转换

	     public static int com.basic.BytesToObj(Object obj, byte []bytes);
	
	     public static int com.basic.BytesToObj(Object []objs, byte []bytes);

## 调用流程

<div><img src="http://open.xmeye.net/upload/image/20160516/1463375625617066148.png"></div>
