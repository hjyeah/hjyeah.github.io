---
layout:     post
title:      "nginx安装"
subtitle:   "简述nginx在ubuntu16.04上的安装"
date:       2017-02-27
author:     "hj_yeah"
header-img: "img/post-bg-version.jpg"
tags:
    - nginx
---

> [参考网址](https://www.digitalocean.com/community/tutorials/how-to-install-nginx-on-ubuntu-16-04)  

##### step one      
**sudo apt-get update**      
**sudo apt-get install nginx**       
注：更新本地的apt包，获取最新的nginx版本       

##### step two        
配置ubuntu的防火墙以致可以访问nginx服务，这里说明ufw是ubuntu的一个防火墙配置工具（自带集成）     
**sudo ufw app list** > 列出防火墙下的应用可配置列表     
显示如下：
<blockquote>     
	Output    
	Available applications:    
	  Nginx Full     
	  Nginx HTTP     
	  Nginx HTTPS      
</blockquote> 
开启某种类型的服务，这边假设开启nginx http服务：          
**sudo ufw allow 'Nginx HTTP'**         
验证类型状态：          
**sudo ufw status**          
如果显示服务是激活状态，则已开启：         
<blockquote>
	Output      
	Status: active     
	To                         Action      From      
	--                         ------      ----      
	Nginx HTTP                 ALLOW       Anywhere                      
	Nginx HTTP (v6)            ALLOW       Anywhere (v6)         
</blockquote>
##### step three           
验证nginx服务有没开启     
**systemctl status nginx**    
如果显示如下，则已经开启   
<blockquote>  
	nginx.service - A high performance web server and a reverse proxy server       
	   Loaded: loaded (/lib/systemd/system/nginx.service; enabled; vendor preset: enabled)     
	   Active: active (running) since Mon 2016-04-18 16:14:00 EDT; 4min 2s ago      
	 Main PID: 12857 (nginx)      
	   CGroup: /system.slice/nginx.service      
	           ├─12857 nginx: master process /usr/sbin/nginx -g daemon on; master_process on      
	           └─12858 nginx: worker process       
</blockquote> 
或者直接访问 curl http://127.0.0.1:80即可     

##### step four      
停止nginx服务：      
**sudo systemctl stop nginx**     

开启nginx服务：    
**sudo systemctl start nginx**    

重启nginx服务：     
**sudo systemctl restart nginx**       

如果只是简单的修改了nginx的配置，可以重新加载nginx      
**sudo systemctl reload nginx**     


