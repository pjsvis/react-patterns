# unstated with typescript

unstated is a pretty neat state management library that takes `setState` to the next level and helps avoid [prop drilling](https://blog.kentcdodds.com/prop-drilling-bb62e02cb691) 

Using unstated with react requires some minimal configuration

Basically, export an instance of the satContainer and export the container so that we can get the types

```javascript
import { Container } from 'unstated';

interface State {
  isDebug: boolean;
}

class SomeContainer extends Container<State> {
  state: State = {
    isDebug: true
  }

  getStuff = (param: number) => {
   return [{id: 1, name: 'thing 1'}, {id: 2, name: 'thing 2'}];
  }
}
const someContainer = new SomeContainer();
export { someContainer as default, SomeContainer };
```

Use the unstated container as follows

```javascript
import * as React from 'react';
import { Provider, Subscribe } from 'unstated';
import someContainer, { SomeContainer } from '../Containers/SomeContainer';



const someRandomMethod = (isDebug: boolean) => {
  console.log(isDebug)
}

interface Props {}

export const SomeComponent = (props: Props) => {
  return (
  <Provider>
      <Subscribe to={[someContainer]}>
        {(sc: SomeContainer) => (
          <>
          {someRandomMethod(sc.state.isDebug)}
          <table>
            {map(sc.getStuff(), x => (<tr key={x.id}><td>{x.id}</td>{x.name}<td</td></tr>)}
          </>
          </table>
            )}
      </Subscribe>
    </Provider>
  );
};
        

```

## Refs

- [unstated](https://github.com/jamiebuilds/unstated)
- [managing state in react with unstated](https://able.bio/drenther/managing-state-in-react-with-unstated--35akdue)
- [codesandbox example](https://codesandbox.io/s/ko27x3wvm3)
- [good blog post on state management](https://medium.com/@amcdnl/the-future-of-javascript-state-management-is-less-state-management-ba1d97b99308)
