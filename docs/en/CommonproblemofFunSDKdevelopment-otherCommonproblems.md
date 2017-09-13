
<label style="color:#000044;"><b>1.Fast registration (does not use the phone number or e-mail, and directly register).
</b></label><br/>
SDK supports that use mobile phone number and mailbox to verify registration and no verification registered<br/>
（1）Cell-phone number verify registration<br/>
（2）Mailbox verify registration<br/>
（3）No verification registered<br/>

<label style="color:#000044;"><b>2.Does the latest SDK support IPv6？</b></label><br/>
Support<br/>

<label style="color:#000044;"><b>3.What are the requirements for registering a username?
</b></label><br/>
Username requires 4~15 characters, include Chinese, letters, numbers and "_"<br/>

<label style="color:#000044;"><b>4.What is the format of alarm information?</b></label><br/>
Chinese：You have an alarm notice serialnumber: xxxxxx Time: 2016-06-24 10:00:00　　　　<br/>　　
English: You have an alarm notice serialnumber: xxxxxx Time: 2016-06-24 10:00:00<br/>

<label style="color:#000044;"><b>5.Libeznat: EventIOThread has been always reported such an error, what is the problem?
</b></label><br/>
This is print.

<label style="color:#000044;"><b>6.After switching resolution, it needs to restart the device. Does it need to call the funsdk interface or to re-charge the device?</b></label><br/>
If the IE modify the resolution, and need to manually start the device, then it will need to operate; otherwise it needs to call the interface to restart the device.<br/>

<label style="color:#000044;"><b>7.Alarm pictures sometimes cannot show?
</b></label><br/>
First reason: the device is not normally uploaded to the server so that download failed.<br/>
Second reason: FunSDK may download failed.<br/>

<label style="color:#000044;"><b>8.What is the relationship between the device and the user?</b></label><br/>
A device can be bound to a number of users; a user can bind multiple devices. Theoretically the account is bound without limit. Recommend 100 devices within the best.<br/>

<label style="color:#000044;"><b>9.How to judge that the coding and decoding of video use the hard decoding or soft decoding?
</b></label><br/>
When opening the video, the type of View that needs to be uploaded. If it is GLSurfaceView20, it is soft decoding, or it is hard decoding.<br/>

<label style="color:#000044;"><b>10.What is the way to download the alarm picture?</b></label><br/>
The first one: you can directly open it in the web page via the URL images in the returned result of querying history, or use the third party library or control download to display.<br/>
The second one: use FunSDK interface to achieve picture download.<br/>

<label style="color:#000044;"><b>11.Video type?</b></label><br/>
Configuration, closure and always. Configuration has ordinary, alarm and motion detection. The three is represented by mask.

<label style="color:#000044;"><b>12.Resolution switching?</b></label><br/>
The value of Resolution：<br/>
720p -> 720P<br/>
960p ->1_3M<br/>

<label style="color:#000044;"><b>13.Account distinction?</b></label><br/>
The registered user, who uses the app developed by open platform FunSDK, can only login the developed app and unable to login our company's other app. Account system has been separated.<br/>

<label style="color:#000044;"><b>14.Cloud alarm</b></label><br/>
On APP, server alarm has frequency limit. Too fast will be filtered out in order to avoid excessive pressure on the server.<br/>

<label style="color:#000044;"><b>15.App cannot receive the alarm push?</b></label><br/>
（1）App may not subscribed, solution: subscribe this device alarm on the App, calling interface is LinkDev.<br/>
（2）May be the device DNS is not set, solution: the domestic DNS is set to 114.114.114.114<br/>
（3）The reserved certificate on the server may not be correct (IOS), the solution is to provide a certificate.<br/>

<label style="color:#000044;"><b>16.What does it mean when querying alarm history will return -222400?</b></label><br/>
This indicates that no query to the alarm history<br/>

<label style="color:#000044;"><b>17.HD forwarding mode is not supported?</b></label><br/>
Need to use the DSS device to support HD (forwarding mode), the firmware of device needs to be upgraded to DSS.<br/>

<label style="color:#000044;"><b>18.This interface which gets the device status, accept multiple devices to get online status, how do I distinguish between online and offline in callback?</b></label><br/>
Get device status can request multiple devices status at one time, device uuid uses ";" to be separated. Only return a device status at a time, and divide into many times to return. In callback, Param1 is greater than 0 is online. Equal to 0 is offline.
<br/>






