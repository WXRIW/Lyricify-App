<div align="center">

# Custom Spotify API Client Configuration Tutorial
[简体中文](Readme.zh-CN.md)

</div>

## Benefits from customising Spotify API Client
Spotify API won't affect you by returning 429 Error anymore.

## Preparations
If you have already completed the preparation steps, you can directly use the previously obtained `Client ID` and `Client Secret` in `Works on Lyricify Mobile` part.
1. Login to Spotify (https://www.spotify.com) in your browser, if you have already logged in, go to step 2.
2. Open https://developer.spotify.com/dashboard, if this is your first navigation to this website, you will need to agree with Spotify Developer Terms. Just check `I accept the Spotify Developer Terms of Service` and click `Accept the terms`.
![](pic/Demo-Pic01.png)
3. Click `Create app` in Dashboard's right top corner.  
   If you are prompted with `You need to verify your email address before you can create an app.`, you need to verify your email address first.
![](pic/Demo-Pic02.png)
4. Fill Create app page with these:
   - App name: Lyricify
   - App description: Lyricify Custom API Client
   - Website: (Leave it empty)
   - Redirect URI:
     - http://localhost:766/callback
     - lyricify://callback
5. Check `Web API` in `Which API/SDKs are you planning to use?` section;  
   Check `I understand and agree with Spotify's Developer Terms of Service and Design Guidelines`;  
   Click `Save`.  
![](pic/Demo-Pic03.png)
6. Click `Settings` at the right top corner.
7. Now you can see your Client ID，Click `View client secret` to show the Client secret. `Client ID` and `Client Secret` are needed in future steps.
![](pic/Demo-Pic04.png)

## Works on Lyricify Mobile
1. If you have already logged Spotify in Lyricify Mobile, then you will need to click Cancel button at open.
2. Enter `Client ID` and `Client Secret` you previously obtained in welcome page's `Custom API Client` part.
3. Click Login (Get Token), finish the login and authorization, and you are good to go.