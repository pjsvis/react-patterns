## functional

- ref Sean May [Super Typescript II Turbo FP Remix](https://www.youtube.com/watch?v=9oVKjZrgXmU)

```typescript
type Comparator<A> = (a:A, b: A) => boolean
type Comparator<A> = (a:A, b:A) => numnber
type Compatre = <A>(test: Comparator<A>) => Comparison<A>

const compare: Compare = (test) => (a, b) => {
  test(a,b) ? -1
  : test(b, a) ? 1
  : 0
}

const gt: Comparator<number> = (a, b) => b > a;
const lt: Comparator<number> = (a,b) => b < a;

const sortAscending = compare(gt);
const sortDescending = compare(lt);

const arr = [5,4,3,2,1].sort(sortAscending);
```
