# cover-view scroll & zIndex:


## zIndex:
> 这个是不能控制 cover-view 的层级的； 如果需要控制，利用加载顺序的方式去控制。

## 如果有 scroll 的情况：
> scroll 的组件永远在最底层（最后加载进去），尝试过动态设置 `overflow-y: scroll` 的方案，但发现小程序现在的处理方式，还是把这个层级调到最底层。

## 示例代码如下：
```html
<tu-cover-backdrop className="fixed z1" bindtap="onTap" wx:if="{{ msgListVisible }}"/>
<cover-view class="fixed z2 b0 bs-b w100 z1 tu-service-bar">
  <cover-image mode="aspectFit" class="z1 abs trbl0" src="https://i.stack.imgur.com/G3jOw.png"/>
  <cover-view class="rel z2 px14 pt14 row row-center body">
    <button class="btn-reset col-50 action service left" bindtap="service">
      <cover-image src="{{iconService}}"/>
    </button>
    <cover-view class="right row row-justify-end">
      <cover-view wx:if="{{ !model.is_selected}}" bindtap="select" hover-class="is-active" class="action star">
        <cover-image src="{{iconCollect}}"/>
      </cover-view>
      <cover-view wx:else bindtap="unselect" class="unstar">
        <cover-image src="{{iconCollected}}"/>
      </cover-view>
      <button open-type="share" hover-class="is-active" class="btn-reset action share">
        <cover-image src="{{iconShare}}"/>
      </button>
    </cover-view>
  </cover-view>
</cover-view>

<tu-service-message-list class="z3" bindclose="onClose" items="{{ serviceItems }}" wx:if="{{ msgListVisible }}"/>
```


## 截图如下：
<img width="500" src=""/>
<img width="500" src=""/>