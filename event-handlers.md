# event-handlers

tldr; Use partial application to avoid re-rendering when using event handlers with parameters in React components.

Below is a typical case where we map over an array of notes and add a deleteNote event handler for each note.

```tsx
<div>
    <div>
        Contacts
    </div>
    {stuff.map(x => (
        <div key={x.id}>
            <button onClick={e => editNote(x)}>Edit</button> {x.content}
        </div>
    ))}
</div>
```

The problem with this pattern is the event handler is created each time the component is re-rendered, 
which means the button content has changed so the button is re-rendered.

An alternative pattern is shown below using partial application and closures.


```tsx
import * as React from 'react';

interface Note {
    id: number;
    content: string;
}
const notes: Note[] = [
    { id: 1, content: 'Note one' },
    { id: 2, content: 'Note two' },
    { id: 3, content: 'Note three' }
];


const editNote = (x: Note) => (e: any) => {
    e.preventDefault();
    console.log(`Edit note ${x.id}`);
};

interface Props {}

export const NoteManager = (props: Props) => {
    return (
        <div>
            <div>
                Contacts
            </div>
            {notes.map(x => (
                <div key={x.id}>
                    <button type="button" onClick={editNote(x)}>
                        Delete
                    </button>
                    {x.content}
                </div>
            ))}
        </div>
    );
};
```

Thanks to 

- [Miron Machnicki](https://medium.com/@machnicki/handle-events-in-react-with-arrow-functions-ede88184bbb)
- [Charles Stover](https://medium.com/@Charles_Stover/cache-your-react-event-listeners-to-improve-performance-14f635a62e15)
