---
layout:     post
title:      "oracle中部分函数的用法摘要以及用到的一些日常方法"
subtitle:   "记录平时开发中碰到的函数用法、介绍等等"
date:       2016-04-20
author:     "hj_yeah"
header-img: "img/post-bg-sql-oracle.jpg"
tags:
    - oracle
---

> 蓦然回首那人却在灯火阑珊处

*  [instr()](#instr)
*  [substr()](#substr)
*  [to_char()](#tochar)
*  [case()](#case)
*  [REGEXP_LIKE](#REGEXP_LIKE)

#### instr函数
instr函数对字符串进行判断，判断其是否含有指定的字符,返回被查找到的指定的字符的位置     

> 语法： instr(sourceString,destString,start,appearPosition)    
> 其中sourceString代表源字符串；    
> destString代表要从源字符串中查找的子串；     
> start代表查找的开始位置，这个参数可选的，默认为1；       
> appearPosition代表想从源字符中查找出第几次出现的destString，这个参数也是可选的， 默认为1      
> 如果start的值为负数，则代表从右往左进行查找，但是位置数据仍然从左向右计算。      

#### substr函数
SUBSTR()函数:从给定的字符表达式或备注字段中返回一个子字符串。    

> 语法： SUBSTR(cExpression，nStartPosition [，count])      
> cExpression指定要从其中返回字符串的字符表达式或备注字段     
> nStartPosition用于指定返回的字符串在字符表达式或备注字段中的位置     
> count用于指定返回的字符数目，缺省时返回字符表达式的值结束前的全部字符 　

#### to_char函数
有效的工具用于把各种数据类型（日期/时间，int，float，numeric）转换成格式化的字符串以及反过来从格式化的字符串转换成原始的数据类型;参考[相关链接](http://www.cnblogs.com/reborter/archive/2008/11/28/1343195.html)

#### case函数
Case具有两种格式:简单Case函数和Case搜索函数。基本格式：case ... when... then...else....end   
> 参考链接：[case文章](http://www.cnblogs.com/eshizhan/archive/2012/04/06/2435493.html)

> 简单Case函数    
CASE sex  
WHEN '1' THEN '男'  
WHEN '2' THEN '女'  
ELSE '其他' END  

> Case搜索函数     
CASE WHEN sex = '1' THEN '男'  
WHEN sex = '2' THEN '女'  
ELSE '其他' END   

> GROUP BY CASE WHEN 用法  
SELECT  
CASE WHEN salary <= 500 THEN '1'  
WHEN salary > 500 AND salary <= 600  THEN '2'  
WHEN salary > 600 AND salary <= 800  THEN '3'  
WHEN salary > 800 AND salary <= 1000 THEN '4'  
ELSE NULL END salary_class, -- 别名命名  
COUNT(*)  
FROM    Table_A  
GROUP BY  
CASE WHEN salary <= 500 THEN '1'  
WHEN salary > 500 AND salary <= 600  THEN '2'  
WHEN salary > 600 AND salary <= 800  THEN '3'  
WHEN salary > 800 AND salary <= 1000 THEN '4'  
ELSE NULL END;  

#### REGEXP_LIKE正则
> 正则过滤非数字
REGEXP_LIKE('1.1', '^[0-9]+\.{0,1}[0-9]*$') 



