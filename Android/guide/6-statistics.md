title: 媒体流统计
---

本篇文档介绍如何获取本地媒体流和远端媒体流的统计数据。


### 设置监听回调

设置 `Conversation` 中的 `StatsListener` 接口可以实时获取视频的宽、高、帧率、发送接收总大小、比特率、延迟等信息：

```java
mConversation.setStatsListener(rtcStatsListener);
```

### 统计本地媒体流

实现回调接口方法 `onLocalStreamStatsReport(LocalStreamStatsReport localStats);`，持续收到本地媒体流的统计信息：

```java
   mConversation.setStatsListener(new StatsListener() {
            @Override
            public void onLocalStreamStatsReport(LocalStreamStatsReport localStats) {
                //localStats.getWidth();
                //localStats.getHeight();
                //localStats.getFps();
                //localStats.getBytesSent();
                //localStats.getBitsSentRate();    
            }

            @Override
            public void onRemoteStreamStatsReport(RemoteStreamStatsReport remoteStats) {

            }
   });
}
```

### 统计远程视频媒体流

实现代理方法 `onRemoteStreamStatsReport(RemoteStreamStatsReport remoteStats)`，持续收到远端媒体流的统计信息：

```java
   mConversation.setStatsListener(new StatsListener() {
            @Override
            public void onLocalStreamStatsReport(LocalStreamStatsReport localStats) {
  
            }

            @Override
            public void onRemoteStreamStatsReport(RemoteStreamStatsReport remoteStats) {
                //remoteStats.getWidth();
                //remoteStats.getHeight();
                //remoteStats.getFps();
                //remoteStats.getBytesReceived();
                //remoteStats.getBitsReceivedRate(); 
				//remoteStats.getDelay();
            }
   });
```
