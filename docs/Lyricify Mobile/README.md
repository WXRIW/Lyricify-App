<div align="center">

# Lyricify Mobile 使用指南

</div>

# 安装问题

## 如何在 Android 设备上安装 Lyricify Mobile
下载 .apk 安装包，打开后点击安装即可。  

## 如何在 iPhone 或 iPad 上安装 Lyricify Mobile
目前 Lyricify Mobile 并未上架 App Store，原因详见[这里](#ios-版是否会上架-app-store)。  
您可以在下载 .ipa 安装包后，采用自签的方式安装，点击[这里](iOS/IpaGuide.md)查看详细教程。  

# 常见问题

## 无法登录
红框提示：糟糕！出了点问题。
### 导致原因
网络问题。
### 解决方案
科学上网。

## 无法使用第三方登录
使用 Google、Facebook 等第三方无法成功登录授权。
### 解决方案
使用 Spotify 账号登录。

## 无法正常进入歌词界面
**提示 connection closed:** 检查你的网络  
**提示 invalid_grant:** 重新登录  

## 如何导入歌词
提示 “没有找到歌词，您可以在 Lyricify 4 中导入歌词”
### 解决方案
在 Lyricify 4 中自行导入即可。  
*注：Lyricify 4 是电脑软件。*  
[具体操作方法](https://github.com/WXRIW/Lyricify-App/blob/main/docs/Lyricify%204/README.md#%E6%AD%8C%E8%AF%8D%E6%A0%87%E8%AE%B0%E5%8F%8A%E5%AF%BC%E5%85%A5)

## 提示没有找到歌词
没搜到歌词。  
提示 “没有找到歌词，您可以在 Lyricify 4 中导入歌词”
### 导致原因
确实没搜到歌词。
### 解决方案
在 Lyricify 4 中自行导入即可。  
*注：Lyricify 4 是电脑软件。*  
[具体操作方法](https://github.com/WXRIW/Lyricify-App/blob/main/docs/Lyricify%204/README.md#%E6%AD%8C%E8%AF%8D%E6%A0%87%E8%AE%B0%E5%8F%8A%E5%AF%BC%E5%85%A5)

## 电脑上有歌词，手机上没有/错误
### 解决方案
在 Lyricify 4 中标记歌词后重新打开 Lyricify Mobile 即可。

## 歌词没有翻译
歌词对的啊，为啥没翻译啊。
### 导致原因
搜到的这个歌词就是没翻译的，反正不是 Lyricify 的锅。
### 解决方案
在 Lyricify 4 中自行导入有翻译的版本即可。

## 没有逐字歌词
为啥不显示逐字歌词呢？
### 导致原因
Lyricify Mobile 不支持逐字歌词的显示。也没有加入此功能的计划。
### 解决方案
自行脑补逐字歌词。或使用 Lyricify 4。

## 如何调整字号
歌词字号太大或太小。
### 导致原因
Lyricify Mobile 不支持字号调节。
### 解决方案
更换设备以使用 Lyricify 4。如果您使用的是手机，建议更换电脑。如果您使用的是平板，则建议更换 Windows 平板。

## 如何使用其他界面
我只找到了 Apple Music 界面，没找到其他界面哎。
### 导致原因
Lyricify Mobile 只有这个界面。
### 解决方案
在 Windows 设备上使用 Lyricify 4。

## 如何使用桌面歌词
Lyricify Mobile 不支持桌面歌词。  
### 导致原因
由于 Lyricify Mobile 是跨平台开发的，需要同时考虑 Android 和 iOS，而 iOS 上无法实现传统桌面歌词效果，故 Android 上也暂时不会添加桌面歌词功能。
### 解决方案
在 Android 上可使用小窗等功能来近似实现。  
在 Windows 上可使用 Lyricify 4 获取完整体验。  
在 iOS、iPadOS、macOS 上暂无解决方案。

## 如何在手机上使用 Lyricify 4
Lyricify 4 好多功能 Lyricify Mobile 都没有啊，啥时候才能有呢。
### 导致原因
Lyricify Mobile 目标就是显示歌词，现在目标已经达成。
### 解决方案
在 Windows 设备上使用 Lyricify 4。您可以给您的手机安装 Windows on ARM。

## 歌词比歌曲快或慢
Lyricify Mobile 中显示的歌词比歌曲快了或者慢了。  
### 导致原因
Spotify API 提供的播放进度不准，这是由多个原因导致的。
1. Spotify 客户端向 Spotify 服务器发送进度有误差或延迟。
2. Lyricify Mobile 向 Spotify 服务器发送进度请求有误差或延迟。
3. Spotify 本身进度不准。
由一系列原因，造成歌词显示时间轴不准确。
### 解决方案
±2s 内的延迟属于正常范围。  
如果您无法接受这个延迟，则建议在 Windows 设备上使用 Lyricify 4。

## 切歌后反应迟钝
切歌后 Lyricify 需要过较长时间才能显示新的歌曲信息。  
见下方 `总是提示出现 429 错误`

## 总是提示出现 429 错误
进行操作时总是提示出现 429 错误。  
### 导致原因
Spotify 返回了 `429 请求过多` 错误，不是 Lyricify 的锅。
### 解决方案
配置自定义 API Client，可参考[这个教程](CustomClient/Readme.zh-CN.md)。  
或者等待，等到 Spotify 不返回 429 了，就好了。  

## iOS 版是否会上架 App Store
使用自签方式安装非常麻烦，而上架 App Store 后则会方便很多，为什么不上架呢？  
### 导致原因
1. Apple 要求上传 App Store 需要 Apple 开发者账号，年费 688 元，十分高昂。
2. 若需在 App Store 大陆地区上架，还需进行 ICP 备案，导致通过审核的几率更低。若仅上架外区，大部分大陆用户没有相关支付方式，也将成为一个问题。
### 解决方案
自签安装即可。  
或者资助开发者购买 Apple 开发者账号。若成功通过审核，开发者将返还 Apple 开发者账号年费，并赠送 Lyricify 授权一份。  