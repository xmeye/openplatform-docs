
<div style="font-size:20px;"><b>The required parameters description called by library method:</b></div> 
<br/>
<style>
	table{
		width:100%;
		font-family:"楷体";
		border-collapse:collapse;
	}
	table tr:hover{
	    background-color:#f5f5f5;
	}
</style>
<table>
<tr><td>Parameters</td><td>Parameters description</td></tr>
<tr><td>username</td><td>Username</td></tr>
<tr><td>password</td><td>Password</td></tr>
<tr><td>confirmPass</td><td>Confirm password</td></tr>
<tr><td>userId</td><td>User unique identifier</td></tr>
<tr><td>mail</td><td>Mailbox</td></tr>
<tr><td>type</td><td>re(register), fp(find back password)</td></tr>
<tr><td>verCode</td><td>Verification code received by mobile phone or mailbox</td></tr>
<tr><td>phone</td><td>Cell-Phone number</td></tr>
<tr><td>oldPwd</td><td>Old password</td></tr>
<tr><td>newPwd</td><td>New password</td></tr>
<tr><td>uuid</td><td>Developer unique identifier</td></tr>
<tr><td>userId</td><td>User unique identifier</td></tr>
<tr><td>devicename</td><td>Device name</td></tr>
<tr><td>devicePwd</td><td>Device password</td></tr>
<tr><td>deviceNickname</td><td>Device nickname</td></tr>
<tr><td>oldDevicePwd</td><td>Old device password</td></tr>
<tr><td>newDevicePwd</td><td>New device password</td></tr>
<tr><td>deviceConfirmPsaaword</td><td>Device confirm password</td></tr>
</table>


<div name="yonghu" id="yonghu" style="font-size:20px;"><b>2.1User system</b></div>

<div name="yonghu1" id="yonghu1" style="font-size:20px;margin-left:25px;">
2.1.1Mailbox register
</div>
<div style="margin-left:40px;">
(1)Use a unique checking mailbox, username:
</div>   
		User client = User.newInstance();
	    CheckMailVo vo = client.checkMailVo(mail);
	    CheckUsernameVo vo = client.checkUsernameVo(username);
	   Or
	    client.checkMail(mail);
	    client.checkUsername(username);
	   Example of thejsonresponse:
	    {
	        "code": 4023,
	        "msg": "mail exist",
	        "data": ""
	    }

<div style="margin-left:40px;">
(2)Send mailbox verification code:
</div>
		SendCode client = SendCode.newInstance();
	    //SendCodeVo vo = client.mailVo(mail, "re");
	    SendCodeVo vo = client.mailVo(mail,Type.REGISTER);
	    Or
	    client.mail(mail, type);
	    Example of thejson response:
	    1:Register to send e-mail or send failed
	    {
	        "code": 4023,
	        "msg": "mail exist",
	        "data": ""
	    }
	   2:Finding back password is sent successfully will return to user ID and user
	    {
	        "code": 2000,
	        "msg": "",
	        "data": {
	            "userId": "12345xx",
	            "data": "mrava"
	        }
	    }
<div style="margin-left:40px;">
 (3)Get verification code xxxx from the registered mailbox, call regMail () or regMailVo () to register
</div>
		User client = User.newInstance();
	    UserRegVo vo = client.regMailVo(username, password, confirmPass, mail, verCode);
	    Or
	    client.regMail(username, password, confirmPass, mail, verCode);
	    Example of the json response:
	    {
	        "code": 4012,
	        "msg": "username exist",
	        "data": ""
	    }

<div name="yonghu2" id="yonghu2" style="font-size:20px;margin-left:25px;">
2.1.2Mobile phone register
</div>
<div style="margin-left:40px;">
 (1)Use a unique checking mobile phone, username:
</div>
		 User client = User.newInstance();
	     CheckPhoneVo vo = client.checkPhoneVo(mail);
	     CheckUsernameVo vo = client.checkUsernameVo(username);
