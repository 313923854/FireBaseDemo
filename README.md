# Google FireBase的简单介绍和使用

---

### 一、FireBase是啥东东，可以吃嘛？
* [FireBase官网](https://firebase.google.com/)(需要科学上网)

* 用官网简介的话来说就是：构建更出色应用和成功地扩大业务所需的工具和基础架构。
* 再次用官网的话描述：Firebase 是一个移动平台，可以帮助您快速开发高品质应用，扩大用户群，并赚取更多收益。Firebase 由多种互补功能组成，您可以自行组合和匹配这些功能以满足自己的需求。

* 最后总结一下：FireBase是一个用于构建移动应用、提供实时数据存储和同步、用户身份验证等功能的平台。因为是国外的东西，所有需要科学上网，请自备梯子。

### 二、FireBase主要功能介绍
#### 2.1 功能划分
* FireBase功能众多，我们先来看一下官网给出的总结图。

![功能划分](http://upload-images.jianshu.io/upload_images/2786991-5a197199d9770be2.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

* 从上图我们可以知道Google把整个功能切割成四部分，核心功能是强大的Analytics，还有其他三个等分的功能：Develop相关，Grow相关，Earn相关。

#### 2.2 功能介绍
##### 2.2.1 分析（Analytics）
* Firebase 的核心是 Firebase Analytics，这是一项免费且无限制的分析解决方案。从单一信息中心查看用户行为和衡量行为特性。

![分析](http://upload-images.jianshu.io/upload_images/2786991-863aeb3b39d4675e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

##### 2.2.2 开发（Develop）
* 专心构建更好的应用，将具体操作留给我们来完成。节省宝贵的开发时间，交付高品质、无缺陷的应用。

 ![开发](http://upload-images.jianshu.io/upload_images/2786991-5422ffd272031eeb.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

* 开发模块又包括了许多小功能
    * Cloud Messaging 云消息传递
    * Authentication 身份验证
    * Realtime Database 实时数据库
    * Storage 存储
    * Hosting 托管
    * Remote Config 远程配置
    * Test Lab 测试实验室
    * Crash Reporting 奔溃报告

##### 2.2.3 增长（Grow）
* 在合适的时间赢得和吸引合适的用户。不靠碰运气，实现精准稳健增长。

![增长](http://upload-images.jianshu.io/upload_images/2786991-044eb56234f6dad9.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

* 增长模块包括了五个功能
    * Notifications 通知
    * App Indexing 搜索
    * Dynamic Links 动态链接
    * Invites 邀请，分享
    * AdWords 广告

##### 2.2.4 获利（Earn）
* 通过向全球受众展示引人入胜的广告赚钱。

![获利](http://upload-images.jianshu.io/upload_images/2786991-ab559d9044c41c15.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

* 通过使用谷歌的移动广告平台AdMob来获取利益。

### 三、将 Firebase 添加至Android 项目
> 由于FireBase的功能太过强大，所以这里只是简单集成，具体的内容还请到[FireBase官网](https://firebase.google.com/)学习。

* 集成之前，需要确保你的SDK管理器有Google Play服务SDK。

#### First step
* 进入Fire Base官网，登录谷歌账号，新建项目。

![First step](http://upload-images.jianshu.io/upload_images/2786991-92b9b7a76f8da444.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### Second step
* 建立项目之后，我们需要将当前项目的配置文件下载拷贝到你实际项目的app目录下，因为使用FireBase需要依赖这个配置文件。


![Second step](http://upload-images.jianshu.io/upload_images/2786991-9544c6bef7626b93.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



* 下载google-services.json文件，拷贝到你的app目录，每个项目的配置都不一样，所以下一次新建项目同样需要拷贝。



![Second step01](http://upload-images.jianshu.io/upload_images/2786991-b36bf10abbbf0302.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


#### Third step
* 拷贝好了配置文件，我们还需要为使用的功能添加依赖。
* 首先在项目级build.gradle中添加Google服务规则。

        buildscript {
            // ...
            dependencies {
                // ...
                classpath 'com.google.gms:google-services:3.0.0'
            }
        }

* 之后要需要在app/build.gradle添加依赖和插件

        dependencies {
          // ...
          compile 'com.google.firebase:firebase-core:9.6.1'
        }
        
        // ADD THIS AT THE BOTTOM
        apply plugin: 'com.google.gms.google-services'

* 因为FireBase每个不同的功能都需要添加不同的依赖，所以在这里把所有的依赖都贴出来


![依赖可用库](http://upload-images.jianshu.io/upload_images/2786991-1c5e72fdfd72cfe8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


> 以上只是简单的集成，更多信息请查看[官方集成教程](https://firebase.google.com/docs/android/setup)

### 四、FireBase Demo教程
* 本教程使用的Demo是一个登录验证和实时数据库功能结合使用的案例，需要学习的请[点这里](https://github.com/PingerWan/FireBaseDemo)

* 官方在GitHub上也提供了一系列的快速入门的教程，想了解的请上[传送门](https://github.com/firebase/quickstart-android)

### 五、FireBase更多知识和学习资源
#### 5.1 资讯
* [I/O 2016：谷歌让Firebase转型为面向移动开发者的一体化平台](http://www.cnbeta.com/articles/502725.htm)
* [Firebase成Google I/O主角，实时成最大关注焦点](http://news.sina.com.cn/o/2016-05-20/doc-ifxsktvr1005737.shtml)

#### 5.2 资源
* [官网](https://firebase.google.com/)
* [官方文档](https://firebase.google.com/docs/android/setup)
* [官方案例](https://github.com/firebase/quickstart-android)
* [friendlychat](https://github.com/firebase/friendlychat)
* [AndroidChat](https://github.com/firebase/AndroidChat)
* [Firebase Android 使用整理](http://www.2cto.com/kf/201608/532885.html)

