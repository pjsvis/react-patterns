## render-component

- [components as data](https://www.youtube.com/watch?time_continue=2046&v=4cEJ-1rXqMg)

Components as Data moves the "decouple line" further toward the frontend to absorb queries, denormalization, business logic, and A/B testing into the backend. In practice, the API serves JSON structured in terms of the tree of UI components that will be used to render the respective data. In doing so, it becomes a quasi frontend in its own right, but it renders JSON instead of HTML or native views. This enables some amazing features:

1. Simpler, presentational frontends

2. Centralized business logic

3. Centralized A/B Testing and Feature Flagging

4. Design consistency via a "Design Schema"

5. Query optimization

Finally, this pattern opens the door for writing a cross platform UI library that implements the "design schema" and can be used as the rendering engine for each platform.


```javascript
interface Component {
  component: String!
  treatment: String
}

type  VideoTile implements Component {
  component: String!
  treatment: String
  data: VideoData
}

type VideoData {
  image: String!
  title: String!
  secondaryTitle: String!
  percentViewed: Float
}

type SeriesTitle implements Component {
  component: String!
  treatment: String
  data: SeriesData
}

type SeriesData {
  image: String!
  title: String!
  secondaryTitle: String!
  favoriteId: String
}

union Tile = VideoTile | SeriesTile

type ShelfData = {
  title: String
  items: [Tile]
}

interface Section {
  component: String!
  treatment: String
}

type Shelf implements Section & Component {
  component: String!
  treatment: String
  data: ShelfData
}

interface Featured {
  component: String!
  treatment
}

type SlideshowData {
  items: [Slide]
}

type Slideshow implements Featured & Component {
  component: String!
  treatment: String
  data: SlideshowData
}

type Page implements Component {
  id: ID!
  treatment: String
  component: String!
  name: String
  featured: Featured
  section: [Section]!
}

type Query {
  page(
    id: ID
    name: String!
    userId: String!
    platform: SupportedPlatforms!
  ): Page
}

// graphql data
const data = {
  "component": "Slide", 
  "data": {
    "title": "Hello there",
    
  }
}

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

export const Slide = (props) => {
  return (
    <div className="slide">
      <img alt={props.title} src={props.image} />
      <hi>{props.title}</h1>
    </div>
  )
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

export const Shelf = (props) => {
  return (
    <div className="shelf">
      {
        props.items.map(tile => renderComponent((COMPONENTS_DICTIONARY, {...tile, slideNumber})
      )}
    </div>
  )
}

export const App = (props) => {
  const [loading, data] = useComponentAPIFetch()
  if(loading){
    return 'loading...'
  }
  return (
    <div>
      <section className="featured>
        {renderComponent(FEATURED_DICTIONARY, data.featured)}
      </section>
      <section className="sections">
        {data.sections.map(section => 
          renderComponent(SECTIONS_DICTIONARY, section)
        )}
      </section>
    </div>
  )
  
}
```
