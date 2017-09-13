## 库方法调用所需参数说明

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
<tr><td>参数</td><td>参数说明</td></tr>
<tr><td>username</td><td>用户名</td></tr>
<tr><td>password</td><td>密码</td></tr>
<tr><td>confirmPass</td><td>确认密码</td></tr>
<tr><td>userId</td><td>用户唯一标识符</td></tr>
<tr><td>mail</td><td>邮箱</td></tr>
<tr><td>type</td><td>re(注册)、fp(找回密码)</td></tr>
<tr><td>verCode</td><td>手机或邮箱收到的验证码</td></tr>
<tr><td>phone</td><td>手机号</td></tr>
<tr><td>oldPwd</td><td>旧密码</td></tr>
<tr><td>newPwd</td><td>新密码</td></tr>
<tr><td>uuid</td><td>开发者唯一标识符</td></tr>
<tr><td>userId</td><td>用户唯一标识符</td></tr>
<tr><td>devicename</td><td>设备名</td></tr>
<tr><td>devicePwd</td><td>设备密码</td></tr>
<tr><td>deviceNickname</td><td>设备别名</td></tr>
<tr><td>oldDevicePwd</td><td>旧设备密码</td></tr>
<tr><td>newDevicePwd</td><td>新设备密码</td></tr>
<tr><td>deviceConfirmPsaaword</td><td>设备确认密码</td></tr>
</table>
<br/>

## 用户系统

### 邮箱注册

#### 1、使用唯一性校验邮箱，用户名

		User client = User.newInstance();
	    CheckMailVo vo = client.checkMailVo(mail);
	    CheckUsernameVo vo = client.checkUsernameVo(username);
	    或者
	    client.checkMail(mail);
	    client.checkUsername(username);
	    响应json示例:
	    {
	        "code": 4023,
	        "msg": "mail exist",
	        "data": ""
	    }


#### 2、发送邮箱验证码

		SendCode client = SendCode.newInstance();
	    //SendCodeVo vo = client.mailVo(mail, "re");//在1.2版本之前的写法
	    SendCodeVo vo = client.mailVo(mail,Type.REGISTER);//在1.2版本之后的写法
	    或者
	    client.mail(mail, type);
	    响应json示例:
	    1:注册发送邮件或发送失败
	    {
	        "code": 4023,
	        "msg": "mail exist",
	        "data": ""
	    }
	    2:找回密码发送成功会返回用户id和用户
	    {
	        "code": 2000,
	        "msg": "",
	        "data": {
	            "userId": "12345xx",
	            "data": "mrava"
	        }
	    }

#### 3、从注册邮箱中获取验证码xxxx,调用regMail()或regMailVo()注册

		User client = User.newInstance();
	    UserRegVo vo = client.regMailVo(
	    username, password, confirmPass, mail, verCode
	    );
	    或者
	    client.regMail(username, password, confirmPass, mail, verCode);
	    响应json示例:
	    {
	        "code": 4012,
	        "msg": "username exist",
	        "data": ""
	    }

### 手机注册

#### 1、使用唯一性校验手机,用户名:

		 User client = User.newInstance();
	     CheckPhoneVo vo = client.checkPhoneVo(mail);
	     CheckUsernameVo vo = client.checkUsernameVo(username);

#### 2、发送手机验证码:

		SendCode client = SendCode.newInstance();
    	//SendCodeVo vo = client.phone(phone,"re");//在1.2版本之前的写法
    	SendCodeVo vo = client.phone(phone,Type.REGISTER);//在1.2版本之后的写法

#### 3、获取验证码code,调用regPhone()或regPhoneVo()注册

		User client = User.newInstance();
    	UserRegVo vo = client.regPhoneVo(username,password,confirmPass,phone,verCode);

### 找回密码验证码验证

#### 1、通过邮件或手机发送验证码

		1.发送邮箱验证码:
	    SendCode client = SendCode.newInstance();
	    //SendCodeVo = client.mailVo(mail,"fp");//在1.2版本之前的写法
	    SendCodeVo = client.mailVo(mail,Type.FIND_PASSWORD);//在1.2版本之后的写法
	    2.发送手机验证码:
	    SendCode client = SendCode.newInstance();
	    SendCodeVo = client.phoneVo(phone,Type.FIND_PASSWORD);

#### 2、支持手机号和邮箱.同时输入手机号和邮箱时只验证手机号

		User client = User.newInstance();
	    EditorPassVo vo = client.cpcVo(phone, mail, verCode);
	    响应json示例:
	    {
	        "code": 4010,
	        "msg": "code error",
	        "data": ""
	    }

### 邮件找回密码


#### 1、发送邮箱验证码

		SendCode client = SendCode.newInstance();
	    //SendCodeVo vo = client.mailVo(mail,"fp");//在1.2版本之前的写法
	    SendCodeVo vo = client.mailVo(mail,Type.FIND_PASSWORD);//在1.2版本后用枚举常量替代

#### 2、从邮箱中获取验证码xxxx,调用byMVo ()或byM()找回

		FindPassword client = FindPassword.newInstance();
	    FindPasswordVo vo = client.byMVo(userId,mail,verCode,password,confirmPass);

