# tobe resolved problems:

## 1. 小程序组件中的样式调用问题
> 在 page 中可以用样式对组件，以及组件内部的样式进行控制，但如果组件 A 引用组件 B，则这种情况则不生效
```html
<compa className="cls1"/>
```
<!-- 代码片段如下： -->
- https://developers.weixin.qq.com/s/7AnW7FmC7J64

## 2. 小程序在列表页点收藏/详情页
1. 详情页点收藏
2. 返回到列表页，列表页刷新某一项，但不要刷新列表

## 3. 小程序定制 header/navigator 自己控制导航栏的样式
- 分享时：显示 home
- 正常时候：显示 back + home

## 4.小程序 wxs filters 的功能