<div style="margin-left:40px;">
(2)Send mobile phone verification code:
</div>
		SendCode client = SendCode.newInstance();    
    	//SendCodeVo vo = client.phone(phone,"re");//在1.2版本之前的写法
    	SendCodeVo vo = client.phone(phone,Type.REGISTER);//在1.2版本之后的写法
<div style="margin-left:40px;">
(3)Get verification code, call regPhone() or regPhoneVo() to register
</div>
		User client = User.newInstance();
    	UserRegVo vo = client.regPhoneVo(username,password,confirmPass,phone,verCode);
<div name="yonghu3" id="yonghu3" style="font-size:20px;margin-left:25px;"> 
2.1.3Find back password verification code to verify
</div>
<div style="margin-left:40px;">
 (1).Send verification code by mailbox or mobile phone
</div>
		1.Send mailbox verification code:
	    SendCode client = SendCode.newInstance();
	    //SendCodeVo = client.mailVo(mail,"fp");
	    SendCodeVo = client.mailVo(mail,Type.FIND_PASSWORD);
	    2.Send mobile phone verification code:
	    SendCode client = SendCode.newInstance();
	    SendCodeVo = client.phoneVo(phone,Type.FIND_PASSWORD);
<div style="margin-left:40px;">
  (2)Support cellphone number and mailbox. If you input cellphone number and mailbox at the same time, only verify cell-phone number.
</div>
		User client = User.newInstance();
	    EditorPassVo vo = client.cpcVo(phone, mail, verCode);
	    Example of the json response:
	    {
	        "code": 4010,
	        "msg": "code error",
	        "data": ""
	    }
<div name="yonghu4" id="yonghu4" style="font-size:20px;margin-left:25px;"> 
2.1.4Find back password by mailbox
</div>
<div style="margin-left:40px;">
 (1)Send mailbox verification code:
</div>
		SendCode client = SendCode.newInstance();
	    SendCodeVo vo = client.mailVo(mail,Type.FIND_PASSWORD);
<div style="margin-left:40px;">
  (2)Get verification code xxxx from mailbox, call byMVo () or byM() to find back
</div>
		FindPassword client = FindPassword.newInstance();
	    FindPasswordVo vo = client.byMVo(userId,mail,verCode,password,confirmPass);
<div name="yonghu5" id="yonghu5" style="font-size:20px;margin-left:25px;"> 
2.1.5Find back password by mobile phone
</div>
<div style="margin-left:40px;">
 (1)Send mobile phone verification code:
</div>
		SendCode client = SendCode.newInstance();
	    SendCodeVo vo = client.phoneVo("phone",Type.FIND_PASSWORD);
<div style="margin-left:40px;">
  (2)Get verification code xxxx from mobile phone, call byPVo () or byP() to find back
</div>
	    FindPassword client = User.newInstance();
	    FindPasswordVo vo = client.byPVo(userId,phone,verCode,newPass,confirmPass);
<div name="yonghu6" id="yonghu6" style="font-size:20px;margin-left:25px;"> 
 2.1.6Modify password
</div>
<div style="margin-left:40px;">
 (1)Input username and old password, then input new password and confirm password, call cp () or coVo ()
</div>
		User client = User.newInstance();
	    EditorPassVo vo = client.cpVo(username,oldPwd,newPwd,confirmPass);
<div name="yonghu7" id="yonghu7" style="font-size:20px;margin-left:25px;"> 
 2.1.7Obtain user information via user identifier
</div>
<div style="margin-left:40px;">
 (1)Input userld, call info () or infoVo() to obtain user information
</div>
	 	User client = User.newInstance();
	    UserInfoVo vo = client.infoVo(userId);
	    Example of the json response:
	    {
	        "code": 2000,
	        "msg": "success",
	        "data": {
	            "id": "demo",
	            "username": "mrava",
	            "mail": "demo@qq.com",
	            "phone": "demo",
	            "company": "demo"
	        }
	    }
<div name="yonghu8" id="yonghu8" style="font-size:20px;margin-left:25px;"> 
 2.1.8Obtain user information via username and password
