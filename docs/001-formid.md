# formid:
> 小程序通知原理

## code:
```html
<form style="display: none" report-submit="true" @submit="onSubmitTest">
    <button form-type="submit">获取formid test</button>
</form>
```

```js
onSubmitTest(inEvent) {
    console.log('collect formid:->', inEvent.target)
},
```

## 注意点：
- formid 只能使用一次，对应 openid
- 点多次收集多次