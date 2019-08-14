# bg-audio
- https://developers.weixin.qq.com/miniprogram/dev/api/media/background-audio/BackgroundAudioManager.html


## keng
1. 音频设置好 src 等属性之后，会自动播放
2. title 属性必须设置，否则会报错
3. 刚开始不自动播放，可以设置：src=null
4. play方法重构为：
    ```js
    play() {
      const { model } = this.data;
      if (this.ctx.src) {
        this.ctx.play();
      } else {
        this.ctx.src = model.media_url;
      }
    },
    ```