### 手机找回密码


#### 1、发送手机验证码

		SendCode client = SendCode.newInstance();
	    //SendCodeVo vo = client.phoneVo("phone","fp");//在1.2版本之前的写法
	    SendCodeVo vo = client.phoneVo("phone",Type.FIND_PASSWORD);//在1.2版本后用枚举常量替代

#### 2、从手机中获取验证码xxxx,调用byPVo ()或byP ()找回

	    FindPassword client = User.newInstance();
	    FindPasswordVo vo = client.byPVo(userId,phone,verCode,newPass,confirmPass);

### 修改密码

#### 1、输入用户名和旧密码,再输入新密码和确认密码,调用cp()或cpVo()

		User client = User.newInstance();
	    EditorPassVo vo = client.cpVo(username,oldPwd,newPwd,confirmPass);

### 通过用户标识符获取用户信息

#### 1、输入userId,调用info()或infoVo()获取用户信息

	 	User client = User.newInstance();
	    UserInfoVo vo = client.infoVo(userId);
	    响应json示例:
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

### 通过用户名和密码获取用户信息

#### 1、输入username和password,调用info2()或info2Vo获取用户信息

		User client = User.newInstance();
	    UserInfoVo vo = client.info2Vo(username, password);
	    响应json示例:
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

## 设备系统

### 用户获取设备列表

#### 1、输入用户唯一标识符,用户名和密码,调用list()或listVo()

		UserDevice userDevice = UserDevice.newInstance();
	    DeviceVo vo = userDevice.listVo(userId, username, password);
	    响应示例:
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

### 用户获取设备带授权码列表

#### 1、输入用户名和密码,调用listCode()或listCodeVo()

		UserDevice userDevice = UserDevice.newInstance();
	    DeviceListCodeVo vo = userDevice.listCodeVo(userId, username, password);
	    响应示例:
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

### 增加设备

#### 1、用户设备添加

		UserDevice userDevice = UserDevice.newInstance();
	    DeviceAddVo vo = userDevice.addVo(
	    uuid, devicename, devicePwd, deviceNickname, userId, username, password
	    );
	    响应示例:
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

### 用户设备删除

		UserDevice userDevice = UserDevice.newInstance();
	    CommonVo vo = userDevice.rmVo(uuid, userId, username, password);

### 修改设备信息

		UserDevice userDevice = UserDevice.newInstance();
	    CommonVo vo = userDevice.editVo(
	    uuid, devicename, deviceNickname, userId, username, password
	    );

### 更改设备登录密码

		UserDevice userDevice = UserDevice.newInstance();
	    CommonVo vo = userDevice.editPassVo(
	    uuid, oldDevicePwd, newDevicePwd, deviceConfirmPassword, userId, username, password
	    );

### 设备状态查询

 用于查询设备当前状态,设备状态为异步查询，一般建议查询3-4次。需要查询的设备序列号，以“；”分隔

		UserDevice userDevice = UserDevice.newInstance();
	    DeviceQueryStatusVo vo = userDevice.queryStatusVo(uuids);
	    返回示例：
	    {
	       "code":2000,
	       "msg":"success",
	       "data":[
	          {"uuid":"0123456789012345","status":"0"},
	          {"uuid":"0123456789012346","status":"1"}]
	     }

## 授权系统

<table style="width:100%;border-collapse:collapse;">
<tr>
<td>type</td><td>需要申请的类型：TYPE.CSS，TYPE.DSS，TYPE.P2P，Type.PMS，TYPE.TPS
</td>
</tr>
<tr>
<td>uuid</td><td>设备确认密码</td>
</tr>
</table>
在1.2版本之后type改为了枚举，更不易出错。

### 设备授权

#### 1、业务需求云存储，云报警...申请开通

		AuthCode code = AuthCode.newInstance();
	    //在1.2版本之前type为"css", "dss","pms","tps","p2p"
	    //AuthCodeVo vo = code.appVo(uuid, type, userId, username, password);
	    //在1.2版本之前type为枚举类型，添加了新的授权类型Type.RPS
	    AuthCodeVo vo = code.appVo(uuid, Type.CSS, userId, username, password);
	    响应示例:
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

### 设备授权码查询

#### 1、所有授权码码都会返回

		AuthCode code = AuthCode.newInstance();
	    AuthCodeVo vo = code.queryVo(uuids, userId, username, password);

### 设备授权码同步


#### 1、当发现有设备授权码但不成功时调用此接口同步授权码

		AuthCode code = AuthCode.newInstance();
	    AuthCodeVo vo = code.synVo(uuids, userId, username, password);
	    响应示例:
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

### 设备授权码按类型同步

#### 1、当发现有设备授权码但不成功时调用此接口同步授权码，根据不同类型，同步不同授权码

		AuthCode code = AuthCode.newInstance();
	    CommonVo vo = client.acsyntypeVo(uuid, Type.DSS, userId, uname, upass);
	    响应示例:
	    {"code":2000,"msg":"dss syn success","data":"0149957b1262899001"}