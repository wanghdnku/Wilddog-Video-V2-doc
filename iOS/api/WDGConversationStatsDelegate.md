title: WDGConversationStatsDelegate
---

[WDGVideoConversation](url_placeholder) 的代理方法。用于获取视频流的统计数据。

## 方法

### - conversation: didUpdateLocalStreamStatsReport

**定义**

```objectivec
- (void)conversation:(WDGConversation *)conversation didUpdateLocalStreamStatsReport:(WDGLocalStreamStatsReport *)report;
```

**说明**

`WDGConversation` 通过调用该方法通知代理处理当前视频通话中本地视频流的统计信息。

**参数**

 参数名 | 说明 
---|---
conversation | 调用该方法的 `WDGConversation` 实例。
report | 包含统计信息的 `WDGLocalStreamStatsReport` 实例。

</br>

---

### - conversation: didUpdateRemoteStreamStatsReport

**定义**

```objectivec
- (void)conversation:(WDGConversation *)conversation didUpdateRemoteStreamStatsReport:(WDGRemoteStreamStatsReport *)report;
```

**说明**

`WDGConversation` 通过调用该方法通知代理处理当前视频通话中远程视频流的统计信息。

**参数**

 参数名 | 说明 
---|---
conversation | 调用该方法的 `WDGConversation` 实例。
report | 包含统计信息的 `WDGRemoteStreamStatsReport` 实例。

</br>

---