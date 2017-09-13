<p style="color:red">(Note: this section is for API developer reference, and FunSDK mobile client developers can skip this section.)</p>
<h2>Illustration：</h2>
  <div style="margin-left:30px;">
   The whole open api uses restful style and private protocol. State code extends to HTTP state code:<br/>

   2xxx：success correlation<br/>

   4xxx：failure information correlation<br/>

   5xxx：indicates that the server error<br/>


  </div>
## Protocol format: ##
<br/>
<div style="margin-left:30px;">
https://domain name/interface code/interface version number/ timestamp/ secret key.rs<br/>

a)Interface code: English letters combination   <br/>   

b)Interface version number: v1…   <br/>

c) Timestamp: view specific timestamp algorithm   <br/>

d)Secret key: view specific encrypted word check authority algorithm <br/>    

e)Header add parameters uuid, appKey   <br/>

f)Example:https://rs.xmeye.net/demo01/v1/0000014631346736/4jkhdsf796dsd74gdfe364ds.rs   <br/>

</div>

## Related algorithms ##
<br/>
### 1.Timestamp ###
---

The whole timestamp is composed of counter (counter) and Green time (timeMillis). Counter is the first six numbers, if less than 6, use 0 to fill. TimeMillis is to get the local millisecond time.



  javaexample code:

	public class TimeMillisUtil {    
	  private static long timMillis;//Timestamp   
	  private static long counter = 0l;//Counter  
	  /**     
	  * Get counter    
	  *       
	  * @return     
	  */   
	  private static synchronized String getCounter(){        
	  ++counter;        
	  if (counter < 10L)            
	    return "000000" + String.valueOf(counter);        
	  else if (counter < 100L)            
	    return "00000" + String.valueOf(counter);            
	  else if (counter < 1000L)            
	    return "0000" + String.valueOf(counter);        
	  else if (counter < 10000L)            
	    return "000" + String.valueOf(counter);        
	  else if (counter < 100000L)            
	    return "00" + String.valueOf(counter);        
	  else if (counter < 1000000L)            
	    return "0" + String.valueOf(counter);        
	  else if (counter < 10000000L)            
	    return String.valueOf(counter);        
	  else {            
	    counter = 1L;            
	    return "000000" + String.valueOf(counter);        
	  }    
	}    
	/**     
	 * Get combined timestamps    
	 *     
	 * @return     
	 */    
	  public static String getTimMillis() {        
	    timMillis = System.currentTimeMillis();                
	    return getCounter() + String.valueOf(timMillis);    
	  }
	}

2.Encrypted word check authority algorithm
---
<br>
uuid，appkey，appSecret，timeMillis，movedCard are the necessary parameters for the encryption algorithm, the steps are as follows:


a)Successively stitch uuid，appkey，appSecret，timeMillis，movedCard

b)Get the binary array of the string after stitching

c) Binary array with a simple shift algorithm to get new binary array

d)The original binary array and the new binary array merge into the combined binary array

e)Encrypted the combined binary array md5 to generate a secret key



 

  javaexample code: 

	/** 
	 * Get a signature character string 
	 * 
	 * @param uuid       Customer unique identifier
	 * @param appKey     Application key 
	 * @param appSecret  Application secret key
	 * @param timeMillis Timestamp
	 * @param movedCard  Moved card
	 * @return 
	 * @throws Exception 
	 */
	public static String getEncryptStr(String uuid, String appKey, String appSecret, String timeMillis, int movedCard) throws Exception {    
		String encryptStr = uuid + appKey + appSecret + timeMillis;    
		byte[] encryptByte = encryptStr.getBytes("iso-8859-1");    
		byte[] changeByte = change(encryptStr, movedCard);    
		byte[] mergeByte = mergeByte(encryptByte, changeByte);    
		return DigestUtils.md5Hex(mergeByte);
	}
	
	/** 
	 * Simple shift 
	 */
	private static byte[] change(String encryptStr, int moveCard) throws UnsupportedEncodingException {    
		byte[] encryptByte = encryptStr.getBytes("iso-8859-1");    
		int encryptLength = encryptByte.length;    
		byte temp;    
		for (int i = 0; i < encryptLength; i++) {        
			temp = ((i % moveCard) > ((encryptLength - i) % moveCard)) ? encryptByte[i] : encryptByte[encryptLength - (i + 1)];        
			encryptByte[i] = encryptByte[encryptLength - (i + 1)];        
			encryptByte[encryptLength - (i + 1)] = temp;    
		}    
		return encryptByte;
	}
	
	/** 
	 * Merge 
	 * 
	 * @param encryptByte 
	 * @param changeByte 
	 * @return 
	 */
	private static byte[] mergeByte(byte[] encryptByte, byte[] changeByte) {    
		int encryptLength = encryptByte.length;    
		int encryptLength2 = encryptLength * 2;    
		byte[] temp = new byte[encryptLength2];    
		for (int i = 0; i < encryptByte.length; i++) {        
			temp[i] = encryptByte[i];        
			temp[encryptLength2 - 1 - i] = changeByte[i];    
		}    
		return temp;
	}

  **Algorithm checksum：**

   uuid：test ，appkey：test，appSecret：password，timeMillis：00000011461748332239，movedCard：5   
   signature:285a38b2ebf8787e42f047e0b711297b  

