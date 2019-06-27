# seckill
这是一个基于SSM框架针对秒杀操作的秒杀系统

**&emsp;&emsp;写在前面:就在前几天，看完了《Redis设计与实现》这本书对于redis的基础操作和一些底层原理，又对使用redis做秒杀系统早有耳闻，所以今天就参考慕课老师对于秒杀系统的设计和实现做一个系统的整理，并让自己真正能够理解秒杀背后的原理，以及redis服务以此带来的好处。**

### 一.系统架构
+ 框架：Spring-SpringMVC-MyBatis
+ 数据：MySQL、Redis
+ 接口设计规范:Restful
+ 项目管理工具：maven

### 二.秒杀系统业务核心流程：
<img src="http://kan.027cgb.com/622253/github/seckill/TIM%E6%88%AA%E5%9B%BE20190627131120.png"  alt="核心流程" widht="150" height = "150"/> 

### 三.秒杀系统业务分析：
用户对商品的操作是业务的核心:  

<img src="http://kan.027cgb.com/622253/github/seckill/TIM%E6%88%AA%E5%9B%BE20190627132646.png"  alt="用户针对库存业务分析" widht="150" height = "200"/> 

### 四.秒杀系统存在的问题以及难点：
1. 如下图会存在的一些问题:  
<img src="http://kan.027cgb.com/622253/github/seckill/TIM%E6%88%AA%E5%9B%BE20190627123157.png"  alt="问题" widht="150" height = "200"/>  
&emsp;&emsp;这些问题的出现无异于是对操作没有事务的支持，导致出现的数据不一致的问题，所以我们需要使用MySQL服务以及Spring为我们提供的事务支持来保证数据的一致性以及安全性。

2.难点:  
<img src="http://kan.027cgb.com/622253/github/seckill/TIM%E6%88%AA%E5%9B%BE20190627123933.png"  alt="问题" widht="150" height = "200"/>  
&emsp;&emsp;对于秒杀接口如果暴露的话，那么这对用户是不公平的，因为一些黑客会通过不正规手段来快速获取商品的秒杀权。所以我们应该需要提供一定的技术手段来对秒杀路径进行保护。

3.天猫的秒杀架构：  
&emsp;&emsp;对于秒杀系统做的最成熟的公司应该就是阿里了吧，对于双11以及一些大型活动下淘宝每秒产生的并发量...如果没有一个好的系统架构的支持，那么会产生不可估量的价值损失。  
<img src="http://kan.027cgb.com/622253/github/seckill/TIM%E6%88%AA%E5%9B%BE20190627123817.png"  alt="问题" widht="150" height = "200"/>      &emsp;&emsp; 这复杂的架构一定结晶了许多架构师的心血呀...
