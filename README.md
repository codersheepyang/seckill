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
 
 