---
#**HTTP状态码详解**#
<br/>
<style>
	table tr:hover{
	    background-color:#f5f5f5;
	}
</style>
<table style="margin-left:30px;">
<tr style="background-color:#696969;color:#fff;height:60px;text-align:center"><td style="width:80px;">状态码</td><td style="text-align:center">含义</td></tr>
<tr><td>100</td><td>The client should continue to send the request. This temporary response is used to notify the client that its part of the request has been received by theserver, and has not yet been rejected.       The client should continue to send   the   remaining part of the request, or if the request has been completed, pleae  ignore the response. The server must send a final response to the client after the request is completed.</td></tr>
<tr><td>101</td><td>The server has understood the client's request, and will notify the client via the Upgrade message header to complete the request with a different protocl.  After sending the final blank line of       this response, the server will  switch  to those protocols defined in the Upgrade message header. You should take similar measures only when switching to a new protocol is more beneficial.    For  example, switching to a new HTTP version is better than  the  old   version,  or switching to a real-time and synchronous protocol to transfer the resources that use such characteristic.
</td></tr>
<tr><td>102</td><td>Status code extended by WebDAV (RFC 2518), indicate that processing will be continued.</td></tr>
<tr><td>200</td><td>The request has been successful, the request of the desired response header or the data body will return this response.</td></tr>
<tr><td>201</td><td>Requests have been implemented, and a new resource has been created based on the needs of the request, the URI has returned with the Location header information. If the resources needed cannot be established in time, it should be returned to ‘202 Accepted’.
</td></tr>
<tr><td>202</td><td>The server has accepted the request, but has not yet been processed. As it may be rejected, the request may be or may not be executed. In the case of asynchronous operation, there is no more convenient method than sending this status code. The purpose of returning the response of status code 202 is to    allow  the server to accept the request of other processes (For example, an operation based on the batch processing that is performed only once a day), but don't  have to always keep the client connection to the server until the batch operation is complete. When accepting the request processing and  return to 202 status code response, it should contain some information in the returned entity, which indicating and processing the current state, and a  pointer of pointing processing  status monitor or state prediction, so that the user can estimate whether the operation has been completed.</td></tr>
<tr><td>203</td><td>Server has successfully processed the request, but the returned entity header meta-information is not an effective determined collection on the original server,  while a copy from the local or        third party. The current information may be the subset or superset of the original version. The metadata containing resources may cause that the original server knows the superset of meta-information. It is not necessary to use this status code, and only in response to such the response is not returned with 200 OK from this status code.</td></tr>
<tr><td>204</td><td>The server successfully processed the request, but did not need to return any entity content, and would like to return the updated meta-information. Responses  may be returned to the new or     updated meta-information via the form of an entity header. If there is such header information, it should be echoed with    the requested variable. If the client is the browser, the user browser      should retain the requested page which has been sent without any change in the  document view, even according to specifications, the new or updated meta-information should be applied to       the document in the user's browser activity view.  The 204 response is prohibited from containing any information, so it is always end with the first blank line after the message header.
</td></tr>
<tr><td>205</td><td>The server successfully processed the request, and did not return any content, but the difference with the 204 response is that the response to this status code requires requestor to reset the         document view. This response is mainly used to accept the user input, and immediately reset the form so that users can easily start another input. Same with the 204 response, this response is    also prohibited from containing any information, and it is end with the first blank line after the message header.</td></tr>
<tr><td>206</td><td>The server has successfully processed some GET requests. This kind of HTTP download tools such as FlashGet or thunder are using such response to achieve HTTP or decompose a large      document for more than one download section and simultaneously download. The request must include the Range header information to indicate the content range that client wants to obtain,     and may contain If-Range as a request condition. The response must contain the following header fields: use Content-Range to indicate the content range returned in this response; if Content-    Type is multi-segment download of multipart/byteranges, then each multipart section should contain the Content-Range domain to indicate the content range of this segment. If the response       contains Content-Length, then its value must match the true number of bytes in the returned content range. Date ETag and / or Content-Location, if the request is same, it should return to the      200 response. Expires, Cache-Control and / or Content-Location, if the value may be different with the value of the same variable that corresponding to other response values. If the request for  this response uses If-Range strong Cache Validation, so the response should not include other entities; if the request for this response uses the If-Range weak Cache Validation, so this              response is prohibited from containing other entities; this avoids the inconsistency between the cached entity content and the updated entity header information. Otherwise, the response should  contain  all the entity header domains that should be returned in the 200 response. If ETag header or Last-Modified header is not exactly matched, then the client cache should prohibit from       combining the returned content of the 206 response with the previous cached contents. Any cache that does not support Range and Content-Range header is prohibited to cache the returned response. </td></tr>
<tr><td>207</td><td>The status code extended by WebDAV (RFC 2518), represents that the later message body will be a XML message, and may be according to the difference of the previous number of sub requests, contain a series of independent response codes.</td></tr>
<tr><td>300</td><td>The requested resources have a series of available feedback information, each with its own specific address and browser driven negotiation information. Users or browsers can choose a preferred address for their own choice. Unless this is an HEAD request, the response should include an entity in a list of resource characteristics and addresses so that user or browser can select the most appropriate redirection address. The format of this entity is determined by the format defined by Content-Type. The browser can automatically make the most appropriate choice according to the format of the response and the browser’s own ability. Of course, the RFC 2616 specification does not require that how to carry out such an automatic choice. If the server itself has a preferred feedback choice, then in the Location it should be specified this feedback URI; the browser may regard Location value as automatic redirection address. In addition, this response is also cached unless otherwise specified.</td></tr>
<tr><td>301</td><td>The requested resource has moved to a new location permanently, and any future references to this resource should use one of the URI that is returned by this response. If possible, a client with link editing capability should automatically modify the request address to the address returned from the server. This response is also cached unless otherwise specified. New permanent URI should be returned in the responsive Location domain. Unless this is an HEAD request, the responsive entity should contain a hyperlink and a short description pointing to the new URI. If this is not a GET or HEAD request, the browser is prohibited to automatically redirect; unless get the confirmation of user, because the request conditions may change.  Note: for some browsers that use the HTTP/1.0 protocol, when they send a POST request and get a 301 response, the next redirection request will be turned into GET mode.</td></tr>
<tr><td>302</td><td>302 Requested resources now temporarily respond to requests from different URI. Since such a redirection is temporary, the client should continue to send later requests to the original address. This response is cached only if the Cache-Control or Expires is specified. New temporary URI should be returned in responsive Location domain. Unless this is an HEAD request, the responsive entity should contain a hyperlink and a short description pointing to the new URI. If this is not a GET or HEAD request, the browser is prohibited to automatically redirect; unless get the confirmation of user, because the request conditions may change. Note: Although RFC 1945 and RFC 2068 specification does not allow the client to change the request method in redirection, many existing browsers regard the 302 response as the 303 response and use GET mode to visit the specified URI in the Location, while ignoring the method originally requested. The status code 303 and 307 are added in to make it clear how the server expects the client to react.</td></tr>
<tr><td>303</td><td>The response to the current request can be found on the other URI, and the client should use the GET mode to visit the resource. The main purpose of this method is to allow the POST request output activated by script to be redirected to a new resource. This new URI is not a substitute for the original resource. At the same time, the 303 response is forbidden to be cached. Of course, the second request (redirection) may be cached. New temporary URI should be returned in responsive Location domain. Unless this is an HEAD request, the responsive entity should contain a hyperlink and a short description pointing to the new URI. Note: many HTTP/1.1 previous versions of browsers cannot correctly understand the 303 state. If you need to consider the interaction between the browsers, 302 status code should be competent, because the way for most browsers dealing with 303 response is precisely the way that above specifications require the client to handle a 303 response.
</td></tr>
<tr><td>304</td><td>If the client sends a GET request with condition and the request is allowed, but the contents of the document (since the last visit or according to the request condition) do not change, the server should return to this status code. The 304 response is prohibited from containing the message body, so it is always end with the first blank line after the message header. The response must contain the following header information: Date, unless the server does not have a clock. If the server without a clock also follows these rules, then the proxy server and the client can add the Date field into the received response header (as specified in RFC 2068), cache mechanism will work normally. ETag and / or Content-Location, if the request is same, it should return to the 200 response. Expires, Cache-Control and / or Vary, if the value may be different with the value of the same variable that corresponding to other response values. If the request for this response uses strong Cache Validation, so the response should not include other entities; otherwise (for example, a GET request with a condition uses a weak Cache Validation), this response is prohibited to contain other entities; this avoids the inconsistency between the cached entity content and the updated entity header information. If the 304 response indicates that the current entity does not have a cache, then the cache system must ignore this response and repeat send a request that does not contain any restrictions. If received the 304 response that is required to update a cache item, then the cache system must update the entire items to reflect all fields’ values that are updated in the response.</td></tr>
<tr><td>305</td><td>The requested resource must be visited through the specified proxy. Location domain will give the specified agent URI information, the recipient needs to repeat a separate request to visit the corresponding resources through this agent. Only the original server can set up the 305 response. Note: RFC 2068 does not have a clear 305 response in order to redirect a separate request, and can only be established by the original server. Ignoring these restrictions may lead to serious security consequences.</td></tr>
<tr><td>306</td><td>In the latest version of the specification, the 306 status code is no longer used.</td></tr>
<tr><td>307</td><td>Requested resources now temporarily requests from different URI response. Since such a redirection is temporary, the client should continue to send the later request to the original address. This response is cached only if the Cache-Control or Expires is specified. New temporary URI should be returned in responsive Location domain. Unless this is an HEAD request, the responsive entity should contain a hyperlink and a short description pointing to the new URI. Because some browsers cannot recognize the 307 response, it needs to add the necessary information so that users can understand and issue visiting request to the new URI. If this is not a GET or HEAD request, the browser is prohibited to automatically redirect; unless get the confirmation of user, because the request conditions may change.
</td></tr>
<tr><td>400</td><td>1. Semantic error, the current request cannot be understood by the server. The client should not repeat the request unless it is modified.<br/>
2. Request parameters error.</td></tr>
<tr><td>401</td><td>The request requires user authorization. The response must include a WWW-Authenticate information header which is applicable to be requested to resource, to query the user information. The client can repeat a request that contains an appropriate request of Authorization header information. If the current request already contains Authorization certificates, then the 401 response represents that server authentication has been rejected those certificates. If the 401 response contains the same authentication inquiry with the previous response and the browser has at least validated once, then the browser should display the entity information to the user which contained in the response, because this entity information might include relevant diagnostic information. See RFC 2617.
</td></tr>
<tr><td>402</td><td>The status code is reserved for future demand.</td></tr>
<tr><td>403</td><td>The server understands the request, but refuses to execute it. The difference with the 401 response is that authentication does not provide any help, and the request should not be repeated to submit. If this is not an HEAD request, and the server wants to be able to make it clear why the request cannot be executed, then the reason for the refusal should be described in the entity. Of course, the server can also return to the 404 response, if it does not want to allow  the client to get any information.</td></tr>
<tr><td>404</td><td>Request failed. The requested and desired resource is not found on the server. There is no information can tell the user whether the situation is temporary or permanent. If the server knows the situation, it should use the 410 status code to tell. Because of some internal configuration issues, the old resource has been permanently unavailable, and there is no any address can jump. This 404 status code is widely used in such a situation when the server does not want to reveal exactly why the request was rejected or there is no other suitable response is available.</td></tr>
<tr><td>405</td><td>The requested method specified in the request line cannot be used to request the corresponding resource. The response must return Allow header information to indicate a list of request methods that the current resource is able to accept. In view of the PUT, DELETE method will write on the server resources, so most of the web server does not support or in the default configuration does not allow the above request method, for such requests will return to the 405 error.</td></tr>
<tr><td>406</td><td>The content characteristics of the requested resource cannot satisfy the condition in the request header, and thus the response entity cannot be generated. Unless this is an HEAD request, the response should be returned to an entity that user or browser can select the most appropriate entity characteristics and the address list. The format of the entity is determined by the media type defined in the Content-Type header. The browser can make the best choice according to the format and its own ability. However, the specification does not define any criteria for making such an automatic selection.
</td></tr>
<tr><td>407</td><td>　Sthe 40imilar to 1 response, but the client must authenticate on the proxy server. The proxy server must return Proxy-Authenticate for identity inquiry. The client can return Proxy-Authorization header to verify. See RFC 2617.
</td></tr>
<tr><td>408</td><td>Request is timeout. The client does not complete a request in the time that the server is ready to submit the request at any time without making any changes.</td></tr>
<tr><td>409</td><td>The request cannot be completed because there is a conflict between the current state of the requested resource. This code is only allowed to be used in such a situation: users are considered to be able to resolve conflicts, and will resubmit new requests. The response should contain sufficient information to allow users to discover the source of the conflict. Conflicts usually occur in the processing of PUT requests. In the environment of using version check, the version information, which is included in a modified request to particular resources submitted by PUT, is in conflict with a previous (third party) request, and then the server should return a 409 error, inform the user that the request could not be completed. At this point, the responsive entity is likely to contain the difference comparison between the two conflicting versions so that the user can resubmit the new version after merging.</td></tr>
<tr><td>410</td><td>The requested resource is no longer available on the server, and there is no known forwarding address. Such a situation should be considered permanent. If possible, a client with link editing capability should remove all references pointing to this address after obtaining the user's permission. If the server does not know or cannot determine whether this condition is permanent, it should use the 404 status code. This response is cached unless there are additional instructions. The purpose of the 410 response is mainly to help the site administrator maintain the website, notify the user that the resource is no longer available, and the server owner wished that all the remote connection pointing to this resource is also deleted. Such events in the limited time and value-added services are very common. Similarly, the 410 response is also used to notify the client that in the current server site, the resource originally belongs to a person is no longer available. Of course, it is entirely up to the server owner whether mark all the permanently unavailable resources as ‘Gone 41’, and how long this tag needs to keep.</td></tr>
<tr><td>411</td><td>The server refuses to accept the request without defining the Content-Length header. After adding an effective Content-Length header which indicates the length of the request message body, the client can submit the request again.</td></tr>
<tr><td>412</td><td>When the server is verifying that giving a prerequisite in the request header field, it cannot able to satisfy one or more. This status code allows the client to set a prerequisite in the request meta-information (request header field data) when getting resource, in order to avoid that the request method is applied to other resources that beyond the desired content.</td></tr>
<tr><td>413</td><td>The server refuses to handle the current request because the size of the entity data submitted by this request exceeds the range that server is willing or able to handle. In this case, the server can close the connection in order to avoid the client to continue to send the request. If this condition is temporary, the server should return a Retry-After response header to inform the client how much time it can be tried again.</td></tr>
<tr><td>414</td><td>The request URI length exceeds the length that the server can explain, so the server refuses to provide the service to the request. This is relatively rare, usually including: it originally should use the POST method to submit the form, but it uses GET method, so that the query string (String Query) is too long. Redirect URI "black holes". In each redirection, it put the old URI as a part of the new URI, which causes that after several redirections, URI is super long. Client is trying to use the security vulnerabilities existing in some servers to attack server. This type of server uses fixed length buffer to read or operate the request URI. When the GET parameters exceed a certain value, it may generate a buffer overflow which causes that arbitrary code is executed [1]. The server without such vulnerability should return to 414 status code.</td></tr>
<tr><td>415</td><td>For the method and resource of the current request, the entity submitted in the request is not the format supported by the server, so the request is rejected.</td></tr>
<tr><td>416</td><td>If the request contains the Range request header and any data range specified in the Range are not coincident with the available scope of the current resources; at the same time, it does not define the If-Range request header in the request, then the server should return to 416 status code. If the Range uses a byte range, then this situation indicates that the first byte position of all data range specified by the request exceeds the length of current resource. The server should also return to 416 status code and contain a Content-Range entity header to specify the length of the current resource. This response is also prohibited from using multipart/byteranges as its Content-Type.</td></tr>
<tr><td>417</td><td>The expected content specified in the request header Expect cannot be satisfied by the server or the server is a proxy server, it has clear evidence to prove that the next node in the current routing, Expect content cannot be met.</td></tr>
<tr><td>421</td><td>The number of connections from the IP address of the current client to the server exceeds the maximum range of the server license. Usually, the IP address here refers to the client's address (such as a user's gateway or proxy server address) seen from the server. In this case, the calculation of the number of connections may involve more than one end user.</td></tr>
<tr><td>422</td><td>The number of connections from the IP address of the current client to the server exceeds the maximum range of the server license. Usually, the IP address here refers to the client's address (such as a user's gateway or proxy server address) seen from the server. In this case, the calculation of the number of connections may involve more than one end user.</td></tr>
<tr><td>423</td><td>The request format is correct, but due to semantic errors, cannot respond. (RFC 4918 WebDAV)   423 Locked Current resources are locked. (RFC 4918 WebDAV)</td></tr>
<tr><td>424</td><td>The current request failed due to an error in a previous request, such as PROPPATCH. (RFC 4918 WebDAV)</td></tr>
<tr><td>425</td><td>Defined in the draft of WebDav Advanced Collections, but not appear in the “WebDAV sequence set protocol” (RFC 3658).</td></tr>
<tr><td>426</td><td>The client should switch to TLS/1.0. (RFC 2817)</td></tr>
<tr><td>449</td><td>Extended by Microsoft, the representative request should try again after performing proper operation.</td></tr>
<tr><td>500</td><td>The server encountered an unexpected condition that caused it to be unable to complete the processing of the request. In general, this problem occurs when the server's code is wrong.</td></tr>
<tr><td>501</td><td>The server does not support the function required by the current request. When the server is unable to identify the request method, and cannot support its request for any resource.</td></tr>
<tr><td>502</td><td>An invalid response is received from the upstream server when the server as a gateway or proxy server attempts to execute the request.</td></tr>
<tr><td>503</td><td>Due to the maintenance or overload of the temporary server, the server is currently unable to handle the request. This situation is temporary and will be restored after a period of time. If the delay time can be expected, then the response can contain Retry-After header to indicate the delay time. If the Retry-After information is not given, the client should handle it in a way that handles the 500 response. Note: the presence of the 503 status code does not mean that the server must use it when it is overloaded. Some servers just want to refuse the connection to the client.</td></tr>
<tr><td>504</td><td>When the server as a gateway or proxy server attempts to execute the request, it cannot receive a timely response from the upstream server (servers identified by URI, such as HTTP, FTP, and LDAP) or the secondary server (such as DNS).     Note: some proxy servers will return to 400 or 500 error when DNS queries overtime.</td></tr>
<tr><td>505</td><td>The server does not support, or refuses to support the HTTP version that is used in the request. This implies that the server is unable or unwilling to use the same version as the client. The response should contain an entity that describes why the version is not supported and which protocols are supported by the server.</td></tr>
<tr><td>506</td><td>Extended by “Transparent content negotiation protocol” (RFC 2295), it represents that the server has an internal configuration error: the requested negotiation becomes meta-resource and is configured to use itself in a transparent content negotiation, so it is not a proper focus in a negotiation processing.</td></tr>
<tr><td>507</td><td>​The server cannot store completely the content required by the request. This situation is considered to be temporary. WebDAV (RFC 4918)</td></tr>
<tr><td>509</td><td>The server reaches the bandwidth limitation. This is not an official status code, but it is still widely used.</td></tr>
<tr><td>510</td><td>The required strategies when obtaining resources are not met. (RFC 2774)</td></tr>
</table>



