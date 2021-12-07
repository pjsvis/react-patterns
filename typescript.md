# typescript

- [union types](https://blog.scottlogic.com/2021/07/27/union-types-react-components.html)
```typescript
interface WithIdAndType<T extends 'text' | 'number' | 'checkbox'> {
  id: string;
  type: T;
}

type TextInputDefinition = TextInputProps & WithIdAndType<'text'>;

type NumberInputDefinition = NumberInputProps & WithIdAndType<'number'>;

type CheckboxInputDefinition = CheckboxProps & WithIdAndType<'checkbox'>

type Input = TextInputDefinition | NumberInputDefinition | CheckboxInputDefinition;
```

- [Figma article on migrate to strict null checks](https://www.figma.com/blog/inside-figma-a-case-study-on-strict-null-checks/)
- [migrate to strictNullChecks tools](https://github.com/figma/strict-null-check-migration-tools)
- [VSCode migration to strictNullChecks](https://code.visualstudio.com/blogs/2019/05/23/strict-null)
- [Qerko mod](https://github.com/qerko/strict-null-check-migration-tools)
- [Extra TS Types](https://github.com/sindresorhus/type-fest)
- [ts-strictify blog post](https://dev.to/viridia/typescript-strictnullchecks-a-migration-guide-3glo)
- [betterer](https://dev.to/phenomnominal/stricter-typescript-compilation-with-betterer-dp7)
- [typescript-strict-plugin](https://github.com/allegro/typescript-strict-plugin)
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
