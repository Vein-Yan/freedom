<p align="center">
  <img src="https://i.loli.net/2019/02/08/5c5c5dcf30f30.png">
</p>

<p align="center">
  "有时我幻想拯救世界,带领那些处在痛苦的人们逃出来"
</p>
<p align="center">
  "Sometimes I fantasize about saving the world and leading people in pain to escape."
</p>

<p align="center">
"翻越防火长城，你可以到达世界上的每一个角落。"<br>
"Across the Great Firewall, you can reach every corner in the world."
</p>

```bash
.
├── LICENSE
├── README.md
├── bin
│   └── ssr # ssr脚本
├── docs
│   ├── GFW.md # gfw历史
│   └── ss_history.md # shadowsocks前世今生
└── shell
    ├── bbr.sh # 开启 bbr
    └── ssr.sh # ssr 脚本

```

## 前言

第一次接触翻墙是在`15`年,当时我记得挂的是`vpn`,后来,貌似所有的`vpn`都挂掉了,时间辗转到`16`年,自学计算机,这时才发现不翻墙真的会被国内的服务**强奸**,我便去百度搜索一切关于`翻墙`的信息,然后却什么都没有得不到(我相信此时的你也经历过!),我在学习`linux`的时候,遇到的报错信息一切都无法解决,所以我便去**各大论坛**去请教别人,但却没人愿意做这吃力不讨好的事,搞不好还会**请去喝茶**,只是隐晦的说了一句:

> 懂电脑都会科学上网,不要再论坛里谈论这个话题

时间转眼间已经到了`2019`年,三年里,我已然成为了**老司机**,翻墙早已是必备技能,
所以,我希望这个项目能够帮助到你,如果能够帮助到你,是我的荣幸之极

## 开始
所谓`GFW`,实则是指: 中国政府在其互联网边界审查系统,详情 [看这里](docs/GFW.md)

技术是在不断提升的,上有政策,下有对策,所以有了[shadowsocks](docs/ss_history.md)

相信很多的小伙伴应该都听过几个技术名词: `ss` | `ssr` | `v2ray`

后两者就是从前者衍生出来的,也就是`shadowsocks`

至于的它的原理,推荐看看: https://github.com/gwuhaolin/blog/issues/12

### 安装 & 配置
额,这个感觉没什么好说的,别的教程都写的很清楚了,也就是安装一下

- Macos GUI: https://github.com/qinyuhang/ShadowsocksX-NG-R/releases
- 推荐`electron-ssr`: https://github.com/erguotou520/electron-ssr.git