</div>
<div style="margin-left:40px;">
 (1)Input username and password, call info2() or info2 Vo to obtain user information
</div>
		User client = User.newInstance();
	    UserInfoVo vo = client.info2Vo(username, password);
	   Example of the json response:
	    {
	        "code": 2000,
	        "msg": "success",
	        "data": {
	            "id": "demo",
	            "username": "mrava",
	            "mail": "demo@qq.com",
	            "phone": "demo",
	            "company": "demo"
	        }
	    }
<br/>
<div name="shebei" id="shebei" style="font-size:20px;"><b>2.2Device system</b></div> 

<div name="shebei1" id="shebei1" style="font-size:20px;margin-left:25px;"> 
 2.2.1User gets device list
</div>
<div style="margin-left:40px;">
 (1)Input user unique identifier, username and password, call list() or listVo()
</div>
		UserDevice userDevice = UserDevice.newInstance();
	    DeviceVo vo = userDevice.listVo(userId, username, password);
	   Responsive example:
	    {
	        "code": 2000,
	        "msg": "success",
	        "data": {
	            "userId": "demo",
	            "data": [{
	                    "id": "demo",
	                "uuid": "demo",
	                "ip": "demo",
	              "port": "demo",
	              "nickname": "demo",
	                "username": "admin",
	                "password": "demo",
	                "type": "demo"}
	            ]
	        }
	    }
<div name="shebei2" id="shebei2" style="font-size:20px;margin-left:25px;"> 
2.2.2User gets device list with authorization codes
</div>
<div style="margin-left:40px;">
  (1)Input username and password, call listCode() or list CodeVo()
</div>
		UserDevice userDevice = UserDevice.newInstance();
	    DeviceListCodeVo vo = userDevice.listCodeVo(userId, username, password);
	    Responsive example:
	    {
	        "code": 2000,
	        "msg": "success",
	        "data": {
	            "userId": "demo",
	            "data": [{
	                "id": "demo",
	                "uuid": "demo",
	                "ip": "demo",
	                "port": "demo",
	                "nickname": "demo",
	                "username": "admin",
	                "password": "demo",
	                "type": "demo",
	                "css": "demo",
	                "dss": "demo",
	                "p2P": "demo",
	                "pms": "demo",
	                "tps": "demo"}]
	        }
	    }
<div name="shebei3" id="shebei3" style="font-size:20px;margin-left:25px;"> 
2.2.3Add device
</div>
<div style="margin-left:40px;">
 (1) Add user device
</div>
		UserDevice userDevice = UserDevice.newInstance();
	    DeviceAddVo vo = userDevice.addVo(uuid, devicename, devicePwd, deviceNickname, userId, username, password);
	    Responsive example:
	    {
	        "code": 2000,
	        "msg": null,
	        "data": {
	            "id": "74a6597bcf6d467a8ede4f0852d7bcf1",
	            "uuid": "123456789",
	            "ip": "",
	            "port": "",
	            "nickname": "my device",
	            "username": "admin",
	            "password": "pass",
	            "type": ""
	        }
	    }
<div name="shebei4" id="shebei4" style="font-size:20px;margin-left:25px;"> 
2.2.4Delete user device
</div>
		UserDevice userDevice = UserDevice.newInstance();
	    CommonVo vo = userDevice.rmVo(uuid, userId, username, password);
<div name="shebei5" id="shebei5" style="font-size:20px;margin-left:25px;"> 
2.2.5Modify device information
</div>
		UserDevice userDevice = UserDevice.newInstance();
	    CommonVo vo = userDevice.editVo(uuid, devicename, deviceNickname, userId, username, password);
