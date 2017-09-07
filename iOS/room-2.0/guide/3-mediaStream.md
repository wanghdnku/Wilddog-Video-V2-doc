title: 媒体流
---

本篇文档介绍视频会议中媒体流的概念，包含了本地媒体流和远端媒体流。


WilddogRoom 中使用 Stream 的概念来表示视频通话的参与者。每个参与者将自己的本地媒体流上传到服务器，同时从服务器获得其他参与者的媒体流。

在视频会议中，Stream 只包含了简单的流的描述信息，要获取到多媒体数据，需要订阅该媒体流。详情请阅读后面章节。

## 本地媒体流

### 1.创建本地流

本地媒体流包含了本地设备所采集的音频、视频信息，是视频会议所需要的基本数据。在加入视频会议之前，需要创建 [WDGLocalStream](placeholder) 实例：

```objectivec
WDGLocalStream *localStream = [[WDGLocalStream alloc] initWithOptions:options];
```

### 2.配置本地流

创建的时候，需要传入一个 [WDGLocalStreamOptions](/conversation/iOS/api/WDGLocalStreamOptions.html) 对象，这个参数确定了本地视频流的音频、视频开关、最大尺寸和最大帧率：
* shouldCaptureAudio / shouldCaptureVideo 为音／视频采集的开关，设置为 NO 表示关闭音／视频采集，默认为 YES；
* dimension 用来设置视频的最大尺寸，默认为 480p，如果网络条件较差，会自动降低尺寸大小；
* maxFPS 用来设置视频的最大帧率，默认为 16 帧／秒，如果网络条件较差，会自动降低帧率。

```objectivec
WDGLocalStreamOptions *localStreamOption = [[WDGLocalStreamOptions alloc] init];
localStreamOption.shouldCaptureAudio = YES;
localStreamOption.shouldCaptureVideo = YES;
localStreamOptions.dimension = WDGVideoDimensions720p;
localStreamOptions.maxFPS = 20;
```

### 3.预览本地流

媒体流包括音频流和视频流，音频流默认会自动播放，视频流需要使用 [WDGVideoView](/conversation/iOS/api/WDGVideoView.html) 来播放。

播放视频流：

```objectivec
[localStream attach:self.localVideoView];
```

停止播放视频流：

```objectivec
[localStream detach:self.localVideoView];
```


## 远端媒体流

远端媒体流需要从服务器获取。在视频会议中，远端媒体流有 MCU 和 SFU 两种模式。在 MCU 模式下，服务器会将收到的所有远端媒体流进行混流处理，并作为一个媒体流发给客户端。在 SFU 模式下，服务器将远端媒体流转发给客户端，客户端可能收到多个独立的媒体流。

