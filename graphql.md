## graphql

- [graphcool](https://www.graph.cool) graphql server
- [ref](https://www.youtube.com/watch?v=F_M8v6MK0Sc)

```bash
yarn add react-apollo apollo-boost graphql
```

```typescript
import {ApolloProvider} from 'react-apollo'
import ApolloClient from 'apollo-boost'


const client = new ApolloClient({
  uri: 'http://www.graphql.fun/graphql'
})

RectDOM.render(

<ApolloProvider>
<App />
</ApolloProvider>, document.getElementById('root)
)
```

```typescript
import { Query, Mutation } from 'react-apollo'
import { gql } from 'apollo-boost'

const ALL_PLAYERS_QUERY = gql`
  query {
    playerCount
      allPlayers{
        login
        name
        avatar
        team {
          color{
            name
          }
        }
      }
  }
`
const CREAT_TEAMSMUTATION = gql`
  mutation {
    createTeams(count:20){
      color {
        name
      }
    }
  }
`

const App = () => {
<Query query={ALL_PLAYERS_QUERY} pollInterval={1000}>
{({loading, data}) => {
  <div>
    <Mutation mutation={CREATE_TEAMS_MUTATION}>
      {createTeams => <button onClick={createTeams}>Create Teams</button>}
    </Mutation>
    <div>
      {!loading && dat.allPlayers.map(p => 
        <img
          src={p.avatar})
          key={p.login}
          width={40}
          style={p.team && {
            borderRadius: '50%',
            border: `4px solid ${p.team.color.name}`
          }}
        />  
    </div>  
  </div>
  }
}
</Query>
}
```
