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
