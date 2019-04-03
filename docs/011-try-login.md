# try login
> 小程序登录的时候 token ，分享时， token 同步问题。

## tryLogin:
~~~
直接加个方法，tryLogin
里面的逻辑是：
1. 检测是否有token
2. 有，直接返回 promise
3. 没有，login 之后，再返回 promise
所有的页面ready 用这个 tryLogin包一层。
~~~

## monitor
~~~
~~~

## redirect page
~~~
## URL定义为：
/pages/redirect/index?url=cGFnZXMvaW5kZXgvaW5kZXg/dGFiPTEyMw

如：页面为：pages/index/index?id=1

## 分享的URL为：
则后端给前端的URL为：/pages/redirect/index?redirect_url=${base64.encode('pages/index/index?id=1')}

## 前端接收到处理：
const redirect_url = base64.decode(params.redirect_url);
$route.go(redirect_url);
~~~

## 类似于 domReady，实现一个 appReady
```js
// 这个需要根据业务实现
import { $api, $auth } from '#';

function appReady(inCallback){
    const token = $auto.getToken();
    if(!token){
        $api.get_token().then(response=>{
            $auto.setToken(response);
            inCallback();
        })
    }else{
        inCallback();
    }
}

// 调用的地方：
appReady(()=>{
    // your logic
})
```
