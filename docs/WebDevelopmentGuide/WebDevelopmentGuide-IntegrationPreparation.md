## 获得uuid/AppKey/AppSecret/moveCard

在"控制台"中找到您的应用，可以查看uuid、AppKey、AppSecret和moveCard四个值。
如果您还未创建应用，请查看"开发者必读"->"<a href="http://open.xmeye.net/resource.do?cid=ec799b013aec4a589357b644630fd4d2&rid=69896d3a5962401dbd5db30988e67a56#undefined">新手指南</a>"。

## 下载SDK

SDK及Demo在 资源中心->下载中心->web(java)Client下载中，请选择对应的平台进行下载。

## 导入SDK

将client.jar放在lib目录下

<img src="http://open.xmeye.net/upload/image/20160713/1468397181338020287.png">

## 配置spring和app证书

### 配置spring-config.xml(或applicationContext.xml)

在spring-config.xml(或applicationContext.xml)配置文件中初始化Cfg类

<img src="http://open.xmeye.net/upload/image/20160726/1469514149844006427.bmp">


### 填写App证书

当spring容器加载完成后立即执行ClientFactory.init(cfg),可编写一个实现ApplicationListener的listener类来实现spring容器初始化后最初执行的方法,并注入bean(cfg).

	public class ClientFactoryInit implements ApplicationListener<ContextRefreshedEvent> {
	    private Cfg cfg;
	    public void setCfg(Cfg cfg) {
	        this.cfg = cfg;
	    }
	    @Override
	    public void onApplicationEvent(ContextRefreshedEvent contextRefreshedEvent) {
	        if(contextRefreshedEvent.getApplicationContext().getParent() == null) {
	            ClientFactory.init(cfg);
	        }
	    }
	}

spring-config.xml
	
	    <bean id="init"class="net.xmcloud.action.ClientFactoryInit">    
	        <property name="cfg" ref="cfg"></property>
	    </bean>

 
