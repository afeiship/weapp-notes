# event-capth:
> https://blog.csdn.net/qq_36002582/article/details/78755427

## code:
> 阻止冒泡事件的发生，其实很简单，直接把bindtap改为catchtap

```html
<view class='redview' bindtap='redclick'>
  红色
  <view class='yellowview' bindtap='yellowclick'>
    黄色
    <view class='blueview' catchtap='blueclick'>
      蓝色
    </view>
  </view>
</view>
```