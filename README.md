#cordova-plugin-inappbrowser-wkwebview

- This is a fork of [cordova-plugin-inappbrowser](https://github.com/apache/cordova-plugin-inappbrowser) 
- It uses the the newer [WKWebview](https://developer.apple.com/documentation/webkit/wkwebview) to power the InAppBrowser, in contrast to `cordova-plugin-inappbrowser` which still currently uses the legacy [UIWebView](https://developer.apple.com/documentation/uikit/uiwebview).
- Only the iOS platform has been changed from the original `cordova-plugin-inappbrowser`.
- The plugin supports iOS 9 and above
    - While WKWebView was introduced in iOS 8, it contained critical bugs making it effectively unusable for Cordova-based apps
    
Some advantages of using WKWebView over UIWebView include:

- Performance: graphic-intensive operations such as WebGL run much faster and more efficiently in WKWebView.
- Stability: WKWebView has many improvements which leads to up to 70% less crashes.
- Shared cookies: setting a cookie in an IAB window makes it available in the main Cordova Webview and vice-versa. This is especially useful for cookies that store authentication credentials since they will be preserved between IAB sessions.
    
## Installation

    cordova plugin add cordova-plugin-inappbrowser-wkwebview
    cordova plugin add cordova-plugin-wkwebview-engine

- This plugin depends on [cordova-plugin-wkwebview-engine](https://github.com/apache/cordova-plugin-wkwebview-engine) which adds WKWebView support to Cordova.
- You need to add this (or a variant) manually to your project
- This means the main Cordova app Webview will also use WKWebView on iOS 9+.


## Plugin usage and API

The plugin API is identical to [cordova-plugin-inappbrowser](https://github.com/apache/cordova-plugin-inappbrowser).