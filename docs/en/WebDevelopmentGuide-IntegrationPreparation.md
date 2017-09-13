
<div name="zhunbei" id="zhunbei" style="font-size:25px;"><b>Integration preparation</b></div><br/> 

<div name="huode" id="huode" style="font-size:20px;"><b>1.1Get uuid/AppKey/AppSecret/moveCard </b></div>  
<p>Find your application in “Console”, and view uuid, AppKey, AppSecret and moveCard these four values. If you haven't created an application, please see “Developers Must Read”- > <a href="http://open.xmeye.net/resource.docid=ec799b013aec4a589357b644630fd4d2&rid=69896d3a5962401dbd5db30988e67a56#undefined">“Newbie guide”.</a>"。</p>

<div name="xiazai" id="xiazai" style="font-size:20px;"><b>1.2Download SDK</b></div> 

<p>SDK and Demo are in “Resource Center - > Download Center >web (java) Client, please select the corresponding platform to download.</p>

<div name="daoru" id="daoru" style="font-size:20px;"><b>1.3Import SDK</b></div> 

<p>Put client.jar under the lib directory.</p>
<img src="http://open.xmeye.net/upload/image/20160713/1468397181338020287.png">

<div name="peizhi" id="peizhi" style="font-size:20px;"><b>1.4Configure spring and app certificates</b></div>
<div name="peizhi1" id="peizhi1" style="font-size:15px;margin-left:20px;">1.4.1Configure spring-config.xml (or applicationContext.xml)Initialize Cfg in the configuration files of spring-config.xml (or applicationContext.xml)
</div>
<label style="margin-left:120px;">
<img src="http://open.xmeye.net/upload/image/20160726/1469514149844006427.bmp">
</label>

<div name="peizhi2" id="peizhi2" style="font-size:15px;margin-left:20px;">1.4.2Fill in APP certificates</div>

<p>When the loading of spring container is completed, execute ClientFactory.init (cfg) immediately. You can write a listener to achieve the ApplicationListener, to achieve the method of original execution after the spring container is initialized and inject bean (cfg).</p>

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
<p>spring-config.xml</p>
	
	    <bean id="init"class="net.xmcloud.action.ClientFactoryInit">    
	        <property name="cfg" ref="cfg"></property>
	    </bean>

 
