# typescript

- [Figma article on migrate to strict null checks](https://www.figma.com/blog/inside-figma-a-case-study-on-strict-null-checks/)
- [migrate to strictNullChecks tools](https://github.com/figma/strict-null-check-migration-tools)

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
