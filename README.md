# CSRF
Bypass CSRF-XMLRequestWith

- **前提条件**

1）可利用swf未校验referer和origin 的bypass 含json xml格式的数据，

2）可使用swf添加X-Request-With

**crossdomain XML文件:**

```
<cross-domain-policy>
<allow-access-from domain="*" secure="false"/>
<allow-http-request-headers-from domain="*" headers="*" secure="false"/>
</cross-domain-policy>
```

这个文件应该放在攻击者网站的根目录下，这样Flash文件就可以向攻击者的主机发送请求。

注意：如果Flash文件＆重定向器页面在同一个域，则不需要crossdomain文件。

POC包含：

1. 精心制作的Flash文件
2. 跨域XML文件
3. 带有307个状态的PHP文件
4. 精心制作的flash文件

PS:ffdec_11.2.0_nightly1721_setup为swf编辑软件 

参考：<https://hackerone.com/reports/44146> 

测试环境

![img]({{site.baseurl}}/assets/images/CSRF/6.png)

![img2]({{site.baseurl}}/assets/images/CSRF/7.png)





