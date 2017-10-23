
# 1. AVCapture相关API
## 1.1 AVCaptureDevie
> An AVCaptureDevice represents a physical device that provides realtime input media data, such as video and audio.

AVCaptureDevice代表提供像视频、音频这样的实时数据的物理设备

### 1.1.1 获得设备

```
 + (nullable AVCaptureDevice *)defaultDeviceWithDeviceType:(AVCaptureDeviceType)deviceType 
                                                 mediaType:(nullable AVMediaType)mediaType  
                                                 position:(AVCaptureDevicePosition)position  

```
 
### 1.1.2 AVCaptureDeviceType 
* AVCaptureDeviceTypeBuiltInMicrophone
* AVCaptureDeviceTypeBuiltInWideAngleCamera
* AVCaptureDeviceTypeBuiltInTelephotoCamera  
  
   >  A built-in camera device with a longer focal length than a wide angle camera. Note that devices of this type may only be discovered using an AVCaptureDeviceDiscoverySession.  
   长焦镜头，只在双镜头手机上才有，所以只能通过 AVCaptureDeviceDiscoverySession来获取。

* AVCaptureDeviceTypeBuiltInDualCamera
 >  device that consists of two fixed focal length cameras, one wide and one telephoto  
 混合相机，两个相机虚拟出来的相机
 
 
### 1.1.3 AVMediaType
* AVMediaTypeVideo
* AVMediaTypeAudio
* AVMediaTypeText
* AVMediaTypeClosedCaption
* AVMediaTypeSubtitle
* AVMediaTypeTimecode
* AVMediaTypeMetadata
* AVMediaTypeMuxed
* AVMediaTypeMetadataObject
* AVMediaTypeDepthData
 
### 1.1.4 AVMediaType
* AVCaptureDevicePositionUnspecified
* AVCaptureDevicePositionBack
* AVCaptureDevicePositionFront
 
## 1.2 AVCaptureDeviceInput
> AVCaptureDeviceInput is a concrete subclass of AVCaptureInput that provides an interface for capturing media from an AVCaptureDevice  
AVCaptureDeviceInput 为 AVCaptureDevice捕获的数据提供一个接口，  
继承自AVCaptureInput。类似的子类还有AVCaptureScreenInput、AVCaptureMetadataInput。
 
 
 
 
# 2. ImageOrientation
# 3. Core Motion
# 4. system privacy authority
# 4. imageView的缩放、切换、动画、网络加载
# 5. 仿微信图片简单处理
# 6. 自定义相机，自己的图文记录工具。