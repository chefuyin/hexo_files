---
title: WINODWS系统下MONGODB的配置
date: 2017-10-18 17:38:37
categories:
- 撸代码
tags:
- MongoDB
- Database

---

#### 导语：
_ mongodb 作为NoSQL的典型代表，使用起来比较方便，但是安装过程对于新手小白来说还是略显蛋疼，总会遇到一些坑，为了防止自己忘记，于是写下来，方便备查。 _



#### 1. 基础环境说明
**Key Words**：**查看文档很重要**。
**操作系统**：windows7 64位
**MONGODB版本**：社区版(3.4.9)

#### 2. 打开官方文档

[社区版：官方文档](https://docs.mongodb.com/tutorials/install-mongodb-on-windows/)

**文档很重要**，但是一长串的英文很容易让新人望而却步，请耐着性子仔细的跟着操作步骤来。

#### 3. 下载mongodb
[社区版：官网下载地址](https://www.mongodb.com/download-center?jmp=tutorials#community)

#### 4. 安装mongodb
安装上没啥技术含量，按照默认的一路NEXT即可，但请记住默认的安装路径，后面会涉及。通常情况下，默认路径为：
`C:\Program Files\MongoDB\`

![mongodb安装1](/images/mongodb/1.bmp)
![mongodb安装2](/images/mongodb/2.bmp)
![mongodb安装3](/images/mongodb/3.bmp)

#### 5. 设置数据库存储路径
- **win键 +R ，输入“cmd”，打开命令行**
- **新建一个文件夹存储数据**
注：我设置的是`E:\mongodb_data\data`
- **设定数据存储路径**
`"C:\Program Files\MongoDB\Server\3.4\bin\mongod.exe" --dbpath E:\mongodb_data\data`
**如果路径中有空格，请用引号引起来**，比如：`"C:\Program Files\MongoDB\Server\3.4\bin\mongod.exe" --dbpath "d:\test\mongo db data"`

- **MONGODB连接网络，点击同意**

#### 6.配置WINDOWS服务
- **在数据存储路径新建db、log文件夹**
也可以使用`mkdir`在命令行创建，如下图
![新建db、log文件夹](/images/mongodb/4.bmp)

- **在软件安装目录下创建cfg文件**
注意是与bin文件夹同一级，不是在bin文件夹下
![创建cfg文件](/images/mongodb/5.bmp)
在cfg文件内写入如下代码：

```
systemLog:
    destination: file
    path: E:\mongodb_data\data\log\mongod.log
storage:
    dbPath: E:\mongodb_data\data\db
```


- **注册服务**
在命令行输入如下命令
`"C:\Program Files\MongoDB\Server\3.4\bin\mongod.exe" --config "C:\Program Files\MongoDB\Server\3.4\mongod.cfg" --install`

**注意：WIN10等操作系统会存在运行命令行工具时权限不够的问题，最好在进入菜单时查看所有软件，找到命令行工具，右键管理员权限运行。权限不够时会导致服务注册不成功。**

- **启动MONGODB**
在命令行输入：
`net start MongoDB`

![启动服务](/images/mongodb/6.bmp)

#### 7.下载可视化软件

- **下载软件**
[Robo 3T：官网下载地址](https://robomongo.org/download)

- **连接数据库**
软件默认安装，一路NEXT

![连接数据库1](/images/mongodb/7.bmp)
![连接数据库2](/images/mongodb/8.bmp)
![连接数据库3](/images/mongodb/9.bmp)

**至此大功告成！**





















