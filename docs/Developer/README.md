# Lyricify 开发者文档

注意：本计划暂时搁置，短期内不考虑启动！

Lyricify 将会在未来择期开放 Lyricify 词库，欢迎更多开发者使用 Lyricify 词库，让歌词传播变得更轻松。  
“Lyricify 开放词库”，后文简称“词库”。

## 了解 Lyricify 开放词库
Lyricify 开放词库，是以 Lyricify 4 歌词库为基础的供开发者接入歌词软件用途使用的开放的只读性词库。  
词库包含了由 Lyricify 用户标记和上传的歌词，由 Lyricify 歌词库、QQ 音乐歌词、网易云音乐歌词组成。  

### 词库特点
- 提供多种可用信息，包括歌词原文、时间轴、标题行、对唱视图、创作者等信息。为歌词显示带来充足的数据支撑。
- 由 Lyricify 4 管理员管理，Lyricify 4 全体用户建立，具有高可靠性、高可用性等优势

## 接入 Lyricify 开放词库
Lyricify 开放词库欢迎所有热爱 Lyricify 的开发者使用。  
下方将介绍词库的相关信息规格，及使用要求和限制。

### 词库接口
`GET http://......../..../....`  
需传入的参数：
- id: Spotify 曲目 ID
- isrc: 曲目的 ISRC
- user: Lyricify 用户信息

### 词库信息
通过词库接口，可以获取到 Json 格式返回的信息，下方是一个示例：  
```
{
    "writer": "Ryan Tedder",
    "isInstrumental": false,
    "text": "[type:LyricifyLines]\n[140,2250]Used to pray for a moment just like this\n[2250,4416]There's a fire in your eyes I can't resist\n",
    "trans": "[00:00.140]我曾祈祷着这一刻\n[00:02.250]火焰划过你的眼眸 而我无法抗拒\n",
    "offset": 0,
    "titleLines": 0,
    "endingLines": 0,
    "duetProperties": "00"
}
```

### 歌词格式
为了方便开发者使用歌词，使反序列化更加容易，歌词将以两种格式中的一种返回：`LRC 格式` 或 `Lyricify Lines 格式`  
LRC 标准详见 [Lyricify 4 歌词指南及标准](https://github.com/WXRIW/Lyricify-App/blob/main/docs/Lyricify%204/Lyrics.md)。  
Lyricify Lines 格式详见附录《Lyricify Lines 格式规范》。  

### 词库使用
接入词库，需要遵守以下规则。  
1. 仅可将本词库用于“歌词显示”用途，不可用于其他任何用途。如有其他用途，请联系 Lyricify 词库。
2. 将本词库作为唯一词库、主词库或非备用词库 (备用词库：当所有可用词库都无法找到歌词时才调用的词库) 作用接入的，有以下规则：
   1. 须在明显处显示 “歌词提供者: Lyricify 词库” (英文: Lyrics provided by Lyricify Lyrics Vault)，并设置跳转链接，跳转至 https://github.com/WXRIW/Lyricify-App 。
   2. 须在软件启动时显示 Powered by Lyricify (中文: 由 Lyricify 驱动)。
   3. 建议在软件名中包含 Lyricify 字样，这里有几个优秀的示范：Lyricify XXX, XXX with Lyricify。不要使用 by Lyricify 作为末尾。
   4. 当词库没有歌词时，需引导用户在 Lyricify 4 上导入歌词，附上教程链接。
3. 将本次库作为备用词库接入的，有以下规则：
   1. 须在明显处显示 “歌词提供者: Lyricify 词库” (英文: Lyrics provided by Lyricify Lyrics Vault)，并设置跳转链接，跳转至 https://github.com/WXRIW/Lyricify-App 。
   2. 当词库没有歌词时，需引导用户在 Lyricify 4 上导入歌词，附上教程链接。

# 附录

## Lyricify Lines 格式规范
本部分为 Lyricify Lines 格式的介绍。

### 头部信息
Lyricify Lines 的歌词头部会带有 `[type:LyricifyLines]` 的标记。

### 歌词
Lyricify Lines 歌词的标准格式为：
```
[start,end]Lyrics
```
`start` 为起始时间，`end` 为结束时间。  
时间戳的是大于零的整数，单位是毫秒 (ms)。  
  
这是一个示范：
```
[54260,57380]Stop and stare
[57380,62840]I think I'm moving but I go nowhere
[62840,67730]Yeah, I know that everyone gets scared
[67730,73370]But I've become what I can't be
```