# audio
> audio/voice音频相关的行为调研。


## audio/voice音频相关的行为调研
+ 直接调用网页里的 audio，而不用 `playVoice`的 API 的情况
  - 1.使用：https://music.163.com/#/song?id=25706282
  - 2. 结论：可以播放，但并不知道在哪里播放，需要找到小程序
  - 3. 延展：如果采用此方案，需要调继续研究 audio 的定制方案(这里有第三方的，需要再做测试)
+ 使用 `playVoice` 的API的情况(这块需要slu在报告页面做对应的script代码处理，检测到 tu-audio，然后写script来playVoice)
  - 发现播放本地文件的思路是走不通的
  - 如果可能，期待以后操作 audio 相关的API
+ 使用 `startRecord/stopRecord/playVoice` 来操作录音，播放录音文件
  - 发现这块需要走公众号SDK的集成过程，需要后端配合
  - 而且，这块的走的是录音，而不是线上的mp3/wmv文件


## 关于 webview 能否播放 mp3等音频，退出后的支持情况
- 网易云音乐，退出后可以播放，但没有进度条
- 原生的 audio可以播放，也没有进度条
- QQ音乐同样的情况
- 微信公众号文章可以播放，退出也有进度条

## 微信公众号为什么可以播放
- 真实的播放是用 audio 
- 但还有一个 mpvoice 标签
- 经调研究： mpvoice 是特供标签，底层是 iframe, 真正播放的还是 audio。没有对应，暂时走不通