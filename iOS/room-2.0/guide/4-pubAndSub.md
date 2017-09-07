title: 发布和订阅
---

本篇文档介绍如何将本地的媒体流发布到视频会议的房间中。


## 发布本地流

在创建了本地媒体流之后，客户端需要将本地的媒体流发送到房间中，以供视频会议的其他用户订阅：

```objectivec
[self.room publishLocalStream:self.localStream withCompletionBlock:^(NSError * _Nullable error) {
    // 在发布完成后执行该 Block
}];
```


## 订阅远端流

在新加入一个视频会议，或者视频会议进行中有其他用户加入时，[WDGRoom](placeholder) 的代理会通过 `-[WDGRoomDelegate wilddogRoom:didStreamAdded:]` 回调方法来通知客户端有远端媒体流可以订阅：

```objectivec
- (void)wilddogRoom:(WDGRoom *)wilddogRoom didStreamAdded:(WDGRoomStream *)roomStream {
    // 获取该视频流信息，决定是否订阅
}

此时的远端媒体流只包含了描述信息，要想获取和预览该远端流的媒体信息，必须订阅该媒体流：

```objectivec
[self.room subscribeRoomStream:roomStream withCompletionBlock:^(NSError * _Nullable error) {
    // 在订阅完成后执行该 Block
}];
```

订阅成功后，[WDGRoom](placeholder) 的代理会通过 `-[WDGRoomDelegate wilddogRoom:didStreamReceived:]` 回调方法来将媒体信息发送给客户端，客户端此时可以预览该媒体流：

```objectivec
- (void)wilddogRoom:(WDGRoom *)wilddogRoom didStreamReceived:(WDGRoomStream *)roomStream {
    // 展示收到的媒体流
}
```


## 取消发布／订阅

不需要发布或者订阅媒体流时，客户端可以向服务器发送信息以停止发布或订阅：

```objectivec
[self.room unpublishLocalStream:self.localStream withCompletionBlock:^(NSError * _Nullable error) {
    // 完成后执行该 Block
}];

[self.room unsubscribeRoomStream:roomStream withCompletionBlock:^(NSError * _Nullable error) {
    // 完成后执行该 Block
}];
```