安装很简单,然后是配置,首先是在浏览器下,你需要装: [switchyomega](https://www.switchyomega.com/) 我先假如你用的 **chromium** 内核的浏览器(国内大部分都是这个内核的,你可以打开一个新`tab`然后输入`chrome://version`查看版本),打开: [switchyomega](https://switchyomega.com) 官网,然后去下载,这里有一个坑,就是`chrome`在新版本中无法使用拖拽`.ctx`的方法安装插件,你下载了,它只会是删除你的文件并且报个错误
![](https://i.loli.net/2019/02/08/5c5d5ffa75d65.png)
这个时候你有几种解决办法,前提是你下载了`.ctx`扩展文件

上面说了,你若在`chrome`里下载它只帮你把文件自动删除,那么你需要用别的下载软件,比如迅雷之类的(这个坑是初学者最大的坑.),你也可以使用`wget` | `curl`之类的下载

若是你小子无法下载,那么推荐你去国内镜像站: [chromefor](https://www.chromefor.com/proxy-switchyomega_v2-5-20/)

现在,假设你下载好了文件,那么可以干大事了

打开 `chrome://flags/#extensions-on-chrome-urls`，找到（ `Ctrl + F` ）**#extensions-on-chrome-urls** 那一选项，然后改为 Enable，重启以后可以在扩展程序页面拖进去一个 crx 扩展来安装。感谢原帖：[v2ex](https://www.v2ex.com/t/502181)

![](https://i.loli.net/2019/02/08/5c5d62267bbd3.png)
然后拖拽`.ctx`文件
![](https://i.loli.net/2019/02/08/5c5d642932fe5.gif)

你也可以将`.ctx`解压然后加载文件夹(我常用这种方式),首先你需要将其解压成文件夹,最好将文件夹摆放在你看不见的地方,不然强迫症难受啊,然后通过加载解压包的方式
![](https://i.loli.net/2019/02/08/5c5d660fc91da.gif)

现在你已经成功的安装了: `shadowsocks` + `switchyomega`

首先打开你的`shadowsocks`,然后复制你找到的`ss`连接,然后就可以漫游了(这个真没什么好说的,自己玩着先)

关于`SwitchyOmega`的使用也很简单,直接新建一个`new preofile`
然后在`Protocol`上选择: `socks5`,而`server`上: `127.0.0.1`,在端口`port`上: `1080`,行吧,ojbk,高阶用法后面会讲到

### 进阶
你可能有点懵,为什么要下载这两个东西和我要干什么,我在那,我是谁.

让你先入为主是有道理的,就像任何东西,你先尝试了,你才知道(比如闹心的谈恋爱.)

(我到哪里去找`ss`和`ssr`账号之类的话,先别吐槽,往后看)

相信你也感受到自由的味道♐️ 但白嫖是不存在,除非你来一波PY交易,所以建议大家就去看看别人家的**机场**(我就不推荐了,搜索关键词: `ss 机场`),里面基本有教程,自行去查吧

一些白嫖账号汇聚地:
- https://tool.ssrshare.us/tool/free_ssr :< 经常被墙.你自己注意收藏镜像站
- https://ssfree.blog/ :( 同上,容易墙
- https://free-ss.site/ :< 非常好用,已被墙,自行翻墙之后访问

(可能你没有看到我写服务器配置搭建那些乱七八糟的,我只能说,自行`baidu`+`google`)

### 高阶
恭喜你获得称号: **老司机**
![](https://i.loli.net/2019/01/01/5c2a446be6036.png)

若你是一个`cli`爱好者,你可以使用`bin/ssr`
```bash
  # 下载文件
  wget -O /usr/local/bin/ssr https://raw.githubusercontent.com/d1y/freedom/master/bin/ssr
  # 基于权限
  sudo chmod 775 /usr/local/bin/ssr
  # 安装
  ssr install
  # 配置文件在 /usr/local/share/shadowsocksr/config.json
```
现在配合: [`ss`转`json`](http://es6.top/ssr2json/),将`ss`链接转为`json`
然后将配置文件写入: `/usr/local/share/shadowsocksr/config.json`

启动: `ssr start`,具体配置见: `ssr help`

在`/shell`目录下有两个文件,分别是`ssr`安装脚本和`bbr`加速脚本
```bash
  # 给予权限
  chmod u+x shell/*
  ./ssr.sh
  ./bbr.sh
```

总有那么一个需求: 命令行过代理,这我使用的是: [proxychains](https://github.com/rofl0r/proxychains-ng)
```bash
  # 包管理安装
  brew install proxychains
  sudo apt install proxychains
  # 自行编译(git + gcc)
  git clone https://github.com/rofl0r/proxychains-ng
  cd proxychains-ng
  # prefix=安装路径 sysconfdir=配置文件路径
  ./configure --prefix=/usr --sysconfdir=/etc
  make
  (sudo) make install
  (sudo) make install-config
```
安装好了之后,取决于你的配置文件路径,打开你的配置文件
```bash
  # 默认在 /etc/proxychains.conf
  # 在文件的最后头添加代理设置,并且注释掉 socks4
  socks5 127.0.0.1 1080
```
使用很简单
```bash
  # 你可以测试一个是否成功了
  proxychains curl ip.sb

  # 在你需要使用的命令前面添加
  proxychains you-get https://youtube.com....

  # 或者你可以代理整个终端
  proxychains zsh # bash

```

你可以免费的搭建(抓包获取)这些

- [Heroku平台](docs/heroku-shadowsocks.md)
- [Google镜像站](docs/google-mirror.md)
- [Chrome插件白嫖法](docs/chrome-ex)

![](https://files.catbox.moe/plt9wt.svg)

**如果你实在找不到,请给我发♂♂邮件**
## Donate
我也是一个普通人,如果你觉得我切实帮助到你,你可以选择请我喝一杯咖啡☕️ , Thank you!
![](https://i.loli.net/2019/02/08/5c5d51447f869.jpg)
