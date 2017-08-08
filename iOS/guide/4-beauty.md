title: 美颜功能
---

本篇文档介绍如何处理本地视频流，用户可以调用第三方 SDK 来处理将要上传的本地媒体流。


### 获取原始视频流接口

设置 `WDGVideoLocalStream` 的 `delegate` 来获取本地视频流，可以对视频流做美颜处理再返回给野狗 SDK。

```objectivec
WDGVideoLocalStream *localStream = [[WDGVideoLocalStream alloc] initWithOptions:localStreamOptions];
localStream.delegate = self;

- (CVPixelBufferRef)processPixelBuffer:(CVPixelBufferRef)pixelBuffer {
    // 使用第三方 SDK 处理当前图片。
    return [BeautySDK process:pixelBuffer];
}
```
