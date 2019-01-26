# map-filter-reduce

-  [ref](https://medium.com/@alex.permyakov/15-useful-javascript-examples-of-map-reduce-and-filter-74cbbb5e0a1f)

- remove duplicates from array

```javascript
let values = [3, 1, 3, 5, 2, 4, 4, 4];
let uniqueValues = [...new Set(values)];
// uniqueValues is [3, 1, 5, 2, 4]
```

- case-insensitive filter

```javascript
let res = users.filter(x => new RegExp('oli', "i").test(x.name));
// res is
[
  { id: 97, name: 'Oliver', age: 28, group: 'admin' }
]
```

- group and count

```javascript
let users = [
  { id: 11, name: 'Adam', age: 23, group: 'editor' },
  { id: 47, name: 'John', age: 28, group: 'admin' },
  { id: 85, name: 'William', age: 34, group: 'editor' },
  { id: 97, name: 'Oliver', age: 28, group: 'admin' }
];
let groupByAge = users.reduce((acc, it) =>
  ({ ...acc, [it.age]: (acc[it.age] || 0) + 1 }),
{});
// groupByAge is {23: 1, 28: 2, 34: 1}
```
