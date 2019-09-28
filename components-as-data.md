## render-component

```javascript
const COMPONENTS_DICTIONARY = {
  Slide,
  SeriesTile
}
export const renderComponent = (DICTIONARY, {component, data}) =>  {
  const Component = DICTIONARY[component]
  if(!Component){
    return null
  }
  return <Component {...data} />
} 

export const Slideshow = (props) => {
const slideNumber = useTimedCounter(props.items.length)
return (
  <div className="slideshow">
    {props.items.map(slide => 
      renderComponent(COMPONENTS_DICTIONARY, {...slide, slideNumber})
    )}
  </div>
)
}
```
