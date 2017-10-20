## zl-fetch

Using the fetch API, zlFetch is a library that abstracts away the handleResponse function so you can skip ahead to and handle both your data and errors without worrying about the response.

#### Helpful Links
| Name | Link |
|---------------|----------------------------|
| CSS-Tricks: Using Fetch | https://css-tricks.com/using-fetch/ |

### Example

Performing a `GET` request

```js
import 'whatwg-fetch';
import zlFetch from 'zl-fetch';

// Make a request for a user with a given ID
zlFetch('https://jsonplaceholder.typicode.com/posts/5')
  .then(json => {
    // Parsed JSON response data
    console.log(json);
  })
  .catch(error => {
    // Catches 404 and 500 errors among others
    throw Error(`There was a ${error.statusCode} error`);
  });
```

<br>

Performing a `POST` request

```js
import 'whatwg-fetch';
import zlFetch from 'zl-fetch';

zlFetch('https://jsonplaceholder.typicode.com/posts', {
  method: 'post',
  body: {
    title: 'A new title'
  }
})
  .then(json => {
    // Parsed JSON response data
    console.log(json);
  })
  .catch(error => {
    // Catches 404 and 500 errors among others
    throw Error(`There was a ${error.statusCode} error`);
  });
```

<br>

Performing a `PUT` request

```js
import 'whatwg-fetch';
import zlFetch from 'zl-fetch';

zlFetch('https://jsonplaceholder.typicode.com/posts/5', {
  method: 'put',
  body: {
    title: 'An updated title'
  }
})
  .then(json => {
    // Parsed JSON response data
    console.log(json);
  })
  .catch(error => {
    // Catches 404 and 500 errors among others
    throw Error(`There was a ${error.statusCode} error`);
  });
```

<br>

Performing a `DELETE` request

```js
import 'whatwg-fetch';
import zlFetch from 'zl-fetch';

zlFetch('https://jsonplaceholder.typicode.com/posts/5', {
  method: 'delete'
})
  .then(json => {
    // Parsed JSON response data
    console.log(json);
  })
  .catch(error => {
    // Catches 404 and 500 errors among others
    throw Error(`There was a ${error.statusCode} error`);
  });
```

<br>

Performing multiple concurrent requests

```js
import 'whatwg-fetch';
import zlFetch from 'zl-fetch';

const grabContent = url =>
  zlFetch(url)
    .then(json => console.log(json))
    .catch(error => console.log(error));

const urls = [
  'https://jsonplaceholder.typicode.com/posts',
  'https://jsonplaceholder.typicode.com/posts/5'
];

Promise.all(urls.map(grabContent)).then(() => {
  console.log(`Urls ${urls} were grabbed`);
});
```

<br>


