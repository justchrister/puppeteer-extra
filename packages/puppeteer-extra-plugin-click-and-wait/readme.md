# puppeteer-extra-plugin-click-and-wait

> A plugin in for [puppeteer-extra](https://github.com/berstend/puppeteer-extra).

### Install

```bash
yarn add puppeteer-extra-plugin-click-and-wait
```

## API

<!-- Generated by documentation.js. Update this documentation by updating the source code. -->

#### Table of Contents

-   [Plugin](#plugin)

### [Plugin](https://github.com/berstend/puppeteer-extra/blob/959522771a8618e8f5f97f8eb7b6193acd3fe039/packages/puppeteer-extra-plugin-click-and-wait/index.js#L24-L39)

**Extends: PuppeteerExtraPlugin**

Convenience function to wait for navigation to complete after clicking on an element.

Adds a new `page.clickAndWaitForNavigation(selector, clickOptions, waitOptions)` method.

See this issue for more context: <https://github.com/GoogleChrome/puppeteer/issues/1421>

> Note: Be wary of ajax powered pages where the navigation event is not triggered.

Type: `function (opts)`

-   `opts`   (optional, default `{}`)

Example:

```javascript
await page.clickAndWaitForNavigation('input#submitData')

// as opposed to:

await Promise.all([
  page.waitForNavigation(waitOptions),
  page.click('input#submitData', clickOptions),
])
```

* * *