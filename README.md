# iframe pros and cons + examples

An Inline Frame is an HTML document embedded into another website.

iFrames are made for embedding other websites in your site (e.g. embedding codepen snippets, slides from slideshare, and previously maps and videos).

## General

+ + isolated page components
+ +/- increases security when embedding third party untrusted components

## Application issues

Web

- - events don't bubble out ot the iframe, harder for components to talk to each other
- - state management is difficult or impossible 
- - session and cookie management/sharing is different across browsers -> very difficult to manage country exceptions / translations / user saved settings inside the iframe 
- - general increased complexity

Native

- - no guaranteed support for iframe in next versions of embedded browsers
- - double development and maintenance for webpage embedded iframe and WebView embedded in native app
- - harder to manage iframe failures due to connectivity issues
- -	3rd party payment services could require to integrate native SDKs provided by the vendor itself, making it easy to add payments to mobile apps. For example PayPal provides an iOS SDK (https://github.com/paypal/PayPal-iOS-SDK) which offers usability and user experience consistency through native components.

## Design/interface

Web

- - css of parent website is not inherited from the iframe -> very hard to seamlessly integrate content of iframe
- - responsive design is extremely difficult because each frame is a new viewport and media queries won't match
- - hindered design flexibility if submit button is inside the iframe
- - iframe must have a width and a height, content that overflows will scroll, content that is smaller will leave space

Native

- - need to use REST API to create tailor-made per brand UX/UI interfaces
- - layout can change per brand/app and must adapt to each possible device/resolutions

## Performance

Web

- + download assets in parallel (it can be done this without iframes in 2016)
- - iframes are separate documents, so more resources needs to be downloaded, load event arrives later
- - browsers need to render 2 documents and 2 browser contexts
- - browser will request same files multiple times, and browser caching isn't guaranteed

Native

- - Slower interaction because we need to use a webview (useless middle layer)

## Accessibility

Web

- - keyboard interaction is harder if submit button is outside the iframe
- - non-semantic

Native

- - Voiceover implications to be analyzed in depth (how does it read a webview inside an app)

# Conclusion

As the cons are much more than the pros, it's strongly unadvisable to use them as an integral part of your site.
