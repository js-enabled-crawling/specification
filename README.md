# Specification for JavaScript-enabled Crawling

Google made a leap forward by executing JavaScript when crawling the internet. However, developers of JavaScript-heavy websites and Single Page Applications can't make use of it because no other crawler executes JavaScript, yet. This is understandable since JS-enabled crawling involves some heavy lifting. Nonetheless, Google found a sweet spot by most importantly cutting off AJAX calls. This way crawlers and web developers can meet in the middle.

This specification shall allow implementors of crawlers to follow Google's lead and provide a contract for framework and website developers to rely on.

*Read more about the motivation in this [blog post](http://www.analog-ni.co/precomposing-a-spa-may-become-the-holy-grail-to-seo).*

---

Go to the [current draft of the specification](specification.md).

---

## Contributing

You may:

- Star this project to add your voice to this community effort,
- [![Gitter](https://badges.gitter.im/Join Chat.svg)](https://gitter.im/js-enabled-crawling/specification?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
- Open an issue to give feedback and discuss certain aspects of the specification, and
- Create a pull request based on an issue of which the discussion came to a resolution.

New core contributors are always welcome!