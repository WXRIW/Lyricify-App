<div align="center">

# Lyricify Lite 使用指南

</div>

# App 支持列表
已知支持 Lyricify Lite 的 app 如下表所示。

| 名称 | SMTC 支持情况 | 曲目匹配 | 备注 |
| - | - | - | - |
| HyPlayer | 完美 | 完美 |  |
| LyricEase | 完美 | 完美 |  |
| Spotify | 完美 | 较好 |  |
| Apple Music | 时间轴精度低；曲目信息不全 | 一般 |  |
| QQ 音乐 | 完美 | 较好 |  |
| QQ 音乐 UWP | 一般，信息提供不稳定 | 较好 |  |
| 网易云音乐 | 一般，信息提供不稳定 | 较好 | 需安装额外的[插件](https://github.com/BetterNCM/InfinityLink) |
| 网易云音乐 UWP | 无时间轴信息 | 较好 |  |
| 酷狗音乐 | 无时间轴信息 | 较好 |  |
| Groove Music | 时间轴完美；曲目信息取决于具体曲目 | 一般，取决于具体文件 |  |
| Foobar 2000 | 无时间轴信息；曲目信息取决于具体曲目 | 一般，取决于具体文件 |  |
| PotPlayer | 时间轴完美；曲目信息取决于播放内容的文件名 | 较差，取决于文件名 |  |
| Google Chrome | 时间轴较好；曲目信息取决于具体播放内容 | 一般，取决于具体内容 | 默认不启用 |
| Microsoft Edge | 时间轴较好；曲目信息取决于具体播放内容 | 一般，取决于具体内容 | 默认不启用 |

**注意：**
1. 请确保相关 app 已更新至最新版本，部分旧版本可能并不支持 SMTC。Spotify 用户建议使用 Lyricify 4，不建议使用 Lyricify Lite，点击查看[具体原因](#spotify-用户应使用-lyricify-4)。
2. 对于 SMTC 无时间轴信息的 app，Lyricify Lite 将使用内置定时器更新歌词进度，所以在手动修改播放进度后，Lyricify Lite 无法更新播放进度，歌词会发生前后错位。
3. 曲目匹配“完美”指 Lyricify Lite 可以完美匹配当前播放的曲目。其它匹配程度指 Lyricify Lite 需要通过对曲目信息进行搜索来匹配对应曲目，所以匹配可能不精准或匹配不到。
4. 所有接入 SMTC 的应用均支持 Lyricify Lite，未在上表中列出的 app 并不代表不支持 Lyricify Lite。

# Lyricify Lite 基础

## Lyricify Lite 是什么
Lyricify Lite 是 Lyricify 家族于 2024 年 12 月推出的新软件，它运行于 Windows 平台，仅保留了 Lyricify 4 的灵动词岛功能（后期会加入桌面歌词等功能），支持所有接入了 SMTC 的音乐播放器，包括 HyPlayer、LyricEase、Apple Music、QQ 音乐、网易云音乐 UWP、酷狗音乐、Foobar 2000、Groove Music 等诸多音乐软件。 

## Lyricify Lite 有哪些功能
Lyricify Lite 目前只有灵动词岛功能，后期会加入桌面歌词等功能。

## 运行 Lyricify Lite
如果您想使用 Lyricify Lite，请确保您的系统版本不低于 10.0.17763.0，且安装了 `.NET Desktop Runtime 8.0`。如果启动时提示您的未安装，则需要您在这里下载安装：  
点击下载 .NET Desktop Runtime 8.0.11 [x86](https://dotnet.microsoft.com/zh-cn/download/dotnet/thank-you/runtime-desktop-8.0.11-windows-x86-installer) [x64](https://dotnet.microsoft.com/zh-cn/download/dotnet/thank-you/runtime-desktop-8.0.11-windows-x64-installer) [Arm64](https://dotnet.microsoft.com/zh-cn/download/dotnet/thank-you/runtime-desktop-8.0.11-windows-arm64-installer)   
[点击转到 .NET 8.0 官方下载地址](https://dotnet.microsoft.com/zh-cn/download/dotnet/8.0)

## 如何找到运行中的 Lyricify Lite
你随时可以在系统通知栏（托盘）中找到 Lyricify Lite 的图标。  
你可以右击该图标以控制 Lyricify Lite，包括开启功能、配置设置、退出 Lyricify Lite 等。

# 常见问题

**注意：** 如需反馈或提问，对于 Lyricify 功能，请使用[官方认定的正确的名称](#lyricify-%E5%90%8D%E8%AF%8D)来描述。  

## Microsoft Store 版本与 GitHub 版本有什么区别
*注：下文中的 GitHub 版本指 Microsoft Store 版本外的其他分发方式分发的版本，含群聊、网盘等分发渠道。*
### 主要区别
1. 发布新版本时，Microsoft Store 版本通常会提前 1-3 天更新，您可以提前体验新功能。
2. Microsoft Store 版本的自动更新由 Microsoft 负责和管理，体验更好。
   GitHub 版本的更新由 Lyricify 负责，更新源为 GitHub 服务器，在部分地区体验不如 Microsoft Store 版本。
3. 部分功能为 Microsoft Store 版本独享功能。

### Microsoft Store 独享功能
为了提升用户体验，促进开发良性循环，部分功能是作为 Microsoft Store 独享功能开发的。  
目前 Microsoft Store 版本有以下独享功能：
1. 灵动词岛的自定义字体功能。
2. 桌面歌词的自定义字体功能。
3. 独享中国大陆加速服务器。
  
在 Microsoft Store 购买 Lyricify 是对 Lyricify 开发者的一种支持和信任，感谢所有购买或打赏过 Lyricify 的用户！也欢迎各位用户给出 5 星好评和评语，这对我有很大帮助！  

### 更多信息
Lyricify Lite 是免费软件，如果你觉得 Lyricify Lite 做的不错，则可以通过以下渠道支持：
- 在软件中，菜单-关于页里有打赏方式
- 在 [Microsoft Store](https://apps.microsoft.com/store/detail/9NLTPSV395K2?launch=true&mode=full) 中购买

如果您在 Microsoft Store 购买过程中遇到困难，可以考虑通过打赏的方式支持 Lyricify。  

如果你发现有人在非法销售本软件 (只有 Microsoft Store 中的 Lyricify 是官方发布)，请联系我们！感谢你的支持！

## Self-contained 版本特殊说明
Self-contained 版本包含 .NET 8.0 Desktop Runtime 运行时，仅建议那些因某些原因无法正常安装 .NET 8.0 运行时的用户使用。其他用户建议选择 Microsoft Store 版本或标准安装版（即不包含 .NET 运行时的版本）。  
请注意：Self-contained 版本不支持自动更新。在发布新版本后，用户需要手动下载并安装更新。Lyricify 默认开启自动更新，尽管 self-contained 版本仍会尝试下载并安装更新，但由于更新内容为标准版本，即不包含 .NET 运行时，更新后 Lyricify 应用将无法启动。  

## 无法检测到播放器
Lyricify Lite 无法检测到你正在使用的音乐软件的播放状态。
### 导致原因
你使用的软件可能并不支持 SMTC，或是没有正确配置 SMTC。
### 解决方案
如果你使用的软件在 [App 支持列表](#app-支持列表) 中列出，请查看[逐应用常见问题](#常见问题逐应用)。

## Microsoft Store 版创建快捷方式
1. 打开 `开始菜单`，点击右上角的 `所有应用`。
2. 找到 `Lyricify Lite`，按住拖动到想要创建快捷方式的地方即可完成创建。

## 桌面歌词 或 灵动词岛 异常消失
打开 `桌面歌词` 或 `灵动词岛` 后，闪一下就消失了，或是在最小化所有窗口后消失。
### 导致原因
有全屏窗口处于前台。
### 解决方案
想办法关闭该全屏窗口 (如动态壁纸等)，或在设置中关闭 `全屏隐藏` 选项。

## 桌面歌词如何调整字号
纵向调整桌面歌词大小即可调整字号。

## 使用 OBS 捕获桌面歌词
因为这个功能的特殊性，所以没有在 `设置` 页面中提供修改选项，目前需要手动修改配置文件。
打开 `设置`，找到 `高级` `设置文件` `打开`，然后找到 `enable_obs_capture` 属性 (在 187 行附近)，将 `false` 修改为 `true` 后保存文件，然后点击 `加载` 即可。

## 自定义字体
Lyricify Lite 有着强大的自定义字体功能，您可以为 `灵动词岛` 和 `桌面歌词` 设置自定义字体。
如果您想要自定义字体，则可以通过以下步骤实现：
1. 设置中找到对应界面的 `字体家族` 设置，点击 `自定义` 按钮。
2. 这时会打开 `字体选择工具` 窗口，左侧为已安装字体列表，右侧为自定义字体列表。
3. 在左侧找到你想设置的字体，选中后点击 `添加到列表` 或直接双击该字体，即可添加至右侧自定义字体列表。
4. 点击确定即可保存。在保存之前，您可以在 `预览` 文本框中测试自定义字体效果。
5. 如果您想为中西文设置不同字体，可以自行了解 `字体回退机制`，Lyricify Lite 自带的 `字体选择工具` 支持 `字体回退 (Font Fallback)`。

**如果您想使用某字体的加粗版本，您可以这样设置：**  
1. 首先在 `字体选择工具` 中设置好字体（步骤在上方）。
2. 点击 `设置` 窗口 `高级` 页 `设置文件` 的 `打开` 按钮。
3. 在打开的文件中找到对应的字体配置。
   - 桌面歌词: `desktop_lyrics` `font_family`
4. 修改字体名，在字体名后加上 ` Bold`，如 `Microsoft YaHei` 修改后为 `Microsoft YaHei Bold`。

**注意：**  
1. 并非所有字体都支持这种修改为加粗版本的方式。
2. 如果有不理解的地方，您可以自行搜索和学习 `JSON 文件` 的相关知识。

## 自动更新
Lyricify Lite 支持自动更新，其策略如下。
### Microsoft Store 版本
Microsoft Store 版本的自动更新由 Microsoft 负责。  
Lyricify Lite 的默认策略是在启动时自动检查更新，有更新时会请求 Microsoft Store 进行静默更新，并在用户关闭 Lyricify Lite 或重启后完成更新。  
你可以在 Lyricify Lite 的设置中修改该策略。
### 非 Microsoft Store 版本 (GitHub 版本)
非 Microsoft Store 版本的自动更新由 Lyricify Lite 负责。  
Lyricify Lite 会在启动时自动检查更新，有更新时会立即下载更新并完成安装，更新过程会自动重启 Lyricify Lite。  
Lyricify Lite 默认开启自动更新，你可以在设置中修改该策略以停用普通更新。需要注意的是，版本过低时的强制更新不受该设置影响。

# 常见问题（逐应用）

## Spotify 用户应使用 Lyricify 4
对于 Spotify 用户，我们推荐使用 Lyricify 4，而不建议使用 Lyricify Lite。
### 具体原因
1. Lyricify 4 全称 Lyricify for Spotify，是专为 Spotify 研发的软件，针对 Spotify 提供了专门的优化，提升用户体验。
2. Lyricify 4 提供独立的词库，用户可以标记或上传准确的歌词，并对错误歌词进行修正。与之相比，Lyricify Lite 当前尚未接入 Lyricify 4 的词库，使用时体验较差。
3. Lyricify 4 不仅拥有更丰富的歌词展示界面，还包含诸如针对 Spotify 优化的全局快捷键、曲库查询、时间轴优化等更多实用功能。
### 更多信息
如果你仅使用 Lyricify Lite 的灵动词岛或桌面歌词功能配合 Spotify，仍然建议切换到 Lyricify 4。尽管它们在表面功能上相似，但在实际体验上，Lyricify 4 将为你提供更好的词库与功能支持。

## 使用 QQ 音乐时没有时间轴
在使用 QQ 音乐时，手动修改播放进度后，Lyricify Lite 无法更新播放进度，歌词发生前后错位。
### 导致原因
没有更新至支持 SMTC 时间轴的 QQ 音乐版本。
### 解决方案
更新 QQ 音乐至最新版，确保其版本号不低于 21.10.2962。

## 无法检测到 QQ 音乐
### 导致原因
QQ 音乐不是最新版，或未开启 SMTC。
### 解决方案
更新 QQ 音乐至最新版，并确保 SMTC 已启用（位置：`设置->常规设置->通知->显示系统媒体传输控件（SMTC）`）。

## 无法检测到网易云音乐
### 导致原因
网易云音乐 Win32 原版并不支持 SMTC。
### 解决方案
安装 [InfinityLink 插件](https://github.com/BetterNCM/InfinityLink)即可。

## 无法检测到酷狗音乐
### 导致原因
酷狗音乐不是最新版，或未开启 SMTC。
### 解决方案
更新酷狗音乐至最新版，并确保 SMTC 已启用（位置：`设置->常规设置->播放->支持系统播放控件，如锁屏界面`）。

## 无法检测到 PotPlayer
### 导致原因
PotPlayer 不是最新版，没有 SMTC 功能。
### 解决方案
更新 PotPlayer 至最新版，最低版本要求 240618。

# 附录

## Lyricify 名词
请规范使用 Lyricify 正确的名称或专有名词来描述反馈、提问。自行造词会带来很多麻烦和困惑。  

### 功能
| 名称 | 描述 |
| - | - |
| 灵动词岛 | 外观与“灵动岛”和刘海有关的用于显示歌词的悬浮窗口，“灵动岛”“灵动岛歌词” 等是不被 Lyricify 认同的说法 |
| 桌面歌词 | 桌面歌词，“悬浮歌词”是不被 Lyricify 认同的说法 |

### 灵动词岛
| 名称 | 描述 |
| - | - |
| 单词发光效果 | 简称“发光效果”，播放到时长较长单词时的发光效果，“辉光效果”是不被 Lyricify 认同的说法 |

### 其它
| 名称 | 描述 |
| - | - |
| 歌词 | 歌词，“字幕”是不被 Lyricify 认同的说法 |
| Lyricify | Lyricify 的名称是 “Lyricify”，“ly”“Ly”“Lyr”“Liricify”“Lyricfy” 等是不被 Lyricify 认同的说法 |
| Lyricify Lite | Lyricify Lite 的名称是 “Lyricify Lite”，“ly lite” 等是不被 Lyricify 认同的说法 |
