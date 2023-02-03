# data-input

- [numbers and dates](https://www.builder.io/blog/numbers-and-dates)
- [null check](https://javascript.plainenglish.io/how-to-check-for-null-in-javascript-dffab64d8ed5)
- 
```javascript
const number = myInput.valueAsNumber
if (!isNaN(number)) {
  // We actually have, like, a *number* number
}
```

```javascript
const date = myInput.valueAsDate
if (date !== null && date !== undefined)) {
  // We actually have, like, a *date* date
}
```
