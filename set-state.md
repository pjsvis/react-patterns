# set-state

- If we want to update state we can use setState
- If we want to add an item to an array in state we should use an updater function

```typescript
 this.setState(prevState => ({
      documentData: [
        ...prevState.documentData,
        {
          title: this.state.title,
          authors: this.state.authors,
          version: this.state.version,
          dateCreated: this.state.dateCreated
        }
      ]
    }));
```
