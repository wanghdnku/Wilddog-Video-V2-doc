title: WDGRemoteStream
---

表示通过 [WDGConversation](url_placeholder) 传来的远端音频和视频流。

## 属性

### videoEnabled

**定义**

```objectivec
@property (nonatomic, assign) BOOL videoEnabled;
```

**说明**

代表流中的视频是否开启。

</br>

---

### audioEnabled

**定义**

```objectivec
@property (nonatomic, assign) BOOL audioEnabled;
```

**说明**

代表流中的音频是否开启。

</br>

---

## 方法

### - close

**定义**

```objectivec
- (void)close;
```

**说明**

关闭当前流，当前流被关闭后不能继续使用。

</br>

---

### - attach:

**定义**

```objectivec
- (void)attach:(WDGVideoView *)view;
```

**说明**

绑定流与视图，使当前流在指定的 `WDGVideoView` 中显示。

**参数**

 参数名 | 说明 
---|---
view | `WDGVideoView` 实例，流在该视图中展示。

</br>

---

### - detach:

**定义**

```objectivec
- (void)detach:(WDGVideoView *)view;
```

**说明**

解除当前流与指定的 `WDGVideoView` 的绑定。

**参数**

 参数名 | 说明 
---|---
view | `WDGVideoView` 实例，流在该视图中展示。
