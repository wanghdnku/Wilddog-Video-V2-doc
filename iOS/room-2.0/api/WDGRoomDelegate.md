title: WDGRoomDelegate
---

`WDGRoom` 的代理方法，用于通知房间相关的事件。

## 方法

### - wilddogRoomDidConnect:

**定义**

```objectivec
- (void)wilddogRoomDidConnect:(WDGRoom *)wilddogRoom;
```

**说明**

`WDGRoom` 通过调用该方法通知代理房间已成功连接。

**参数**

参数名             | 说明 
------------------|------------------
wilddogRoom       | 调用该方法的 `WDGRoom` 实例。

---

### - wilddogRoomDidDisconnect:

**定义**

```objectivec
- (void)wilddogRoomDidDisconnect:(WDGRoom *)wilddogRoom;
```

**说明**

WDGRoom` 通过调用该方法通知代理房间已断开连接。

**参数**

参数名             | 说明 
------------------|------------------
wilddogRoom       | 调用该方法的 `WDGRoom` 实例。

---

### - wilddogRoom: didStreamAdded: 

**定义**

```objectivec
- (void)wilddogRoom:(WDGRoom *)wilddogRoom didStreamAdded:(WDGRoomStream *)roomStream;
```

**说明**

`WDGRoom` 通过调用该方法通知代理房间中有远端媒体流加入。

**参数**

参数名             | 说明 
------------------|------------------
wilddogRoom       | 调用该方法的 `WDGRoom` 实例。
roomStream        | 加入房间的远端媒体流，只包含描述流的基本信息，不包含媒体数据。

---

### - wilddogRoom: didStreamChanged: 

**定义**

```objectivec
- (void)wilddogRoom:(WDGRoom *)wilddogRoom didStreamChanged:(WDGRoomStream *)roomStream;
```

**说明**

`WDGRoom` 通过调用该方法通知代理房间中有远端媒体流发生改变。

**参数**

参数名             | 说明 
------------------|------------------
wilddogRoom       | 调用该方法的 `WDGRoom` 实例。
roomStream        | 房间中发生变化的远端媒体流，只包含描述流的基本信息，不包含媒体数据。

---

### - wilddogRoom: didStreamRemoved:

**定义**

```objectivec
- (void)wilddogRoom:(WDGRoom *)wilddogRoom didStreamRemoved:(WDGRoomStream *)roomStream;
```

**说明**

`WDGRoom` 通过调用该方法通知代理房间中有远端流断开。

**参数**

参数名             | 说明 
------------------|------------------
wilddogRoom       | 调用该方法的 `WDGRoom` 实例。
roomStream        | 房间中断开的远端媒体流，只包含描述流的基本信息，不包含媒体数据。

---

### - wilddogRoom: didStreamReceived:

**定义**

```objectivec
- (void)wilddogRoom:(WDGRoom *)wilddogRoom didStreamReceived:(WDGRoomStream *)roomStream;
```

**说明**

`WDGRoom` 通过调用该方法通知代理收到远端媒体流数据。

**参数**

参数名             | 说明 
------------------|------------------
wilddogRoom       | 调用该方法的 `WDGRoom` 实例。
roomStream        | 房间中断开的远端媒体流，包含了媒体数据。

---

### - wilddogRoom: didFailWithError:

**定义**

```objectivec
- (void)wilddogRoom:(WDGRoom *)wilddogRoom didFailWithError:(NSError *)error;
```

**说明**

`WDGRoom` 通过调用该方法通知代理发生错误。

**参数**

参数名             | 说明 
------------------|------------------
wilddogRoom       | 调用该方法的 `WDGRoom` 实例。
error             | 错误信息，可通过错误码区分错误类型。

---