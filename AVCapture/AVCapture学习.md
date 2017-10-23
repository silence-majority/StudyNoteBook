
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
 
### 1.1.4 AVCaptureDevicePosition(category)
* AVCaptureDevicePositionUnspecified
* AVCaptureDevicePositionBack
* AVCaptureDevicePositionFront
 
### 1.1.5 AVCaptureFlashMode(category)
* AVCaptureFlashModeOff
* AVCaptureFlashModeOn
* AVCaptureFlashModeAuto

### 1.1.6 AVCaptureTorchMode(category)
* AVCaptureTorchModeOff
* AVCaptureTorchModeOn
* AVCaptureTorchModeAuto

### 1.1.7 AVCaptureDeviceFocus(category)
AVCaptureFocusMode  

* AVCaptureFocusModeLocked
* AVCaptureFocusModeAutoFocus
* AVCaptureFocusModeAutoFocus  

AVCaptureAutoFocusRangeRestriction

* AVCaptureAutoFocusRangeRestrictionNone
* AVCaptureAutoFocusRangeRestrictionNear
* AVCaptureAutoFocusRangeRestrictionFar  

### 1.1.8 AVCaptureDeviceExposure(category)  
AVCaptureExposureMode  

* AVCaptureExposureModeLocked
* AVCaptureExposureModeAutoExpose  
* AVCaptureExposureModeContinuousAutoExposure  
* AVCaptureExposureModeCustom  

### 1.1.9 AVCaptureDeviceWhiteBalance(category)
### 1.1.10 AVCaptureDeviceWhiteBalance(category)
### 1.1.11 AVCaptureDeviceSubjectAreaChangeMonitoring(category)
### 1.1.12 AVCaptureDeviceLowLightBoost(category)
### 1.1.13 AVCaptureDeviceVideoZoom(category)
### 1.1.14 AVCaptureDeviceAuthorization(category)
AVAuthorizationStatus  

* AVAuthorizationStatusNotDetermined
* AVAuthorizationStatusNotDetermined
* AVAuthorizationStatusDenied
* AVAuthorizationStatusAuthorized

### 1.1.15 AVCaptureDeviceTransportControls(category)
### 1.1.16 AVCaptureDeviceHighDynamicRangeSupport(category)
### 1.1.17 AVCaptureDeviceColorSpaceSupport(category)
### 1.1.18 AVCaptureDeviceDepthSupport(category)

## 1.2 AVCaptureDeviceDiscoverySession
```
+ (instancetype)discoverySessionWithDeviceTypes:(NSArray<AVCaptureDeviceType> *)deviceTypes 
                                      mediaType:(nullable AVMediaType)mediaType 
                                       position:(AVCaptureDevicePosition)position;  
                                       
@property(nonatomic, readonly) NSArray<AVCaptureDevice *> *devices;                          
```
## 1.3 AVCaptureDeviceInput(AVCaptureInput)  

> AVCaptureDeviceInput is a concrete subclass of AVCaptureInput that provides an interface for capturing media from an AVCaptureDevice  
AVCaptureDeviceInput 为 AVCaptureDevice捕获的数据提供一个接口，  
继承自AVCaptureInput。类似的子类还有AVCaptureScreenInput、AVCaptureMetadataInput。
 
## 1.4 AVCaptureOutput(子类)  
## 1.5 AVCaptureConnection
## 1.6 AVCaptureInputPort 
 
 
# 2. ImageOrientation
# 3. Core Motion
# 4. system privacy authority
# 4. imageView的缩放、切换、动画、网络加载
# 5. 仿微信图片简单处理
# 6. 自定义相机，自己的图文记录工具