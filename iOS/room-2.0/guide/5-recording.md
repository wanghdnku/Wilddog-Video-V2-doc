title: 视频录制
---

WilddogRom SDK 提供服务端视频录制功能。使用视频录制 API 保存通话内容为 `.mp4` 格式文件。

## 开始视频录制
使用 `-[WDGRoom startRecording]` 方法开启视频录制：

```objectivec
[self.room startRecording]
```

## 结束视频录制
使用 `-[WDGRoom stopRecording]` 方法结束视频录制：

```objectivec
[self.room stopRecording]
```
