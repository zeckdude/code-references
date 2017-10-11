## Implementation

#### Common components
| Component | Notes | Link |
|---------------|-------------------------------------|----------------------------|
| `<BrowserRouter>` | The router implementation for HTML5 browsers (vs Native) that will handle dynamic requests (knows how to respond to any possible URI) | https://medium.com/@pshrmn/a-simple-react-router-v4-tutorial-7f23ff27adf#d47d |
| `<HashRouter>` | The router implementation for HTML5 browsers (vs Native) that is used for static websites (can only respond to requests for files that it knows about) | https://medium.com/@pshrmn/a-simple-react-router-v4-tutorial-7f23ff27adf#d47d |
| `<Route>` | Shows a specified component if the URL matches a specified path. It expects a URL pattern that describes the type of `path` that the route matches. Unless the `exact` property is specified, it will match if the URL that begins with the `path` specified. The component that should be shown when the route matches can be specified using the `component` property as well as the `render` property (which accepts a function), with the distinction being that the `render` property's function can perform additional logic or pass props to the component before rendering it. | https://medium.com/@pshrmn/a-simple-react-router-v4-tutorial-7f23ff27adf#7a3d |
| `<Switch>` | Returns only the first matching route rather than all matching routes. Place the most specific routes at the top of the list so it checks those first, unless an `exact` property is specified. | https://medium.com/@pshrmn/a-simple-react-router-v4-tutorial-7f23ff27adf#215c |

