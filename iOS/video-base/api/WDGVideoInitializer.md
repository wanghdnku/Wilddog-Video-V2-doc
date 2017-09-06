title: WDGVideoInitializer
---

野狗视频的共用类，用来配置 WilddogVideo 和 WilddogRoom。

## 方法

### + sharedInstance

**定义**

```objectivec
+ (instancetype)sharedInstance;
```

**说明**

用于获取 `WDGVideoInitializer` 的单例。

**返回值**

`WDGVideoInitializer` 单例。

</br>

---

### - configureWithVideoAppId: token:

**定义**

```objectivec
- (void)configureWithVideoAppId:(NSString *)videoAppId token:(NSString *)token;
```

**说明**

用于配置 `WDGVideoInitializer` 单例。

**参数**

参数名             | 说明 
------------------|------------------
videoAppId        | 在野狗控制面板创建App后分配的 Video AppID。
token             | 通过 `WilddogAuth` 验证登录后获取的 Wilddog ID token。

</br>

---

### - setToken:

**定义**

```objectivec
- (void)setToken:(NSString *)token;
```

**说明**

用于设置 token。

**参数**

参数名             | 说明 
------------------|------------------
token             | 通过 `WilddogAuth` 验证登录后获取的 Wilddog ID token。

</br>

---
