## Implementation

#### Common components
| Component | Notes | Link |
|---------------|-------------------------------------|----------------------------|
| `<BrowserRouter>` | The router implementation for HTML5 browsers (vs Native) that will handle dynamic requests (knows how to respond to any possible URI) | https://medium.com/@pshrmn/a-simple-react-router-v4-tutorial-7f23ff27adf#d47d |
| `<HashRouter>` | The router implementation for HTML5 browsers (vs Native) that is used for static websites (can only respond to requests for files that it knows about) | https://medium.com/@pshrmn/a-simple-react-router-v4-tutorial-7f23ff27adf#d47d |
| `<Route>` | Shows a specified component if the URL matches a specified path. It expects a URL pattern that describes the type of `path` that the route matches. Unless the `exact` property is specified, it will match if the URL that begins with the `path` specified. The component that should be shown when the route matches can be specified using the `component` property as well as the `render` property (which accepts a function), with the distinction being that the `render` property's function can perform additional logic or pass props to the component before rendering it. | https://medium.com/@pshrmn/a-simple-react-router-v4-tutorial-7f23ff27adf#7a3d |
| `<Switch>` | Returns only the first matching route rather than all matching routes. Place the most specific routes at the top of the list so it checks those first, unless an `exact` property is specified. | https://medium.com/@pshrmn/a-simple-react-router-v4-tutorial-7f23ff27adf#215c |
| `<Link>` | Provides an element that acts like a traditional link, but doesn't reload the page. Rather it will update the browser location, which in turn will cause `<BrowserRouter>` to check the new location against its defined routes. It requires a `to` property which is the location that the link should take the user to. | https://medium.com/@pshrmn/a-simple-react-router-v4-tutorial-7f23ff27adf#54c4 |

<br>

#### A simple `<BrowserRouter>` Implementation
```js
import { Switch, Route } from 'react-router-dom';

<BrowserRouter>
  <Switch>
    <Route exact path='/' component={Home} />
    <Route path='/roster' component={Roster} />
    <Route path='/schedule' component={Schedule }/>
  </Switch>
</BrowserRouter>
```

<br>


#### Specifying the `component` or `render` properties on the `<Route>` component
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
      <p>The matched path is exact?: {props.match.isExact}</p>
    </div>
  )
};
```
