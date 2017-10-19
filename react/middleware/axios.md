## Axios

Axios is a Promise based HTTP client for the browser and node.js. It lets you make make XMLHttpRequests from the browser. 

#### Helpful Links
| Name | Link |
|---------------|----------------------------|
| Github: axios | https://github.com/axios/axios |
| NPM: axios | https://www.npmjs.com/package/axios |
| Medium: How to make API calls in a smart way | https://codeburst.io/how-to-call-api-in-a-smart-way-2ca572c6fe86 |
| Difference between Put & Patch request | https://stackoverflow.com/a/28558968/83916 |

### Example

Performing a `GET` request

```js
import axios from 'axios';

// Make a request for a user with a given ID
axios.get('/user?ID=12345')
  .then(function (response) {
    console.log(response);
  })
  .catch(function (error) {
    console.log(error);
  });

// Optionally the request above could also be done as
axios.get('/user', {
    params: {
      ID: 12345
    }
  })
  .then(function (response) {
    console.log(response);
  })
  .catch(function (error) {
    console.log(error);
  });
```

<br>

Performing a `POST` request

```js
import axios from 'axios';

axios.post('/user', {
    firstName: 'Fred',
    lastName: 'Flintstone'
  })
  .then(function (response) {
    console.log(response);
  })
  .catch(function (error) {
    console.log(error);
  });
```

<br>

<br>

Performing a `PUT` request

```js
import axios from 'axios';

axios.put('/user/12345', {
    firstName: 'Fred',
    lastName: 'Flintstone'
  })
  .then(function (response) {
    console.log(response);
  })
  .catch(function (error) {
    console.log(error);
  });
```

<br>

Performing a `DELETE` request

```js
import axios from 'axios';

axios.delete('/user/12345')
  .then(function (response) {
    console.log(response);
  })
  .catch(function (error) {
    console.log(error);
  });
```

<br>

Performing multiple concurrent requests

```js
function getUserAccount() {
  return axios.get('/user/12345');
}

function getUserPermissions() {
  return axios.get('/user/12345/permissions');
}

axios.all([getUserAccount(), getUserPermissions()])
  .then(axios.spread(function (acct, perms) {
    // Both requests are now complete
  }));
```

<br>


