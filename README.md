基本说明
===================
本demo有两个目的：
 > - 使用鸿瑞云视频的组件，进行html5断点续传。
 > - 监听鸿瑞云视频的回调，实现个性化的功能。
demo的java代码能在java6的环境下正常编译，并能在tomcat7下正常部署和测试通过。
你也可以尝试在其他java服务器下部署。

快速开始
-------------
1. 配置ACCESS_KEY和ACCESS_SECRET
>
登陆鸿瑞云视频, 在开发者支持页面查询ACCESS_KEY和ACCESS_SECRET, 然后配置到demo的com.pispower.video.upload.SignServlet中。

2. 配置callback url
>
demo中默认的callback url为"/callback"
登陆鸿瑞云视频, 在开发者支持页面填写callback url, 格式为http://域名/callback。
>
（注意：如果要使用鸿瑞云视频的回调功能，必须要确保域名在Internet上是可以访问的。请用浏览器访问callback url是否正常。
如果没有配置callback url, 你也可以正常使用断点续传功能，并能在鸿瑞云视频访问到你上传的视频。）

使用说明
-------------
用浏览器访问demo应用，在视频上传页面点击“浏览文件”，选择视频，然后点击“上传”；或者在广告页面上传广告，进行广告的投放、下线演示。

文件组织
-------------
```
demo
  |
  |--src--com--pispower--video--upload--SignServlet.java		计算restful请求的签名
  |	   |							 |
  |    |							 |--CallbackListenerServlet.java	监听鸿瑞云视频的回调
  |	   |
  |    |--log4j.properties	log4j			配置文件
  |
  |--webcontent
  	   |
	   |--css--default.css					demo页面样式文件
	   |    |
	   |	|--videoupload.css 				鸿瑞云视频Html5上传默认样式文件
	   |
	   |--js--jquery-1.11.1.min.js			jquery
	   |   |
	   |   |--spark-md5.min.js				用于计算文件md5值
	   |   |
	   |   |--onecloud-restful.js
	   |   |  
	   |   |--restful-video-upload.js		鸿瑞云视频的Html5上传js库
	   |   |
	   |   |--upload.js						demo用于调用的上传视频的js文件
	   |   |
	   |   |--upload-ad.js          		demo用于调用的上传广告的js文件
	   |   |
	   |   |--apply-ad.js               	demo用于调用的投放、下线广告的js文件
	   |
	   |--WEB-INF--lib			        	java web project依赖的jar包
	   |		|
	   |		|--web.xml		   			web配置文件
	   |
	   |--error.jsp							错误页面
	   |
	   |--index.jsp							主页面
	   |
	   |--upload.jsp        				上传页面
	   |   |
	   |   |--upload-ad.jsp          		上传广告的页面
	   |   |
	   |   |--apply-ad.jsp             		投放、下线广告的页面
```		
	

