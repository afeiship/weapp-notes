# webview:

## cover-view 覆盖
~~~
有效果
~~~


## webview 与 cover-view 调研究结果：
+ webview 加载网页分两种情况 A、B(B1/B2)：
    - A：加载自己域名的网页，配置好业务域名后，可正常加载
    - B1：订阅号文章，配置好之后(没配过，但肯定可以，应该打勾就行)，可以正常加载 
    - B2: 如果未配置好，在 webview 的 title 上会显示 ”验证“，并且页面是空白
+ webview 加载后会自动全屏，可以用 cover-view 覆盖
    - IOS 正常写样式 （测试过，可以）
    - Android 需要配合 setTimeout 加载，还需要测试 （还未测试）
+ webview 里的 cover-view 不可以放 input 框（测试过，确实不行）
    - cover-view 没有 webview 的时候，加入 input框也直接过滤掉了
    - 有 webview 也不会显示 input

## 参考：
- https://imweb.io/topic/5c0aa26f611a25cc7bf1d7ea
- https://www.jianshu.com/p/d3edf5fa51cb
- https://developers.weixin.qq.com/miniprogram/dev/component/cover-view.html
- https://developers.weixin.qq.com/miniprogram/dev/component/web-view.html

## 验证结果截图：
<img width="320" src="https://ws3.sinaimg.cn/large/006tKfTcly1g0crmtpwo3j30hs0vkmxg.jpg" />


## resouces:
- https://www.cnblogs.com/kevinCoder/p/9155361.html
- https://imweb.io/topic/5c0aa26f611a25cc7bf1d7ea