
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

### 1.3.1 AVCaptureInput  
AVCaptureInput只有一个属性：ports，AVCaptureInputPort类型的数组;  

### 1.3.2 AVCaptureDeviceInput  
继承自AVCaptureInput，增加了AVCaptureDevie属性，一个工厂方法和一个初始化方法。
## 1.4 AVCaptureOutput(子类)。
```
#import <AVFoundation/AVCaptureAudioDataOutput.h>
#import <AVFoundation/AVCaptureAudioPreviewOutput.h>
#import <AVFoundation/AVCaptureDepthDataOutput.h>
#import <AVFoundation/AVCaptureFileOutput.h>
#import <AVFoundation/AVCaptureMetadataOutput.h>
#import <AVFoundation/AVCapturePhotoOutput.h>
#import <AVFoundation/AVCaptureStillImageOutput.h>
#import <AVFoundation/AVCaptureVideoDataOutput.h>
```  
>    AVCaptureOutput provides an abstract interface for connecting capture output destinations, such as files and video previews, to an AVCaptureSession.  

>  An AVCaptureOutput can have multiple connections represented by AVCaptureConnection objects, one for each stream of media that it receives from an AVCaptureInput. An AVCaptureOutput does not have any connections when it is first created. When an output is added to an AVCaptureSession, connections are created that map media data from that session's inputs to its outputs.  
一个 AVCaptureOutput拥有多个AVCaptureConnection对象，每一个AVCaptureConnection对象对应一个数据流。  

### 1.4.1 AVCaptureStillImageOutput
AVCaptureOutput

## 1.5 AVCaptureConnection  
>  AVCaptureInputs have one or more AVCaptureInputPorts. AVCaptureOutputs can accept data from one or more sources (example - an AVCaptureMovieFileOutput accepts both video and audio data). AVCaptureVideoPreviewLayers can accept data from one AVCaptureInputPort whose mediaType is AVMediaTypeVideo. When an input or output is added to a session, or a video preview layer is associated with a session, the session greedily forms connections between all the compatible AVCaptureInputs' ports and AVCaptureOutputs or AVCaptureVideoPreviewLayers. Iterating through an output's connections or a video preview layer's sole connection, a client may enable or disable the flow of data from a given input to a given output or preview layer.  

>   AVCaptureInputs拥有一个或多个AVCaptureInputPorts。AVCaptureOutputs能从一个或多个资源中接受数据。（比如，AVCaptureMovieFileOutput既可以接受视频数据，也可以接收音频数据）AVCaptureVideoPreviewLayers可以接收来自mediaType为AVMediaTypeVideo的AVCaptureInputPort的数据。当输入输出加入到会话中，或者视频预览图层与会话联系起来，会话会连续的在所有合适的输入口和输出或者视频预览图层之间建立连接。


## 1.6 AVCaptureInputPort   
>  An AVCaptureInputPort describes a single stream of media data provided by an AVCaptureInput and provides an interface for connecting that stream to AVCaptureOutput instances via AVCaptureConnection.    

>由AVCaptureInput提供的一个单一的媒体数据流，由AVCaptureInputPort提供接口将该数据流与AVCaptureOutput实例连接起来，通过AVCaptureConnection。
 
 
# 2. ImageOrientation
# 3. Core Motion
# 4. system privacy authority
# 4. imageView的缩放、切换、动画、网络加载
# 5. 仿微信图片简单处理
# 6. 自定义相机，自己的图文记录工具