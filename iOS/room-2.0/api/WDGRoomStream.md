title: WDGRoomStream
---

表示房间中的远端媒体流。

## 属性

### streamId

**定义**

```objectivec
@property (nonatomic, retain) NSNumber *streamId;
```

**说明**

代表一个远端流的唯一标识，由服务器分配。

</br>

---

### isMixed

**定义**

```objectivec
@property (nonatomic, assign) BOOL isMixed;
```

**说明**

布尔类型，若为 YES 表示该远端流经过了 MCU 混流处理，若为 NO 表示该远端流经过 SFU 转发。

</br>

---

### streamOwners

**定义**

```objectivec
@property (nonatomic, strong) NSArray *streamOwners;
```

**说明**

数组类型，包含了远端媒体流的参与者。

</br>

---

### delegate

**定义**

```objectivec
@property (nonatomic, weak) id<WDGRoomStreamDelegate> delegate;
```

**说明**

符合 `WDGRoomStreamDelegate` 协议的代理，用于接收房间中远端媒体流的变化。

</br>

---
