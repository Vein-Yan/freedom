# runkit
使用[runkit](https://runkit.com)来搭建`google`镜像站,首先打开[runkit](https://runkit.com),创建一个账号,新建一个项目
![](https://i.loli.net/2019/02/08/5c5d756b78e12.png)
填入:
```javascript
var express = require('express');
var proxy = require('http-proxy-middleware');
var app = express();
app.all('*', function(req, res, next) {
    res.header("Access-Control-Allow-Origin", "*");
    res.header("Access-Control-Allow-Headers", "X-Requested-With");
    res.header("Access-Control-Allow-Methods","PUT,POST,GET,DELETE,OPTIONS");
    res.header("X-Powered-By",' 3.2.1')
    res.header("Content-Type", "application/json;charset=utf-8");
    next();
});
app.use('/',proxy({
  target: 'https://google.com',
  changeOrigin: true
}));
app.listen(3000);

```
点击之后有个链接,over,可以了,你现在可以自由的畅游了
![](https://i.loli.net/2019/02/08/5c5d7609416a5.png)
理论上大部分网站都可以,只需要你把`target`修改为你需要的网站就行


** 那么是否想到了`now.sh` | `heroku` 都可以这么干? ** 同样思路,大家自己玩玩,我就不写了,不然就是侮辱大家智商了
