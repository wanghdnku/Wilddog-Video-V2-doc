title: 房间
---

本篇文档介绍如何创建或加入视频会议。

Room 表示一个多人的视频会话。多个用户可以加入同一个 Room 进行音视频通话。


## 加入 Room

WilddogRoom 通过用房间的概念来指代一次视频会议，一个房间中包含了参与视频会议的各方发送到服务器的媒体流。每个房间有一个 roomId 作为唯一标识。

[WDGRoom](placeholder) 是视频会议的主入口。建立视频会议的时候，需要使用 roomId 来初始化 [WDGRoom](placeholder) 实例。如果指定的 roomId 已经存在，则加入该视频会议；若果 roomId 不存在，则使用这个 roomId 创建新的会议：

```objectivec
WDGRoom *room = [[WDGRoom alloc] initWithRoomId:@"your-roomId"];
```

建立房间后，需要调用 `-[WDGRoom connect]` 方法开启网络连接：

```objectivec
[room connect];
```

## 离开 Room

要结束视频会议，需要调用 `-[WDGRoom disconnect]` 方法断开链接：

```objectivec
[room disconnect];
```


## 处理 Room 事件

设置 [WDGRoom](placeholder) 的代理 <[WDGRoomDelegate](placeholder)> 用于处理 Room 的事件：

```objectivec
room.delegate = self;
```

### 1. 连接事件

实现代理方法 `-[WDGRoomDelegate wilddogRoomDidConnect:]`，当客户端与服务器成功连接时，会触发该方法：

```objectivec
- (void)wilddogRoomDidConnect:(WDGRoom *)wilddogRoom {
    // 已成功连接
}
```

实现代理方法 `-[WDGRoomDelegate wilddogRoomDidDisconnect:]`，当客户端与服务器断开连接时，会触发该方法：

```objectivec
- (void)wilddogRoomDidDisconnect:(WDGRoom *)wilddogRoom {
    // 已断开链接，可以释放资源
}
```

### 2. 媒体流通知事件

实现代理方法 `-[WDGRoomDelegate wilddogRoom:didStreamAdded:]`，当房间中有远端媒体流加入时，会触发该方法：

```objectivec
- (void)wilddogRoom:(WDGRoom *)wilddogRoom didStreamAdded:(WDGRoomStream *)roomStream {
    // 获取该视频流信息，决定是否订阅
}
```

实现代理方法 `-[WDGRoomDelegate wilddogRoom:didStreamChanged:]`，当房间中有远端媒体流发生改变时，会触发该方法：

```objectivec
- (void)wilddogRoom:(WDGRoom *)wilddogRoom didStreamChanged:(WDGRoomStream *)roomStream {
    // 获取发生改变的媒体流的信息，决定执行何种操作
}
```

实现代理方法 `-[WDGRoomDelegate wilddogRoom:didStreamRemoved:]`，当房间中有远端媒体流断开时，会触发该方法：

```objectivec
- (void)wilddogRoom:(WDGRoom *)wilddogRoom didStreamRemoved:(WDGRoomStream *)roomStream {
    // 不再显示该视频流
}
```

### 3. 媒体流接收事件

实现代理方法 `-[WDGRoomDelegate wilddogRoom:didStreamReceived:]`，当收到远端流的媒体数据时，会触发该方法：

```objectivec
- (void)wilddogRoom:(WDGRoom *)wilddogRoom didStreamReceived:(WDGRoomStream *)roomStream {
    // 展示收到的媒体流
}
```

### 4. 错误事件

实现代理方法 `-[WDGRoomDelegate wilddogRoom:didFailWithError:]`，当视频会议发生错误时，会触发该方法：

```objectivec
- (void)wilddogRoom:(WDGRoom *)wilddogRoom didFailWithError:(NSError *)error {
    // 处理错误
}

```
