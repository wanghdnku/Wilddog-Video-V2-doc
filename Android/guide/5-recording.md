title: 本地视频录制
---

本篇文档介绍如何录制并保存本地媒体流。

 
## 录制本地媒体流

在视频通话中，使用 `startVideoRecording(File file)` 来录制本地媒体流，该方法需要传入存储路径：

```java
File file = getYourFile();
mConversation.startVideoRecording(file);
```

## 停止录制媒体流

使用 `stopVideoRecording()` 来停止录制本地媒体流：

```java
mConversation.stopVideoRecording();
```
