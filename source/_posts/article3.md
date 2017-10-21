---
title: hexo+git搭建自己域名博客之二——hexo配置
date: 2017-10-20 22:03:39
categories:
- 撸代码
tags: 
- hexo
- blog
- node.js
- git
- github desktop
- vscode
---

#### 导语：
`Hexo` 是一个快速、简洁且高效的博客框架。`Hexo` 使用 `Markdown`（或其他渲染引擎）解析文章，在几秒内，即可利用靓丽的主题生成**静态网页**。

**如果不想费心费力的去写HTML的话，也不愿意花费租用主机且想有自己独特域名的，选用GitHub+hexo是个不错的选择。**


#### 一、官方文档：

[hexo官方文档:英文](https://hexo.io/docs/index.html)

[hexo官方文档:中文](https://hexo.io/zh-cn/docs/index.html)

#### 二、基础环境说明：
**1.操作系统**：win10 64位

**2. 配置环境**：`node.js` + `github desktop`

**官方文档的配置采用的是：**
`node.js` +`git`。

![git截图](/images/hexo/2.png)

**说明一下：**在这里我用Github desktop替换了`git`，因为我是小白入门，不是特别喜欢`git`那种命令行的操作，更喜欢Gui一些，所以宁愿用直观牺牲掉高效。不过，如果你已经熟悉`git`的操作了，完全可以使用`git`；当然也可以选择后续逐步来适应`git`。

![官方手册环境配置要求](/images/hexo/0.png)

#### 三、配置hexo基础环境：

**1.下载node.js**

`Node.js` 是一个基于 `Chrome V8` 引擎的 `JavaScript` 运行环境。`Node.js` 的包管理器 `npm`，是全球最大的开源库生态系统。`hexo`就是其中的一个包。
[node.js官网下载地址](https://nodejs.org/en/)

![可以选择LTS版本](/images/hexo/1.png)

[node.js中文站下载地址](http://nodejs.cn/download/)

因为已经安装过了，就懒得安装截图了。


**2.下载github desktop**

- github desktop下载
[github desktop下载地址]()

![github desktop](/images/hexo/3.png)

下载后先安装即可，后文讲如何注册、创建仓库、设置域名等




#### 四、下载、安装hexo

**1. 通过npm下载hexo**

在命令行可以通过`npm`命令下载`hexo`:

`$ npm install -g hexo-cli
`

温馨提示：**纯小白请注意，命令行输入时不含`$`符号**；
网速可能会有些慢，耗时会有点久，如果你知道梯子怎么用，可以搭起来，稍微会快点。

**2.设置初始化文件夹**
可以先建好文件夹，然后在文件夹使用`shift`+鼠标右键，然后选择打开命名行。我的是win10用的是powershell，效果没啥差别。
![shift+右键](/images/hexo/5.png)
 - 在命令行输入:
`$ hexo init <folder>`
注意：`<folder>`是你打算存放的目标文件夹名字
 - 切换至目标文件：
 `$ cd <folder>`
 - 输入命令：
 `$ npm install`
 - 文件夹结构
完成上述步骤后，文件夹大体如下（我的因为使用过，会有细微差别）：
![文件夹结构](/images/hexo/6.png)


#### 五、修改配置信息

**1.使用文本编辑器打开`_config.yml`**

文件夹内有个`_config.yml`，这就是配置文件，可以使用文本编辑器（如：Notepad++：[官网下载地址](https://notepad-plus-plus.org/download/v7.5.1.html)）打开

**2.自定义部分信息**

主副标题、作者、描述：可以自定义
语言：可以参照下图设置为中文
时区：可以参照下图设置为亚洲上海
url：改为自己注册的域名

![自定义信息](/images/hexo/7.png)

**3.deploy可以暂不改**

注：因为我们使用GitHub desktop来同步文件到GitHub，所以后续不适用deploy来发布、更新网站，所以暂时可以不用修改，如果你会使用git且愿意使用的，可以参照官方文档步骤设置。
![deploy](/images/hexo/8.png)

**4.其他文件可以不必修改**

**5.修改完毕后保存`_config.yml`文件**


#### 六、hexo的使用

**1.hexo 创建文章**

使用如下命令可以创建新文章：

`$ hexo new [layout] <title>`
可以在命令中指定文章的布局（layout），默认为 post，可以通过修改 `_config.yml` 中的 `default_layout` 参数来指定默认布局。由于我们并未修改，所以可以直接使用`$ hexo new <title>`创建文章。
**注意**:`<title>`即文章名，没有尖括号

**2.编辑文章**

  - 查找到`.md`文件
由于layout我们并未修改，所以默认在hexo目标文件夹的`\source\_posts`文件夹下，为`<title>.md`文件，该文件可以使用文本编辑器进行编辑，使用MARKDOWN语法。
  - vscode 下载
目前我使用的是VSCODE,可以配合插件在编辑同时预览。

[vscode官方网站](https://code.visualstudio.com/)
  - Markdown插件
安装vscode后可以打开“拓展”，搜索`Auto-Open Markdown Preview`插件
![markdown插件](/images/hexo/9.png)
安装插件后打开`.md`文件进行编辑，点击右上角预览图标开启预览
![vscode markdown预览](/images/hexo/10.png)

**3.生成静态文件**

- 文章编辑完成后，可以通过如下命令来生成静态文件：`$ hexo generate` 或者`$ hexo g`；

- 文件生成后，会产生一个`public`文件夹，这个文件夹里的内容就是需要我们同步到GitHub的内容了。

**4.本地服务器预览**

- 在命令行输入如下命令启动服务器：

`$ hexo server`




![启动本地服务器](/images/hexo/11.png)

- 在浏览器搜索栏里输入`localhost:4000`就可以预览到网站了

- `ctrl+c`可以退出本地服务器

#### 七、github 注册、同步
**1.github 注册**
![注册github](/images/hexo/4.png)

**2.新建仓库**
- 通过“new repository”新建代码仓库，届时用于存储博客需要展示的页面等文件
![新建仓库](/images/hexo/12.png)
- 使用"用户名"+"github.io"组合命名仓库，注意每个账户仅能配置一个这样的仓库。
实例中用户名"yin",所以用"yin.github.io"
![设置名字](/images/hexo/13.png)

- 将仓库克隆到本地
用客户端打开——然后选择仓库本地存储路径——保存
![用desktop clone到本地](/images/hexo/14.png)

![选择路径，然后clone](/images/hexo/15.png)

**3.复制hexo里的public文件夹中的所有文件到本地仓库**
复制粘贴到本地仓库后，GitHub desktop就可以自动发现变化了
![复制文件](/images/hexo/16.png)
![粘贴文件](/images/hexo/17.png)
![github desktop发现文件](/images/hexo/18.png)

**4.提交修改，然后同步**
- 选择"master"，填写commit说明，然后点击"commit to master",commit后其实4就会发生变化,然后选择"push origin",完成同步。这样在网页版看到的就是同步后的内容了。
![commit](/images/hexo/19.png)

![push origin](/images/hexo/20.png)

![github repository](/images/hexo/21.png)

- 关于git的用法，还有很多很多，具体可以学习廖雪峰的教程：
[廖雪峰博客](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)

#### 八、域名注册与绑定

**1.注册域名**
国内的域名注册商一般需要做备案，为了偷懒，我直接在“狗爹”[godaddy.com](https://godaddy.com)上注册的。

- 挑选喜欢的域名，添加到购物车
![域名示例](/images/hexo/22.png)
- 隐私保护不需要的话可以选“不，谢谢”
![隐私保护](/images/hexo/23.png)
- 虚拟主机选“不，谢谢”，因为我们后续将使用GitHub托管内容
![虚拟主机](/images/hexo/24.png)
- 前去付款
![订单信息](/images/hexo/25.png)
- 开始付款，填写结算信息，可以选择支付宝和银联
![付款页面](/images/hexo/26.png)

**2.使用DNSPOD来解析域名**
- 域名注册完成后进入“我的产品”，示例是我自己的域名
![域名](/images/hexo/27.png)

- 自定义域名服务器
DNSPOD免费的域名服务器分别如下，添加后点击保存



`f1g1ns1.dnspod.net`

`f1g1ns2.dnspod.net`



![自定义域名服务器](/images/hexo/28.png)

**3.github 仓库里添加CNAME**
- 通过“create new file”添加CNAME
![创建文件](/images/hexo/32.png)
- 注意CNAME文件名为大写，且**没有后缀名**
![CNAME](/images/hexo/33.png)
- 在文件中写入自己的网址，注意没有"http"、"https"和"www"
- "commit new file"提交文件
![commit CNAME](/images/hexo/34.png)
- 进入该仓库的"settings"，往下拉设置域名
![settings](/images/hexo/35.png)
![settings](/images/hexo/31.png)

**4.进入DNSPOD去绑定域名，设置解析**
- 注册dnspod账户,不细说
[dnspod.cn](https://dnspod.cn/)

- 进入控制台——域名解析——添加域名
![添加域名](/images/hexo/29.png)
- 添加 @ 和 www 两个主机记录，下图第一、四行红色框内的
![主机记录](/images/hexo/30.png)

- 记录值可以写"用户名"+"github.io"的域名，如"yin.github.io"，也可以先ping到"用户名"+"github.io"的ip后填写进入
![ping](/images/hexo/36.png)

**5.其他注意事项:**
- CNAME文件请同步到本地仓库，将hexo public文件更新到本地仓库时，不要把CNAME删除了。
- 如果涉及多个设备管理博客，可以另建一个仓库，把hexo里的所有文件同步到GitHub里了。



