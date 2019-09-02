# cover-view-bugs


## resources
1. https://www.jianshu.com/p/50fcac41e9d5
2. https://developers.weixin.qq.com/community/develop/doc/000aa4b2820df84320c8bb3f956400


## bugs
1. 文字换行需要手动设置
   ```css
   word-break: break-all;
   word-wrap: break-word;
   ```
2. cover-view 在ios上的设置border-radius渲染错误
   ~~~
   用图代替
   ~~~
3. 滚动的 cover-view 并没有  scroll 事件，所以，需要用点击的方式做“加载更多”功能
4. cover-view 有 scroll 的情况下，他的层级会变得很低；如果要做一个 overlay 就可以用 cover-image(src弄个 PNG 半透的图图即可) 模拟