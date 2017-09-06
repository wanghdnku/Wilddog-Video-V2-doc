title: WDGRoom
---

`WDGRoom` 是视频会议的主入口，用于创建或加入房间，管理本地媒体流和远端媒体流。

## 属性

### roomId

**定义**

```objectivec
@property (nonatomic, strong) NSString *roomId;
```

**说明**

代表一个房间的唯一标识。

</br>

---

### delegate

**定义**

```objectivec
@property (nonatomic, weak) id<WDGRoomDelegate> delegate;
```

**说明**

符合 `WDGRoomDelegate` 协议的代理，用于接收房间内事件的通知。

</br>

---

## 方法

### - 方法名

**定义**

```objectivec
- (void)acceptWithLocalStream:(WDGLocalStream *)localStream;
```

**说明**

方法说明

**参数**

参数名             | 说明 
------------------|------------------
参数               | 说明
参数               | 说明

**返回值**

视频录制是否成功关闭。

</br>

---

### - initWithRoomId:

**定义**

```objectivec
- (instancetype)initWithRoomId:(NSString *)roomId;
```

**说明**

使用 roomId 初始化房间。如果 roomId 不存在，则创建新房间；如果存在，则加入该房间。

**参数**

参数名             | 说明 
------------------|------------------
roomId            | 字符串类型，代表一个房间的唯一标识。

**返回值**

初始化完成的 `WDGRoom` 实例。

</br>

---

### - connect

**定义**

```objectivec
- (void)connect;
```

**说明**

开启与房间的网络连接。

</br>

---

### - disconnect

**定义**

```objectivec
- (void)disconnect;
```

**说明**

断开与房间的网络连接。

</br>

---

### - publishLocalStream:

**定义**

```objectivec
- (void)publishLocalStream:(WDGLocalStream *)localStream;
```

**说明**

将本地的媒体流发布到房间。

**参数**

参数名             | 说明 
------------------|------------------
localStream       | 表示`WDGLocalStream` 类型的本地媒体流。

</br>

---

### - publishLocalStream: withCompletionBlock:

**定义**

```objectivec
- (void)publishLocalStream:(WDGLocalStream *)localStream withCompletionBlock:(void(^)(NSError *error))block;
```

**说明**

将本地媒体流发布到房间，并在收到服务器回应后执行回调。

**参数**

参数名             | 说明 
------------------|------------------
localStream       | 表示`WDGLocalStream` 类型的本地媒体流。
block             | 收到服务器回应时执行的 Block，用于通知本地流是否成功发布。

</br>

---

### - publishLocalStream: shouldMixed:

**定义**

```objectivec
- (void)publishLocalStream:(WDGLocalStream *)localStream shouldMixed:(BOOL)mixed;
```

**说明**

将本地的媒体流发布到房间，并指定该媒体流是否允许 MCU 合流。

**参数**

参数名             | 说明 
------------------|------------------
localStream       | 表示`WDGLocalStream` 类型的本地媒体流。
mixed             | 布尔类型，用于指定媒体流是否允许 MCU 合流。

</br>

---

### - publishLocalStream: shouldMixed: withCompletionBlock:

**定义**

```objectivec
- (void)publishLocalStream:(WDGLocalStream *)localStream shouldMixed:(BOOL)mixed withCompletionBlock:(void(^)(NSError *error))block;
```

**说明**

将本地的媒体流发布到房间，同时指定该媒体流是否允许 MCU 合流，并在收到服务器回应后执行回调。

**参数**

参数名             | 说明 
------------------|------------------
localStream       | 表示`WDGLocalStream` 类型的本地媒体流。
mixed             | 布尔类型，用于指定媒体流是否允许 MCU 合流。
block             | 收到服务器回应时执行的 Block，用于通知本地流是否成功发布。

</br>

---

### - unpublishLocalStream:

**定义**

```objectivec
- (void)unpublishLocalStream:(WDGLocalStream *)localStream;
```

**说明**

停止在房间中发布本地媒体流。

**参数**

参数名             | 说明 
------------------|------------------
localStream       | 表示`WDGLocalStream` 类型的本地媒体流。

</br>

---

### - unpublishLocalStream: withCompletionBlock:

**定义**

```objectivec
- (void)unpublishLocalStream:(WDGLocalStream *)localStream withCompletionBlock:(void(^)(NSError *error))block;
```

**说明**

停止在房间中发布本地媒体流，并在收到服务器回应后执行回调。

**参数**

参数名             | 说明 
------------------|------------------
localStream       | 表示`WDGLocalStream` 类型的本地媒体流。
block             | 收到服务器回应时执行的 Block，用于通知本地流是否成功取消发布。

</br>

---

### - subscribeRoomStream:

**定义**

```objectivec
- (void)subscribeRoomStream:(WDGRoomStream *)roomStream;
```

**说明**

订阅房间中指定的远端媒体流。

**参数**

参数名             | 说明 
------------------|------------------
roomStream        | `WDGRoomStream` 类型的远端媒体流，代表房间中除自己以外的其他媒体流。

</br>

---

### - subscribeRoomStream: withCompletionBlock:

**定义**

```objectivec
- (void)subscribeRoomStream:(WDGRoomStream *)roomStream withCompletionBlock:(void(^)(NSError *error))block;
```

**说明**

订阅房间中指定的远端媒体流，并在收到服务器回应后执行回调。

**参数**

参数名             | 说明 
------------------|------------------
roomStream        | `WDGRoomStream` 类型的远端媒体流，代表房间中除自己以外的其他媒体流。
block             | 收到服务器回应时执行的 Block，用于通知远端流是否成功订阅。

</br>

---

### - unsubscribeRoomStream:

**定义**

```objectivec
- (void)unsubscribeRoomStream:(WDGRoomStream *)roomStream;
```

**说明**

取消订阅房间中指定的远端媒体流。

**参数**

参数名             | 说明 
------------------|------------------
roomStream        | `WDGRoomStream` 类型的远端媒体流，代表房间中除自己以外的其他媒体流。

</br>

---

### - unsubscribeRoomStream: withCompletionBlock:

**定义**

```objectivec
- (void)unsubscribeRoomStream:(WDGRoomStream *)roomStream withCompletionBlock:(void(^)(NSError *error))block;
```

**说明**

订阅房间中指定的远端媒体流，并在收到服务器回应后执行回调。

**参数**

参数名             | 说明 
------------------|------------------
roomStream        | `WDGRoomStream` 类型的远端媒体流，代表房间中除自己以外的其他媒体流。
block             | 收到服务器回应时执行的 Block，用于通知远端流是否成功取消订阅。

</br>

---