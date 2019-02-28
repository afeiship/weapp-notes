# setData Callback bug:


## code:

```html
<tu-service-message-list class="z3" bindclose="onClose" items="{{ serviceItems }}" wx:if="{{ msgListVisible }}"/>
<cover-view class="fixed b0 bs-b w100 z1 tu-service-bar">
  <cover-image mode="aspectFit" class="z1 abs trbl0" src="https://i.stack.imgur.com/G3jOw.png"/>
  <cover-view class="rel z2 px14 pt14 row row-center body">
    <button class="btn-reset col-50 action service left" bindtap="service">
      <cover-image src="https://image-static.segmentfault.com/199/432/1994323560-5c77bd6217042_articlex"/>
    </button>
    <cover-view class="right row row-justify-end">
      <cover-view wx:if="{{ !model.is_selected}}" bindtap="select" hover-class="is-active" class="action star">
        <cover-image src="https://image-static.segmentfault.com/144/415/1444150144-5c77b41cee14c_articlex"/>
      </cover-view>
      <cover-view wx:else bindtap="unselect" class="unstar">
        <cover-image src="https://image-static.segmentfault.com/307/966/3079668078-5c77c278d8679_articlex"/>
      </cover-view>
      <button open-type="share" hover-class="is-active" class="btn-reset action share">
        <cover-image src="https://image-static.segmentfault.com/189/820/1898203220-5c77bda3df69c_articlex"/>
      </button>
    </cover-view>
  </cover-view>
</cover-view>
```

```js
service() {
      // delay click for cover-view:
    $interaction.loading(true, { title: '加载中' });
    $api.ext_info_desc().then(({ found, info }) => {
    this.setData({ found, info }, () => {
        // todo: 这里如果用回调，会出问题：
        // $interaction.loading(true, {
        //   title: '你的回调里如果是异步，在 IOS 上永远不执行； 同步可以执行'
        // });
    });
    this.selectAction(found);
    });
},
```