## Functional Components

#### Different types of functional components

##### [Functional dumb component](#functional-dumb-component)

- Used for presenting static data
- Can't handle fetching data
- Easy to write
- Does not keep local state
- Easy to re-use
- Easy to test against

##### [Functional stateful component](#functional-stateful-component)

- Used for dynamic sources of data
- Handles any data that might change (fetching data, user events, etc)
- Knows when it gets rendered (useful for fetching data)
- Keeps local state
- Handles lifecycle changes

<br>

#### Writing a functional component

#### Using a functional dumb component

```js
const Username = function({ username }) {
  return <p>The logged in user is: {username}</p>;
};
```

<br>

#### Using a functional stateful component

Demo: https://stackblitz.com/edit/demo-react-functional-stateful-component

```jsx
import React, { useState, useEffect } from "react";

function Counter({ initialCount = 0 }) {
  const [count, setCount] = useState(initialCount);

  useEffect(() => {
    console.log("This only runs when the component mounts");
  }, []);

  useEffect(() => {
    console.log(
      "This runs when the component mounts and when the count property on state changes"
    );
  }, [count]);

  return (
    <>
      {name} count: {count}
      <button onClick={() => setCount(initialCount)}>Reset</button>
      {/* Use the function callback when changing a state value based on its previous value in order to guarantee that the value is accurate */}
      <button onClick={() => setCount(prevCount => prevCount - 1)}>-</button>
      <button onClick={() => setCount(prevCount => prevCount + 1)}>+</button>
    </>
  );
}
```
