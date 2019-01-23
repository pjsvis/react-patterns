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
