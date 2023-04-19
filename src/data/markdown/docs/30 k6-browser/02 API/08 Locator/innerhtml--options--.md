---
title: 'innerHTML([options])'
excerpt: 'Browser module: locator.innerHTML method'
---

Returns the `element.innerHTML`.

<TableWithNestedRows>

| Parameter       | Type   | Default | Description                                                                                                                                                                                                                           |
|-----------------|--------|---------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| options         | object | `null`  |                                                                                                                                                                                                                      |
| options.timeout | number | `30000` | Maximum time in milliseconds. Pass `0` to disable the timeout. Default is overridden by the `setDefaultTimeout` option on [BrowserContext](/javascript-api/k6-browser/api/browsercontext/) or [Page](/javascript-api/k6-browser/api/page/). |

</TableWithNestedRows>

### Returns

| Type   | Description                    |
|--------|--------------------------------|
| string | The innerHTML of the element. |

### Example

<CodeGroup labels={[]}>

```javascript
import { chromium } from 'k6/experimental/browser';

export default async function () {
  const browser = chromium.launch();
  const page = browser.newPage();
  
  await page.goto('https://test.k6.io/browser.php');
  const offScreen = page.locator('#off-screen');
  const innerHTML = offScreen.innerHTML();
  console.log(innerHTML);
}
```

</CodeGroup>