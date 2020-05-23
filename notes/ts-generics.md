---
tags: [typescript]
title: ts-generics
created: '2019-06-11T19:39:36.035Z'
modified: '2019-08-03T09:56:07.929Z'
---

# generics

```typescript
function identity<T>(arg: T): T {
    return arg;
}

/**
 * Add a uuid to an generic object 
 */
function withUID<T>(obj: T) { 
   return Object.assign({}, obj, { uuid: _.uniqueId() });
}
```
