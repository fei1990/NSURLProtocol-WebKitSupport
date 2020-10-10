# NSURLProtocol+WebKitSupport

> Note：If you target iOS 11, you can now use [WKURLSchemeHandler](https://developer.apple.com/documentation/webkit/wkurlschemehandler) to avoid this trick! 😆

[让 WKWebView 支持 NSURLProtocol](https://blog.yeatse.com/2016/10/26/support-nsurlprotocol-in-wkwebview/)

[WKWebView的那些坑](https://toutiao.io/posts/yy19e7/preview)

[关于WKWebView的post请求丢失body问题的解决方案
](https://www.jianshu.com/p/4dfc80ca7db2)

This example project shows a way to use NSURLProtocol with WKWebView, which was not possible before.

# Screenshot

![](snapshot.gif)

# Usage

Drag `NSURLProtocol+WebKitSupport.h` and `NSURLProtocol+WebKitSupport.m` into your project, then register the scheme for NSURLProtocol to handle:

```objc
[NSURLProtocol wk_registerScheme:@"https"];

// You can now use your own NSURLProtocol subclasses as before.
[NSURLProtocol registerClass:[MyAwesomeURLProtocol class]];
```

To remove the scheme from registery:

```objc
[NSURLProtocol wk_unregisterScheme:@"https"];
```

# Note

This category uses undocumented APIs in WebKit. Use at your own risk.
