# generics

- [Extra TS Types](https://github.com/sindresorhus/type-fest)
- [tsdx](https://www.npmjs.com/package/tsdx) cli for components

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