<div name="shebei6" id="shebei6" style="font-size:20px;margin-left:25px;"> 
2.2.6Change device login password
</div>
		UserDevice userDevice = UserDevice.newInstance();
	    CommonVo vo = userDevice.editPassVo(uuid, oldDevicePwd, newDevicePwd, deviceConfirmPassword, userId,
<div name="shebei7" id="shebei7" style="font-size:20px;margin-left:25px;"> 
2.2.7Device status query
</div>
<div style="margin-left:15px;">
 Use to check the current status of the device. If the device status is asynchronous query, generally recommend you to query 3 to 4 times, separated by “;”.  
</div>
		UserDevice userDevice = UserDevice.newInstance();
	    DeviceQueryStatusVo vo = userDevice.queryStatusVo(uuids);
	   Return to example:
	    {
	       "code":2000,
	       "msg":"success",
	       "data":[
	          {"uuid":"0123456789012345","status":"0"},
	          {"uuid":"0123456789012346","status":"1"}]
	     }

<br/>
<div name="shouquan" id="shouquan" style="font-size:20px;"><b>2.3Authorization system</b></div> 
<br/>
<table style="width:100%;border-collapse:collapse;">
<tr>
<td>type</td><td>Types that need to apply for:  css, dss, p2p, pms, tps
</td>
</tr>
<tr>
<td>uuid</td><td>Device confirm password</td>
</tr>
</table>

<div name="shouquan1" id="shouquan1" style="font-size:20px;margin-left:25px;"> 
2.3.1Device authorization
</div>
<div style="margin-left:40px;">
 (1) Due to business needs to apply for the opening of cloud storage, cloud alarm, etc.
</div>
		AuthCode code = AuthCode.newInstance();
	    //AuthCodeVo vo = code.appVo(uuid, type, userId, username, password);
	    AuthCodeVo vo = code.appVo(uuid, Type.CSS, userId, username, password);
	    Responsive example：
	    {
	        "code": 2000,
	        "msg": "success",
	        "data": [{
	            "id": 1,
	            "css": "04a99572c39c099046",
	            "dss": "00699572c39c099059",
	            "uuid": "09224d6379573b35a3db4490a8d98c53",
	            "p2P": "03499572c39c199021",
	            "pms": "01299572c39ca9901c",
	            "tps": "05799572c39ca99035"}
	        ]
	    }
<div name="shouquan2" id="shouquan2" style="font-size:20px;margin-left:25px;"> 
2.3.2Device authorization code query
</div>
<div style="margin-left:40px;">
 (1) All the authorization code will return
</div>
		AuthCode code = AuthCode.newInstance();
	    AuthCodeVo vo = code.queryVo(uuids, userId, username, password);
<div name="shouquan3" id="shouquan3" style="font-size:20px;margin-left:25px;"> 
 2.3.3Device authorization code synchronization
</div>
<div style="margin-left:40px;">
 (1) When you find a device authorization code but not successful, you can use this interface to synchronize the authorization code.
</div>
		AuthCode code = AuthCode.newInstance();
	    AuthCodeVo vo = code.synVo(uuids, userId, username, password);
	   Responsive example:
	    {
	        "code": 2000,
	        "msg": "success",
	        "data": [
	            {
	                "id": 1,
	                "css": "",
	                "dss": "",
	                "uuid": "09224d6379573b35a3db4490a8d98c53",
	                "p2P": "",
	                "pms": "",
	                "tps": ""
	            },
	            {
	                "id": 2,
	                "css": "0119956f37de89900a",
	                "dss": "",
	                "uuid": "123456",
	                "p2P": "",
	                    "pms": "",
	                "tps": ""
	            }
	        ]
	    }
<div name="shouquan4" id="shouquan4" style="font-size:20px;margin-left:25px;"> 
2.3.4The device authorization code is synchronized by type
</div>
<div style="margin-left:40px;">
 (1) When a device authorization code is found but not successful, this interface is called to synchronize the authorization code, and different authorization codes are synchronized according to different types
</div>
		AuthCode code = AuthCode.newInstance();
	    CommonVo vo = client.acsyntypeVo(uuid, Type.DSS, userId, uname, upass);
	    Responsive example:
	    {"code":2000,"msg":"dss syn success","data":"0149957b1262899001"}