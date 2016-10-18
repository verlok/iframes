# iframe pros and cons + examples

An Inline Frame is an HTML document embedded into another website.

iFrames are made for embedding other websites in your site (e.g. embedding codepen snippets, slides from slideshare, and previously maps and videos).

## General best practices

+ isolated page components
+/- increases security when embedding third party untrusted components

Application issues

- messages can't exit the iframe, harder for components to talk to each other
- events don't bubble out
- state management is difficult or impossible
- session and cookie management/sharing is different across browsers
	- how do we manage country exceptions?
	- how do we manage languages and translations?
- general increased complexity
- can js talk to other frames? **TBV**

## Design/interface

- css of parent website is not inherited from the iframe
	- how do we make the form look exactly like other forms in the website?
- responsive design is extremely difficult because each frame is a new viewport and media queries won't match
- hindered design flexibility if submit button is inside the iframe
- iframe must have a width and a height, content that overflows will scroll, content that is smaller will leave space
- forces a new scollbar **TBV**

## Performance

+ download assets in parallel (we can do this without iframes)
- iframes are separate documents, so more resources needs to be downloaded, load event arrives later
- browsers need to render 2 documents and 2 browser contexts
- browser will request same files multiple times, and browser caching isn't guaranteed

## Accessibility

- keyboard interaction is impossible if submit button is outside the iframe
- non-semantic

# Conclusion

As the cons are much more than the pros, it's strongly unadvisable to use them as an integral part of your site.