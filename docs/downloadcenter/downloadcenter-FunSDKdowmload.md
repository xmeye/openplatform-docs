## SDK和Demo下载地址

<style>
	#table1{
		width:1000px;
		border-collapse:collapse;
		text-align:center;
	}
	table tr:hover{
	    background-color:#f5f5f5;
	}

</style>
<table id="table1">
<tr><td style="width:300px;"><img src="http://open.xmeye.net/upload/image/20160516/1463375682024076806.png"></td>
	<td><a href="http://xmopen.ks3-cn-beijing.ksyun.com/funsdk/ios/FunSDK.framework_iOS_ForCustom_V1.2.7_171023.zip">下载 SDK for iOS 2017-10-23</a></td>
	<td><a href="http://xmopen.ks3-cn-beijing.ksyun.com/funsdk/ios/FunSDKDemo_iOS_New_V1.5.zip">下载 Demo  for iOS 2018-01-10</a></td></tr>
<tr><td><img src="http://open.xmeye.net/upload/image/20160516/1463375687266037320.png"></td>
	<td><a href="http://xmopen.ks3-cn-beijing.ksyun.com/funsdk/android/FunSDKLibs_ReleaseV1.1.9_20171014.zip">下载 SDK for Android v1.1.9 2017-10-14</a>
</td><td><a href="http://xmopen.ks3-cn-beijing.ksyun.com/funsdk/android/FunSDKDemo_v1.4.0_20171127.zip">下载 Demo for Android v1.4.0 2017-11-27</a> 
</td></tr>
</table>

## 集成相关问题及解决方法

<div style="margin-left:20px;">
1. FunSDKDemo集成常见bug(ios).docx  <a href="http://xmopen.ks3-cn-beijing.ksyun.com/funsdk/ios/FunSDKDemo%E9%9B%86%E6%88%90%E5%B8%B8%E8%A7%81bug%28iOS%29.docx">下载</a><br/>
2. 开放平台FunSDK使用时常见问题以及解决方法.docx  <a href="http://xmopen.ks3-cn-beijing.ksyun.com/funsdk/SDK/%E5%BC%80%E6%94%BE%E5%B9%B3%E5%8F%B0FunSDK%E4%BD%BF%E7%94%A8%E6%97%B6%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98%E4%BB%A5%E5%8F%8A%E8%A7%A3%E5%86%B3%E6%96%B9%E6%B3%95.docx"> 下载 </a><br/>    
3. FunSDK库使用说明(ios).doc   <a href="http://xmopen.ks3-cn-beijing.ksyun.com/funsdk/ios/FunSDK%E5%BA%93%E4%BD%BF%E7%94%A8%E8%AF%B4%E6%98%8E%28IOS%29.docx">下载</a> <br/>
</div>

## Demo功能说明

<div style="margin-left:20px;">
    1. Demo提供了FunSDK部分功能的代码示例，并不包括所有功能接口，如果需要完成Demo中没有的功能，还请联系业务人员或客服；<br/>
    2. Demo代码只作为参考，使用者可以引用或者拷贝部分代码，并不建议作为正式版App来发布使用；<br/>
</div>

## Demo功能列表

<style>
	#table2{
		width:1000px;
		border-collapse:collapse;
	}
	#table2 tr{
		text-align:left;
	}
</style>
<div>
<label style="color:#039">Demo for Android功能列表</label>
<table id="table2">
<tr style="text-align:center"><td>模块</td><td>功能</td><td>说明</td></tr>
<tr><td rowspan="5">1 用户相关</td><td>1.1 用户注册(手机注册，邮箱注册)</td><td> </td></tr>
<tr><td>1.2 用户登录</td><td> </td></tr>
<tr><td>1.3 修改密码</td><td></td></tr>
<tr><td>1.4 忘记密码(通过手机，通过邮箱)</td><td></td></tr>
<tr><td>1.5 用户信息</td><td></td></tr>
<tr><td rowspan="10">2 设备相关</td><td>2.1链接设备（通过序列号连接）</td><td>  </td></tr>
<tr><td>2.2 连接设备（附近AP连接）</td><td>  </td></tr>
<tr><td>2.3 连接设备（局域网内）</td><td>  </td></tr>
<tr><td>2.4 用户添加设备</td><td>  </td></tr>
<tr><td>2.5 用户移除设备</td><td>  </td></tr>
<tr><td>2.6 设备参数</td><td>  </td></tr>
<tr><td>2.7 连接设备（用户远程）</td><td>  </td></tr>
<tr><td>2.8 浏览设备文件<br/>
（参考：2.7 连接设备（用户远程）-> 控制->图片/视频浏览）</td><td>  </td></tr>
<tr><td>2.9 设备报警<br/>
（参考：2.7 连接设备（用户远程） -> 报警）</td><td> 仅添加到注册用户的设备可用</td></tr>
<tr><td>2.10 快速配置WiFi</td><td>  </td></tr>
<tr><td rowspan="8">3 媒体功能</td><td>3.1 播放实时视频<br/>
（参考：监控类设备控制->播放）</td><td>  </td></tr></tr>
<tr><td>3.2 播放远程录像</td><td>  </td></tr>
<tr><td>3.3 播放远程录像-按时间</td><td>  </td></tr>
<tr><td>3.4 播放本地录像</td><td>  </td></tr>
<tr><td>3.5 云播放录像</td><td>  </td></tr>
<tr><td>3.6 播放控制（暂停/继续等）</td><td>  </td></tr>
<tr><td>3.7 录像控制<br/>
（参考：监控类设备控制->播放->录制）</td><td>  </td></tr>
<tr><td>3.8 视频抓图<br/>
（参考：监控类设备控制->播放->截图）</td><td>  </td></tr>
<tr><td rowspan="2">4. 其他功能</td><td>串口命令：打开/关闭/读/写串口<br/>
（参考：设备列表->设备->串口）
</td><td>  </td></tr>
<tr><td>     </td><td>  <br/><br/></td><tr>
</table>
</div>
