## Implementation

#### Helpful articles
| Name | Link |
|---------------|----------------------------|
| A Simple React Router v4 Tutorial | https://medium.com/@pshrmn/a-simple-react-router-v4-tutorial-7f23ff27adf#d47d |
| All About React Router 4 | https://css-tricks.com/react-router-4/ |
| Github: Basic example of React Router | https://gist.github.com/siakaramalegos/df4620c52e829f6107c75d5c3f0ad7f5 |


#### Common components
| Component | Notes | Link |
|---------------|-------------------------------------|----------------------------|
| `<BrowserRouter>` | The router implementation for HTML5 browsers (vs Native) that will handle dynamic requests (knows how to respond to any possible URI) | https://reacttraining.com/react-router/web/api/BrowserRouter |
| `<HashRouter>` | The router implementation for HTML5 browsers (vs Native) that is used for static websites (can only respond to requests for files that it knows about) | https://reacttraining.com/react-router/web/api/HashRouter |
| `<Route>` | Shows a specified component if the URL matches a specified path. It expects a URL pattern that describes the type of `path` that the route matches. Unless the `exact` property is specified, it will match if the URL that begins with the `path` specified. The component that should be shown when the route matches can be specified using the `component` property as well as the `render` property (which accepts a function), with the distinction being that the `render` property's function can perform additional logic or pass props to the component before rendering it. The `children` property can also be used to show a component. It is different than the `render` and `component` property because it will always render, so it is useful to use other logic to determine what to render. | https://reacttraining.com/react-router/web/api/Route |
| `<Switch>` | Returns only the first matching route rather than all matching routes. Place the most specific routes at the top of the list so it checks those first, unless an `exact` property is specified. | https://reacttraining.com/react-router/web/api/Switch |
| `<Link>` | Provides an element that acts like a traditional link, but doesn't reload the page. Rather it will update the browser location, which in turn will cause `<BrowserRouter>` to check the new location against its defined routes. It requires a `to` property which is the location that the link should take the user to. | https://reacttraining.com/react-router/web/api/Link |
| `<NavLink>` | Provides a special version of the `<Link>` that will add styling attributes to the rendered element when it matches the current URL. It requires a `to` property which is the location that the link should take the user to. | https://reacttraining.com/react-router/web/api/NavLink |
| `<Redirect>` | Updates the browser location, which in turn will cause `<BrowserRouter>` to check the new location against its defined routes. It requires a `to` property which is the location that the user will be redirected to. | https://reacttraining.com/react-router/web/api/Redirect |

<br>

#### A simple `<BrowserRouter>` Implementation
```js
import { Switch, Route } from 'react-router-dom';

<BrowserRouter>
  <Switch>
    <Route exact path='/' component={Home} />
    <Route path='/roster' component={Roster} />
    <Route path='/schedule' component={Schedule }/>
    
    // By placing a route at the end of the <Switch> contents and omitting the path, it will by default render the return value of the provided function
    <Route render={() => <h1>Page not found</h1>} />
  </Switch>
</BrowserRouter>
```

<br>


#### Specifying the `component`, `render`, or `children` properties on the `<Route>` component
```js
import { Switch, Route } from 'react-router-dom';

<Switch>
  // Providing the component
  <Route path='/page' component={Page} />
  
  // Providing a function in which additional props can be passed to the component that gets rendered
  const extraProps = { color: 'red' };
  <Route path='/page' render={(props) => (
    <Page {...props} data={extraProps} />
  )}/>
</Switch>

  // A route that will always be run regardless of the path. You pass it a function which has access to the route properties so you can use that information for further logic
  <Route path="/blog" children={(props) => (
    props.match
    ? <Blog {...props}/>
    : <div>Page not found</div>
  )}/>
```

<br>

#### Nesting routes
```js
import { Switch, Route } from 'react-router-dom';

// The first <Switch> component will match `/roster` and will render the <Roster> component
const Main = () => (
  <main>
    <Switch>
      <Route path='/roster' component={Roster} />
    </Switch>
  </main>
);

// The <Switch> component within the the <Roster> component will contain another set of routes which it will try to match against before it displays more detailed information.
const Roster = () => (
  <Switch>
    <Route exact path='/roster' component={FullRoster}/>
    <Route path='/roster/:number' component={Player}/>
  </Switch>
);
```

<br>

#### Using the `<Link>` component
```js
import { Link } from 'react-router-dom';

const Header = () => (
  <header>
    <nav>
      <ul>
        <li><Link to='/'>Home</Link></li>
        <li><Link to='/roster'>Roster</Link></li>
        <li><Link to='/schedule'>Schedule</Link></li>
      </ul>
    </nav>
  </header>
);
```

<br>
#### Redirect the user to another page
```js
import { Switch, Route, Redirect } from 'react-router-dom';

<BrowserRouter>
  <Switch>
    <Route exact path='/' component={Home} />
    <Route path='/roster' component={Roster} />
    <Route path='/schedule' component={Schedule }/>
    
    // By placing the <Redirect> component at the end of the routes, if none of the routes match, it will redirect the user to the homepage
    <Redirect to="/" />
  </Switch>
</BrowserRouter>
```

<br>

#### Accessing matched URL properties in the matched route's component. Also accessing other properties for the matched route.
```js
import { Switch, Route } from 'react-router-dom';

// The :number part of the path /roster/:number means that the part of the pathname that comes after /roster/ will be captured and stored as match.params.number
const Roster = () => (
  <Switch>
    <Route path='/roster/:number' component={Player}/>
  </Switch>
);

// The <Player> component can then use the props.match.params object
const Player = (props) => {
  return (
    <div>
      <h1>props.match Properties</h1>
      <p>The player number: {props.match.params.number}</p>
      <p>The matched part of the pathname: {props.match.url}</p>
      <p>The route path that was entered: {props.match.path}</p>
      <p>The matched path is exact?: {props.match.isExact.toString()}</p>
    </div>
  )
};
```
