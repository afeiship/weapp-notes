# type-number-string:

## type: 
```html
<tu-shadow-box className="tu-media-card" bindtap="onItemTap">
  <block wx:if="{{ type == '1'}}"><tu-info-item-chart model="{{ model }}"/></block>
  <block wx:elif="{{ type == '2'}}"><tu-info-item-data model="{{ model }}" /></block>
  <block wx:elif="{{ type == '3'}}"><tu-info-item-article model="{{ model }}" /></block>
</tu-shadow-box>
```
1. 模拟器上： type === 1，显示正确
2. 真机上(iphoneSE) type === '1', 显示正确
3. 所以，这里只能用  type == '1'
