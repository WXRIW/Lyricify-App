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
| QQ 音乐 | 无时间轴信息 | 较好 |  |
| QQ 音乐 UWP | 一般，信息提供不稳定 | 较好 |  |
| 网易云音乐 | 无时间轴信息 | 较好 | 需安装额外的[插件](https://github.com/BetterNCM/InfinityLink) |
| 网易云音乐 UWP | 较好 | 较好 |  |
| 酷狗音乐 | 无时间轴信息 | 较好 |  |
| Groove Music | 时间轴完美；曲目信息取决于具体曲目 | 一般，取决于具体文件 |  |
| Foobar 2000 | 无时间轴信息；曲目信息取决于具体曲目 | 一般，取决于具体文件 |  |
| Google Chrome | 时间轴较好；曲目信息取决于具体播放内容 | 一般，取决于具体内容 | 默认不启用 |
| Microsoft Edge | 时间轴较好；曲目信息取决于具体播放内容 | 一般，取决于具体内容 | 默认不启用 |

**注意：**
1. 请确保相关 app 已更新至最新版本，部分旧版本可能并不支持 SMTC。
2. 对于 SMTC 无时间轴信息的 app，Lyricify Lite 将使用内置定时器更新歌词进度，所以在手动修改播放进度后，Lyricify Lite 无法更新播放进度，歌词会发生前后错位。
3. 曲目匹配“完美”指 Lyricify Lite 可以完美匹配当前播放的曲目。其它匹配程度指 Lyricify Lite 需要通过对曲目信息进行搜索来匹配对应曲目，所以匹配可能不精准或匹配不到。
4. 所有接入 SMTC 的应用均支持 Lyricify Lite，未列在上述表格中的应用也可能支持 Lyricify Lite。

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
2. 独享中国大陆加速服务器。
  
在 Microsoft Store 购买 Lyricify 是对 Lyricify 开发者的一种支持和信任，感谢所有购买或打赏过 Lyricify 的用户！也欢迎各位用户给出 5 星好评和评语，这对我有很大帮助！  

### 更多信息
Lyricify Lite 是免费软件，如果你觉得 Lyricify Lite 做的不错，则可以通过以下渠道支持：
- 在软件中，菜单-关于页里有打赏方式
- 在 [Microsoft Store](https://apps.microsoft.com/store/detail/9NLTPSV395K2?launch=true&mode=full) 中购买

如果您在 Microsoft Store 购买过程中遇到困难，可以考虑通过打赏的方式支持 Lyricify。  

如果你发现有人在非法销售本软件 (只有 Microsoft Store 中的 Lyricify 是官方发布)，请联系我们！感谢你的支持！

## Microsoft Store 版创建快捷方式
1. 打开 `开始菜单`，点击右上角的 `所有应用`。
2. 找到 `Lyricify Lite`，按住拖动到想要创建快捷方式的地方即可完成创建。

## 桌面歌词 或 灵动词岛 异常消失
打开 `桌面歌词` 或 `灵动词岛` 后，闪一下就消失了，或是在最小化所有窗口后消失。
### 导致原因
有全屏窗口处于前台。
### 解决方案
想办法关闭该全屏窗口 (如动态壁纸等)，或在设置中关闭 `全屏隐藏` 选项。

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
