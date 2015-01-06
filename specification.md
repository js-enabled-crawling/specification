# JS-enabled Crawling

**A community-formulated contract for crawling JavaScript-heavy websites.**

---

This specification is in alpha. Do not base your implementation on it, yet!

---

This specification aims to define a contract between crawlers and websites that:

- Allows crawlers to execute JavaScript to an extend to which their resources are still conserved,
- Allows websites to serve the same sources to humans and to crawlers with minimal development effort to conform to this specification.

Since the Googlebot pioneered the field of executing JavaScript and thus demonstrated the feasibility of its design this specification is geared towards it.

## 1. Terminology

TODO

## 2. The Contract

1. A website shall indicate to a crawler that it should execute JavaScript according to this contract by including `<meta name="js-enabled-crawling" content="!">` in the HTML page.
2. If the website also includes `<meta name="fragment" content="!">` the crawler should ignore this tag if it supports this contract.
3. The crawler shall execute JavaScript to the following extend:
	a. It shall load and execute all JavaScript scripts referenced or inlined through `<script>` tags.
	b. It shall wait until all registered handlers for the `window.load` event are executed before processing the page content. [3.1]
	c. It may block all outgoing AJAX calls.

## 3. Notes

3.1. The crawler may register its own `window.load` event handler to start processing the page content at the right time:

``` js
function ownHandler() {
	setTimeout(function () {
		// Start processing the page content...
	});
}
```

---

[![CC0](https://i.creativecommons.org/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

To the extent possible under law, the [JS-enabled Crawling organization](https://github.com/js-enabled-crawling) has waived all copyright and related or neighboring rights to the JS-enabled Crawling specification. This work is published from: United States.