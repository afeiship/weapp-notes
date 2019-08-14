# max-size
> 微信小程序:VM6260:1 vdSyncBatch 数据传输长度为 1623104 已经超过最大长度 1048576

~~~
setData 单次设置的数据不能超过1024kB，请尽量避免一次设置过多的数据。
~~~

## resources
- https://blog.csdn.net/laishaojiang/article/details/83619998


## 实际的情况
1. 本身这个场景问题并不大，而且数据量也并不多
2. 前面一个页面是详情页： detail，然后，回到首页 switchTab
3. 发现这个时间点，详情页的内容 hold 在内存里，detail 组件内部的hide，并没有被释放掉 hide 的事件并没有被执行
```js
// old 
this.context.setData({
  dataSource: response.items,
  pagination: this.loader.pagination,
  topItems: response.topItems
});


// now:
nx.ConsoleTime.time('renderPagination');
const target = {
  dataSource: response.items,
  pagination: this.loader.pagination,
  topItems: response.topItems
};
nx.forIn(target, (key, value) => {
  wx.nextTick(() => {
    console.log('set key', key);
    this.context.setData({
      [key]: value
    });
  });
});
nx.ConsoleTime.timeEnd('renderPagination');
```