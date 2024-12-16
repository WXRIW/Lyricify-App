<div align="center">

# Lyricify Mobile 使用指南

</div>

# 安装问题

## 如何在 Android 设备上安装 Lyricify Mobile
下载 `.apk` 安装包，打开后点击安装即可。  

## 如何在 iPhone 或 iPad 上安装 Lyricify Mobile
目前 Lyricify Mobile 并未上架 App Store，原因详见[这里](#ios-版是否会上架-app-store)。  
您可以在下载 `.ipa` 安装包后，采用自签的方式安装，点击[这里](iOS/IpaGuide.md)查看详细教程。   

## 如何在 Mac 上安装 Lyricify Mobile
直接下载 `macOS.pkg` 安装即可。（推荐）  
您也可以下载 `.macOS.zip`，将压缩包中的 Lyricify Mobile for macOS.app 拖入 `应用程序` 文件夹，即可完成安装。  

## 如何在 Windows 上使用 Lyricify Mobile
Lyricify Mobile for Windows 为测试性质，不建议日常使用，建议使用具有完整功能的 Lyricify 4。
Lyricify Mobile for Windows 下载 `.Windows.zip` 后，解压后运行 `Lyricify Mobile.WPF.exe` 即可。
不支持网页登录，需要手动输入 Token。

# 常见问题

## 无法登录
红框提示：糟糕！出了点问题。
### 导致原因
网络问题。
### 解决方案
科学上网。

## 登录时提示 INVALID_CLIENT: Invalid Redirect URI
检查你的 Redirect URI 是否正确填写。确保[教程](CustomClient/Readme.zh-CN.md)中的两条 Redirect URI 均已正确填写。

## 无法正常进入歌词界面
**提示 connection closed:** 检查你的网络  
**提示 invalid_grant:** 重新登录  

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

## 超长 429 错误
配置了自定义 API Client 并使用了一段时间后，提示出现了等待时长达到几千或几万秒的 429 错误。
### 导致原因
连续使用时长过长。连续使用十几个小时，或在没有播放歌曲时使用 Lyricify 达几个小时，都有几率出现超长 429 错误。  
### 解决方案
- 创建一个新的 Client，然后重新在 Lyricify 中登录和授权。
- 您还可以等待，直至 429 错误结束。
### 一些建议
1. 尽量避免连续使用过长时间 (10 小时以上)，这会导致单位时间内的请求量超过 Spotify API 阈值，这就会让出现超长 429 错误的概率增大很多。
2. 如果您在多台设备上使用 Lyricify，且使用频率高，则可以为每台设备单独创建一个 Client，这样可以分散请求，防止触发阈值限制。
3. 在没有播放歌曲时，请关闭 Lyricify。在这种情况下保持 Lyricify 的运行，几个小时 (最短 1-3 小时) 就会导致 429 错误。（Android 设备上不使用 Lyricify 时，请关闭其后台，若不关闭，则会连续发送请求，造成超长 429 错误。iOS 设备及部分 Android 设备上可以不关闭后台）

## Lyricify 无法获取当前播放信息
Lyricify 没有显示当前正在播放的歌曲。
### 导致原因
Spotify 没有上传当前的播放信息。这是网络原因，也可能是 Spotify 客户端的问题。
### 解决方案
1. 校园网用户，可以尝试使用热点。
2. 科学上网工具改为全局。
3. 重装 Spotify 最新版。
4. 使用 Spotify 网页版。
5. 反正不是 Lyricify 的锅，自己想办法解决。

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

## 非 Android 设备上没有模糊效果
在 iOS 等设备及部分 Android 设备上没有模糊效果。
### 导致原因 & 解决方案
iOS 的 UIKit 没有提供可指定半径的模糊接口，故无法实现此效果。需等待 Lyricify Mobile 2。  
Android 旧版本没有提供模糊 API，可升级至 Android 12 或更高版本以实现本效果。  

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

## iOS 版是否会上架 App Store
使用自签方式安装非常麻烦，而上架 App Store 后则会方便很多，为什么不上架呢？  
### 导致原因
1. Apple 要求上传 App Store 需要 Apple 开发者账号，年费 688 元，十分高昂。
2. 若需在 App Store 大陆地区上架，还需进行 ICP 备案，导致通过审核的几率更低。若仅上架外区，大部分大陆用户没有相关支付方式，也将成为一个问题。
### 解决方案
自签安装即可。  
或等待 Lyricify Mobile 2 的到来。Lyricify Mobile 2 将专为 Apple 平台开发，在完成开发后会在 App Store 上架，预计最快一至两年后会开始开发，敬请期待。