# Vue仿小米商城系统

[TOC]



### 项目介绍

本项目是基于Vue全家桶的仿小米商城系统，商城的流程如下：

登录 -> 产品首页 -> 产品站 -> 产品详情

购物车 -> 订单确认 -> 订单支付 -> 订单列表

 该项目是对小米商城系统的模仿，实现了从浏览商品到结算商品的整个过程。使用Scss、mixin来对公共样式抽离；对不同页面进行组件复用；商品展示图片使用vue-lazyload实现懒加载；通过vuex实现商品的状态管理，最终实现了登录、浏览商品并加入购物车、结算等功能。



### 商城页面与组件

![](https://cdn.jsdelivr.net/gh/mengqiuleo/images/202206241746396.jpg)



### 技术栈

![](https://cdn.jsdelivr.net/gh/mengqiuleo/images/202206241746397.jpg)




### 技术内容

- 对开发时请求后台数据设置跨域

- 对sessionStorage进行封装
- 对axios进行封装，设置拦截器，根据后端返回的不同状态码来进行不同响应设置
- 使用cookie管理
- 使用Vuex管理用户信息和购物车状态
- 封装Modal弹框组件
- 使用swiper轮播图组件
- 使用elementUI美化页面，如何按需引入
- 使用路由懒加载提高性能
- 使用Scss的mixin对公共样式抽离
- 使用图片懒加载
- 使用微信、支付宝支付



### 简单使用

npm install 下载依赖

npm run serve 本地运行

#### 登录账号

**登录账号和密码：账号：admin  密码：admin**



#### 源码说明：

- src目录下是源码
- public目录下存放了一些用到的图片
- resource目录下存放了接口文档


### 商城各页面展示

#### 商品首页

首页各个组件的静态代码实现，并实现了图片懒加载，实现了swiper轮播图。

![](https://cdn.jsdelivr.net/gh/mengqiuleo/images/202206241746399.jpg)



#### 产品站

产品站页面吸顶组件、参数组件实现。

![]()![产品站页](https://cdn.jsdelivr.net/gh/mengqiuleo/images/202206241746400.jpg)

#### 商品详情

商品详情交互接口实现。

![](https://cdn.jsdelivr.net/gh/mengqiuleo/images/202206241746401.jpg)



#### 登录页面：账号 admin 密码 admin

登录页面交互和接口完整代码实现。

![](https://cdn.jsdelivr.net/gh/mengqiuleo/images/202206241746402.jpg)

#### 订单确认

订单确认页面中部分静态模块实现以及接口功能实现。

![](https://cdn.jsdelivr.net/gh/mengqiuleo/images/202206241746403.jpg)

#### 购物车页面

购物车头部组件以及购物车所有功能的动态交互实现。

![](https://cdn.jsdelivr.net/gh/mengqiuleo/images/202206241746404.jpg)

#### 订单支付页面

订单结算交互实现，同时包含微信支付和支付宝支付同后台对接。

![](https://cdn.jsdelivr.net/gh/mengqiuleo/images/202206241746405.jpg)

#### 支付宝支付

![](https://cdn.jsdelivr.net/gh/mengqiuleo/images/202206241746406.jpg)

#### 微信支付

![](https://cdn.jsdelivr.net/gh/mengqiuleo/images/202206241746407.jpg)

#### 订单列表

![](https://cdn.jsdelivr.net/gh/mengqiuleo/images/202206241746408.jpg)