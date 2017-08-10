title: 美颜滤镜
---

本篇文档介绍如何处理本地视频流，用户可以调用第三方 SDK（如Camera360 SDK、涂图、开为）来处理将要上传的本地视频流，实现美颜、人脸识别等效果。。


### 设置监听

设置 `LocalStream` 的回调监听用于处理本地视频流。

```java
localStream.setOnFrameListener(
     new CameraFrameListener() {
            @Override
            public void onByteFrame(byte[] data, int width, int height, int rotation, long timestatmp) {
                
            }
        });
```

### 处理本地视频流

实现回调监听方法 `onByteFrame(byte[] bytes, int i, int i1,int var4, long var5)`，获得本地视频流后，会调用该方法处理原始视频流：

设置 `LocalStream` 的 `setOnFrameListener` 来获取本地视频流，可以对视频流做美颜处理再返回给 Video SDK。

```java
localStream = video.createLocalStream(localStreamOptions);
localStream.setOnFrameListener(new WilddogVideo.CameraFrameListener() {
            @Override
            public void onByteFrame(byte[] bytes, int i, int i1,int var4, long var5) {
                // TODO 设置美颜效果
                frameProcess(bytes, 0, mFirstFrame, true, i, i1, var4 );//data 可以传空 根据TextureId进行美颜

            }
        });
```
