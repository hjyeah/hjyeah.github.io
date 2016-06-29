---
layout:     post
title:      "web的url获取方式"
subtitle:   "获取url的路径方式"
date:       2016-05-24
author:     "hj_yeah"
header-img: "img/post-bg-version.jpg"
tags:
    - JavaWeb
---

>路径获取的方式  

假定你的web application 名称为news,你在浏览器中输入请求路径：   
http://localhost:8080/news/main/list.jsp 
则执行下面向行代码后打印出如下结果：   

*  System.out.println(request.getContextPath()); //可返回站点的根路径。也就是项目的名字 
打印结果：/news    

*  System.out.println(request.getServletPath()); 
打印结果：/main/list.jsp     

*  System.out.println(request.getRequestURI()); 
打印结果：/news/main/list.jsp    

*  System.out.println(request.getRealPath("/")); 
打印结果：F:\Tomcat 6.0\webapps\news\test 