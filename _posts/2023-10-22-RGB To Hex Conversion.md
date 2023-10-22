---
title: RGB To Hex Conversion
date: 2023-10-22 16:00:00 +0100
categories: [Algorithms, JavaScript]
tags: [algorithms] # TAG names should always be lowercase
author: <author_id>
---

```javascript
function rgb(r, g, b) {
  const clamp = (value) => Math.min(255, Math.max(0, value));
  //ensure that value falls between 0 and 255
  const toHex = (value) => {
    const hex = clamp(value).toString(16).toUpperCase();
    return hex.length === 1 ? "0" + hex : hex;
  };

  const red = toHex(r);
  const green = toHex(g);
  const blue = toHex(b);

  return red + green + blue;
}
```
