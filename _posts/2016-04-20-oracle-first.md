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