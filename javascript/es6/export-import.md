## Export/Import modules
> A module is a JavaScript file that exports one or more values (objects, functions or variables), using the export keyword.

#### Export using a default export
`helper/user.js`
```js
const getUserById = id => {
  console.log(`I'm user ${id}`);
};

const users = ['joe', 'zack', 'greg'];

export default { getUserById, users };
```

```js
import UserHelper from './helper/user';

UserHelper.getUserById(555);
// Outputs: I'm user 555
UserHelper.users.forEach(userName => console.log(`Hi, my name is ${userName}`));
// Outputs:
// Hi, my name is joe
// Hi, my name is zack
// Hi, my name is greg
```

<br>

#### Export using named exports
`helper/user.js`
```js
const getUserById = id => {
  console.log(`I'm user ${id}`);
};

const users = ['joe', 'zack', 'greg'];

export { getUserById, users };
```

```js
import { getUserById, users } from './helper/user';

getUserById(555);
// Outputs: I'm user 555
users.forEach(userName => console.log(`Hi, my name is ${userName}`));
// Outputs:
// Hi, my name is joe
// Hi, my name is zack
// Hi, my name is greg
```

_You can also store all named exports in an object when importing_
```js
import * as UserHelper from './helper/user';

UserHelper.getUserById(555);
// Outputs: I'm user 555
UserHelper.users.forEach(userName => console.log(`Hi, my name is ${userName}`));
// Outputs:
// Hi, my name is joe
// Hi, my name is zack
// Hi, my name is greg
```

<br>

#### Alias when importing named export
```js
import { getUserById as getUserByPk } from './helper/user';

getUserByPk(555);
// Outputs: I'm user 555
```

<br>

