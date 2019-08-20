### Wukong CRM9.0 (JAVA version)
Wukong Software has long provided enterprises with integrated information services in the development, implementation, marketing, consulting, training and service of Business Management Software(CRM/HRM/OA/ERP, etc.). Upholding high-tech as our starting point, technology as the core and perfect after-sale service as our backing, with the spirit of steady development and constant innovation, we have provided services for thousands of enterprises at home and abroad.


The development of Wukong benefits from open source and vice versa. In the future, Wukong CRM will still uphold the idea of "embracing, openness, cooperation and win-win, creating values". We will keep moving forward with more community developers to make more contributions for the world's open source.


Official website：[http://www.5kcrm.com](http://www.5kcrm.com/) / [http://www.72crm.com](http://www.72crm.com/)


DEMO：[demo9java.5kcrm.net](http://demo9java.5kcrm.net/) (Account：18888888888   Password：123456)


Wukong CRM adopts the brand new mode of front-end and back-end seperation. The front-end vue packaged files have been integrated in the repository, so users needn't to package it.

If you need to modify the front-end code, please download the front-end code separately. The front-end code is in the ux folder of the root directory.


## Main Technology Stack

Core framework：jfinal3.8

Cache：redis

Database connection pool：Druid

Utility classes：hutool,fastjson,poi-ooxml

Timed task：jfinal-cron

Project management tool：maven

Web container：tomcat,jetty,undertow(默认)

Front-end MVVM framework：Vue.JS 2.5.x 

Routing：Vue-Router 3.x 

Data interaction：Axios 

UI framework：Element-UI 2.6.3 



## Installation Instructions


Configure Java runtime environment, redis environment and mysql environment; import the 72crm.sql in directory doc into database; modify database in `resources/config/erpsnow-config.txt` and redis configuration file; modify undertow start port number in `resources/config/undertow.txt`. (Default Account: admin  Default Password: 123456) 





## Deployment Instructions

The project requires JDK8 or higher.

### 一、Tomcat deployment


```
<dependency>
    <groupId>javax.servlet</groupId>
    <artifactId>javax.servlet-api</artifactId>
    <version>4.0.1</version>
    <scope>provided</scope>
</dependency>
```

Uncomment the above code, comment undertow references; change the packaging method to war, run the maven package command, and place the war package in the `tomcat/webapps directory`.


### 二、Undertow (default)


```
<dependency>
    <groupId>com.jfinal</groupId>
    <artifactId>jfinal-undertow</artifactId>
    <version>1.6</version>
</dependency>
```



Uncomment the above code, comment tomcat and undertow references, change the packaging method to jar. Upload the zip file generated by the above packaging commands to server and decompress it. Put `72crm.sh/72crm.bat` in directory to the decompressed directory and run it.

The project webapp includes the packaged front-end code. If you needn't to modify the front-end code, please directly visit it. If you have modified the front-end code, please replace the static folder and index.html in packaged dist into webapp.
p.s.: you can use `nginx` proxy to process static file, the back-end only implement interfaces. And the designation of the program is a completely separated front-end the back-end.




### Front-end deployment

Install node.js. :

Due to the front-end runs on node.js, you should first install `node.js` 6.0 or above.
Use npm install dependency to download the front-end code of Wukong CRM; And you can first put the front-end code into the the sibling directory "front-end" of back-end, and then executive the command to install dependency：

    npm install

Modify the interior configuration and the Domain Name or IP: 
Modify BASE_API in config/dev.env.js (the default address of SDE is localhost) 

Modify custom port: the port parameter of dev object in config/index.js (the default port is 8090 and we do not recommend to modify it. )

### Running front-end

     npm run dev

NOTE: Port 8090 will be used when running the front-end. So before running the front-end service, please ensure port 8090 is not in use, and the server needs to be set up before the program runs.

---

### 悟空CRM9.0（JAVA版）
悟空软件长期为企业提供企业管理软件(CRM/HRM/OA/ERP等)的研发、实施、营销、咨询、培训、服务于一体的信息化服务。悟空软件以高科技为起点，以技术为核心、以完善的售后服务为后盾，秉承稳固与发展、求实与创新的精神，已为国内外上千家企业提供服务。

悟空的发展受益于开源，也会回馈于开源。2019年，悟空CRM会继续秉承“拥抱开放、合作共赢、创造价值”的理念，在开源的道路上继续砥砺前行，和更多的社区开发者一起为国内外开源做出积极贡献。

官网：[http://www.5kcrm.com](http://www.5kcrm.com/)

官网：[http://www.72crm.com](http://www.72crm.com/)

论坛：[http://bbs.72crm.net](http://bbs.72crm.net/)

演示地址：[demo9java.5kcrm.net](http://demo9java.5kcrm.net/)(帐号：18888888888   密码：123456)

JAVA版QQ群交流群①群：[1026560336](https://shang.qq.com/wpa/qunwpa?idkey=13d5e5809eb9feb350336e55c8b7a00b9cb472078b09b4441222a52dd76b278e)




悟空CRM采用全新的前后端分离模式，本仓库代码中已集成前端vue打包后文件，可免去打包操作

如需调整前端代码，请单独下载前端代码，前端代码在根目录的ux文件夹中


## 主要技术栈

核心框架：jfinal3.8

缓存：redis caffeine

数据库连接池：Druid

工具类：hutool,fastjson,poi-ooxml

定时任务：jfinal-cron

项目构建工具：maven

Web容器：tomcat,undertow(默认)

前端MVVM框架：Vue.JS 2.5.x 

路由：Vue-Router 3.x 

数据交互：Axios 

UI框架：Element-UI 2.6.3 



## 安装说明

1、配置java运行环境，redis环境，mysql环境。  
2、将目录doc下的crm9.sql导入到数据库( `初始化安装只需要导入crm9.sql就好了，更新代码导入对应日期的sql文件`)。  
3、修改`resources/config/crm9-config.txt`下的数据库配置文件。
4、修改`resources/config/redis.json`下的redis连接文件
5、undertow启动端口号在`resources/config/undertow.txt`下修改。  
默认账号 admin 默认密码 123456  





## 部署说明

本项目JDK要求JDK8及以上


### 一、Undertow（默认）


```
<dependency>
    <groupId>com.jfinal</groupId>
    <artifactId>jfinal-undertow</artifactId>
    <version>1.6</version>
</dependency>
```

取消以上代码的注释，将tomcat的pom依赖javax.servlet.javax.servlet-api注释掉，打包方式改为jar 运行maven package，打包完成后  
将上述打包命令生成的 crm9-release.zip 文件上传到服务器并解压,运行对应的72crm.sh/72crm.bat即可

### 二、Tomcat部署


```
<dependency>
    <groupId>javax.servlet</groupId>
    <artifactId>javax.servlet-api</artifactId>
    <version>4.0.1</version>
    <scope>provided</scope>
</dependency>
```

取消以上代码的注释，将undertow的pom依赖com.jfinal.jfinal-undertow注释掉，并将com.kakarote.crm9.Application的main方法注释掉，打包方式改为war，  
运行maven package命令，将war包放在`tomcat/webapps`目录下

项目默认是ROOT.war，若需要携带项目名，需要修改 ux/config/prod.env.js的BASE_API为'"/项目名/"'，改动完成后需要重新打包替换到webapp下  


项目webapp下自带打包后的前端代码，如果不需要对前端代码更改，直接访问即可  
如果更改了前端代码，需要将打包后的dist下static文件夹和index.html替换到webapp下     
ps:可以使用`nginx`代理静态文件，后台只做接口响应，项目本身设计是前后端完全分离的  



### 前端部署

安装node.js 前端部分是基于node.js上运行的，所以必须先安装`node.js`，版本要求为6.0以上

使用npm安装依赖 下载悟空CRM9.0前端代码； 可将代码放置在后端同级目录ux，执行命令安装依赖：

    npm install

修改内部配置 修改请求地址或域名：config/dev.env.js里修改BASE_API（开发环境服务端地址，默认localhost） 修改自定义端口：config/index.js里面的dev对象的port参数（默认8090，不建议修改）

### 运行前端

     npm run dev

注意：前端服务启动，默认会占用8090端口，所以在启动前端服务之前，请确认8090端口没有被占用。
程序运行之前需搭建好Server端



## 系统介绍

以下为悟空CRM9.0 JAVA版部分功能系统截图

![](https://github.com/72crm/72crm/blob/master/ux/intro_img/g1.png)
![](https://github.com/72crm/72crm/blob/master/ux/intro_img/g2.png)
![](https://github.com/72crm/72crm/blob/master/ux/intro_img/g3.png)
![](https://github.com/72crm/72crm/blob/master/ux/intro_img/g4.png)
![](https://github.com/72crm/72crm/blob/master/ux/intro_img/g5.png)
![](https://github.com/72crm/72crm/blob/master/ux/intro_img/g6.png)
![](https://github.com/72crm/72crm/blob/master/ux/intro_img/g7.png)
![](https://github.com/72crm/72crm/blob/master/ux/intro_img/g8.png)
![](https://github.com/72crm/72crm/blob/master/ux/intro_img/g9.png)
![](https://github.com/72crm/72crm/blob/master/ux/intro_img/g10.png)


