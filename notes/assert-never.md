---
tags: [typescript]
title: assert-never
created: '2019-06-11T19:39:36.027Z'
modified: '2019-08-03T09:56:27.481Z'
---

# typescript

## pick and omit

```javascript
export interface Product {
id: string;
name: string;
price: number;
description: string;
author: string
authorLink: string;
}

export type ProductFormValues = Pick<Product, 'name' | 'price' | 'description'>
```

## assert-never

```javascript
function assertNever(x: never): never {
    throw new Error("Unexpected object: " + x);
}
function area(s: Shape) {
    switch (s.kind) {
        case "square": return s.size * s.size;
        case "rectangle": return s.height * s.width;
        case "circle": return Math.PI * s.radius ** 2;
        default: return assertNever(s); // error here if there are missing cases
    }
}
```
