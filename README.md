#nginx集群

###1.安装nginx

>因为session问题,nginx对session不友好,所以采用阿里的tengine(只是对nginx进行封装,语法和nginx一样)  

######链接:http://tengine.taobao.org/
>版本采用最新版2.1.1

######安装步骤
1. 上传tengine至usr/local目录  
2. 编译tengine      ./configure --prefix=/usr/local/nginx --with-http_stub_status_module --with-http_ssl_module






