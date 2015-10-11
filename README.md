#nginx集群

###1.安装nginx

>因为session问题,nginx对session不友好,所以采用阿里的tengine(只是对nginx进行封装,语法和nginx一样)  

######链接:http://tengine.taobao.org/
>版本采用最新版2.1.1

######安装步骤
1. 上传tengine至usr/local目录  
2. 编译tengine  
命令:./configure --prefix=/usr/local/tengine --with-http_stub_status_module --with-http_ssl_module  
说明:将编译后的tengine放到/usr/local/tengine目录下,并且安装ssl模块  
注意点:  
>1. 必须进入tengine的源码目录(/tengine的一级目录)进行编译,否则无法找到tengine  
>2. 编译的目录和源码目录不能相同否则编译会失败!!!!  
>3. linux可能环境没有安装好,这个需要根据具体情况百度  
>4. 如果编译失败的话请删除tengine重试
3. 配置集群,进入/usr/local/tengine/conf目录修改nginx.conf配置文件  
       upstream snkefu-web{
          server 218.244.149.110:8080;
          server 218.244.149.110:9081;
	      session_sticky;
       }
以上代码写在http{}里面,建议放在第一行






