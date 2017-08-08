title: WDGVideoDelegate
---

[WDGVideo](url_placeholder) 的代理方法。

## 方法

### - wilddogVideo: didReceiveCallWithConversation: data:

**定义**

```objectivec
- (void)wilddogVideo:(WDGVideo *)video didReceiveCallWithConversation:(WDGConversation *)conversation data:(NSString * _Nullable)data;
```

**说明**

`WDGVideo` 通过调用该方法通知当前用户收到新的视频通话邀请。

**参数**

 参数名 | 说明 
---|---
video | 调用该方法的 `WDGVideo` 实例。
conversation | 代表收到的视频通话的 `WDGConversation` 实例。
data | 随通话邀请传递的 `NSString` 类型的数据。

</br>

---

### - wilddogVideo: didFailWithTokenError:

**定义**

```objectivec
- (void)wilddogVideo:(WDGVideo *)video didFailWithTokenError:(NSError * _Nullable)error;
```

**说明**

`WDGVideo` 通过调用该方法通知当前用户配置 `WDGVideo` 时发生 token 错误。

**参数**

 参数名 | 说明 
---|---
video | 调用该方法的 `WDGVideo` 实例。
error | 错误信息。
