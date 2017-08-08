title: 媒体流统计
---

本篇文档介绍如何获取本地视频流和远端视频流的统计数据。


### 设置代理

使用 `WDGConversation` 中的 `statsDelegate` 属性可以实时获取视频的宽、高、帧率、发送接收总大小、比特率、延迟等。

```objectivec
// VideoConversation 是邀请成功或者接受邀请成功时返回的参数。
self.videoConversation.statsDelegate = self;
```

### 统计本地视频数据

实现本地视频数据统计接口。

```objectivec
- (void)conversation:(WDGVideoConversation *)conversation didUpdateLocalStreamStatsReport:(WDGVideoLocalStreamStatsReport *)report {
    // report.width
    // report.height
    // report.FPS
    // report.bytesSent
    // report.bitsSentRate
}
```

### 统计远程视频数据

实现远程视频数据统计接口。

```objectivec
- (void)conversation:(WDGVideoConversation *)conversation didUpdateRemoteStreamStatsReport:(WDGVideoRemoteStreamStatsReport *)report {
    // report.width
    // report.height
    // report.FPS
    // report.bytesReceived
    // report.bitsReceivedRate
    // report.delay
}
```
