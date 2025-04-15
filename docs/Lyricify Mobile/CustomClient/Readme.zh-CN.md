<div align="center">

# 自定义 Spotify API Client 配置教程

</div>

## 自定义 Spotify API Client 的好处
不再会因 Spotify API 返回 429 错误而影响 Lyricify 使用体验。

## 准备步骤
如果你已经完成过准备步骤，则可以直接使用之前获得的 `Client ID` 和 `Client Secret`，在 `Lyricify Mobile 上的工作` 中使用。
1. 在浏览器中登录 Spotify (https://www.spotify.com) ，如果你已登录，可进入步骤 2。
2. 打开 https://developer.spotify.com/dashboard ，如果你是第一次打开这个网址，则需要先同意 Spotify Developer Terms。勾选下方的 `I accept the Spotify Developer Terms of Service`，再点击 `Accept the terms` 即可。
![](pic/Demo-Pic01.png)
3. 点击 Dashboard 页面右上方的 `Create app`。  
   如果提示 `You need to verify your email address before you can create an app.`，则需要你先验证你的邮箱。
![](pic/Demo-Pic02.png)
4. 在 Create app 页面中填写以下信息：
   - App name: Lyricify
   - App description: Lyricify Custom API Client
   - Website: （空着不写）
   - Redirect URI: （填写以下两条，每条填写完成后点击 `Add` 按钮）
     - http://127.0.0.1:766/callback
     - lyricify://callback
5. 勾选 `Which API/SDKs are you planning to use?` 部分中的 `Web API`；  
   勾选 `I understand and agree with Spotify's Developer Terms of Service and Design Guidelines`；  
   点击 `Save` 按钮。  
![](pic/Demo-Pic03.png)
6. 这时你就能看到 Client ID，点击 `View client secret`，即可显示 Client secret。在后续步骤中将需要用到 `Client ID` 和 `Client Secret`。
![](pic/Demo-Pic04.png)

## Lyricify Mobile 上的工作
1. 如果你已经在 Lyricify Mobile 中登录了 Spotify，则需要在打开 Lyricify Mobile 后，进入登录界面时点击 `取消`。
2. 在欢迎界面 `自定义 API Client` 区域对应处输入准备步骤中获取到的 `Client ID` 和 `Client Secret`。
3. 点击 `登录 (获取 Token)`，重新完成登录和授权即可。

# 常见问题

## 授权时提示 INVALID_CLIENT: Invalid redirect URI
请检查 `Redirect URI` 是否填写错误，确保其值包含 `lyricify://callback` 和 `http://127.0.0.1:766/callback`，而不是 `https://127.0.0.1:766/callback`。  
如果你是在 Android 或 iOS 设备上使用，请确保其值包含 `lyricify://callback`。

### 特别注意
如果你**在 2025 年 4 月 9 日前**创建并配置过自定义 API Client，请务必前往 Spotify Developer Dashboard 更新设置。由于 Spotify 调整了对重定向 URI 的要求，**原本使用 `localhost` 的 URI 已不再被接受**，你需要将原先的：

```
http://localhost:766/callback
```

替换为：

```
http://127.0.0.1:766/callback
```

请进入对应应用的设置页面，并在 `Redirect URI` 中添加 `http://127.0.0.1:766/callback`。完成后即可正常使用自定义 API Client 进行授权。  

> ⚠️ 注意：`127.0.0.1` 是 `localhost` 的等效 IP 地址，在当前 Spotify 的校验机制中被视为有效地址，而 `localhost` 会被拒绝。

## 授权时提示 INVALID_CLIENT: Insecure redirect URI
近期，Spotify 正式强制执行新的登录授权政策，要求使用更安全的重定向 URI。这一变更已影响到 Lyricify 系列中的 Lyricify 4 和 Lyricify Mobile，而 Lyricify 3 也将在 2025 年 11 月起受到影响。  

Lyricify Mobile 使用了非 HTTP 协议的重定向 URI（lyricify://callback），理论上仍符合 Spotify 的新安全要求。然而，目前 Spotify 存在误判问题，将这类 URI 错误地视为不安全并阻止授权流程。  

对于 2025 年 4 月 9 日之后创建的应用，将直接遭遇授权被拦截的问题。目前已有开发者在 Spotify 社区中反馈此问题，但尚未获得官方修复。  

欢迎你前往下方链接留言反馈，帮助推动问题尽快得到解决：https://community.spotify.com/t5/Spotify-for-Developers/Web-API-authetication-after-2025-04-09/td-p/6915683  
关联 issue：https://github.com/WXRIW/Lyricify-App/issues/483  