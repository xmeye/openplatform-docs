## Uniform description

1)  If there is no special description method, then return "EE_OK" for success; other for failure, failure see “error code description” section.<br/>

2) Function is the way of asynchronous message and the message recipient that directly return to the method.<br/>

3) Asynchronous results message description.<br/></b>

The method uses the asynchronous message way to return the result to the caller thread interface, interface descriptions are as follows:<br/>

Functional interface user calls SDK.RegUser (this) method, complete the message receiver's registration, realize the interface “OnFunSDKResult (MSG Message, ex XMSG)”, and complete the processing of the message receiving functions. Remove the registration use “SDK.UnRegUser ()”. After registration, the message recipient is assigned to a unique recipient ID (an int value). When using the corresponding functional interface, this value, which is used as the result recipient identifier, is transferred to the interface.<br/>

<b>4)  The related method of general system method starts with “Sys”;</b><br/>

The related method of device function starts with “Dev”<br/>

The related methods of media function start with “Media”<br/>

<b>5) C++ class structure and Java class can be converted to the byte stream by using the unified transformation function.</b><br/>
	<div style="margin-left:60px;">
	     public static int com.basic.BytesToObj(Object obj, byte []bytes);<br/>
	
	     public static int com.basic.BytesToObj(Object []objs, byte []bytes);<br/>
	</div>
</div>

## Calling process

<div><img src="http://open.xmeye.net/upload/image/20160516/1463375625617066148.png"></div>
