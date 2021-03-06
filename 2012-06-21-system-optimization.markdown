---
layout: post
title: "系统优化"
date: 2012-06-21 21:18
categories: Dev
tags: 
---


前一段时间一直在忙一个子系统的优化.今年主要的工作内容貌似都跟性能优化相关了.接下来是另外一个项目的优化.在优化的工程中有点感受.

性能优化是基于现有的框架来做的,除非先有的框架是在无法满足了性能需求了,不到万不得已,不能推到重来.重来的风险挺大的.

代码总是可以优化的,一些微不足道的操作,累加起来以后.对性能的影响也是很大的.诸如对象的序列化,频繁的数据库操作,装箱拆箱.这些虽然都不导致某个功能点不能使用,但是累加起来的确会对性能造成很大的影响.

数据库优化,不仅仅是后期参数的调整,更需要前期DBA对sql的一个评审.

这个项目的优化,自己主要做了两点:

*   数据库访问加锁(由于有之前的缓存机制有缺陷,决解并发情况下缓存重复建立的问题)
*   减少对象序列化的过程

以上两点对代码的修改,对原有功能的影响都是最小的.

以最小的代价,修改最少的代码,优化性能.同时不影响功能.
