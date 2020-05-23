## rest-spread

- [6-tricks](https://blog.bitsrc.io/6-tricks-with-resting-and-spreading-javascript-objects-68d585bdc83)


```typescript
// Remove property from object
const user1 = {
  id: 100,
  name: 'Howard Moon',
  password: 'Password!'
}
const removeProperty = prop => ({ [prop]: _, ...rest }) => rest
//                     ----       ------
//                          \   /
//                dynamic destructuring

const removePassword = removeProperty('password')
const removeId = removeProperty('id')

removePassword(user1) //=> { id: 100, name: 'Howard Moon' }
removeId(user1) //=> { name: 'Howard Moon', password: 'Password!' }
```
