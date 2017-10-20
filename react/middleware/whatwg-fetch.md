## whatwg-fetch

The fetch() function is a Promise-based mechanism for programmatically making web requests in the browser. This project is a polyfill that implements a subset of the standard Fetch specification, enough to make fetch a viable replacement for most uses of XMLHttpRequest in traditional web applications. 

#### Helpful Links
| Name | Link |
|---------------|----------------------------|
| CSS-Tricks: Using Fetch | https://css-tricks.com/using-fetch/ |
| David Walsh: fetch API | https://davidwalsh.name/fetch |

### Example

Performing a `GET` request

```js
import 'whatwg-fetch';

// Make a request for a user with a given ID
fetch(`https://jsonplaceholder.typicode.com/posts/5`)
  .then(function(response) {
    // The first then() block will return the promise along with some data about the promise
    // {
    //   body: ReadableStream
    //   bodyUsed: false
    //   headers: Headers
    //   ok : true
    //   redirected : false
    //   status : 200
    //   statusText : "OK"
    //   type : "cors"
    //   url : "https://jsonplaceholder.typicode.com/posts"
    //   __proto__ : Response
    // }

    // The Promise returned from fetch() won't reject on HTTP error status even if the response is an HTTP 404 or 500. Instead, it will resolve normally, and it will only reject on network failure or if anything prevented the request from completing.
    // Therefore, this block can be used to check the status code and throw an error if it's not desired.
    if (!response.ok) {
      throw Error(`There was a ${response.status} error`);
    }

    return response.json();
  })
  .then(function(json) {
    // The second then() block will parse the response.body from the previous then() block and will provide it as its argument
    console.log('parsed json', json);
  })
  .catch(function(error) {
    // Network failure or something prevented the request from completing
    console.log('parsing failed', error);
  });
```

<br>

Performing a `POST` request

```js
import 'whatwg-fetch';

fetch(`https://jsonplaceholder.typicode.com/posts`, {
  method: 'post',
  headers: {
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    title: 'My New Title'
  })
})
  .then(function(response) {
    // The same concept applies as in the GET example so refer to that for more details
    return response.json();
  })
  .then(function(json) {
    // The second then() block will parse the response.body from the previous then() block and will provide it as its argument
    console.log('parsed json', json);
  })
  .catch(function(error) {
    // Network failure or something prevented the request from completing
    console.log('parsing failed', error);
  });
```

<br>

Performing a `PUT` request

```js
import 'whatwg-fetch';

fetch(`https://jsonplaceholder.typicode.com/posts/5`, {
  method: 'put',
  headers: {
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    title: 'My New Title'
  })
})
  .then(function(response) {
    // The same concept applies as in the GET example so refer to that for more details
    return response.json();
  })
  .then(function(json) {
    // The second then() block will parse the response.body from the previous then() block and will provide it as its argument
    console.log('parsed json', json);
  })
  .catch(function(error) {
    // Network failure or something prevented the request from completing
    console.log('parsing failed', error);
  });
```

<br>

Performing a `DELETE` request

```js
import 'whatwg-fetch';

fetch(`https://jsonplaceholder.typicode.com/posts/5`, {
  method: 'delete'
})
  .then(function(response) {
    // The same concept applies as in the GET example so refer to that for more details
    return response.json();
  })
  .then(function(json) {
    // The second then() block will parse the response.body from the previous then() block and will provide it as its argument
    console.log('parsed json', json);
  })
  .catch(function(error) {
    // Network failure or something prevented the request from completing
    console.log('parsing failed', error);
  });
```

<br>

Performing multiple concurrent requests

```js
import 'whatwg-fetch';

const grabContent = url =>
  fetch(url).then(res => res.json()).then(json => {
    console.log(json);
  });

const urls = [
  'https://jsonplaceholder.typicode.com/posts',
  'https://jsonplaceholder.typicode.com/posts/5'
];

Promise.all(urls.map(grabContent)).then(() => {
  console.log(`All fetches have been made`);
});
```

<br>


