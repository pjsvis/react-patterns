# is-key


```javascript
// Ref: https://github.com/burakcan/mb
export const mb = (...p: any[]) => p.reduce.bind(p, (a: any, c: any) => Object(a)[c]);
```

