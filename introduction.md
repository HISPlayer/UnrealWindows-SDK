# HISPlayer Unreal Windows SDK
The most advanced video streaming player for Unreal Engine supporting supporting local files, VOD, and live streaming. It enables premium DASH and HLS video streaming inside your Unreal games and metaverses on Windows.
Fully customizable and extensible to fit advanced streaming requirements. If you require specific or advanced features, please don't hesitate to contact us at [contact@hisplayer.com](mailto:contact@hisplayer.com).


## Compatibility
### Supported Unreal Versions: 
  * [Deprecated] 4.27 - 5.4
  * 5.5
  * 5.6
  * 5.7

Only official Unreal Engine versions distributed through the Epic Games Launcher are supported. Custom source builds are not supported.

If you need other Unreal version support, please contact us at contact@hisplayer.com.

### Supported Stream Protocols: 
  * HLS (Live & VOD)
  * DASH (VOD)
    * Profile: `urn:mpeg:dash:profile:isoff-on-demand:2011`

### Supported Video Codecs:
  * H.264
  * H.265 / HEVC
    * [MS HEVC codec extension](https://apps.microsoft.com/store/detail/hevc-video-extensions/9NMZLZ57R3T7) is required.
    * Only streams using the fMP4 container are supported. MPEG-2 TS is not supported.

### Supported Video Formats:
  * MP4
  * AVI

### Supported Audio Codecs:
  * AAC

### Supported Audio Formats:
  * MP3
  * WAV

### Supported Unreal Rendering Modes:
  * Texture
  * UMG UI

### Supported Graphics API:
  * DirectX 11
  * DirectX 12

### Maximum Supported Resolution:
  * 8,192 × 4,320 (8K)
    * H.265/HEVC codec is required to play 8K video.

## Unreal Engine 5 – Windows Requirements
  * Visual Studio 2019 v16.11.5, Visual Studio 2022
  * Windows SDK 10.0.18362
  * LLVM clang 13.0.1
  * .NET 4.6.2 Targeting Pack
  * .NET 6.0
