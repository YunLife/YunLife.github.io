java解析json文件
首先配置几个解析java的包，maven配置为

<dependency>      
     <groupId>net.sf.json-lib</groupId>     
     <artifactId>json-lib</artifactId>      
     <version>2.4</version>   
     <classifier>jdk15</classifier>   
</dependency> 
<dependency>
    <groupId>commons-lang</groupId>
    <artifactId>commons-lang</artifactId>
    <version>2.6</version>
</dependency>
<dependency>
    <groupId>commons-httpclient</groupId>
    <artifactId>commons-httpclient</artifactId>
    <version>3.1</version>
</dependency>
<dependency>
    <groupId>commons-beanutils</groupId>
    <artifactId>commons-beanutils</artifactId>
    <version>1.8.3</version>
</dependency>
<dependency>
    <groupId>commons-collections</groupId>
    <artifactId>commons-collections</artifactId>
    <version>3.2</version>
</dependency>
<dependency>
    <groupId>commons-logging</groupId>
    <artifactId>commons-logging</artifactId>
    <version>1.1.1</version>
</dependency>
<dependency>
    <groupId>net.sf.ezmorph</groupId>
    <artifactId>ezmorph</artifactId>
    <version>1.0.6</version>
</dependency>
<dependency>    
    <groupId>net.sf.json-lib</groupId>    
    <artifactId>json-lib-ext-spring</artifactId>    
    <version>1.0.2</version>
</dependency>

配置好包之后就可以解析了，范例如下：



package com.jusfoun.util;
 
import java.util.Iterator;
 
import org.junit.Test;
 
import net.sf.json.JSONArray;
import net.sf.json.JSONObject;
 
public class Dtest {
 
	@Test
	public void ddtest(){
		String jsonStr = "{\"id\":\"3\",\"name\":\"bob\",\"pass\":\"123\"}";
		JSONObject jsonObj = JSONObject.fromObject(jsonStr);
		System.out.println(jsonObj.get("name"));
		String arrStr = "[{\"id\":\"3\",\"name\":\"bob\",\"pass\":\"123\"},{\"id\":\"4\",\"name\":\"lancy\",\"pass\":\"134\"}]";
		JSONArray jsonArr = JSONArray.fromObject(arrStr);
		System.out.println(jsonArr.getJSONObject(1).get("name"));
		Iterator<Object> it = jsonArr.iterator();
		while(it.hasNext()){
			JSONObject obj = (JSONObject)it.next();
			System.out.println("name:"+obj.get("name")+" pass:"+obj.get("pass"));
		}

}

