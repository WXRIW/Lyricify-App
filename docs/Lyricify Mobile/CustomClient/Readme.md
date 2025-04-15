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
     - http://127.0.0.1:766/callback
     - lyricify://callback
5. Check `Web API` in `Which API/SDKs are you planning to use?` section;  
   Check `I understand and agree with Spotify's Developer Terms of Service and Design Guidelines`;  
   Click `Save`.  
![](pic/Demo-Pic03.png)
6. Now you can see your Client ID，Click `View client secret` to show the Client secret. `Client ID` and `Client Secret` are needed in future steps.
![](pic/Demo-Pic04.png)

## Works on Lyricify Mobile
1. If you have already logged Spotify in Lyricify Mobile, then you will need to click Cancel button at open.
2. Enter `Client ID` and `Client Secret` you previously obtained in welcome page's `Custom API Client` part.
3. Click Login (Get Token), finish the login and authorization, and you are good to go.

# Common Issues

## Error during authorization: INVALID_CLIENT: Invalid redirect URI
Please check if the `Redirect URI` is entered correctly. Make sure it includes both `lyricify://callback` and `http://127.0.0.1:766/callback`, and **not** `https://127.0.0.1:766/callback`.  
If you're using an Android or iOS device, be sure to include `lyricify://callback` in the `Redirect URI`.

### Important Note
If you **created and configured your custom API Client before April 9, 2025**, please make sure to update your app settings in the Spotify Developer Dashboard. Due to recent changes in Spotify's redirect URI validation, **URIs using `localhost` are no longer accepted**. You need to replace the original:

```
http://localhost:766/callback
```

with:

```
http://127.0.0.1:766/callback
```

Go to your app’s settings page, and add `http://127.0.0.1:766/callback` under the **Redirect URIs** section. Once updated, your custom API Client should work properly during authorization.

> ⚠️ Note: `127.0.0.1` is the IP address equivalent of `localhost`. Under Spotify's current validation rules, `127.0.0.1` is accepted, while `localhost` is not.

## Authorization Error: INVALID_CLIENT: Insecure redirect URI
Recently, Spotify has officially enforced a new login authorization policy requiring the use of more secure redirect URIs. This change has impacted the Lyricify series, including Lyricify 4 and Lyricify Mobile, and Lyricify 3 will also be affected starting from November 2025.  
 
Lyricify Mobile uses a non-HTTP redirect URI (`lyricify://callback`), which, in theory, still complies with Spotify's new security requirements. However, Spotify is currently experiencing a misjudgment issue, mistakenly identifying such URIs as insecure and blocking the authorization flow.

For applications created after April 9, 2025, this issue will cause immediate authorization failures. Developers have already reported the problem in the Spotify Community, but no official fix has been provided yet.

You're welcome to leave a comment at the following link to help accelerate the resolution of this issue:  
https://community.spotify.com/t5/Spotify-for-Developers/Web-API-authetication-after-2025-04-09/td-p/6915683  

Related issue: https://github.com/WXRIW/Lyricify-App/issues/483