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

  someMethod = (param: number) => {
    alert(param)
  }
}
const someContainer = new SomeContainer();
export { someContainer as default, SomeContainer };
```

Use the unstated container as follows

```javascript
import * as React from 'react';
import { Subscribe } from 'unstated';
import someContainer, { SomeContainer } from '../Containers/SomeContainer';

const someMethod = (isDebug: boolean) => {
console.log(isDefault)
}

export const AssignAnalystModal = (props: Props) => {
  return (
    <Subscribe to={[someContainer]}>
      {(some: SomeContainer) => (
        <>
        {someMethod(some.state.isDebug)}
        </>
          )}
    </Subscribe>
  );
};
        

```

## Refs

- [unstated](https://github.com/jamiebuilds/unstated)
- [managing state in react with unstated](https://able.bio/drenther/managing-state-in-react-with-unstated--35akdue)
- [codesandbox example](https://codesandbox.io/s/ko27x3wvm3)
