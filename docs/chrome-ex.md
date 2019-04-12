> 如果可以的话,希望大家不要用这种卑劣的方法,尊重正版 )滑稽保命

# chrome-extensions 常见`vpn`破解思路

`chrome`商店里有很多`vpn`,你可以自行利用技术手段来得到其免费账号♂

给大家提供思路,首先寻找一个vpn插件
![](https://i.loli.net/2019/02/08/5c5d7896641a3.png)
哟呵,看到第一个没,用户最多,肯定好用点击进去,复制链接中的`id`,然后寻找国内的商店镜像站下载了(或者你经过下载之后,然后找到chrome扩展的路径然后对照`id`然后用编辑器打开分析源码)
![](https://i.loli.net/2019/02/08/5c5d790508264.png)
假如你经过乱七八糟的工序下载好了,然后我们直接解压插件,然后分析代码(分析源码要有基础,有能力自行去啃源码: <https://github.com/sxei/chrome-plugin-demo>)

      unzip vpn.ctx
      atom .

打开它的`manifest.json`观察一下:

```json
{
   "background": {
      "scripts": [ "/js/jquery.min.js", "/js/analytics.js", "/js/storage.js", "/js/app.js", "/js/chrome.js" ]
   },
   "browser_action": {
      "default_icon": "img/32.png",
      "default_popup": "/popup.html",
      "default_title": "__MSG_title__"
   },
   "content_scripts": [ {
      "all_frames": true,
      "js": [ "/js/stat.js" ],
      "matches": [ "*://*/*" ]
   } ]
}
```

去观察`js`,发现前面几个都是依赖,只有这个`app.js`看着可疑,那么我打开看看,相信你看的都是压缩过的内容,别担心,自行百度搜索美化js的,我们继续观察:

```javascript
const c = 'id=' + encodeURIComponent(chrome.runtime.id) + '&t=' + encodeURIComponent(new Date().getTime()) + '&mt=' + encodeURIComponent(this.storage.mTime) + '&lt=' + encodeURIComponent(this.storage.lTime) + (this.storage.vpnOnlyMode || this.vpnOnlyMode ? '&vpn=1' : '') + '&uid=' + encodeURIComponent(this.uid) + '&hash=' + this.storage.hash,
      d = localStorage.devConfigUrl,
      e = d ? d : 'https://pac.safe-proxy.com/config5.php?' + c;
    $.ajax({
    })
```

看到了吗?一眼都看到了哦,下面是`jquery`的`ajax`方法,我们把链接复制,直接打开
```json
"domains": [],
    "proxyList": [],
    "mode": "vpn",
    "locations": [
        {
            "country_code": "AD",
            "country_name": "Andorra",
            "nodes": [
                {
                    "schema": "HTTPS",
                    "ip": "91.187.93.166",
                    "port": "80"
                }
            ]
        }]
```
成功,直接拿到了代理接口,然后我们就可以配合`switchyomega`使用了,是不是非常简单呢?就是这么简单,大家也可以试试其他的插件,用观察源码的方式来实验

谢谢大家.

20190208 by @d1y

**更新于2019/04/12**

# 插件推荐
上面介绍了一些简单破解的一些方法和思路,然而在`chrome`插件里还有有一些免费良心的`vpn`插件,速度也还行,在这里推荐给大家(自用的)
- [Browsec VPN ](https://browsec.com/) :: 速度一般,但免费,貌似有几个节点选哈
- [谷歌访问助手(破解版)](https://github.com/haotian-wang/google-access-helper.git) :: 这货免费,但是强制给你设定流氓主页,贴了一个破解版给大家.提一下,它只支持访问访问`google`官方+商店+`Gmail`
- [skyZIP™ Proxy](https://chrome.google.com/webstore/detail/skyzip-proxy/hbgknjagaclofapkgkeapamhmglnbphi) :: 我觉得还行,免费
- [uVpn](https://chrome.google.com/webstore/detail/uvpn-free-and-unlimited-v/coahpcpgfnnaddeelpphpifmgfobflog) :: 能用，但是很慢，基本刷不出视频，看视频只能看看下面的评论，其他的需要的时间太长，不建议下载
- 还有很多可以♂白嫖♂的,自行搜索呗
