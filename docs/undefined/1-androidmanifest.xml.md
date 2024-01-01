# 1️⃣ AndroidManifest.xml

## AndroidManifest.xml

### 권한

#### 저장소 권한

OS 13 이전

```xml
<uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE" />
<uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" tools:ignore="ScopedStorage" />
```

OS 13 부터

```xml
<uses-permission android:name="android.permission.READ_MEDIA_IMAGES" />
<uses-permission android:name="android.permission.READ_MEDIA_AUDIO" />
<uses-permission android:name="android.permission.READ_MEDIA_VIDEO" />
```



## 트러블 슈팅

### recyclerView Fragment에서 동작 안하는 현상

```
레이아웃 xml 이 잘려있었다. 필히 확인할 것!!!
```
