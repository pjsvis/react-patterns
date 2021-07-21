# Composition

- [Dan Abramov: Before You Memo](https://overreacted.io/before-you-memo/)
- [React docs on Composition vs Inheritance](https://reactjs.org/docs/composition-vs-inheritance.html)
- [Michael Jackson on composition](https://www.youtube.com/watch?v=3XaXKiXtNjw)
- [Michael jackson on composing behaviour](https://www.youtube.com/watch?v=nUzLlHFVXx0)
- [Kent C. Dodds on React Patterns](https://www.youtube.com/watch?v=WV0UUcSPk-0)
- [Kent C. Dodds on AHA Programming](https://kentcdodds.com/blog/aha-programming)
- [Jotai minimalistic state management](https://github.com/pmndrs/jotai)
- [Dan Abramov on file structure](https://react-file-structure.surge.sh/)
- [React Remix](https://remix.run/)
- [Refactoring to react-query](https://www.youtube.com/watch?v=eEKn8UJfYgc)
- [Solid.js](https://www.solidjs.com/)

```javascript
function useLogger([state, dispatch]) {
  const actionRef = useRef()
  const newDispatchRef = useRef(action => 
  {
    actionRef.current = action
    dispatch(action)
  })
  
  useEffect(() => {
    const action = actionRef.current
    
    if(action){
      console.group('Dispatch')
      console.log('Action', action)
      console.log('State', state)
      console.groupEnd()
    }
  }, [state]
  return[state, newDispatch.current] 
}

```
