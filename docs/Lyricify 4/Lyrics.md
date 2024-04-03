# Lyricify 4 歌词指南及标准

Lyricify 4 目前支持的歌词格式有 LRC、QRC、YRC、Lyricify Syllable、Apple Syllable。  
下文中将详细说明 Lyricify 4 的歌词格式标准，及自制歌词指南。  

## 歌词格式简介

| 格式 | 特点 | 备注 |
| :-: | - | - |
| LRC | 记录每行歌词的起始时间，制作方便 | 只能实现逐行歌词 |
| QRC | 记录每个单词/字的起始时间和时长 | 逐字歌词，但制作复杂耗时 |
| YRC | 记录每个单词/字的起始时间和时长 | 网易云音乐的逐字歌词格式，目前不支持手动导入 |
| Lyricify Lines | 记录每行歌词的起始时间和结束时间 | Lyricify 的逐行歌词格式 |
| Lyricify Syllable | 记录每个音节或单词的起始时间和时长，记录每行歌词的背景人声和对唱视图信息 | Lyricify 的逐音节歌词格式 |
| Apple Syllable | 记录字词句段的起始时间和结束时间，记录每行歌词的演唱者信息，记录背景人声信息 | Apple Music 逐音节歌词，管理员可以导入 |

## LRC 格式规范

### 头部信息
歌词头部可选的包含歌词相关信息，如：  
```
[ti:Counting Stars]
[ar:OneRepublic]
[al:Native]
[by:Wang]
[offset:0]
```
*注意：不要包含重复标签。*  

### 歌词
LRC 歌词的标准格式为：
```
[timestamp]lyrics
```

`timestamp` 是时间戳，表示本行歌词的起始时间。  
这里的时间戳应遵循 ISO 8601 标准，格式为 `mm:ss.sss`，不可以写成 `mm:ss:sss`。  

下方是一个示范：
```
[01:17.870]Lately, I've been, I've been losing sleep
[01:21.390]Dreaming about the things that we could be
[01:25.390]But baby, I've been, I've been praying hard
[01:29.390]Said no more counting dollars
[01:31.210]We'll be counting stars
```
**注意：**
1. LRC 歌词不允许重复时间轴，但是允许同一句歌词有多个时间轴，见下方案例：
   ```
   不允许：
        [01:17.870]Lately, I've been, I've been losing sleep
        [01:17.870]Dreaming about the things that we could be
   允许：
        [00:01.670][01:17.870][02:28.640]Lately, I've been, I've been losing sleep
        [00:04.850][01:21.390]Dreaming about the things that we could be
   ```
2. LRC 歌词允许乱序时间轴，如：
   ```
   [01:25.390]But baby, I've been, I've been praying hard
   [01:21.390]Dreaming about the things that we could be
   [01:29.390]Said no more counting dollars
   [01:17.870]Lately, I've been, I've been losing sleep
   ```
3. 如果两句歌词之间的音乐间隔较长（如大于 5s），则建议加入空白行，时间戳为上一句的结束时间，这样可以实现 Lyricify 4 中 Apple Music 歌词界面里的“呼吸点”效果。
   ```
   [00:16.36]We'll be counting stars
   [00:19.28]Yeah we'll be counting stars
   [00:22.89]
   [00:38.05]I see this life like a swinging vine
   [00:40.67]Swing my heart across the line
   ```
4. 在最后一句歌词后可以加入一个空白行，时间戳为最后一句歌词的结束时间。
   ```
   [04:11.66]Sink in the river
   [04:12.60]The lessons I've learned
   [04:13.79]
   ```

