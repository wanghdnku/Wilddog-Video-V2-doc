title: WDGConversation
---

表示用户参与的视频通话，同一时间只能参与一个视频通话。

## 属性

### remoteUid

**定义**

```objectivec
@property (nonatomic, strong) NSString *remoteUid;
```

**说明**

表示视频通话对方的 User ID。

</br>

---

### delegate

**定义**

```objectivec
@property (nonatomic, weak) id<WDGConversationDelegate> delegate;
```

**说明**

符合 `WDGConversationDelegate` 协议的代理，用于通知 `WDGConversation` 发生的事件。

</br>

---

### statsDelegate

**定义**

```objectivec
@property (nonatomic, weak, nullable) id<WDGConversationStatsDelegate> statsDelegate;
```

**说明**

符合 `WDGConversationStatsDelegate` 协议的代理。用于获取视频流的统计数据。

</br>

---

## 方法

### - acceptWithLocalStream:

**定义**

```objectivec
- (void)acceptWithLocalStream:(WDGLocalStream *)localStream;
```

**说明**

接受对方的视频通话请求，并上传自己的本地媒体流。

**参数**

参数名 | 说明 
---|---
localStream | `WDGLocalStream` 实例，表示本地媒体流。

</br>

---

### - reject

**定义**

```objectivec
- (void)reject;
```

**说明**

拒绝视频通话邀请。

</br>

---

### - close

**定义**

```objectivec
- (void)close;
```

**说明**

关闭当前视频通话。

</br>

---

### - startLocalRecording:

**定义**

```objectivec
- (BOOL)startLocalRecording:(NSString *)filePath;
```

**说明**

开始录制视频并保存到本地filePath目录下。

**参数**

参数名 | 说明 
---|---
filePath | 视频文件保存路径。

**返回值**

视频录制是否成功开启。

### -stopLocalRecording

**定义**

```objectivec
- (BOOL)stopLocalRecording;
```

**说明**

停止录制视频。

**返回值**

视频录制是否成功关闭。

</br>

---

## 常量

### WDGCallStatus 

**定义**

```objectivec
typedef NS_ENUM(NSUInteger, WDGCallStatus) {
    WDGCallStatusAccepted,
    WDGCallStatusRejected,
    WDGCallStatusBusy,
    WDGCallStatusTimeout
};
```

**说明**

表示视频通话或会议的连接状态。

- WDGCallStatusAccepted: 表示视频通话邀请被接受。
- WDGCallStatusRejected: 表示视频通话邀请被拒绝。
- WDGCallStatusBusy: 表示视频通话被关闭。
- WDGCallStatusTimeout: 表示视频通话请求等待超时。

</br>

---