### 制作工具
推荐您使用下列工具来制作 LRC 歌词。
- 歌词滚动姬 (https://lrc-maker.github.io/)
- BesLyric (https://github.com/BesLyric-for-X/BesLyric)
- BesLyric-for-X (https://github.com/Beslyric-for-X/Beslyric-for-X)

## QRC 格式规范

### 头部信息
QRC 的歌词头部信息参考 LRC 标准，这里不再重复。

### 歌词
QRC (Lyricify 标准) 歌词的标准格式为：
```
[start,duration]Word (start,duration)word(start,duration)
```
`start` 为起始时间，`duration` 为时长。  
`[]` 中的时间戳为整行歌词的起始时间和时长。  
`()` 中的时间戳为前方单词的起始时间和时长。  
时间戳是大于零的整数，单位是毫秒 (ms)。  
  
这是一个示范：
```
[358,4575]Lately (358,1336)I've (1694,487)been, (2181,673)I've (2854,268)been (3122,280)losing (3402,345)sleep(3747,1186)
[5245,3864]Dreaming (5245,696)about (5941,471)the (6412,306)things (6718,458)that (7176,292)we (7468,511)could (7979,393)be(8372,737)
```
**注意：**
1. QRC (Lyricify 标准) 歌词不允许重复时间轴，也不允许乱序时间轴。歌词应按照时间排序（背景人声除外，具体将在后文中 `背景人声的制作` 部分介绍）。
2. QRC (Lyricify 标准) 歌词允许歌词时间段重叠（即多行高亮），如：
   ```
   [124571,2326]Won't (124571,575)we? (125146,459)Yeah(126404,493)
   [125613,1118]Won't (125613,483)we?(126096,635)
   ```

### 制作工具
不推荐您手动制作 QRC 歌词，因为手动打轴十分艰难，会让您无法坐和放宽，且精确度不高。  
如果您仍想尝试自行制作 QRC 歌词，则推荐您使用下列工具。  
- ALRC (https://github.com/kengwang/ALRC)
- QRC Lyric Maker (https://github.com/BPTPW/qrc-Lyric-Maker)
- Lyricify 逐字行创造器 (Lyricify 4 内嵌，不建议使用)

**注意：**
这些工具都很粗糙，只能提供非常有限的功能，并且会有很多问题，所以强烈建议不要使用。

## YRC 格式规范
`Lyricify 歌词库` 不支持 YRC 歌词的导入。本部分仅为 YRC 格式的介绍。

### 头部信息
YRC 的歌词头部信息可包含 `作词`、`作曲` 等。下方是一个示例：
```
{"t":0,"c":[{"tx":"作词: "},{"tx":"Brent Kutzle"},{"tx":"/"},{"tx":"Tyler Spry"},{"tx":"/"},{"tx":"Steven Mudd"},{"tx":"/"},{"tx":"Ryan Tedder","li":"http://p1.music.126.net/S06CeorJXg0Rgb6KhTB9pQ==/18969874114079440.jpg","or":"orpheus://nm/artist/home?id=42602&type=artist"},{"tx":"/"},{"tx":"Josh Varnadore"}]}
{"t":1000,"c":[{"tx":"作曲: "},{"tx":"Brent Kutzle"},{"tx":"/"},{"tx":"Tyler Spry"},{"tx":"/"},{"tx":"Steven Mudd"},{"tx":"/"},{"tx":"Ryan Tedder","li":"http://p1.music.126.net/S06CeorJXg0Rgb6KhTB9pQ==/18969874114079440.jpg","or":"orpheus://nm/artist/home?id=42602&type=artist"},{"tx":"/"},{"tx":"Josh Varnadore"}]}
```
具体含义自行理解。

### 歌词
YRC 歌词的标准格式为：
```
[start,duration](start,duration,0)Word (start,duration,0)word
```
`start` 为起始时间，`duration` 为时长。  
`[]` 中的时间戳为整行歌词的起始时间和时长。  
`()` 中的时间戳为后方单词的起始时间和时长。  
时间戳的是大于零的整数，单位是毫秒 (ms)。  
  
这是一个示范：
```
[54260,3090](54260,900,0)Stop (55160,480,0)and (55640,1710,0)stare
[57380,5130](57380,150,0)I (57530,600,0)think (58130,180,0)I'm (58310,690,0)moving (59000,420,0)but (59420,150,0)I (59570,690,0)go (60260,2250,0)nowhere
[62840,4800](62840,450,0)Yeah (63290,120,0)I (63410,510,0)know (63920,360,0)that (64280,1260,0)everyone (65540,330,0)gets (65870,1770,0)scared
[67730,5670](67730,360,0)But (68090,360,0)I've (68450,690,0)become (69140,270,0)what (69410,210,0)I (69620,1050,0)can't (70670,2730,0)be
```

## Lyricify Lines 格式规范

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

## Lyricify Syllable 格式规范

### 头部信息
Lyricify Syllable 的歌词头部信息参考 LRC 标准，这里不再重复。

### 歌词
Lyricify Syllable 歌词的标准格式为：
```
[property]Word (start,duration)word(start,duration)
```
`property` 为歌词行属性信息。  
`start` 为起始时间，`duration` 为时长。  
`()` 中的时间戳为前方单词的起始时间和时长。  
时间戳的是大于零的整数，单位是毫秒 (ms)。  

#### 歌词行属性信息
| 属性 | 背景人声 | 对唱视图 |
| :-: | :-: | :-: |
| 0 | 未设置 | 未设置 |
| 1 | 未设置 | 左 |
| 2 | 未设置 | 右 |
| 3 | 否 | 未设置 |
| 4 | 否 | 左 |
| 5 | 否 | 右 |
| 6 | 是 | 未设置 |
| 7 | 是 | 左 |
| 8 | 是 | 右 |
  
这是一个示范：
```
[0]Lately (358,1336)I've (1694,487)been, (2181,673)I've (2854,268)been (3122,280)losing (3402,345)sleep(3747,1186)
[0]Dreaming (5245,696)about (5941,471)the (6412,306)things (6718,458)that (7176,292)we (7468,511)could (7979,393)be(8372,737)
```
**注意：**
Lyricify Syllable 的注意参考 QRC (Lyricify 标准) 标准，这里不再重复。

### 制作工具
不推荐您手动制作 Lyricify Syllable 歌词，因为手动打轴十分艰难，会让您无法坐和放宽，且精确度不高。  
如果您仍想尝试自行制作 Lyricify Syllable 歌词，则推荐您使用下列工具。 
- AMLL TTML Tool (https://steve-xmh.github.io/amll-ttml-tool)

## Apple Syllable 格式规范
略 

## 背景人声的制作
目前只有 QRC (Lyricify 标准)、Lyricify Syllable 和 Apple Syllable 支持“背景人声”。

### QRC 歌词
在 Lyricify 标准下的 QRC 歌词，如符合下列规则，将显示为“背景人声”。  
1. 歌词以 `(` 或 `（` 开头，`)` 或 `）` 结束。
2. 歌词的前一行和后一行均不符合 `规则 1`。

**注意：**
`背景人声` 歌词行应放在其主歌词行的下方，即使它的时间戳比主歌词行更早。  
下方是几个示例：
```
[122385,1295]Yeah, (122385,343)won't (122728,451)we?(123179,501)
[123680,780](Won't (123680,483)we?)(124163,297)
[124571,2326]Won't (124571,575)we? (125146,459)Yeah(126404,493)
[125613,1118](Won't (125613,483)we?)(126096,635)
```
```
[97648,4632]The (97648,384)scars (98032,565)of (98597,552)your (99149,581)love (99730,302)remind (100032,882)me (100914,584)of (101498,483)us(101981,299)
[96826,3715](You're (96826,333)gonna (97159,299)wish (97458,435)you (97893,347)never (99159,267)had (99426,301)met (99727,416)me)(100143,398)
[102285,4362]They (102285,315)keep (102600,568)me (103168,568)thinking (103736,565)that (104301,286)we (104587,298)almost (104885,584)had (105469,299)it (105768,269)all(106037,610)
[101381,3758](Tears (101381,381)are (101762,318)gonna (102080,384)fall, (102464,359)rolling (103746,518)in (104264,349)the (104613,149)deep)(104762,377)
```

### Lyricify Syllable
若 `歌词行属性信息` 中“背景人声”信息为未设置，则会按照 QRC 歌词的背景人声标准来判断。

### Apple Syllable
略，原生支持。
